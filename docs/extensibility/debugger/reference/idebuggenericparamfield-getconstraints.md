---
title: IDebugGenericParamField::GetConstraints | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- IDebugGenericParamField::GetConstraints
- GetConstraints
ms.assetid: 86a78b5a-ee0f-4999-a0ba-919d3dc7d969
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 8a078beaac1cf9ef0255ff7b8d0bcbc4f568fdb8
ms.sourcegitcommit: 16a4a5da4a4fd795b46a0869ca2152f2d36e6db2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/06/2020
ms.locfileid: "80728014"
---
# <a name="idebuggenericparamfieldgetconstraints"></a>IDebugGenericParamField::GetConstraints
Ruft die Einschränkungen ab, die diesem generischen Parameter zugeordnet sind.

## <a name="syntax"></a>Syntax

```cpp
HRESULT GetConstraints(
    ULONG32       cConstraints,
    IDebugField** ppConstraints,
    ULONG32*      pcConstraints
);
```

```csharp
int GetConstraints(
    uint              cConstraints,
    out IDebugField[] ppConstraints,
    ref uint          pcConstraints
);
```

## <a name="parameters"></a>Parameter
`cConstraints`\
[in] Anzahl der Einschränkungen.

`ppConstraints`\
[out] Gibt ein Array zurück, das die diesem Feld zugeordneten Einschränkungen enthält.

`pcConstraints`\
[in, out] Anzahl der Einschränkungen `ppConstraints` im Array.

## <a name="return-value"></a>Rückgabewert
Wenn die Ausführung erfolgreich ist, wird `S_OK`, andernfalls ein Fehlercode zurückgegeben.

## <a name="example"></a>Beispiel
Das folgende Beispiel zeigt, wie diese Methode für ein **CDebugGenericParamFieldType-Objekt** implementiert wird, das die [IDebugGenericParamField-Schnittstelle](../../../extensibility/debugger/reference/idebuggenericparamfield.md) verfügbar macht.

```cpp
HRESULT CDebugGenericParamFieldType::GetConstraints(
    ULONG32 cConstraints,
    IDebugField** ppConstraints,
    ULONG32* pcConstraints)
{
    HRESULT hr = S_OK;
    CComPtr<IMetaDataImport> pMetadata;
    CComPtr<IMetaDataImport2> pMetadata2;
    mdGenericParamConstraint* rgParamConsts = NULL;
    HCORENUM hEnum = 0;
    ULONG cConst = 0;
    ULONG iConst;
    ULONG iConstOut = 0;

    METHOD_ENTRY( CDebugGenericParamFieldType::GetConstraints );

    IfFalseGo(ppConstraints && pcConstraints, E_INVALIDARG );
    *pcConstraints = 0;

    IfNullGo( rgParamConsts = new mdGenericParamConstraint[cConstraints], E_OUTOFMEMORY);

    IfFailGo( m_spSH->GetMetadata( m_idModule, &pMetadata ) );
    IfFailGo( pMetadata->QueryInterface(IID_IMetaDataImport2, (void**)&pMetadata2) );
    IfFailGo( pMetadata2->EnumGenericParamConstraints( &hEnum,
              m_tokParam,
              rgParamConsts,
              cConstraints,
              &cConst) );
    pMetadata->CloseEnum(hEnum);
    hEnum = NULL;

    for (iConst = 0; iConst < cConst; iConst++)
    {
        mdToken tokConst;

        IfFailGo( pMetadata2->GetGenericParamConstraintProps( rgParamConsts[iConst],
                  NULL,
                  &tokConst ) );
        switch (TypeFromToken(tokConst))
        {
            case mdtTypeRef:
                {
                    Module_ID mid;
                    mdTypeDef tokClass;

                    IfFailGo( CDebugClassFieldType::GetClassToken(m_spSH, m_idModule, tokConst, &mid, &tokClass) );
                    IfFailGo( m_spSH->CreateClassType( mid, tokClass, ppConstraints + iConstOut ) );
                    iConstOut++;
                    break;
                }
            case mdtTypeDef:
                {
                    IfFailGo( m_spSH->CreateClassType( m_idModule, tokConst, ppConstraints + iConstOut ) );
                    iConstOut++;
                    break;
                }
            case mdtTypeSpec:
                {
                    PCCOR_SIGNATURE pvSig;
                    ULONG cbSig;
                    DWORD cb = 0;
                    DWORD dwElementType;

                    IfFailGo( pMetadata2->GetTypeSpecFromToken( tokConst, &pvSig, &cbSig) );

                    cb += CorSigUncompressData(&(pvSig[cb]), &dwElementType);

                    IfFailGo( m_spSH->CreateType( pvSig, cbSig, m_idModule, mdMethodDefNil, m_pGenScope, ppConstraints + iConstOut ) );

                    iConstOut++;

                    break;
                }
            default:
                {
                    ASSERT(!"Bad constraint token");
                }
        }
    }

    *pcConstraints = iConstOut;

Error:

    METHOD_EXIT( CDebugGenericParamFieldType::GetConstraints, hr );

    DELETERG(rgParamConsts);

    return hr;
}
```

## <a name="see-also"></a>Weitere Informationen
- [IDebugGenericParamField](../../../extensibility/debugger/reference/idebuggenericparamfield.md)

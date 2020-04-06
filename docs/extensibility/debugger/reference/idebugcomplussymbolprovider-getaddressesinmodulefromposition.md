---
title: IDebugComPlusSymbolProvider::GetAddressesInModuleFromPosition | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- GetAddressesInModuleFromPosition
- IDebugComPlusSymbolProvider::GetAddressesInModuleFromPosition
ms.assetid: f901c66e-f53c-4ea0-8004-d8fcbf46f916
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: f7295d49faa8799731a13f500b31d436df6dc66a
ms.sourcegitcommit: 16a4a5da4a4fd795b46a0869ca2152f2d36e6db2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/06/2020
ms.locfileid: "80734033"
---
# <a name="idebugcomplussymbolprovidergetaddressesinmodulefromposition"></a>IDebugComPlusSymbolProvider::GetAddressesInModuleFromPosition
Ordnet eine Dokumentposition im angegebenen Modul einem Array von Debugadressen zu.

## <a name="syntax"></a>Syntax

```cpp
HRESULT GetAddressesInModuleFromPosition(
   ULONG32                  ulAppDomainID,
   GUID                     guidModule,
   IDebugDocumentPosition2* pDocPos,
   BOOL                     fStatmentOnly,
   IEnumDebugAddresses**    ppEnumBegAddresses,
   IEnumDebugAddresses**    ppEnumEndAddresses
);
```

```csharp
int GetAddressesInModuleFromPosition(
   uint                    ulAppDomainID,
   Guid                    guidModule,
   IDebugDocumentPosition2 pDocPos,
   bool                    fStatmentOnly,
   out IEnumDebugAddresses ppEnumBegAddresses,
   out IEnumDebugAddresses ppEnumEndAddresses
);
```

## <a name="parameters"></a>Parameter
`ulAppDomainID`\
[in] Anwendungsdomänenbezeichner.

`guidModule`\
[in] Eindeutiger Bezeichner des Moduls.

`pDocPos`\
[in] Die Dokumentposition.

`fStatmentOnly`\
[in] Wenn `TRUE`, beschränkt die Debugadressen auf eine einzelne Anweisung.

`ppEnumBegAddresses`\
[out] Gibt einen Enumerator für die Startdebugadressen zurück, die dieser Anweisung oder Zeile zugeordnet sind.

`ppEnumEndAddresses`\
[out] Gibt einen Enumerator für die Enddebugadressen zurück, die dieser Anweisung oder Zeile zugeordnet sind.

## <a name="return-value"></a>Rückgabewert
 Wenn die Ausführung erfolgreich ist, wird `S_OK`, andernfalls ein Fehlercode zurückgegeben.

## <a name="example"></a>Beispiel
 Das folgende Beispiel zeigt, wie diese Methode für ein **CDebugSymbolProvider-Objekt** implementiert wird, das die [IDebugComPlusSymbolProvider-Schnittstelle](../../../extensibility/debugger/reference/idebugcomplussymbolprovider.md) verfügbar macht.

```cpp
HRESULT CDebugSymbolProvider::GetAddressesInModuleFromPosition(
    ULONG32 ulAppDomainID,
    GUID guidModule,
    IDebugDocumentPosition2* pDocPos,
    BOOL fStatementOnly,
    IEnumDebugAddresses** ppEnumBegAddresses,
    IEnumDebugAddresses** ppEnumEndAddresses
)
{
    GUID guidNULL = {0};

    if (guidNULL == guidModule)
    {
        return GetAddressesInAppDomainFromPosition( ulAppDomainID,
                pDocPos,
                fStatementOnly,
                ppEnumBegAddresses,
                ppEnumEndAddresses );
    }
    else
    {
        return GetAddressesInModuleFromPositionHelper( ulAppDomainID,
                guidModule,
                pDocPos,
                fStatementOnly,
                ppEnumBegAddresses,
                ppEnumEndAddresses );
    }
}

HRESULT CDebugSymbolProvider::GetAddressesInModuleFromPositionHelper(
    ULONG32 ulAppDomainID,
    GUID guidModule,
    IDebugDocumentPosition2* pDocPos,
    BOOL fStatementOnly,
    IEnumDebugAddresses** ppEnumBegAddresses,
    IEnumDebugAddresses** ppEnumEndAddresses
)
{
    HRESULT hr = S_OK;
    CComBSTR bstrFileName;
    TEXT_POSITION posBeg;
    TEXT_POSITION posEnd;
    DWORD dwLine;
    USHORT segRet = 0;
    ULONG offRet = 0;
    CAddrList listAddr;
    CAddrList listAddrEnd;
    CAddrList* plistAddrEnd = NULL;
    bool fFileFound = false;
    Module_ID idModule(ulAppDomainID, guidModule);
    DWORD dwListCount;
    bool fFoundAddresses = false;
    CComPtr<CModule> pmodule;
    DWORD dwBegCol = 0;
    DWORD dwEndCol = 0;

    ASSERT(IsValidObjectPtr(this, CDebugSymbolProvider));
    ASSERT(IsValidInterfacePtr(pDocPos, IDebugDocumentPosition2));
    ASSERT(IsValidWritePtr(ppEnumBegAddresses, IEnumDebugAddresses*));

    METHOD_ENTRY(CDebugSymbolProvider::GetAddressesInModuleFromPositionHelper);

    // Bail on Invalid Args

    IfFalseGo( pDocPos && ppEnumBegAddresses, E_INVALIDARG );

    *ppEnumBegAddresses = NULL;
    if (ppEnumEndAddresses)
    {
        *ppEnumEndAddresses = NULL;
        plistAddrEnd = &listAddrEnd;
    }

    // Get the Position

    IfFailGo( pDocPos->GetFileName(&bstrFileName) );
    IfFailGo( pDocPos->GetRange(&posBeg, &posEnd) );

    // Iterate over the module list accumulating addresses
    // that match the position

    dwLine = posBeg.dwLine;
    IfFailGo( GetModule( idModule, &pmodule ) );
    dwListCount = listAddr.GetCount();

    if ( fStatementOnly )
    {
        dwBegCol = posBeg.dwColumn;
        dwEndCol = posBeg.dwLine == posEnd.dwLine ? posEnd.dwColumn : DWORD( -1);
    }
    else
    {
        dwBegCol = 0;
        dwEndCol = DWORD( -1);
    }

    while (!fFoundAddresses && dwLine <= posEnd.dwLine )
    {
        hr = pmodule->GetAddressesFromLine( bstrFileName,
                                            dwLine,
                                            posEnd.dwLine,
                                            dwBegCol,
                                            dwEndCol,
                                            &listAddr,
                                            plistAddrEnd );

        dwLine++;
        dwBegCol = 0;
        dwEndCol = dwLine == posEnd.dwLine ? posEnd.dwColumn : DWORD( -1);

        if (hr == E_SH_INVALID_POSITION)
        {
            fFileFound = true;
            break;
        }

        if (FAILED(hr))
        {
            // Move on to the next module
            break;
        }

        fFileFound = true;
        fFoundAddresses = listAddr.GetCount() != dwListCount;
    }

    // Distinguish no file from bad position in the file
    IfFalseGo( fFileFound, E_SH_FILE_NOT_FOUND);

    // If the list is empty the position is bad
    IfFalseGo( listAddr.GetCount(), E_SH_INVALID_POSITION );

    // Create enumerators
    IfFailGo( CreateEnumerator( ppEnumBegAddresses, &listAddr ) );
    if (ppEnumEndAddresses)
    {
        IfFailGo( CreateEnumerator( ppEnumEndAddresses, &listAddrEnd ) );
    }

Error:

    METHOD_EXIT(CDebugSymbolProvider::GetAddressesInModuleFromPositionHelper, hr);

    return hr;
}
```

## <a name="see-also"></a>Weitere Informationen
- [IDebugComPlusSymbolProvider](../../../extensibility/debugger/reference/idebugcomplussymbolprovider.md)

---
title: BP_RESOLUTION_DATA | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- BP_RESOLUTION_DATA
helpviewer_keywords:
- BP_RESOLUTION_DATA structure
ms.assetid: 9e0b9000-6a84-47b9-b07a-367a75764389
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 93a78f84c10af047e596459b68211b885d3c3085
ms.sourcegitcommit: 16a4a5da4a4fd795b46a0869ca2152f2d36e6db2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/06/2020
ms.locfileid: "80737840"
---
# <a name="bp_resolution_data"></a>BP_RESOLUTION_DATA
Beschreibt das Ergebnis der Bindung eines Datenhaltepunkts.

## <a name="syntax"></a>Syntax

```cpp
typedef struct _BP_RESOLUTION_DATA {
    BSTR              bstrDataExpr;
    BSTR              bstrFunc;
    BSTR              bstrImage;
    BP_RES_DATA_FLAGS dwFlags;
} BP_RESOLUTION_DATA;
```

```csharp
public struct BP_RESOLUTION_DATA {
    public string bstrDataExpr;
    public string bstrFunc;
    public string bstrImage;
    public uint   dwFlags;
};
```

## <a name="members"></a>Member
`bstrDataExpr`\
Der Datenausdruck, der gebunden wurde.

`bstrFunc`\
Der Name der Funktion, an die der Datenhaltepunkt gebunden ist (falls vorhanden).

`bstrImage`\
Der Name des Moduls (z. B. MyModule.dll), an das der Datenhaltepunkt gebunden ist.

`dwFlags`\
Ein Wert [BP_RES_DATA_FLAGS](../../../extensibility/debugger/reference/bp-res-data-flags.md) aus der BP_RES_DATA_FLAGS-Enumeration, der beschreibt, wie der Datenhaltepunkt implementiert wird.

## <a name="remarks"></a>Bemerkungen
Diese Struktur ist ein [BP_RESOLUTION_LOCATION](../../../extensibility/debugger/reference/bp-resolution-location.md) Element der BP_RESOLUTION_LOCATION-Struktur, die wiederum ein Member der [BP_RESOLUTION_INFO-Struktur](../../../extensibility/debugger/reference/bp-resolution-info.md) ist, die von der [GetResolutionInfo-Methode](../../../extensibility/debugger/reference/idebugbreakpointresolution2-getresolutioninfo.md) zurückgegeben wird.

## <a name="requirements"></a>Requirements (Anforderungen)
Kopfzeile: msdbg.h

Namespace: Microsoft.VisualStudio.Debugger.Interop

Assembly: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>Weitere Informationen
- [Structures and Unions](../../../extensibility/debugger/reference/structures-and-unions.md)
- [BP_RESOLUTION_LOCATION](../../../extensibility/debugger/reference/bp-resolution-location.md)
- [BP_RESOLUTION_INFO](../../../extensibility/debugger/reference/bp-resolution-info.md)
- [GetResolutionInfo](../../../extensibility/debugger/reference/idebugbreakpointresolution2-getresolutioninfo.md)

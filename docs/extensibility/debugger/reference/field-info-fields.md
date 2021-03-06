---
title: FIELD_INFO_FIELDS | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- FIELD_INFO_FIELDS
helpviewer_keywords:
- FIELD_INFO_FIELDS enumeration
ms.assetid: a69487d2-e701-4165-804a-8a011df9a3bd
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 9a3d2e796d37606c51918d8e49db920161d63f55
ms.sourcegitcommit: 16a4a5da4a4fd795b46a0869ca2152f2d36e6db2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/06/2020
ms.locfileid: "80736910"
---
# <a name="field_info_fields"></a>FIELD_INFO_FIELDS
Gibt an, welche Informationen zu einem [IDebugField-Objekt](../../../extensibility/debugger/reference/idebugfield.md) abgerufen werden sollen.

## <a name="syntax"></a>Syntax

```cpp
enum enum_FIELD_INFO_FIELDS { 
    FIF_FULLNAME  = 0x0001,
    FIF_NAME      = 0x0002,
    FIF_TYPE      = 0x0004,
    FIF_MODIFIERS = 0x0008,
    FIF_ALL       = 0xffffffff,
    FIF_NONE      = 0x0000
};
typedef DWORD FIELD_INFO_FIELDS;
```

```csharp
public enum enum_FIELD_INFO_FIELDS {
    FIF_FULLNAME  = 0x0001,
    FIF_NAME      = 0x0002,
    FIF_TYPE      = 0x0004,
    FIF_MODIFIERS = 0x0008,
    FIF_ALL       = 0xffffffff,
    FIF_NONE      = 0x0000
};
```

## <a name="fields"></a>Felder
`FIF_FULLNAME`\
Initialisieren/verwenden `bstrFullName` Sie das Feld in der [FIELD_INFO](../../../extensibility/debugger/reference/field-info.md) Struktur.

`FIF_NAME`\
Initialisieren/verwenden `bstrName` Sie das `FIELD_INFO` Feld in der Struktur.

`FIF_TYPE`\
Initialisieren/verwenden `bstrType` Sie das `FIELD_INFO` Feld in der Struktur.

`FIF_MODIFIERS`\
Initialisieren/verwenden `bstrModifiers` Sie das `FIELD_INFO` Feld in der Struktur.

## <a name="remarks"></a>Bemerkungen
Diese Werte werden auch als Argument an die [GetInfo-Methode](../../../extensibility/debugger/reference/idebugfield-getinfo.md) übergeben, um anzugeben, welche Felder der [FIELD_INFO-Struktur](../../../extensibility/debugger/reference/field-info.md) initialisiert werden sollen.

Diese Werte werden auch `dwFields` im `FIELD_INFO` Element der Struktur verwendet, um anzugeben, welche Felder verwendet und gültig sind.

Diese Flags können mit einem `OR`bitwise kombiniert werden.

## <a name="requirements"></a>Requirements (Anforderungen)
Kopfzeile: sh.h

Namespace: Microsoft.VisualStudio.Debugger.Interop

Assembly: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>Weitere Informationen
- [Enumerationen](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)
- [FIELD_INFO](../../../extensibility/debugger/reference/field-info.md)
- [IDebugField](../../../extensibility/debugger/reference/idebugfield.md)
- [GetInfo](../../../extensibility/debugger/reference/idebugfield-getinfo.md)

---
title: BPREQI_FIELDS90 | Microsoft-Dokumentation
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
helpviewer_keywords:
- BPREQI_FIELDS90 enumeration
ms.assetid: bf6f7efc-39f2-46a2-906d-c3647bf89995
caps.latest.revision: 9
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 97a38b4296668cb287f34e5b1afcbd7c90477011
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "68153212"
---
# <a name="bpreqifields90"></a>BPREQI_FIELDS90
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Listet die gültigen Werte, die die Informationen abgerufen werden sollen eine Haltepunkt-Anforderung angeben. Diese Enumeration erweitert die [BPREQI_FIELDS](../../../extensibility/debugger/reference/bpreqi-fields.md) Enumeration.  
  
## <a name="syntax"></a>Syntax  
  
```cpp#  
enum enum_BPREQI_FIELDS90  
{  
   // VS 8.0 values  
   BPREQI90_BPLOCATION                = 0x0001,  
   BPREQI90_LANGUAGE                  = 0x0002,  
   BPREQI90_PROGRAM                   = 0x0004,  
   BPREQI90_PROGRAMNAME               = 0x0008,  
   BPREQI90_THREAD                    = 0x0010,  
   BPREQI90_THREADNAME                = 0x0020,  
   BPREQI90_PASSCOUNT                 = 0x0040,  
   BPREQI90_CONDITION                 = 0x0080,  
   BPREQI90_FLAGS                     = 0x0100,  
   BPREQI90_ALLOLDFIELDS              = 0x01ff,  
   BPREQI90_VENDOR                    = 0x0200,  
   BPREQI90_CONSTRAINT                = 0x0400,  
   BPREQI90_TRACEPOINT                = 0x0800,  
  
   // Values added in VS 9.0  
   BPREQI90_MACROTRACEPOINT           = 0x1000,  
  
   BPREQI90_ALLFIELDS                 = 0xffff  
};  
typedef DWORD BPREQI_FIELDS90;  
```  
  
```csharp  
public enum enum_BPREQI_FIELDS90  
{  
    // VS 8.0 values  
    BPREQI90_BPLOCATION                = 0x0001,  
    BPREQI90_LANGUAGE                  = 0x0002,  
    BPREQI90_PROGRAM                   = 0x0004,  
    BPREQI90_PROGRAMNAME               = 0x0008,  
    BPREQI90_THREAD                    = 0x0010,  
    BPREQI90_THREADNAME                = 0x0020,  
    BPREQI90_PASSCOUNT                 = 0x0040,  
    BPREQI90_CONDITION                 = 0x0080,  
    BPREQI90_FLAGS                     = 0x0100,  
    BPREQI90_ALLOLDFIELDS              = 0x01ff,  
    BPREQI90_VENDOR                    = 0x0200,  
    BPREQI90_CONSTRAINT                = 0x0400,  
    BPREQI90_TRACEPOINT                = 0x0800,  
  
    // Values added in VS 9.0  
    BPREQI90_MACROTRACEPOINT           = 0x1000,  
  
    BPREQI90_ALLFIELDS                 = 0xffff  
};  
```  
  
#### <a name="parameters"></a>Parameter  
 BPREQI90_BPLOCATION  
 Initialisieren oder verwenden Sie die `bpLocation` (Position des Haltepunkts) Feld der [BP_REQUEST_INFO](../../../extensibility/debugger/reference/bp-request-info.md) oder [BP_REQUEST_INFO2](../../../extensibility/debugger/reference/bp-request-info2.md) Struktur.  
  
 BPREQI90_LANGUAGE  
 Initialisieren oder verwenden Sie die `guidLanguage` Feld der `BP_REQUEST_INFO` oder `BP_REQUEST_INFO2` Struktur.  
  
 BPREQI90_PROGRAM  
 Initialisieren oder verwenden Sie die `pProgram` Feld der `BP_REQUEST_INFO` oder `BP_REQUEST_INFO2` Struktur.  
  
 BPREQI90_PROGRAMNAME  
 Initialisieren oder verwenden Sie die `bstrProgramName` Feld der `BP_REQUEST_INFO` oder `BP_REQUEST_INFO2` Struktur.  
  
 BPREQI90_THREAD  
 Initialisieren oder verwenden Sie die `pThread` Feld der `BP_REQUEST_INFO` oder `BP_REQUEST_INFO2` Struktur.  
  
 BPREQI90_THREADNAME  
 Initialisieren oder verwenden Sie die `bstrThreadName` Feld der `BP_REQUEST_INFO` oder `BP_REQUEST_INFO2` Struktur.  
  
 BPREQI90_PASSCOUNT  
 Initialisieren oder verwenden Sie die `bpPassCount` Feld der `BP_REQUEST_INFO` oder `BP_REQUEST_INFO2` Struktur.  
  
 BPREQI90_CONDITION  
 Initialisieren oder verwenden Sie die `bpCondition` (Bedingung für Haltepunkt) Feld der `BP_REQUEST_INFO` oder `BP_REQUEST_INFO2` Struktur.  
  
 BPREQI90_FLAGS  
 Initialisieren oder verwenden Sie die `dwFlags` Feld der `BP_REQUEST_INFO` oder `BP_REQUEST_INFO2` Struktur.  
  
 BPREQI90_ALLOLDFIELDS  
 Initialisieren oder verwenden Sie alle Felder für die von der `BP_REQUEST_INFO` Struktur.  
  
 BPREQI90_VENDOR  
 Initialisieren oder verwenden Sie die `guidVendor` Feld `BP_REQUEST_INFO2` Struktur.  
  
 BPREQI90_CONSTRAINT  
 Initialisieren oder verwenden Sie die `bstrConstraint` Feld `BP_REQUEST_INFO2` Struktur.  
  
 BPREQI90_TRACEPOINT  
 Initialisieren oder verwenden Sie die `bstrTracepoint` Feld `BP_REQUEST_INFO2` Struktur.  
  
 BPREQI90_MACROTRACEPOINT  
 Initialisieren oder verwenden Sie die `bstrMacroTracepoint` Feld `BP_REQUEST_INFO2` Struktur. BPREQI_ALLFIELDS enthält dieses Feld keine.  
  
 BPREQI90_ALLFIELDS  
 Gibt an, alle Felder für die `BP_REQUEST_INFO2` Struktur.  
  
## <a name="requirements"></a>Anforderungen  
 Header: Msdbg90.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Siehe auch  
 [Enumerationen](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)

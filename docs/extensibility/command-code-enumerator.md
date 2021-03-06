---
title: Befehlscode-Enumerator | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- command code enumerator
- source control plug-ins, command code enumeration
ms.assetid: 5d2c360c-59e4-4da8-bcb4-dd07c7441e40
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 15916d26ac0120417205af0bb9117a45ec0397c6
ms.sourcegitcommit: 16a4a5da4a4fd795b46a0869ca2152f2d36e6db2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/06/2020
ms.locfileid: "80739786"
---
# <a name="command-code-enumerator"></a>Befehlscode-Enumerator
Dieser Enumerator wird in den Optionen für die [SccGetCommandOptions](../extensibility/sccgetcommandoptions-function.md) und die [SccPopulateList](../extensibility/sccpopulatelist-function.md)verwendet, um den Befehl anzugeben, für den die Optionen angegeben sind.

## <a name="syntax"></a>Syntax

```
enum SCCCOMMAND {
   SCC_COMMAND_GET,
   SCC_COMMAND_CHECKOUT,
   SCC_COMMAND_CHECKIN,
   SCC_COMMAND_UNCHECKOUT,
   SCC_COMMAND_ADD,
   SCC_COMMAND_REMOVE,
   SCC_COMMAND_DIFF,
   SCC_COMMAND_HISTORY,
   SCC_COMMAND_RENAME,
   SCC_COMMAND_PROPERTIES,
   SCC_COMMAND_OPTIONS
};
```

## <a name="members"></a>Member
SCC_COMMAND_GET Entspricht dem [SccGet](../extensibility/sccget-function.md).

SCC_COMMAND_CHECKOUT Entspricht dem [SccCheckout](../extensibility/scccheckout-function.md).

SCC_COMMAND_CHECKIN Entspricht dem [SccCheckin](../extensibility/scccheckin-function.md).

SCC_COMMAND_UNCHECKOUT Entspricht dem [SccUncheckout](../extensibility/sccuncheckout-function.md).

SCC_COMMAND_ADD Entspricht dem [SccAdd](../extensibility/sccadd-function.md).

SCC_COMMAND_REMOVE Entspricht [sccRemove](../extensibility/sccremove-function.md).

SCC_COMMAND_DIFF Entspricht dem [SccDiff](../extensibility/sccdiff-function.md).

SCC_COMMAND_HISTORY Entspricht der [SccHistory](../extensibility/scchistory-function.md).

SCC_COMMAND_RENAME Entspricht dem [SccRename](../extensibility/sccrename-function.md).

SCC_COMMAND_PROPERTIES Entspricht den [SccProperties](../extensibility/sccproperties-function.md).

SCC_COMMAND_OPTIONS Entspricht der [SccSetOption](../extensibility/sccsetoption-function.md).

## <a name="see-also"></a>Weitere Informationen
- [Quellcodeverwaltungs-Plug-Ins](../extensibility/source-control-plug-ins.md)
- [SccGetCommandOptions](../extensibility/sccgetcommandoptions-function.md)
- [SccPopulateList](../extensibility/sccpopulatelist-function.md)

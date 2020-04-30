---
title: Zuverlässigkeitswarnungen
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- vs.codeanalysis.reliabilityrules
helpviewer_keywords:
- warnings, reliability
- reliability warnings
- managed code analysis warnings, reliability warnings
ms.assetid: 77886846-10a2-4585-968a-7eb60ebe07e8
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: c4b888dbbe7a26e5ff333ec39aa0fdfcec90b429
ms.sourcegitcommit: da5ebc29544fdbdf625ab4922c9777faf2bcae4a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/29/2020
ms.locfileid: "82586199"
---
# <a name="reliability-warnings"></a>Zuverlässigkeitswarnungen

Zuverlässigkeits Warnungen unterstützen die Zuverlässigkeit von Bibliotheken und Anwendungen, z. b. die korrekte Arbeitsspeicher-und Thread Verwendung Die Zuverlässigkeits Regeln umfassen Folgendes:

|Regel|BESCHREIBUNG|
|----------|-----------------|
|[CA2000: Objekte verwerfen, bevor Bereich verloren geht.](../code-quality/ca2000.md)|Da eine Ausnahme auftreten kann, durch die die Ausführung eines Objektfinalizers verhindert wird, sollte das Objekt explizit verworfen werden, bevor sich sämtliche Verweise auf dieses außerhalb des Bereichs befinden.|
|[CA2001: Keine problematischen Methoden aufrufen.](../code-quality/ca2001.md)|Ein Member ruft eine möglicherweise gefährliche oder problematische Methode auf.|
|[CA2002: Auf Objekten mit schwacher Identität nicht sperren.](../code-quality/ca2002.md)|Ein Objekt hat eine schwache Identität, wenn ein Zugriff darauf über Grenzen von Anwendungsdomänen hinweg möglich ist. Ein Thread, der eine Sperre für ein Objekt zu erhalten versucht, das über eine schwache Identität verfügt, kann durch einen zweiten Thread in einer anderen Anwendungsdomäne blockiert werden, der eine Sperre für das gleiche Objekt besitzt.|
|[CA2003: Fibers nicht als Threads behandeln.](../code-quality/ca2003.md)|Ein verwalteter Thread wird als Win32-Thread behandelt.|
|[CA2004: Aufrufe an GC.KeepAlive entfernen.](../code-quality/ca2004.md)|Wenn Sie eine Umstellung auf die SafeHandle-Verwendung durchlaufen, entfernen Sie alle Aufrufe von GC. KeepAlive (-Objekt). In diesem Fall dürfen Klassen nicht GC abrufen. KeepAlive, angenommen, Sie verfügen über keinen Finalizer, verwenden jedoch SafeHandle, um das Betriebssystem Handle für Sie zu finalisieren.|
|[CA2006: SafeHandle verwenden, um native Ressourcen zu kapseln.](../code-quality/ca2006.md)|Die Verwendung von IntPtr in verwaltetem Code kann auf ein potenzielles Sicherheitsrisiko und Zuverlässigkeitsproblem hinweisen. Alle Vorkommen von IntPtr müssen daher überprüft werden, um festzustellen, ob stattdessen die Verwendung von SafeHandle (oder einer ähnlichen Technologie) erforderlich ist.|
|[CA2007: Eine Aufgabe nicht direkt abwarten](../code-quality/ca2007.md)|Eine asynchrone Methode [erwartet](/dotnet/csharp/language-reference/keywords/await) direkt <xref:System.Threading.Tasks.Task> ein.|
|[CA2009: "alimmutablecollection" nicht für einen immutablecollection-Wert aufruft.](../code-quality/ca2009.md)|`ToImmutable`die Methode wurde für eine unveränderliche Auflistung aus <xref:System.Collections.Immutable> dem Namespace unnötig aufgerufen.|

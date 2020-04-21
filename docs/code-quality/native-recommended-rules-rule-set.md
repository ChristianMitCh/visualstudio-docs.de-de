---
title: Regelsatz für systemeigene empfohlene Regeln
ms.date: 11/04/2016
ms.topic: reference
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 4a86cb62fe0ae0db971a417ef923f45eedbefe0c
ms.sourcegitcommit: ade07bd1cf69b8b494d171ae648cfdd54f7800d3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2020
ms.locfileid: "81649292"
---
# <a name="native-recommended-rules-rule-set"></a>Regelsatz für systemeigene empfohlene Regeln

Die nativen empfohlenen Regeln konzentrieren sich auf die kritischsten und häufigsten Probleme im systemeigenen Code, einschließlich potenzieller Sicherheitslücken und Anwendungsabstürze. Dieser Regelsatz enthält alle Regeln im Regelsatz [Für Systemeigene Mindestregeln.](native-minimum-rules-rule-set.md)

Schließen Sie diesen Regelsatz in jeden benutzerdefinierten Regelsatz ein, den Sie für systemeigene Projekte erstellen.

|Regel|BESCHREIBUNG|
|----------|-----------------|
|[C6001](../code-quality/c6001.md)|Nicht initialisierter Speicher wird verwendet|
|[C6011](../code-quality/c6011.md)|Dereferenzierender NULL-Zeiger|
|[C6029](../code-quality/c6029.md)|Verwendung von ungeprüftem Wert|
|[C6031](../code-quality/c6031.md)|Rückgabewert ignoriert|
|[C6053](../code-quality/c6053.md)|0 (null)-Abbruch des Aufrufs|
|[C6054](../code-quality/c6054.md)|Null-Beendigung fehlt|
|[C6059](../code-quality/c6059.md)|Fehlerhafte Verkettung|
|[C6063](../code-quality/c6063.md)|Fehlendes Zeichenfolgenargument für Formatfunktion|
|[C6064](../code-quality/c6064.md)|Fehlendes Ganzzahlargument für Formatfunktion|
|[C6066](../code-quality/c6066.md)|Fehlendes Zeigerargument für Formatfunktion|
|[C6067](../code-quality/c6067.md)|Fehlendes Zeichenfolgenzeigerargument für Formatfunktion|
|[C6101](../code-quality/c6101.md)|Rückgabe von nicht initialisiertem Speicher|
|[C6200](../code-quality/c6200.md)|Index überschreitet maximale Puffergröße|
|[C6201](../code-quality/c6201.md)|Index überschreitet maximale Puffergröße|
|[C6214](../code-quality/c6214.md)|Ungültige Umwandlung HRESULT zu BOOL|
|[C6215](../code-quality/c6215.md)|Ungültige Umwandlung BOOL zu HRESULT|
|[C6216](../code-quality/c6216.md)|Ungültige VomAstrierung s/BooL in HRESULT eingefügte Cast-BooL|
|[C6217](../code-quality/c6217.md)|Ungültiger HRESULT-Test mit NOT|
|[C6220](../code-quality/c6220.md)|Ungültiger HRESULT-Vergleich mit -1|
|[C6226](../code-quality/c6226.md)|Ungültige HRESULT-Zuweisung zu -1|
|[C6230](../code-quality/c6230.md)|Ungültige HRESULT-Verwendung als boolesche|
|[C6235](../code-quality/c6235.md)|Non-Zero-Konstante mit Logical-Or|
|[C6236](../code-quality/c6236.md)|Logisch-oder mit Non-Zero-Konstante|
|[C6237](../code-quality/c6237.md)|Null mit logischen und verliert Nebenwirkungen|
|[C6242](../code-quality/c6242.md)|Lokale Entladung erzwungen|
|[C6248](../code-quality/c6248.md)|Null-DACL wird erstellt|
|[C6250](../code-quality/c6250.md)|Unveröffentlichte Adressbeschreibungen|
|[C6255](../code-quality/c6255.md)|Ungeschützte Verwendung von Alloca|
|[C6258](../code-quality/c6258.md)|Verwenden von Beendigungsthreads|
|[C6259](../code-quality/c6259.md)|Dead Code In Bitwise-Or Limited Switch|
|[C6260](../code-quality/c6260.md)|Verwendung von Byte Arithmetik|
|[C6262](../code-quality/c6262.md)|Übermäßige Stack-Nutzung|
|[C6263](../code-quality/c6263.md)|Verwenden von Alloca In Loop|
|[C6268](../code-quality/c6268.md)|Fehlende Klammern in Guss|
|[C6269](../code-quality/c6269.md)|Zeigerdereferenzierung ignoriert|
|[C6270](../code-quality/c6270.md)|Fehlendes Gleitkommaargument für Formatfunktion|
|[C6271](../code-quality/c6271.md)|Zusätzliches Argument für Formatfunktion|
|[C6272](../code-quality/c6272.md)|Nicht-Gleitkommaargument für Formatfunktion|
|[C6273](../code-quality/c6273.md)|Nicht-Ganzzahlargument für Formatfunktion|
|[C6274](../code-quality/c6274.md)|Nicht-Zeichenargument für Formatfunktion|
|[C6276](../code-quality/c6276.md)|Ungültige Zeichenfolgenumwandlung|
|[C6277](../code-quality/c6277.md)|Ungültiger CreateProcess-Aufruf|
|[C6278](../code-quality/c6278.md)|Array-New Scalar-Delete Mismatch|
|[C6279](../code-quality/c6279.md)|Scalar-New Array-Delete Mismatch|
|[C6280](../code-quality/c6280.md)|Memory Allocation-Deallocation Mismatch|
|[C6281](../code-quality/c6281.md)|Bitweise Beziehungspriorität|
|[C6282](../code-quality/c6282.md)|Zuweisung ersetzt Test|
|[C6283](../code-quality/c6283.md)|Primitive Array-New Scalar-Delete Mismatch|
|[C6284](../code-quality/c6284.md)|Ungültiges Objekt-Argument für Formatfunktion|
|[C6285](../code-quality/c6285.md)|Logical-Or Of Constants|
|[C6286](../code-quality/c6286.md)|Non-Zero Logische-oder Verlust-Nebenwirkungen|
|[C6287](../code-quality/c6287.md)|Redundanter Test|
|[C6288](../code-quality/c6288.md)|Gegenseitige Inklusion über logisch - und ist falsch|
|[C6289](../code-quality/c6289.md)|Gegenseitiger Ausschluss über Logical-Or ist wahr|
|[C6290](../code-quality/c6290.md)|Logischer NOT-Operator hat Vorrang gegenüber bitweisem AND-Operator|
|[C6291](../code-quality/c6291.md)|Logischer NOT-Operator hat Vorrang gegenüber bitweisem OR-Operator|
|[C6292](../code-quality/c6292.md)|Schleife zählt von Maximum|
|[C6293](../code-quality/c6293.md)|Schleife zählt nach unten vom Minimum|
|[C6294](../code-quality/c6294.md)|Loop Body nie ausgeführt|
|[C6295](../code-quality/c6295.md)|Endlosschleife|
|[C6296](../code-quality/c6296.md)|Schleife nur einmal ausgeführt|
|[C6297](../code-quality/c6297.md)|Ergebnis der Verschiebung auf größere Größe|
|[C6299](../code-quality/c6299.md)|Bitfield zu booleschen Vergleich|
|[C6302](../code-quality/c6302.md)|Ungültiges Zeichenfolgenargument für Formatfunktion|
|[C6303](../code-quality/c6303.md)|Ungültiges Zeichenfolgenargument für breite Zeichen zu Formatfunktion|
|[C6305](../code-quality/c6305.md)|Keine Übereinstimmung bei Größe und Count-Verwendung|
|[C6306](../code-quality/c6306.md)|Falscher Variablenargument-Funktionsaufruf|
|[C6308](../code-quality/c6308.md)|Realloc Leak|
|[C6310](../code-quality/c6310.md)|Unzulässige Ausnahmefilterkonstante|
|[C6312](../code-quality/c6312.md)|Ausnahme Fortsetzung der Ausführungsschleife|
|[C6314](../code-quality/c6314.md)|Bitwise-Or-Vorrang|
|[C6317](../code-quality/c6317.md)|Nicht nicht komplementeren|
|[C6318](../code-quality/c6318.md)|Ausnahme Continue Search|
|[C6319](../code-quality/c6319.md)|Ignoriert von Komma|
|[C6324](../code-quality/c6324.md)|Zeichenfolgenkopie statt String-Vergleich|
|[C6328](../code-quality/c6328.md)|Möglicher Argumenttypenkonflikt|
|[C6331](../code-quality/c6331.md)|VirtualFree Ungültige Flags|
|[C6332](../code-quality/c6332.md)|VirtualFree Ungültiger Parameter|
|[C6333](../code-quality/c6333.md)|VirtualFree Ungültige Größe|
|[C6335](../code-quality/c6335.md)|Leaking Process Handle|
|[C6381](../code-quality/c6381.md)|Shutdown-Informationen fehlen|
|[C6383](../code-quality/c6383.md)|Element-Count Byte-Count-Pufferüberlauf|
|[C6384](../code-quality/c6384.md)|Pointer Size Division|
|[C6385](../code-quality/c6385.md)|Leseüberlauf|
|[C6386](../code-quality/c6386.md)|Schreibüberlauf|
|[C6387](../code-quality/c6387.md)|Ungültiger Parameterwert|
|[C6388](../code-quality/c6388.md)|Ungültiger Parameterwert|
|[C6500](../code-quality/c6500.md)|Ungültige Attributeigenschaft|
|[C6501](../code-quality/c6501.md)|In Konflikt stehende Attributeigenschaftswerte|
|[C6503](../code-quality/c6503.md)|Verweise dürfen nicht NULL sein.|
|[C6504](../code-quality/c6504.md)|NULL auf Nichtzeiger|
|[C6505](../code-quality/c6505.md)|MustCheck für "void"|
|[C6506](../code-quality/c6506.md)|Puffergröße auf Nichtzeiger oder Array|
|[C6508](../code-quality/c6508.md)|Schreibzugriff auf Konstante|
|[C6509](../code-quality/c6509.md)|Rückgabe wurde für Vorbedingung verwendet|
|[C6510](../code-quality/c6510.md)|NULL für Nichtzeiger abgebrochen|
|[C6511](../code-quality/c6511.md)|MustCheck Muss "Ja" oder "Nein" lauten|
|[C6513](../code-quality/c6513.md)|Elementgröße ohne Puffergröße|
|[C6514](../code-quality/c6514.md)|Puffergröße übersteigt Arraygröße|
|[C6515](../code-quality/c6515.md)|Puffergröße auf Nichtzeiger|
|[C6516](../code-quality/c6516.md)|Keine Eigenschaften für Attribut|
|[C6517](../code-quality/c6517.md)|Zulässige Größe für nicht lesbaren Puffer|
|[C6518](../code-quality/c6518.md)|Schreibbare Größe für Puffer, der nicht geschrieben werden kann|
|[C6522](../code-quality/c6522.md)|Ungültiger Größenzeichenfolgentyp|
|[C6525](../code-quality/c6525.md)|Ungültiger Größenzeichenfolgenstandort|
|[C6527](../code-quality/c6527.md)|Ungültige Anmerkung: Die 'NeedsRelease'-Eigenschaft kann nicht für Werte des void-Typs verwendet werden.|
|[C6530](../code-quality/c6530.md)|Unbekannter Formatzeichenfolgenstil|
|[C6540](../code-quality/c6540.md)|Bei Verwendung von Attributanmerkungen für diese Funktion werden alle vorhandenen, zugehörigen __declspec-Anmerkungen ungültig|
|[C6551](../code-quality/c6551.md)|Ungültige Größenangabe: Ausdruck nicht analysierbar|
|[C6552](../code-quality/c6552.md)|Ungültiger Deref= oder Notref=: Ausdruck nicht analysierbar|
|[C6701](../code-quality/c6701.md)|Der Wert ist kein gültiger Yes/No/Maybe-Wert|
|[C6702](../code-quality/c6702.md)|Der Wert ist kein Zeichenfolgenwert|
|[C6703](../code-quality/c6703.md)|Der Wert ist keine Zahl|
|[C6704](../code-quality/c6704.md)|Unerwarteter Ausdrucksfehler der Anmerkung|
|[C6705](../code-quality/c6705.md)|Erwartete Anzahl von Argumenten für die Anmerkung stimmt nicht mit tatsächlicher Anzahl von Argumenten für die Anmerkung überein|
|[C6706](../code-quality/c6706.md)|Unerwarteter Anmerkungsfehler für Anmerkung|
|[C6995](../code-quality/c6995.md)|Fehler beim Speichern der XML-Protokolldatei|
|[C26100](../code-quality/c26100.md)|Racebedingung|
|[C26101](../code-quality/c26101.md)|Nichtverwenden des ineingespielten Betriebs|
|[C26110](../code-quality/c26110.md)|Anrufer kann Sperre nicht halten|
|[C26111](../code-quality/c26111.md)|Anrufer kann Sperre nicht freigeben|
|[C26112](../code-quality/c26112.md)|Anrufer kann keine Sperre halten|
|[C26115](../code-quality/c26115.md)|Fehler bei der Freigabe der Sperre|
|[C26116](../code-quality/c26116.md)|Nichtergriff zum Erwerb oder Zum Halten der Sperre|
|[C26117](../code-quality/c26117.md)|Lösen der nicht gehaltenen Sperre|
|[C26140](../code-quality/c26140.md)|Nebenläufigkeitsfehler bei SAL-Anmerkung.|
|[C26441](../code-quality/c26441.md)|NO_UNNAMED_GUARDS|
|[C26444](../code-quality/c26444.md)|NO_UNNAMED_RAII_OBJECTS|
|[C26498](../code-quality/c26498.md)|USE_CONSTEXPR_FOR_FUNCTIONCALL|
|[C28020](../code-quality/c28020.md)|Der Ausdruck ist bei diesem Aufruf nicht wahr|
|[C28021](../code-quality/c28021.md)|Der Parameter, der mit Anmerkungen versehen ist, muss ein Zeiger sein.|
|[C28022](../code-quality/c28022.md)|Die Funktionsklasse(n) dieser Funktion stimmt nicht mit der Funktionsklasse(n) auf dem typdef überein, der zu ihrer Definition verwendet wird.|
|[C28023](../code-quality/c28023.md)|Die Funktion, die zugewiesen \_oder\_\_ übergeben wird, sollte eine Funktion-Klassenanmerkung für mindestens eine der Klassen(en) haben.|
|[C28024](../code-quality/c28024.md)|Der Funktionszeiger, dem zugewiesen wird, wird mit der Funktionsklasse mit Anmerkungen versehen, die nicht in der Liste der Funktionsklassen(e) enthalten ist.|
|[C28039](../code-quality/c28039.md)|Der Typ des tatsächlichen Parameters sollte genau mit dem Typ übereinstimmen.|
|[C28112](../code-quality/c28112.md)|Auf eine Variable, auf die über eine Interlocked-Funktion zugegriffen wird, muss immer über eine Interlocked-Funktion zugegriffen werden.|
|[C28113](../code-quality/c28113.md)|Zugriff auf eine lokale Variable über eine Interlocked-Funktion|
|[C28125](../code-quality/c28125.md)|Die Funktion muss innerhalb eines try/except-Blocks aufgerufen werden.|
|[C28137](../code-quality/c28137.md)|Das Variablenargument sollte stattdessen eine (literale) Konstante sein.|
|[C28138](../code-quality/c28138.md)|Das konstante Argument sollte stattdessen variabel sein.|
|[C28159](../code-quality/c28159.md)|Erwägen Sie stattdessen die Verwendung einer anderen Funktion.|
|[C28160](../code-quality/c28160.md)|Fehleranmerkung|
|[C28163](../code-quality/c28163.md)|Die Funktion sollte niemals innerhalb eines try/except-Blocks aufgerufen werden.|
|[C28164](../code-quality/c28164.md)|Das Argument wird an eine Funktion übergeben, die einen Zeiger auf ein Objekt erwartet (kein Zeiger auf einen Zeiger).|
|[C28182](../code-quality/c28182.md)|Dereferenzierender NULL-Zeiger. Der Zeit enthält denselben NULL-Wert wie ein anderer Zeiger.|
|[C28183](../code-quality/c28183.md)|Das Argument kann ein Wert sein und ist eine Kopie des Werts, der im Zeiger gefunden wird.|
|[C28193](../code-quality/c28193.md)|Die Variable enthält einen Wert, der untersucht werden muss.|
|[C28196](../code-quality/c28196.md)|Die Anforderung ist nicht erfüllt. (Der Ausdruck wird nicht mit "True" ausgewertet.)|
|[C28202](../code-quality/c28202.md)|Illegaler Verweis auf nicht statischen Member|
|[C28203](../code-quality/c28203.md)|Mehrdeutiger Verweis auf Klassenmember.|
|[C28205](../code-quality/c28205.md)|\_Erfolg\_ \_oder\_\_ Fehler in einem illegalen Kontext verwendet|
|[C28206](../code-quality/c28206.md)|„->“ verwenden, wenn linker Operand auf eine Struktur zeigt|
|[C28207](../code-quality/c28207.md)|„.“ verwenden, wenn linker Operand eine Struktur ist|
|[C28209](../code-quality/c28209.md)|Die Erklärung für Symbol hat eine widersprüchliche Erklärung|
|[C28210](../code-quality/c28210.md)|Anmerkungen für den _On_failure_-Kontext dürfen sich nicht im expliziten Vorkontext befinden.|
|[C28211](../code-quality/c28211.md)|Statischer Kontextname für SAL_context erwartet|
|[C28212](../code-quality/c28212.md)|Zeigerausdruck für Anmerkung erwartet|
|[C28213](../code-quality/c28213.md)|Die \_\_Anmerkungen\_zum\_ Verwenden von decl-Anmerkungen müssen verwendet werden, um ohne Änderung auf eine vorherige Deklaration zu verweisen.|
|[C28214](../code-quality/c28214.md)|Attributparameternamen müssen p1...p9 sein.|
|[C28215](../code-quality/c28215.md)|Der Typefix kann nicht auf einen Parameter angewendet werden, der bereits über einen Typefix verfügt.|
|[C28216](../code-quality/c28216.md)|Die checkReturn-Anmerkung gilt nur für Nachbedingungen für den bestimmten Funktionsparameter.|
|[C28217](../code-quality/c28217.md)|Für die Funktion stimmt die Anzahl der Parameter für die Anmerkung nicht mit der in der Datei gefundenen überein|
|[C28218](../code-quality/c28218.md)|Für Funktionsparameter stimmt der Parameter der Anmerkung nicht mit dem in der Datei|
|[C28219](../code-quality/c28219.md)|Member von Enumeration für den Parameter in der Anmerkung erwartet|
|[C28220](../code-quality/c28220.md)|Für den Parameter in der Anmerkung erwarteter Ganzzahlausdruck|
|[C28221](../code-quality/c28221.md)|Für den Parameter in der Anmerkung erwarteter Zeichenfolgeausdruck|
|[C28222](../code-quality/c28222.md)|__yes, \___no oder \___maybe für die Anmerkung erwartet|
|[C28223](../code-quality/c28223.md)|Erwartetes Token/Bezeichner für Anmerkung, Parameter nicht gefunden|
|[C28224](../code-quality/c28224.md)|Anmerkung erfordert Parameter|
|[C28225](../code-quality/c28225.md)|Korrekte Anzahl erforderlicher Parameter konnten in Anmerkung nicht gefunden werden|
|[C28226](../code-quality/c28226.md)|Anmerkung kann nicht zusätzlich ein PrimOp sein (in der aktuellen Deklaration).|
|[C28227](../code-quality/c28227.md)|Anmerkung kann nicht zusätzlich ein PrimOp sein (siehe vorherige Deklaration).|
|[C28228](../code-quality/c28228.md)|Anmerkungsparameter: Typ kann nicht in Anmerkungen verwendet werden.|
|[C28229](../code-quality/c28229.md)|Anmerkung unterstützt keine Parameter.|
|[C28230](../code-quality/c28230.md)|Der Parametertyp weist keinen Member auf.|
|[C28231](../code-quality/c28231.md)|Anmerkung ist nur im Array gültig.|
|[C28232](../code-quality/c28232.md)|Pre, post oder deref wurden auf keine Anmerkung angewendet.|
|[C28233](../code-quality/c28233.md)|Pre, post oder deref wurden auf einen Block angewendet.|
|[C28234](../code-quality/c28234.md)|_At_-Ausdruck gilt nicht für die aktuelle Funktion.|
|[C28235](../code-quality/c28235.md)|Die Funktion kann nicht als Anmerkung alleine stehen.|
|[C28236](../code-quality/c28236.md)|Die Anmerkung kann nicht in einem Ausdruck verwendet werden.|
|[C28237](../code-quality/c28237.md)|Die Anmerkung zum Parameter wird nicht mehr unterstützt.|
|[C28238](../code-quality/c28238.md)|Die Anmerkung zum Parameter verfügt über mehrere Werte vom Typ "value", "stringValue" und "longValue". Verwenden Sie paramn=xxx.|
|[C28239](../code-quality/c28239.md)|Für die Anmerkung zum Parameter wurden sowohl value, stringValue oder longValue sowie paramn=xxx definiert. Verwenden Sie nur paramn=xxx.|
|[C28240](../code-quality/c28240.md)|Die Anmerkung zum Parameter verfügt über param2, jedoch nicht über param1.|
|[C28241](../code-quality/c28241.md)|Die Anmerkung für die Funktion zum Parameter wird nicht erkannt.|
|[C28243](../code-quality/c28243.md)|Die Anmerkung für die Funktion zum Parameter erfordert eine größere Anzahl von Dereferenzierungen, als der derzeit angemerkte Typ zulässt.|
|[C28244](../code-quality/c28244.md)|Die Anmerkung für die Funktion hat einen nicht zu analysierenden Parameter/externe Anmerkung|
|[C28245](../code-quality/c28245.md)|Die Anmerkung für die Funktion merkt „this“ in einer Nicht-Member-Funktion an.|
|[C28246](../code-quality/c28246.md)|Die Parameteranmerkung für die Funktion stimmt nicht mit dem Parametertyp überein.|
|[C28250](../code-quality/c28250.md)|Inkonsistente Anmerkung für die Funktion: die vorherige Instanz weist einen Fehler auf.|
|[C28251](../code-quality/c28251.md)|Inkonsistente Anmerkung für die Funktion: diese Instanz weist einen Fehler auf.|
|[C28252](../code-quality/c28252.md)|Inkonsistente Anmerkung für die Funktion: der Parameter weist andere Anmerkungen für diese Instanz auf.|
|[C28253](../code-quality/c28253.md)|Inkonsistente Anmerkung für die Funktion: der Parameter weist andere Anmerkungen für diese Instanz auf.|
|[C28254](../code-quality/c28254.md)|dynamic_cast<>() wird in Anmerkungen nicht unterstützt.|
|[C28262](../code-quality/c28262.md)|Ein Syntaxfehler in der Anmerkung wurde in der Funktion für Anmerkung gefunden|
|[C28263](../code-quality/c28263.md)|Ein Syntaxfehler in einer bedingten Anmerkung wurde gefunden für systeminterne Anmerkung|
|[C28267](../code-quality/c28267.md)|Ein Syntaxfehler in den Anmerkungen wurde in Anmerkung in der Funktion gefunden.|
|[C28272](../code-quality/c28272.md)|Die Anmerkung für Funktion, Parameter, beim Untersuchen von ist inkonsistent mit der Funktionsdeklaration.|
|[C28273](../code-quality/c28273.md)|Für Funktion sind die Hinweise inkonsistent mit der Funktionsdeklaration.|
|[C28275](../code-quality/c28275.md)|Der Parameter \_\_für\_ den Makrowert ist null|
|[C28279](../code-quality/c28279.md)|Für Symbol wurde ein 'begin' ohne zugehöriges 'end' gefunden.|
|[C28280](../code-quality/c28280.md)|Für Symbol wurde ein 'end' ohne zugehöriges 'begin' gefunden.|
|[C28282](../code-quality/c28282.md)|Formatzeichenfolgen müssen sich in Vorbedingungen befinden|
|[C28285](../code-quality/c28285.md)|Syntaxfehler im Parameter für Funktion|
|[C28286](../code-quality/c28286.md)|Für Funktion wurde ein Syntaxfehler gegen Ende gefunden.|
|[C28287](../code-quality/c28287.md)|Syntaxfehler in der Anmerkung \_At()\_ für die Funktion (unbekannter Parametername)|
|[C28288](../code-quality/c28288.md)|Syntaxfehler in der Anmerkung \_At()\_ für die Funktion (ungültiger Parametername)|
|[C28289](../code-quality/c28289.md)|Für Funktion: ReadableTo oder WritableTo enthielt keine Begrenzungsangabe als Parameter.|
|[C28290](../code-quality/c28290.md)|Die Anmerkung für Funktion enthält mehr Externe als die tatsächliche Anzahl von Parametern.|
|[C28291](../code-quality/c28291.md)|Post null/notnull auf deref-Ebene 0 ist ohne Bedeutung für Funktion.|
|[C28300](../code-quality/c28300.md)|Ausdrucksoperanden von inkompatiblen Typen für Operator|
|[C28301](../code-quality/c28301.md)|Keine Anmerkungen für die erste Deklaration der Funktion.|
|[C28302](../code-quality/c28302.md)|Ein zusätzlicher \_Deref\_-Operator wurde in der Anmerkung gefunden.|
|[C28303](../code-quality/c28303.md)|Ein mehrdeutiger \_Deref\_-Operator wurde in der Anmerkung gefunden.|
|[C28304](../code-quality/c28304.md)|Ein falsch platzierter \_Notref\_-Operator wurde gefunden, der auf das Token angewendet wird.|
|[C28305](../code-quality/c28305.md)|Fehler beim Analysieren eines Token.|
|[C28306](../code-quality/c28306.md)|Die Anmerkung zum Parameter ist obsolet|
|[C28307](../code-quality/c28307.md)|Die Anmerkung zum Parameter ist obsolet|
|[C28350](../code-quality/c28350.md)|Die Anmerkung beschreibt eine Situation, die nicht bedingt anwendbar ist.|
|[C28351](/cpp/code-quality/c28351)|Die Anmerkung beschreibt, wo ein dynamischer Wert (eine Variable) in der Bedingung nicht verwendet werden darf.|

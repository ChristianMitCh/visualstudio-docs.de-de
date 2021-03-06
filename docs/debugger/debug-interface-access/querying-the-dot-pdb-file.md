---
title: Abfragen von. PDB-Datei | Microsoft-Dokumentation
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- PDB files
- .pdb files, querying
ms.assetid: 8da07d1c-2712-45f9-8fbf-f34040408a8a
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: a22bc8fbe65795a3c5162607a12690081e565666
ms.sourcegitcommit: 939407118f978162a590379997cb33076c57a707
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/13/2020
ms.locfileid: "75917105"
---
# <a name="querying-the-pdb-file"></a>Abfragen der PDB-Datei
Bei einer Programm Datenbankdatei (Erweiterung. pdb) handelt es sich um eine Binärdatei, die Typen-und symbolische Debuginformationen enthält, die im Verlauf der Kompilierung und Verknüpfung des Projekts gesammelt werden. Eine PDB-Datei wird erstellt, wenn Sie ein CC++ /Programm mit **/Zi** oder **/Zi** oder einem [!INCLUDE[vbprvb](../../code-quality/includes/vbprvb_md.md)]-, [!INCLUDE[csprcs](../../data-tools/includes/csprcs_md.md)]-oder [!INCLUDE[jsprjscript](../../debugger/debug-interface-access/includes/jsprjscript_md.md)]-Programm mit der **/Debug** -Option kompilieren. Objektdateien enthalten Verweise auf die PDB-Datei zum Debuggen von Informationen. Weitere Informationen zu PDB-Dateien finden Sie unter [PDB-Dateien](/previous-versions/visualstudio/visual-studio-2010/yd4f8bd1(v=vs.100)). Eine Dia-Anwendung kann die folgenden allgemeinen Schritte zum Abrufen von Details über die verschiedenen Symbole, Objekte und Datenelemente innerhalb eines ausführbaren Images verwenden.

### <a name="to-query-the-pdb-file"></a>So Fragen Sie die PDB-Datei ab

1. Rufen Sie eine Datenquelle ab, indem Sie eine [IDiaDataSource](../../debugger/debug-interface-access/idiadatasource.md) -Schnittstelle erstellen.

    ```C++
    CComPtr<IDiaDataSource> pSource;
    hr = CoCreateInstance( CLSID_DiaSource,
                           NULL,
                           CLSCTX_INPROC_SERVER,
                           __uuidof( IDiaDataSource ),
                          (void **) &pSource);

    if (FAILED(hr))
    {
        Fatal("Could not CoCreate CLSID_DiaSource. Register msdia80.dll." );
    }
    ```

2. Nennen Sie [IDiaDataSource:: loadDataFromPdb](../../debugger/debug-interface-access/idiadatasource-loaddatafrompdb.md) oder [IDiaDataSource:: loadDataForExe](../../debugger/debug-interface-access/idiadatasource-loaddataforexe.md) , um die Debuginformationen zu laden.

    ```C++
    wchar_t wszFilename[ _MAX_PATH ];
    mbstowcs( wszFilename, szFilename, sizeof( wszFilename )/sizeof( wszFilename[0] ) );
    if ( FAILED( pSource->loadDataFromPdb( wszFilename ) ) )
    {
        if ( FAILED( pSource->loadDataForExe( wszFilename, NULL, NULL ) ) )
        {
            Fatal( "loadDataFromPdb/Exe" );
        }
    }
    ```

3. Aufrufen von [IDiaDataSource:: OpenSession](../../debugger/debug-interface-access/idiadatasource-opensession.md) zum Öffnen einer [IDiaSession](../../debugger/debug-interface-access/idiasession.md) , um Zugriff auf die Debuginformationen zu erhalten.

    ```C++
    CComPtr<IDiaSession> psession;
    if ( FAILED( pSource->openSession( &psession ) ) )
    {
        Fatal( "openSession" );
    }
    ```

4. Verwenden Sie die Methoden in `IDiaSession`, um die Symbole in der Datenquelle abzufragen.

    ```C++
    CComPtr<IDiaSymbol> pglobal;
    if ( FAILED( psession->get_globalScope( &pglobal) ) )
    {
        Fatal( "get_globalScope" );
    }
    ```

5. Verwenden Sie die `IDiaEnum*`-Schnittstellen, um die Symbole oder andere Elemente der Debuginformationen aufzulisten und zu durchsuchen.

    ```C++
    CComPtr<IDiaEnumTables> pTables;
    if ( FAILED( psession->getEnumTables( &pTables ) ) )
    {
        Fatal( "getEnumTables" );
    }
    CComPtr< IDiaTable > pTable;
    while ( SUCCEEDED( hr = pTables->Next( 1, &pTable, &celt ) ) && celt == 1 )
    {
        // Do something with each IDiaTable.
    }
    ```

## <a name="see-also"></a>Siehe auch
- [IDiaDataSource](../../debugger/debug-interface-access/idiadatasource.md)

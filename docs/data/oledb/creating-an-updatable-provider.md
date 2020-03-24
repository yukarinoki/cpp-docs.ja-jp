---
title: 更新可能なプロバイダーの作成
ms.date: 08/16/2018
helpviewer_keywords:
- OLE DB providers, updatable
- notifications, support in providers
- OLE DB providers, creating
ms.assetid: bdfd5c9f-1c6f-4098-822c-dd650e70ab82
ms.openlocfilehash: 2811cd56bdc87282b9d4395a9a79ba9b333dadee
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80211394"
---
# <a name="creating-an-updatable-provider"></a>更新可能なプロバイダーの作成

ビジュアルC++では、データストアを更新 (書き込み) できる更新可能なプロバイダーまたはプロバイダーがサポートされています。 このトピックでは、OLE DB テンプレートを使用して更新可能なプロバイダーを作成する方法について説明します。

このトピックでは、使用可能なプロバイダーから始めることを前提としています。 更新可能なプロバイダーを作成するには、2つの手順を実行します。 まず、プロバイダーがどのようにデータストアに変更を加えるかを決定する必要があります。具体的には、変更を直ちに実行するか、更新コマンドが発行されるまで延期するかを指定します。 「プロバイダーを[更新可能](#vchowmakingprovidersupdatable)にする」セクションでは、プロバイダーコードで実行する必要がある変更と設定について説明します。

次に、コンシューマーが要求するすべての機能をサポートするために、プロバイダーにすべての機能が含まれていることを確認する必要があります。 コンシューマーがデータストアを更新する場合は、データストアにデータを保持するコードがプロバイダーに含まれている必要があります。 たとえば、C ランタイムライブラリまたは MFC を使用して、データソースに対してこのような操作を実行することができます。 「[データソースへの書き込み](#vchowwritingtothedatasource)」では、データソースに書き込む方法、NULL 値と既定値を処理する方法、および列フラグを設定する方法について説明します。

> [!NOTE]
> [UpdatePV](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/ATL/OLEDB/Provider/UPDATEPV)は、更新可能なプロバイダーの例です。 UpdatePV は MyProv と同じですが、更新可能なサポートがあります。

##  <a name="making-providers-updatable"></a><a name="vchowmakingprovidersupdatable"></a>プロバイダーを更新可能にする

プロバイダーを更新可能にするための鍵は、プロバイダーがデータストアに対して実行する操作と、それらの操作をプロバイダーがどのように実行するかを理解することです。 具体的には、更新コマンドが発行されるまで、データストアの更新が直ちに行われるか、遅延 (バッチ処理) されるかという主な問題があります。

まず、行セットクラスで `IRowsetChangeImpl` または `IRowsetUpdateImpl` を継承するかどうかを決定する必要があります。 どちらを実装するかに応じて、`SetData`、`InsertRows`、および `DeleteRows`の3つの方法の機能が影響を受けます。

- [IRowsetChangeImpl](../../data/oledb/irowsetchangeimpl-class.md)から継承する場合、これら3つのメソッドを呼び出すと、すぐにデータストアが変更されます。

- [IRowsetUpdateImpl](../../data/oledb/irowsetupdateimpl-class.md)から継承する場合、メソッドは `Update`、`GetOriginalData`、または `Undo`を呼び出すまで、データストアへの変更を延期します。 更新プログラムに複数の変更が含まれる場合は、バッチモードで実行されます (変更をバッチ処理すると、大量のメモリオーバーヘッドが発生する可能性があることに注意してください)。

`IRowsetUpdateImpl` は `IRowsetChangeImpl`から派生することに注意してください。 したがって、`IRowsetUpdateImpl` によって、機能とバッチ機能を変更できます。

### <a name="to-support-updatability-in-your-provider"></a>プロバイダーの更新可能性をサポートするには

1. 行セットクラスで、`IRowsetChangeImpl` または `IRowsetUpdateImpl`から継承します。 これらのクラスは、データストアを変更するための適切なインターフェイスを提供します。

   **IRowsetChange の追加**

   次の形式を使用して、継承チェーンに `IRowsetChangeImpl` を追加します。

    ```cpp
    IRowsetChangeImpl< rowset-name, storage-name >
    ```

   また、行セットクラスの `BEGIN_COM_MAP` セクションに `COM_INTERFACE_ENTRY(IRowsetChange)` を追加します。

   **IRowsetUpdate の追加**

   次の形式を使用して、継承チェーンに `IRowsetUpdate` を追加します。

    ```cpp
    IRowsetUpdateImpl< rowset-name, storage>
    ```

   > [!NOTE]
   > 継承チェーンから `IRowsetChangeImpl` 行を削除する必要があります。 前に説明したディレクティブに対するこの例外には、`IRowsetChangeImpl`用のコードが含まれている必要があります。

1. COM マップ (`BEGIN_COM_MAP ... END_COM_MAP`) に次のコードを追加します。

   |  を実装する場合   |           COM マップに追加             |
   |---------------------|--------------------------------------|
   | `IRowsetChangeImpl` | `COM_INTERFACE_ENTRY(IRowsetChange)` |
   | `IRowsetUpdateImpl` | `COM_INTERFACE_ENTRY(IRowsetUpdate)` |

   | を実装する場合 | プロパティセットマップに追加 |
   |----------------------|-----------------------------|
   | `IRowsetChangeImpl` | `PROPERTY_INFO_ENTRY_VALUE(IRowsetChange, VARIANT_FALSE)` |
   | `IRowsetUpdateImpl` | `PROPERTY_INFO_ENTRY_VALUE(IRowsetUpdate, VARIANT_FALSE)` |

1. コマンドで、プロパティセットマップ (`BEGIN_PROPSET_MAP ... END_PROPSET_MAP`) に次のコードを追加します。

   |  を実装する場合   |                                             プロパティセットマップに追加                                              |
   |---------------------|------------------------------------------------------------------------------------------------------------------|
   | `IRowsetChangeImpl` |                            `PROPERTY_INFO_ENTRY_VALUE(IRowsetChange, VARIANT_FALSE)`                             |
   | `IRowsetUpdateImpl` | `PROPERTY_INFO_ENTRY_VALUE(IRowsetChange, VARIANT_FALSE)PROPERTY_INFO_ENTRY_VALUE(IRowsetUpdate, VARIANT_FALSE)` |

1. プロパティセットマップでは、以下の設定をすべて含める必要があります。

    ```cpp
    PROPERTY_INFO_ENTRY_VALUE(UPDATABILITY, DBPROPVAL_UP_CHANGE |
      DBPROPVAL_UP_INSERT | DBPROPVAL_UP_DELETE)
    PROPERTY_INFO_ENTRY_VALUE(CHANGEINSERTEDROWS, VARIANT_TRUE)
    PROPERTY_INFO_ENTRY_VALUE(IMMOBILEROWS, VARIANT_TRUE)

    PROPERTY_INFO_ENTRY_EX(OWNINSERT, VT_BOOL, DBPROPFLAGS_ROWSET |
      DBPROPFLAGS_READ, VARIANT_TRUE, 0)
    PROPERTY_INFO_ENTRY_EX(OWNUPDATEDELETE, VT_BOOL, DBPROPFLAGS_ROWSET |
      DBPROPFLAGS_READ, VARIANT_TRUE, 0)
    PROPERTY_INFO_ENTRY_EX(OTHERINSERT, VT_BOOL, DBPROPFLAGS_ROWSET |
      DBPROPFLAGS_READ, VARIANT_TRUE, 0)
    PROPERTY_INFO_ENTRY_EX(OTHERUPDATEDELETE, VT_BOOL, DBPROPFLAGS_ROWSET |
      DBPROPFLAGS_READ, VARIANT_TRUE, 0)
    PROPERTY_INFO_ENTRY_EX(REMOVEDELETED, VT_BOOL, DBPROPFLAGS_ROWSET |
      DBPROPFLAGS_READ, VARIANT_FALSE, 0)
    ```

   これらのマクロの呼び出しで使用されている値は、プロパティの Id と値について Atldb.h を調べることによって確認できます (Atldb.h がオンラインドキュメントとは異なる場合、Atldb.h はドキュメントに置き換えられます)。

   > [!NOTE]
   > OLE DB テンプレートでは、`VARIANT_FALSE` と `VARIANT_TRUE` の設定の多くが必要です。OLE DB の仕様では、読み取り/書き込みが可能であることが示されていますが、OLE DB テンプレートでサポートされる値は1つだけです。

   **IRowsetChangeImpl を実装する場合**

   `IRowsetChangeImpl`を実装する場合は、プロバイダーで次のプロパティを設定する必要があります。 これらのプロパティは、主に `ICommandProperties::SetProperties`を通じてインターフェイスを要求するために使用されます。

   - `DBPROP_IRowsetChange`: この設定を行うと、`DBPROP_IRowsetChange`が自動的に設定されます。

   - `DBPROP_UPDATABILITY`: `SetData`、`DeleteRows`、または `InsertRow``IRowsetChange`でサポートされているメソッドを指定するビットマスク。

   - `DBPROP_CHANGEINSERTEDROWS`: コンシューマーは、新しく挿入された行に対して `IRowsetChange::DeleteRows` または `SetData` を呼び出すことができます。

   - `DBPROP_IMMOBILEROWS`: 行セットは、挿入または更新された行の順序を変更しません。

   **IRowsetUpdateImpl を実装する場合**

   `IRowsetUpdateImpl`を実装する場合は、前に示した `IRowsetChangeImpl` のすべてのプロパティを設定するだけでなく、プロバイダーで次のプロパティを設定する必要があります。

   - [https://login.microsoftonline.com/consumers/](`DBPROP_IRowsetUpdate`)

   - `DBPROP_OWNINSERT`: READ_ONLY と VARIANT_TRUE である必要があります。

   - `DBPROP_OWNUPDATEDELETE`: READ_ONLY と VARIANT_TRUE である必要があります。

   - `DBPROP_OTHERINSERT`: READ_ONLY と VARIANT_TRUE である必要があります。

   - `DBPROP_OTHERUPDATEDELETE`: READ_ONLY と VARIANT_TRUE である必要があります。

   - `DBPROP_REMOVEDELETED`: READ_ONLY と VARIANT_TRUE である必要があります。

   - [https://login.microsoftonline.com/consumers/](`DBPROP_MAXPENDINGROWS`)

   > [!NOTE]
   > 通知をサポートしている場合は、他のいくつかのプロパティも必要になることがあります。この一覧については、`IRowsetNotifyCP` に関するセクションを参照してください。

##  <a name="writing-to-the-data-source"></a><a name="vchowwritingtothedatasource"></a>データソースへの書き込み

データソースから読み取るには、`Execute` 関数を呼び出します。 データソースに書き込むには、`FlushData` 関数を呼び出します。 (一般に、フラッシュとは、テーブルまたはインデックスに対して行った変更をディスクに保存することを意味します)。

```cpp
FlushData(HROW, HACCESSOR);
```

Row handle (HROW) 引数と accessor handle (HACCESSOR) 引数を使用すると、書き込むリージョンを指定できます。 通常は、一度に1つのデータフィールドを記述します。

`FlushData` メソッドは、データを最初に格納された形式で書き込みます。 この関数をオーバーライドしない場合、プロバイダーは正常に機能しますが、変更はデータストアにフラッシュされません。

### <a name="when-to-flush"></a>フラッシュするタイミング

データがデータストアに書き込まれる必要がある場合は、プロバイダーテンプレートによって FlushData が呼び出されます。これは通常、次の関数を呼び出した結果として発生します (常にではありません)。

- `IRowsetChange::DeleteRows`

- `IRowsetChange::SetData`

- `IRowsetChange::InsertRows` (行に挿入する新しいデータがある場合)

- `IRowsetUpdate::Update`

### <a name="how-it-works"></a>動作のしくみ

コンシューマーは、フラッシュ (更新など) を必要とする呼び出しを行い、この呼び出しがプロバイダーに渡されます。この呼び出しは、常に次のことを実行します。

- 状態の値がバインドされている場合は常に `SetDBStatus` を呼び出します。

- 列フラグをチェックします。

- `IsUpdateAllowed` を呼び出します。

これらの3つの手順は、セキュリティを提供するのに役立ちます。 次に、プロバイダーは `FlushData`を呼び出します。

### <a name="how-to-implement-flushdata"></a>FlushData を実装する方法

`FlushData`を実装するには、いくつかの問題を考慮する必要があります。

データストアが変更を処理できることを確認します。

NULL 値の処理。

### <a name="handling-default-values"></a>既定値の処理。

独自の `FlushData` メソッドを実装するには、次の手順を実行する必要があります。

- 行セットクラスにアクセスします。

- 行セットクラスで、次の宣言を記述します。

   ```cpp
   HRESULT FlushData(HROW, HACCESSOR)
   {
      // Insert your implementation here and return an HRESULT.
   }
   ```

- `FlushData`の実装を提供します。

`FlushData` の適切な実装では、実際に更新される行と列だけが格納されます。 HROW パラメーターと HACCESSOR パラメーターを使用して、最適化のために格納されている現在の行と列を特定できます。

通常、最大の課題は、独自のネイティブデータストアを使用することです。 可能であれば、次のことを試してください。

- データストアへの書き込み方法は、できるだけ単純なものにしておいてください。

- NULL 値を処理します (省略可能ですが、推奨)。

- 既定値を処理します (省略可能ですが、推奨)。

最善の方法は、NULL 値と既定値のデータストアに実際に指定された値を設定することです。 このデータを推定できる場合は、この方法をお勧めします。 それ以外の場合は、NULL 値と既定値を許可しないことをお勧めします。

次の例は、`UpdatePV` サンプルの `RUpdateRowset` クラスで `FlushData` を実装する方法を示しています (サンプルコードの「Rowset」を参照してください)。

```cpp
///////////////////////////////////////////////////////////////////////////
// class RUpdateRowset (in rowset.h)
...
HRESULT FlushData(HROW, HACCESSOR)
{
    ATLTRACE2(atlTraceDBProvider, 0, "RUpdateRowset::FlushData\n");

    USES_CONVERSION;
    enum {
        sizeOfString = 256,
        sizeOfFileName = MAX_PATH
    };
    FILE*    pFile = NULL;
    TCHAR    szString[sizeOfString];
    TCHAR    szFile[sizeOfFileName];
    errcode  err = 0;

    ObjectLock lock(this);

    // From a filename, passed in as a command text,
    // scan the file placing data in the data array.
    if (m_strCommandText == (BSTR)NULL)
    {
        ATLTRACE( "RRowsetUpdate::FlushData -- "
                  "No filename specified\n");
        return E_FAIL;
    }

    // Open the file
    _tcscpy_s(szFile, sizeOfFileName, OLE2T(m_strCommandText));
    if ((szFile[0] == _T('\0')) ||
        ((err = _tfopen_s(&pFile, &szFile[0], _T("w"))) != 0))
    {
        ATLTRACE("RUpdateRowset::FlushData -- Could not open file\n");
        return DB_E_NOTABLE;
    }

    // Iterate through the row data and store it.
    for (long l=0; l<m_rgRowData.GetSize(); l++)
    {
        CAgentMan am = m_rgRowData[l];

        _putw((int)am.dwFixed, pFile);

        if (_tcscmp(&am.szCommand[0], _T("")) != 0)
            _stprintf_s(&szString[0], _T("%s\n"), am.szCommand);
        else
            _stprintf_s(&szString[0], _T("%s\n"), _T("NULL"));
        _fputts(szString, pFile);

        if (_tcscmp(&am.szText[0], _T("")) != 0)
            _stprintf_s(&szString[0], _T("%s\n"), am.szText);
        else
            _stprintf_s(&szString[0], _T("%s\n"), _T("NULL"));
        _fputts(szString, pFile);

        if (_tcscmp(&am.szCommand2[0], _T("")) != 0)
            _stprintf_s(&szString[0], _T("%s\n"), am.szCommand2);
        else
            _stprintf_s(&szString[0], _T("%s\n"), _T("NULL"));
        _fputts(szString, pFile);

        if (_tcscmp(&am.szText2[0], _T("")) != 0)
            _stprintf_s(&szString[0], _T("%s\n"), am.szText2);
        else
            _stprintf_s(&szString[0], _T("%s\n"), _T("NULL"));
        _fputts(szString, pFile);
    }

    if (fflush(pFile) == EOF || fclose(pFile) == EOF)
    {
        ATLTRACE("RRowsetUpdate::FlushData -- "
                 "Couldn't flush or close file\n");
    }

    return S_OK;
}
```

### <a name="handling-changes"></a>変更の処理

プロバイダーが変更を処理できるようにするには、まず、データストア (テキストファイルやビデオファイルなど) に変更を加えるための機能があることを確認する必要があります。 そうでない場合は、プロバイダープロジェクトとは別にそのコードを作成する必要があります。

### <a name="handling-null-data"></a>NULL データの処理

エンドユーザーが NULL データを送信する可能性があります。 データソース内のフィールドに NULL 値を書き込むと、潜在的な問題が発生する可能性があります。 市区町村と郵便番号の値を受け入れる注文書作成アプリケーションを想像してください。この場合、いずれかまたは両方の値を受け入れることができますが、その場合は配信できないため、どちらも受け入れません。 そのため、アプリケーションにとって意味のあるフィールドで、NULL 値の特定の組み合わせを制限する必要があります。

プロバイダー開発者は、データの格納方法、データストアからデータを読み取る方法、およびユーザーに対してそのデータを指定する方法を検討する必要があります。 具体的には、データソース内の行セットデータのデータの状態を変更する方法を検討する必要があります (DataStatus = NULL など)。 コンシューマーが NULL 値を含むフィールドにアクセスしたときに返す値を決定します。

UpdatePV サンプルのコードを確認します。これは、プロバイダーが NULL データを処理する方法を示しています。 UpdatePV では、データストアに文字列 "NULL" を記述することによって、プロバイダーは NULL データを格納します。 データストアから NULL データを読み取ると、その文字列が認識され、バッファーが空になり、NULL 文字列が作成されます。 また、データ値が空の場合に DBSTATUS_S_ISNULL を返す `IRowsetImpl::GetDBStatus` のオーバーライドもあります。

### <a name="marking-nullable-columns"></a>Null 値を許容する列をマークする

スキーマ行セットも実装する場合は (`IDBSchemaRowsetImpl`を参照してください)、列が null 値を許容することを、DBSCHEMA_COLUMNS 行セット (通常は CxxxSchemaColSchemaRowset によってプロバイダーでマークされます) で指定する必要があります。

また、使用しているバージョンの `GetColumnInfo`の DBCOLUMNFLAGS_ISNULLABLE 値が、null 許容型のすべての列に含まれていることを指定する必要もあります。

OLE DB テンプレートの実装では、列を nullable としてマークできない場合、プロバイダーは値が含まれている必要があり、コンシューマーが null 値を送信することを許可しません。

次の例は、`CommonGetColInfo` 関数が CUpdateCommand に実装される方法を示しています (UpdatePV の「UpProvRS」を参照してください)。 列が null 値を許容する列に対してこの DBCOLUMNFLAGS_ISNULLABLE を持つことに注意してください。

```cpp
/////////////////////////////////////////////////////////////////////////////
// CUpdateCommand (in UpProvRS.cpp)

ATLCOLUMNINFO* CommonGetColInfo(IUnknown* pPropsUnk, ULONG* pcCols, bool bBookmark)
{
    static ATLCOLUMNINFO _rgColumns[6];
    ULONG ulCols = 0;

    if (bBookmark)
    {
        ADD_COLUMN_ENTRY_EX(ulCols, OLESTR("Bookmark"), 0,
                            sizeof(DWORD), DBTYPE_BYTES,
                            0, 0, GUID_NULL, CAgentMan, dwBookmark,
                            DBCOLUMNFLAGS_ISBOOKMARK)
        ulCols++;
    }

    // Next set the other columns up.
    // Add a fixed length entry for OLE DB conformance testing purposes
    ADD_COLUMN_ENTRY_EX(ulCols, OLESTR("Fixed"), 1, 4, DBTYPE_UI4,
                        10, 255, GUID_NULL, CAgentMan, dwFixed,
                        DBCOLUMNFLAGS_WRITE |
                        DBCOLUMNFLAGS_ISFIXEDLENGTH)
    ulCols++;

    ADD_COLUMN_ENTRY_EX(ulCols, OLESTR("Command"), 2, 16, DBTYPE_STR,
                        255, 255, GUID_NULL, CAgentMan, szCommand,
                        DBCOLUMNFLAGS_WRITE | DBCOLUMNFLAGS_ISNULLABLE)
    ulCols++;
    ADD_COLUMN_ENTRY_EX(ulCols, OLESTR("Text"), 3, 16, DBTYPE_STR,
                        255, 255, GUID_NULL, CAgentMan, szText,
                        DBCOLUMNFLAGS_WRITE | DBCOLUMNFLAGS_ISNULLABLE)
    ulCols++;

    ADD_COLUMN_ENTRY_EX(ulCols, OLESTR("Command2"), 4, 16, DBTYPE_STR,
                        255, 255, GUID_NULL, CAgentMan, szCommand2,
                        DBCOLUMNFLAGS_WRITE | DBCOLUMNFLAGS_ISNULLABLE)
    ulCols++;
    ADD_COLUMN_ENTRY_EX(ulCols, OLESTR("Text2"), 5, 16, DBTYPE_STR,
                        255, 255, GUID_NULL, CAgentMan, szText2,
                        DBCOLUMNFLAGS_WRITE | DBCOLUMNFLAGS_ISNULLABLE)
    ulCols++;

    if (pcCols != NULL)
    {
        *pcCols = ulCols;
    }

    return _rgColumns;
}
```

### <a name="default-values"></a>既定値

NULL データと同様に、既定値の変更に対処する必要があります。

既定では `FlushData` と `Execute` は S_OK を返します。 このため、この関数をオーバーライドしない場合、変更は正常に表示されます (S_OK が返されます) が、データストアには送信されません。

`UpdatePV` サンプル (Rowset) では、`SetDBStatus` メソッドは次のように既定値を処理します。

```cpp
virtual HRESULT SetDBStatus(DBSTATUS* pdbStatus, CSimpleRow* pRow,
                            ATLCOLUMNINFO* pColInfo)
{
    ATLASSERT(pRow != NULL && pColInfo != NULL && pdbStatus != NULL);

    void* pData = NULL;
    char* pDefaultData = NULL;
    DWORD* pFixedData = NULL;

    switch (*pdbStatus)
    {
        case DBSTATUS_S_DEFAULT:
            pData = (void*)&m_rgRowData[pRow->m_iRowset];
            if (pColInfo->wType == DBTYPE_STR)
            {
                pDefaultData = (char*)pData + pColInfo->cbOffset;
                strcpy_s(pDefaultData, "Default");
            }
            else
            {
                pFixedData = (DWORD*)((BYTE*)pData +
                                          pColInfo->cbOffset);
                *pFixedData = 0;
                return S_OK;
            }
            break;
        case DBSTATUS_S_ISNULL:
        default:
            break;
    }
    return S_OK;
}
```

### <a name="column-flags"></a>列フラグ

列の既定値をサポートする場合は、\<プロバイダークラス\>SchemaRowset クラスのメタデータを使用して設定する必要があります。 `m_bColumnHasDefault = VARIANT_TRUE` を設定します。

また、DBCOLUMNFLAGS 列挙型を使用して指定された列フラグを設定する必要があります。 列フラグは、列の特性を記述します。

たとえば、`UpdatePV` (セッション .h) の `CUpdateSessionColSchemaRowset` クラスでは、最初の列は次のように設定されます。

```cpp
// Set up column 1
trData[0].m_ulOrdinalPosition = 1;
trData[0].m_bIsNullable = VARIANT_FALSE;
trData[0].m_bColumnHasDefault = VARIANT_TRUE;
trData[0].m_nDataType = DBTYPE_UI4;
trData[0].m_nNumericPrecision = 10;
trData[0].m_ulColumnFlags = DBCOLUMNFLAGS_WRITE |
                            DBCOLUMNFLAGS_ISFIXEDLENGTH;
lstrcpyW(trData[0].m_szColumnDefault, OLESTR("0"));
m_rgRowData.Add(trData[0]);
```

このコードでは、特に、列が既定値の0をサポートし、書き込み可能であること、および列内のすべてのデータの長さが同じであることを指定します。 列のデータの長さを可変にする場合は、このフラグを設定しません。

## <a name="see-also"></a>参照

[OLE DB プロバイダーの作成](creating-an-ole-db-provider.md)

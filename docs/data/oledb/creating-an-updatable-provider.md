---
title: 更新可能なプロバイダーの作成
ms.date: 08/16/2018
helpviewer_keywords:
- OLE DB providers, updatable
- notifications, support in providers
- OLE DB providers, creating
ms.assetid: bdfd5c9f-1c6f-4098-822c-dd650e70ab82
ms.openlocfilehash: 720ceba397d17642402de4d44cbb4481852fa153
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81365560"
---
# <a name="creating-an-updatable-provider"></a>更新可能なプロバイダーの作成

Visual C++ では、更新可能なプロバイダまたはデータ ストアの更新 (書き込み) を行うことができるプロバイダがサポートされています。 このトピックでは、OLE DB テンプレートを使用して更新可能なプロバイダーを作成する方法について説明します。

このトピックでは、作業可能なプロバイダーから開始することを前提としています。 更新可能なプロバイダーを作成するには、2 つの手順があります。 まず、プロバイダがデータ ストアに変更を加える方法を決定する必要があります。具体的には、変更を即時に実行するか、更新コマンドが発行されるまで延期するか。 「[プロバイダを更新可能にする](#vchowmakingprovidersupdatable)」では、プロバイダ コードで行う必要がある変更と設定について説明します。

次に、コンシューマーが要求する可能性のあるすべてをサポートする機能がすべてプロバイダーに含まれていることを確認する必要があります。 コンシューマーがデータ ストアを更新する場合、プロバイダーにはデータ ストアにデータを永続化するコードが含まれている必要があります。 たとえば、C ランタイム ライブラリまたは MFC を使用して、データ ソースに対してこのような操作を実行できます。 「データ[ソースへの書き込み](#vchowwritingtothedatasource)」では、データ ソースへの書き込み方法、NULL 値と既定値の処理、および列フラグの設定について説明します。

> [!NOTE]
> [UpdatePV](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/ATL/OLEDB/Provider/UPDATEPV)は、更新可能なプロバイダの例です。 アップデートPVはMyProvと同じですが、更新可能なサポートを備えています。

## <a name="making-providers-updatable"></a><a name="vchowmakingprovidersupdatable"></a>プロバイダを更新可能にする

プロバイダを更新可能にする鍵は、データ ストアでプロバイダが実行する操作と、プロバイダがそれらの操作をどのように実行するかを理解することです。 具体的には、データ ストアの更新を即時に実行するか、更新コマンドが発行されるまで遅延 (バッチ処理) するかが主な問題です。

最初に、行セット クラスから`IRowsetChangeImpl`継承`IRowsetUpdateImpl`するか、行セット クラスで継承するかを決定する必要があります。 実装する方法に応じて、 `SetData`、 、`InsertRows`および`DeleteRows`3 つのメソッドの機能が影響を受けます。

- [IRowsetChangeImpl](../../data/oledb/irowsetchangeimpl-class.md)から継承する場合は、これら 3 つのメソッドを呼び出すと、すぐにデータ ストアが変更されます。

- から継承する場合[は](../../data/oledb/irowsetupdateimpl-class.md)、 `Update` `GetOriginalData`、または`Undo`を呼び出すまで、メソッドはデータ ストアへの変更を延期します。 更新に複数の変更が含まれる場合、それらはバッチ モードで実行されます (バッチ処理の変更により、かなりのメモリ オーバーヘッドが発生する可能性があることに注意してください)。

から`IRowsetChangeImpl`派生`IRowsetUpdateImpl`していることに注意してください。 したがって、`IRowsetUpdateImpl`変更機能とバッチ機能が提供されます。

### <a name="to-support-updatability-in-your-provider"></a>プロバイダでの更新可能性をサポートするには

1. 行セット クラスで、 または`IRowsetChangeImpl``IRowsetUpdateImpl`から継承します。 これらのクラスは、データ ストアを変更するための適切なインターフェイスを提供します。

   **IRowset の追加変更**

   次`IRowsetChangeImpl`の形式を使用して継承チェーンに追加します。

    ```cpp
    IRowsetChangeImpl< rowset-name, storage-name >
    ```

   また、`COM_INTERFACE_ENTRY(IRowsetChange)`行セット`BEGIN_COM_MAP`クラスのセクションに追加します。

   **IRowset 更新の追加**

   次`IRowsetUpdate`の形式を使用して継承チェーンに追加します。

    ```cpp
    IRowsetUpdateImpl< rowset-name, storage>
    ```

   > [!NOTE]
   > 継承チェーンから行`IRowsetChangeImpl`を削除する必要があります。 前述のディレクティブに対するこの 1 つの例外には`IRowsetChangeImpl`、 のコードが含まれている必要があります。

1. COM マップに次の情報を`BEGIN_COM_MAP ... END_COM_MAP`追加します ( ):

   |  実装する場合   |           COM マップに追加             |
   |---------------------|--------------------------------------|
   | `IRowsetChangeImpl` | `COM_INTERFACE_ENTRY(IRowsetChange)` |
   | `IRowsetUpdateImpl` | `COM_INTERFACE_ENTRY(IRowsetUpdate)` |

   | 実装する場合 | プロパティ セット マップに追加 |
   |----------------------|-----------------------------|
   | `IRowsetChangeImpl` | `PROPERTY_INFO_ENTRY_VALUE(IRowsetChange, VARIANT_FALSE)` |
   | `IRowsetUpdateImpl` | `PROPERTY_INFO_ENTRY_VALUE(IRowsetUpdate, VARIANT_FALSE)` |

1. コマンドで、プロパティ セット マップに次の項目を`BEGIN_PROPSET_MAP ... END_PROPSET_MAP`追加します (

   |  実装する場合   |                                             プロパティ セット マップに追加                                              |
   |---------------------|------------------------------------------------------------------------------------------------------------------|
   | `IRowsetChangeImpl` |                            `PROPERTY_INFO_ENTRY_VALUE(IRowsetChange, VARIANT_FALSE)`                             |
   | `IRowsetUpdateImpl` | `PROPERTY_INFO_ENTRY_VALUE(IRowsetChange, VARIANT_FALSE)PROPERTY_INFO_ENTRY_VALUE(IRowsetUpdate, VARIANT_FALSE)` |

1. プロパティ セット マップには、以下の設定もすべて含める必要があります。

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

   これらのマクロ呼び出しで使用される値を見つけるには、Atldb.h でプロパティ ID と値を調べてください (Atldb.h がオンライン ドキュメントと異なる場合、Atldb.h はドキュメントに優先します)。

   > [!NOTE]
   > および`VARIANT_TRUE`設定`VARIANT_FALSE`の多くは OLE DB テンプレートで必要です。OLE DB 仕様では、読み取り/書き込みが可能であると書かれていますが、OLE DB テンプレートでは 1 つの値しかサポートできません。

   **IRowsetChangeImpl を実装する場合**

   を実装`IRowsetChangeImpl`する場合は、プロバイダで次のプロパティを設定する必要があります。 これらのプロパティは、主に を介して`ICommandProperties::SetProperties`インターフェイスを要求するために使用されます。

   - `DBPROP_IRowsetChange`: この設定は`DBPROP_IRowsetChange`自動的に設定されます。

   - `DBPROP_UPDATABILITY``IRowsetChange`: サポートされているメソッド`SetData``DeleteRows`を指定するビットマスク。 `InsertRow`

   - `DBPROP_CHANGEINSERTEDROWS`: コンシューマは`IRowsetChange::DeleteRows`、`SetData`新しく挿入された行を呼び出したり、新しく挿入することができます。

   - `DBPROP_IMMOBILEROWS`: 行セットは、挿入または更新された行の順序を変更しません。

   **を実装する場合は、更新を実装します。**

   を実装`IRowsetUpdateImpl`する場合は、前述のプロパティをすべて設定するだけでなく、プロバイダに次のプロパティを設定する`IRowsetChangeImpl`必要があります。

   - `DBPROP_IRowsetUpdate`.

   - `DBPROP_OWNINSERT`: READ_ONLYとVARIANT_TRUEでなければなりません。

   - `DBPROP_OWNUPDATEDELETE`: READ_ONLYとVARIANT_TRUEでなければなりません。

   - `DBPROP_OTHERINSERT`: READ_ONLYとVARIANT_TRUEでなければなりません。

   - `DBPROP_OTHERUPDATEDELETE`: READ_ONLYとVARIANT_TRUEでなければなりません。

   - `DBPROP_REMOVEDELETED`: READ_ONLYとVARIANT_TRUEでなければなりません。

   - `DBPROP_MAXPENDINGROWS`.

   > [!NOTE]
   > 通知をサポートしている場合は、他のプロパティもいくつかある場合があります。このリストについては、`IRowsetNotifyCP`上のセクションを参照してください。

## <a name="writing-to-the-data-source"></a><a name="vchowwritingtothedatasource"></a>データ ソースへの書き込み

データ ソースから読み取る場合`Execute`は、関数を呼び出します。 データ ソースに書き込むには`FlushData`、関数を呼び出します。 (一般的に、フラッシュとは、テーブルまたはインデックスに加えた変更をディスクに保存することを意味します。

```cpp
FlushData(HROW, HACCESSOR);
```

行ハンドル (HROW) とアクセサー ハンドル (HACCESSOR) 引数を使用すると、書き込む領域を指定できます。 通常、一度に 1 つのデータ フィールドを記述します。

この`FlushData`メソッドは、データを元の格納形式で書き込みます。 この関数をオーバーライドしない場合、プロバイダーは正しく機能しますが、変更はデータ ストアにフラッシュされません。

### <a name="when-to-flush"></a>フラッシュするタイミング

プロバイダ テンプレートは、データをデータ ストアに書き込む必要がある場合は常に FlushData を呼び出します。通常、これは次の関数の呼び出しの結果として発生します (ただし、必ずしもそうではありません)。

- `IRowsetChange::DeleteRows`

- `IRowsetChange::SetData`

- `IRowsetChange::InsertRows`(行に挿入する新しいデータがある場合)

- `IRowsetUpdate::Update`

### <a name="how-it-works"></a>動作のしくみ

コンシューマはフラッシュ (Update など) を必要とする呼び出しを行い、この呼び出しは常に次の処理を行うプロバイダーに渡されます。

- ステータス`SetDBStatus`値がバインドされている場合は常に呼び出されます。

- 列フラグをチェックします。

- `IsUpdateAllowed` を呼び出します。

この 3 つの手順は、セキュリティを提供するのに役立ちます。 その後、プロバイダ`FlushData`は を呼び出します。

### <a name="how-to-implement-flushdata"></a>フラッシュデータを実装する方法

を実装`FlushData`するには、次のようないくつかの問題を考慮する必要があります。

データ ストアが変更を処理できることを確認する。

NULL 値の処理。

### <a name="handling-default-values"></a>既定値の処理。

独自の`FlushData`メソッドを実装するには、次の作業が必要です。

- 行セット クラスに移動します。

- 行セット クラスでは、次の宣言を行います。

   ```cpp
   HRESULT FlushData(HROW, HACCESSOR)
   {
      // Insert your implementation here and return an HRESULT.
   }
   ```

- の実装を`FlushData`提供します。

優れた実装では`FlushData`、実際に更新された行と列だけが格納されます。 HROW パラメーターと HACCESSOR パラメーターを使用して、最適化のために保管されている現在の行と列を判別できます。

一般的に、最大の課題は、独自のネイティブ データ ストアを使用することです。 可能であれば、次の手順を試してください。

- データ ストアへの書き込み方法は、できるだけ単純にしてください。

- NULL 値を処理します (省略可能ですが、推奨)。

- 既定値を処理します (省略可能ですが、推奨)。

最善の方法は、NULL 値と既定値のデータ ストアに実際に指定された値を持つ方法です。 このデータを推定できる場合に最適です。 指定されていない場合は、NULL 値とデフォルト値を許可しないことをお勧めします。

次の例は、`FlushData`サンプルの`RUpdateRowset`クラスで実装する方法を`UpdatePV`示しています (サンプル コードの Rowset.h を参照してください)。

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

プロバイダーが変更を処理するには、まず、データ ストア (テキスト ファイルやビデオ ファイルなど) に変更を加える機能があることを確認する必要があります。 存在しない場合は、プロバイダー プロジェクトとは別にコードを作成する必要があります。

### <a name="handling-null-data"></a>NULL データの処理

エンド ユーザーが NULL データを送信する可能性があります。 データ ソースのフィールドに NULL 値を書き込む場合、潜在的な問題が発生する可能性があります。 都市と郵便番号の値を受け入れる注文を取るアプリケーションを想像してみてください。この場合は配信が不可能になるため、どちらか一方または両方の値を受け入れることができても、どちらも受け入れられません。 したがって、アプリケーションにとって意味のあるフィールドでは、NULL 値の特定の組み合わせを制限する必要があります。

プロバイダー開発者は、データの格納方法、データ ストアからデータを読み取る方法、およびユーザーに対するデータの指定方法を検討する必要があります。 具体的には、データ ソース内の行セット データのデータ状態を変更する方法を検討する必要があります (たとえば、DataStatus = NULL)。 コンシューマが NULL 値を含むフィールドにアクセスしたときに返す値を決定します。

UpdatePV サンプルのコードを見てください。この図は、プロバイダーが NULL データを処理する方法を示しています。 UpdatePV では、プロバイダーは、データ ストアに文字列 "NULL" を書き込み、NULL データを格納します。 データ ストアから NULL データを読み取ると、その文字列を見て、バッファを空にして、NULL 文字列を作成します。 また、データ値が空`IRowsetImpl::GetDBStatus`の場合にDBSTATUS_S_ISNULLを返すオーバーライドも持ちます。

### <a name="marking-nullable-columns"></a>Null 許容列のマーキング

スキーマ行セットも実装する場合 (`IDBSchemaRowsetImpl`を参照)、実装では、DBSCHEMA_COLUMNS行セット (通常はプロバイダーで CxxxSchemaColSchemaRowset によってマークされます) で、列が null 許容であることを指定する必要があります。

また、すべての null 許容列に、使用しているバージョンの DBCOLUMNFLAGS_ISNULLABLE 値が`GetColumnInfo`含まれるように指定する必要もあります。

OLE DB テンプレートの実装では、列を null 許容としてマークしなかった場合、プロバイダーは値を含む必要があり、コンシューマーが NULL 値を送信することを許可しないと見なします。

次の例は、関数`CommonGetColInfo`が UpdatePV で CUpdate コマンド (UpProvRS.cpp を参照) でどのように実装されているかを示しています。 null 許容列に対して、列にこのDBCOLUMNFLAGS_ISNULLABLEが含まれる点に注意してください。

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

NULL データと同様に、既定値の変更に対処する責任があります。

の既定値`FlushData`は、S_OK`Execute`返します。 したがって、この関数をオーバーライドしないと、変更は成功したように見えますが (S_OK返されます)、データ ストアには送信されません。

`UpdatePV`サンプル (Rowset.h) では、`SetDBStatus`メソッドは次のように既定値を処理します。

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

列の既定値をサポートする場合は、プロバイダー クラス SchemaRowset クラス\<\>のメタデータを使用して設定する必要があります。 `m_bColumnHasDefault = VARIANT_TRUE` を設定します。

また、列フラグを設定する必要があります。 列フラグは列の特性を記述します。

たとえば、`CUpdateSessionColSchemaRowset``UpdatePV`クラス (Session.h) では、最初の列は次の方法で設定されます。

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

このコードは、特に、列が既定値 0 をサポートしていること、書き込み可能な値、および列のすべてのデータの長さが同じであることを指定します。 列のデータに可変長を設定する場合は、このフラグを設定しません。

## <a name="see-also"></a>関連項目

[OLE DB プロバイダの作成](creating-an-ole-db-provider.md)

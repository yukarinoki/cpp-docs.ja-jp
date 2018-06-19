---
title: 更新可能なプロバイダーの作成 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- OLE DB providers, updatable
- notifications, support in providers
- OLE DB providers, creating
ms.assetid: bdfd5c9f-1c6f-4098-822c-dd650e70ab82
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 317ccd043b3a69489f9cbd2737ad7741389863c5
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33098642"
---
# <a name="creating-an-updatable-provider"></a>更新可能なプロバイダーの作成
Visual C には、更新可能なプロバイダーまたは更新できるプロバイダーがサポートしています (書き込む) データ ストアです。 このトピックでは、OLE DB テンプレートを使用して、更新可能なプロバイダーを作成する方法について説明します。  
  
 このトピックでは、実行可能なプロバイダーを起動することを前提としています。 更新可能なプロバイダーを作成する 2 つの手順があります。 プロバイダーが、データ ストアに変更を加える方法を決定する必要がありますまず具体的には、かどうかの変更がすぐに実行するまたは更新コマンドが実行されるまで延期します。 セクション"[プロバイダーを更新可能にする](#vchowmakingprovidersupdatable)"の変更と、プロバイダー コードで行う必要がある設定について説明します。  
  
 次に、プロバイダーには、コンシューマーの要求をサポートするためのすべての機能が含まれています。 確認する必要があります。 コンシューマーは、データ ストアを更新する場合、プロバイダーが、データ ストアにデータが引き続き発生するコードが含まれます。 たとえば、データ ソースにこのような操作を実行するのに、C ランタイム ライブラリまたは MFC を使用する可能性があります。 セクション"[データ ソースへの書き込み](#vchowwritingtothedatasource)"データ ソースへの書き込み、対処する方法について説明**NULL**と既定値、および列のフラグを設定します。  
  
> [!NOTE]
>  UpdatePV では、更新可能なプロバイダーの例を示します。 UpdatePV は、MyProv としては更新可能なサポートと同じです。  
  
##  <a name="vchowmakingprovidersupdatable"></a> 更新可能なプロバイダーを作成  
 更新可能なプロバイダーを行うには、データ ストアや、プロバイダーをそれらの操作を実行する方法を実行するプロバイダーを作成するどのような操作を把握できます。 具体的には、主要な問題は、データ ストアへの更新がすぐに実行されたり、遅延がかどうか (バッチ)、update コマンドが発行されるまでです。  
  
 継承するかどうかを決定する必要がありますまず`IRowsetChangeImpl`または`IRowsetUpdateImpl`行セット クラスです。 3 つのメソッドの機能の影響を実装するために選択次のうち、に応じて: `SetData`、 **InsertRows**、および`DeleteRows`です。  
  
-   継承する場合[IRowsetChangeImpl](../../data/oledb/irowsetchangeimpl-class.md)、すぐにこれら 3 つのメソッドを呼び出すデータ ストアを変更します。  
  
-   継承する場合[IRowsetUpdateImpl](../../data/oledb/irowsetupdateimpl-class.md)、メソッドが呼び出されるまで、データ ストアへの変更を延期**更新**、 `GetOriginalData`、または**を元に戻す**です。 更新プログラムには、いくつかの変更が含まれている場合は、バッチ モード (変更のバッチ処理で大量のメモリ オーバーヘッドを追加することに注意してください) で実行されます。  
  
 なお`IRowsetUpdateImpl`から派生した`IRowsetChangeImpl`です。 したがって、`IRowsetUpdateImpl`機能とバッチ機能を変更できます。  
  
#### <a name="to-support-updatability-in-your-provider"></a>プロバイダーで更新をサポートするために  
  
1.  継承するクラスでは行セット、`IRowsetChangeImpl`または`IRowsetUpdateImpl`です。 これらのクラスは、データ ストアを変更するための適切なインターフェイスを提供します。  
  
     **IRowsetChange を追加します。**  
  
     追加`IRowsetChangeImpl`このフォームを使用して、継承チェーンを。  
  
    ```  
    IRowsetChangeImpl< rowset-name, storage-name >  
    ```  
  
     追加も`COM_INTERFACE_ENTRY(IRowsetChange)`を`BEGIN_COM_MAP`行セット クラスのセクションでします。  
  
     **IRowsetUpdate を追加します。**  
  
     追加`IRowsetUpdate`このフォームを使用して、継承チェーンを。  
  
    ```  
    IRowsetUpdateImpl< rowset-name, storage>  
    ```  
  
    > [!NOTE]
    >  削除する必要があります、`IRowsetChangeImpl`継承チェーンからの行。 ディレクティブの前に説明したこの例外が 1 つのコードを含める必要があります`IRowsetChangeImpl`です。  
  
2.  次のコードを COM マップに追加 (**BEGIN_COM_MAP.END_COM_MAP**):  
  
    |実装する場合|COM マップに追加します。|  
    |----------------------|--------------------|  
    |`IRowsetChangeImpl`|`COM_INTERFACE_ENTRY(IRowsetChange)`|  
    |`IRowsetUpdateImpl`|`COM_INTERFACE_ENTRY(IRowsetChange)COM_INTERFACE_ENTRY(IRowsetUpdate)`|  
  
3.  ように、次のコードをプロパティ セットのマップに追加 (**BEGIN_PROPSET_MAP.END_PROPSET_MAP**):  
  
    |実装する場合|プロパティ セットのマップに追加します。|  
    |----------------------|-----------------------------|  
    |`IRowsetChangeImpl`|`PROPERTY_INFO_ENTRY_VALUE(IRowsetChange, VARIANT_FALSE)`|  
    |`IRowsetUpdateImpl`|`PROPERTY_INFO_ENTRY_VALUE(IRowsetChange, VARIANT_FALSE)PROPERTY_INFO_ENTRY_VALUE(IRowsetUpdate, VARIANT_FALSE)`|  
  
4.  マップでは、プロパティ セット、する必要がありますすべて、次の設定の下に表示されます。  
  
    ```  
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
  
     プロパティの Id と値の Atldb.h で検索してこれらのマクロの呼び出しで使用する値を見つけることができます (Atldb.h と異なる場合、オンライン ドキュメント、Atldb.h 置き換えるソフトウェア更新プログラムのドキュメント)。  
  
    > [!NOTE]
    >  多くは、 **VARIANT_FALSE**と`VARIANT_TRUE`設定は、OLE DB テンプレートで必要です。 OLE DB 仕様では読み取り/書き込み、可能性があるが、OLE DB テンプレートは 1 つの値のみをサポートします。  
  
     **IRowsetChangeImpl を実装する場合**  
  
     実装する場合`IRowsetChangeImpl`プロバイダーに、次のプロパティを設定する必要があります。 これらのプロパティは、主にを介してインターフェイスを要求する使用**icommandproperties::setproperties**です。  
  
    -   `DBPROP_IRowsetChange`: この自動的にセットを設定する**DBPROP_IRowsetChange**です。  
  
    -   `DBPROP_UPDATABILITY`: でサポートされているメソッドを指定するビットマスク`IRowsetChange`: `SetData`、 `DeleteRows`、または`InsertRow`です。  
  
    -   `DBPROP_CHANGEINSERTEDROWS`: コンシューマーが呼び出すことができます**irowsetchange::deleterows**または`SetData`新しく挿入された行にします。  
  
    -   `DBPROP_IMMOBILEROWS`: 行セットは、挿入または更新された行を並べ替えられません。  
  
     **IRowsetUpdateImpl を実装する場合**  
  
     実装する場合`IRowsetUpdateImpl`、する必要があります、次プロパティを設定して、プロバイダーでは、さらのすべてのプロパティを設定する`IRowsetChangeImpl`前に示した。  
  
    -   `DBPROP_IRowsetUpdate`。  
  
    -   `DBPROP_OWNINSERT`: READ_ONLY と VARIANT_TRUE をある必要があります。  
  
    -   `DBPROP_OWNUPDATEDELETE`: READ_ONLY と VARIANT_TRUE をある必要があります。  
  
    -   `DBPROP_OTHERINSERT`: READ_ONLY と VARIANT_TRUE をある必要があります。  
  
    -   `DBPROP_OTHERUPDATEDELETE`: READ_ONLY と VARIANT_TRUE をある必要があります。  
  
    -   `DBPROP_REMOVEDELETED`: READ_ONLY と VARIANT_TRUE をある必要があります。  
  
    -   `DBPROP_MAXPENDINGROWS`。  
  
        > [!NOTE]
        >  通知をサポートする場合もあります他のプロパティもです。セクションを参照`IRowsetNotifyCP`この一覧にします。  
  
     たとえば、プロパティの設定方法のプロパティ内のマップの設定を参照してください**CUpdateCommand**は) の「で[UpdatePV](http://msdn.microsoft.com/en-us/c8bed873-223c-4a7d-af55-f90138c6f38f)です。  
  
##  <a name="vchowwritingtothedatasource"></a> データ ソースへの書き込み  
 データ ソースからの読み取りを呼び出して、 **Execute**関数。 データ ソースへの書き込みを呼び出して、`FlushData`関数。 (一般的な意味では、テーブルまたはインデックスをディスクに加えた変更を保存するための手段をフラッシュします)。  
  
```  
FlushData(HROW, HACCESSOR);  
```  
  
 行ハンドル (*HROW*) とアクセサー ハンドル (*HACCESSOR*) 引数により関数を記述する領域を指定できます。 通常は、一度に 1 つのデータ フィールドを作成します。  
  
 `FlushData`メソッドは、最初に格納された形式でデータを書き込みます。 この関数をオーバーライドしていない場合、プロバイダーが正常に機能が、変更はデータ ストアにフラッシュされません。  
  
### <a name="when-to-flush"></a>フラッシュします。  
 プロバイダー テンプレート呼び出し`FlushData`データをデータ ストアに書き込まれる必要があるたびにです。 この通常 (必ずではありませんが)、次の関数を呼び出した結果として発生します。  
  
-   **IRowsetChange::DeleteRows**  
  
-   **IRowsetChange::SetData**  
  
-   **IRowsetChange::InsertRows** (かどうかがある行を挿入する新しいデータ)  
  
-   **IRowsetUpdate::Update**  
  
### <a name="how-it-works"></a>しくみ  
 コンシューマーが、フラッシュが必要な呼び出し (など**更新**) この呼び出しは、プロバイダーは、常に、次の処理に渡されます。  
  
-   呼び出し`SetDBStatus`バインド状態値があるときに (を参照してください*OLE DB プログラマーズ リファレンス*、第 6 章*データ部分: ステータス*)。  
  
-   列のフラグを確認します。  
  
-   `IsUpdateAllowed`.  
  
 これら 3 つの手順は、セキュリティを実現に役立ちます。 プロバイダーの呼び出し、`FlushData`です。  
  
### <a name="how-to-implement-flushdata"></a>FlushData を実装する方法  
 実装する`FlushData`、いくつかの問題を考慮する必要があります。  
  
-   データ ストアが変更を処理できるようにします。  
  
-   処理**NULL**値。  
  
-   既定値を処理します。  
  
 独自に実装する`FlushData`メソッド、する必要があります。  
  
-   行セット クラスに移動します。  
  
-   行セットでは、クラスは、宣言を挿入しました。  
  
```  
HRESULT FlushData(HROW, HACCESSOR)  
{  
    // Insert your implementation here and return an HRESULT.  
}  
```  
  
-   実装を提供`FlushData`です。  
  
 適切に実装した`FlushData`行と実際に更新される列だけを格納します。 使用することができます、 *HROW*と*HACCESSOR*パラメーターは、現在の行および最適化するために格納されている列を指定します。  
  
 通常、独自のネイティブ データ ストアは、最大の課題が処理されます。 可能であればを試してください。  
  
-   できるだけ単純なデータ ストアへの書き込みメソッドを保持します。  
  
-   処理**NULL** values (推奨ですが省略可能)。  
  
-   既定値 (推奨ですが省略可能) を処理します。  
  
 最良の点を行うには、データ ストア内の実際の指定した値を持つこと、 **NULL**と既定値です。 このデータを推測することができますを用意することをお勧めします。 場合は、することをお勧めできないように**NULL**と既定値です。  
  
 例を次にどのように`FlushData`で実装されて、`RUpdateRowset`クラス内で、 [UpdatePV](http://msdn.microsoft.com/en-us/c8bed873-223c-4a7d-af55-f90138c6f38f)サンプル (サンプル コードでを参照してください)。  
  
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
 変更を処理する、プロバイダーでは、最初 (テキスト ファイルまたはビデオ ファイル) など、データ ストアを変更することで有効にする機能を確認する必要があります。 そうでない場合は、プロバイダーのプロジェクトからそのコードを個別に作成してください。  
  
### <a name="handling-null-data"></a>NULL データの処理  
 エンドユーザーから送信されることは**NULL**データ。 作成時に、 **NULL**値フィールド、データ ソースに、潜在的なは問題があります。 市区町村、郵便番号コードの値を指定する順序をアプリケーションを想像してください。場合配信できないはために、いずれかまたは両方の値がどちらもありませんを受け付けることでした。 そのための特定の組み合わせを制限する必要がある**NULL**のアプリケーションの意味のあるフィールドの値。  
  
 プロバイダー開発者は、そのデータを格納する方法、データ ストアからのデータの読み取り方法、およびユーザーへの指定方法を検討する必要があります。 具体的には、データ ソース内の行セット データのデータの状態を変更する方法を検討する必要があります (たとえば、DataStatus = **NULL**)。 コンシューマーを含むフィールドにアクセスするときに返す値を決定する、 **NULL**値。  
  
 内のコードを見て、 [UpdatePV](http://msdn.microsoft.com/en-us/c8bed873-223c-4a7d-af55-f90138c6f38f)サンプル; プロバイダーを処理できる方法が示されている**NULL**データ。 プロバイダーを格納、UpdatePV で**NULL**データ ストアで、文字列"NULL"を記述してデータ。 読み取られる**NULL**データからデータを格納、その文字列を認識し、空にはバッファーを作成する、 **NULL**文字列。 さらのオーバーライド`IRowsetImpl::GetDBStatus`で返されます**DBSTATUS_S_ISNULL**そのデータ値が空の場合。  
  
### <a name="marking-nullable-columns"></a>Null 許容の列をマークします。  
 スキーマ行セットにも実装する場合 (を参照してください`IDBSchemaRowsetImpl`) での実装を指定する必要があります、 **DBSCHEMA_COLUMNS**行セット (通常を使用して、プロバイダーに設定されている**C***xxx***SchemaColSchemaRowset**) 列が null 許容であります。  
  
 Null 許容のすべての列が含まれているを指定する必要があります、 **DBCOLUMNFLAGS_ISNULLABLE**のバージョンの値、`GetColumnInfo`です。  
  
 実装では、OLE DB テンプレート、null 値許容と列を示すために失敗した場合、プロバイダーが値を含める必要があり、null 値を送信するコンシューマーは許可しません。  
  
 例を次にどのように**CommonGetColInfo**関数を実装**CUpdateCommand** (UpProvRS.cpp を参照してください) UpdatePV にします。 列であるこの方法に注意してください**DBCOLUMNFLAGS_ISNULLABLE**列の null 値を許容します。  
  
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
 同様に**NULL**データ、既定値の変更に対処する責任があります。  
  
 既定値は`FlushData`と**Execute**を返す`S_OK`です。 そのため、この関数をオーバーライドしていない場合、変更を成功させるのに表示されます (`S_OK`が返されます)、データ ストアに転送されませんが、します。  
  
 [UpdatePV](http://msdn.microsoft.com/en-us/c8bed873-223c-4a7d-af55-f90138c6f38f)では、サンプル、`SetDBStatus`メソッドは、既定値を次のように処理します。  
  
```  
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
  
### <a name="column-flags"></a>列のフラグ  
 内のメタデータを使用して設定する必要があります、列の既定値をサポートする場合、  **\<***プロバイダー クラス***> SchemaRowset**クラスです。 設定*m_bColumnHasDefault* = `VARIANT_TRUE`です。  
  
 使用して指定されている列のフラグを設定する必要がある場合も、 **DBCOLUMNFLAGS**列挙型。 列のフラグでは、列の特性について説明します。  
  
 たとえば、`CUpdateSessionColSchemaRowset`クラス[UpdatePV](http://msdn.microsoft.com/en-us/c8bed873-223c-4a7d-af55-f90138c6f38f)で Session.h)、最初の列がこのように設定。  
  
```  
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
  
 このコードを指定します、特に、列が、既定値は 0 の場合、書き込み可能なことをサポートしていると、列内のすべてのデータの長さは同じであります。 列のデータの可変長にする場合は、このフラグを設定しません。  
  
## <a name="see-also"></a>関連項目  
 [OLE DB プロバイダーの作成](../../data/oledb/creating-an-ole-db-provider.md)
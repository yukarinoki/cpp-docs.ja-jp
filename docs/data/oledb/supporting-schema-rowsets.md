---
title: スキーマ行セットのサポート |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- schema rowsets
- OLE DB consumer templates, schema rowsets
- OLE DB providers, schema rowsets
- OLE DB, schema rowsets
ms.assetid: 71c5e14b-6e33-4502-a2d9-a1dc6d6e9ba0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 95f1455fde75ec835486cbcc3d590822891d14f5
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33111758"
---
# <a name="supporting-schema-rowsets"></a>スキーマ行セットのサポート
スキーマ行セットでは、コンシューマーはその基になる構造体、またはスキーマを知らなくてもデータ ストアの情報を取得できるようにします。 たとえば、データ ストアには、そのため、読み込むことを除く、スキーマの知識を確認する方法ではありませんは、ユーザー定義の階層に編成されるテーブルがあります。 (別の例としてメモ、Visual C ウィザードでスキーマ行セットを使用して、コンシューマーのアクセサーを生成することです。)これを行うコンシューマーを許可するには、プロバイダーのセッション オブジェクトでメソッドを公開、 [IDBSchemaRowset](https://msdn.microsoft.com/en-us/library/ms713686.aspx)インターフェイスです。 Visual C アプリケーションで使用して、 [IDBSchemaRowsetImpl](../../data/oledb/idbschemarowsetimpl-class.md)を実装するクラス**IDBSchemaRowset**です。  
  
 `IDBSchemaRowsetImpl` 次のメソッドをサポートしています。  
  
-   [CheckRestrictions](../../data/oledb/idbschemarowsetimpl-checkrestrictions.md)スキーマ行セットに対して制限の妥当性をチェックします。  
  
-   [CreateSchemaRowset](../../data/oledb/idbschemarowsetimpl-createschemarowset.md) COM オブジェクトの作成関数をテンプレート パラメーターで指定されたオブジェクトを実装します。  
  
-   [SetRestrictions](../../data/oledb/idbschemarowsetimpl-setrestrictions.md)特定のスキーマ行セットをサポートする制限を指定します。  
  
-   [Idbschemarowset::getrowset](../../data/oledb/idbschemarowsetimpl-getrowset.md) (インターフェイスから継承) スキーマ行セットを返します。  
  
-   [GetSchemas](../../data/oledb/idbschemarowsetimpl-getschemas.md)によってアクセス可能なスキーマ行セットの一覧を返します`IDBSchemaRowsetImpl::GetRowset`(インターフェイスから継承)。  
  
## <a name="atl-ole-db-provider-wizard-support"></a>ATL OLE DB プロバイダー ウィザードでサポート  
 ATL OLE DB プロバイダー ウィザードでは、セッションのヘッダー ファイルに次の 3 つのスキーマ クラスを作成します。  
  
-   **C** *ShortName* **SessionTRSchemaRowset**  
  
-   **C** *ShortName* **SessionColSchemaRowset**  
  
-   **C** *ShortName* **SessionPTSchemaRowset**  
  
 これらのクラスがスキーマについて; コンシューマーの要求に応答します。OLE DB 仕様は、これらの 3 つのスキーマ行セットがサポートされている必要がありますに注意してください。  
  
-   **C** *ShortName* **SessionTRSchemaRowset**テーブル情報の要求を処理 (、`DBSCHEMA_TABLES`スキーマ行セット)。  
  
-   **C** *ShortName* **SessionColSchemaRowset**列情報の要求を処理 (、 **DBSCHEMA_COLUMNS**スキーマ行セット)。 ウィザードでは、これらのクラスでは、DOS プロバイダーのスキーマ情報を返すサンプル実装を提供します。  
  
-   **C** *ShortName* **SessionPTSchemaRowset**プロバイダーの種類に関するスキーマ情報の要求を処理 (、 **DBSCHEMA_PROVIDER_TYPES**スキーマ行セット)。 ウィザードによって提供される既定の実装を返します`S_OK`です。  
  
 これらのクラスは、プロバイダーに対応するスキーマ情報を処理するをカスタマイズすることができます。  
  
-   **C***ShortName***SessionTRSchemaRowset**、カタログ、テーブル、および説明のフィールドに入力する必要があります (**trData.m_szType**、 **trData.m_szTable**、および**trData.m_szDesc**)。 ウィザードで生成された例は、1 つだけ行 (テーブル) を使用します。 その他のプロバイダーは、1 つ以上のテーブルを返す可能性があります。  
  
-   **C***ShortName***SessionColSchemaRowset**、として、テーブルの名前を渡す、 **DBID**です。  
  
## <a name="setting-restrictions"></a>制限を設定します。  
 スキーマ行セットのサポートで重要な概念を設定すると、制限事項を使用して操作を行う`SetRestrictions`です。 制限により、コンシューマーは一致する行だけをフェッチできます (たとえば、テーブル "MyTable" 内のすべての列を検索します)。 制限は省略可能であり、制限がサポートされていない場合 (既定)、常にすべてのデータが返されます。 制約をサポートするプロバイダーの例は、次を参照してください。、 [UpdatePV](http://msdn.microsoft.com/en-us/c8bed873-223c-4a7d-af55-f90138c6f38f)サンプルです。  
  
## <a name="setting-up-the-schema-map"></a>スキーマ マップを設定します。  
 UpdatePV で Session.h のようにスキーマ マップを設定します。  
  
```  
BEGIN_SCHEMA_MAP(CUpdateSession)  
    SCHEMA_ENTRY(DBSCHEMA_TABLES, CUpdateSessionTRSchemaRowset)  
    SCHEMA_ENTRY(DBSCHEMA_COLUMNS, CUpdateSessionColSchemaRowset)  
    SCHEMA_ENTRY(DBSCHEMA_PROVIDER_TYPES, CUpdateSessionPTSchemaRowset)  
END_SCHEMA_MAP()  
```  
  
 サポートする**IDBSchemaRowset**、サポートする必要があります`DBSCHEMA_TABLES`、 **DBSCHEMA_COLUMNS**、および**DBSCHEMA_PROVIDER_TYPES**です。 各自の判断で、追加のスキーマ行セットを追加できます。  
  
 スキーマ行セット クラスの宣言、`Execute`などのメソッド`CUpdateSessionTRSchemaRowset`UpdatePV で。  
  
```  
class CUpdateSessionTRSchemaRowset :   
    public CSchemaRowsetImpl < CUpdateSessionTRSchemaRowset,   
                              CTABLESRow, CUpdateSession >  
...  
// Execute looks like this; what pointers does the consumer use?  
    HRESULT Execute(DBROWCOUNT* pcRowsAffected,   
                    ULONG cRestrictions, const VARIANT* rgRestrictions)  
```  
  
 なお`CUpdateSession`から継承`IDBSchemaRowsetImpl`メソッドを処理するすべての制限があるため、します。 使用して`CSchemaRowsetImpl`、(上記のスキーマ マップに表示)、3 つの子クラスを宣言します。 `CUpdateSessionTRSchemaRowset`、 `CUpdateSessionColSchemaRowset`、および`CUpdateSessionPTSchemaRowset`です。 これらの各子クラスが、`Execute`制約 (検索条件) のそれぞれのセットを処理するメソッド。 各`Execute`メソッドの値を比較し、`cRestrictions`と`rgRestrictions`パラメーター。 これらのパラメーターの説明を参照して[SetRestrictions](../../data/oledb/idbschemarowsetimpl-setrestrictions.md)です。  
  
 特定のスキーマ行セットに対応する制限についての詳細については、スキーマ行セット Guid の表を参照してくださいで[IDBSchemaRowset](https://msdn.microsoft.com/en-us/library/ms713686.aspx)で、 *OLE DB プログラマーズ リファレンス*で、Windows SDK。  
  
 たとえば、サポートする場合、 **TABLE_NAME**に制限`DBSCHEMA_TABLES`、するは、次の操作します。  
  
 最初に、検索`DBSCHEMA_TABLES`し (順序で) の 4 つの制限をサポートしていることを確認します。  
  
|スキーマ行セットの制限|制限値|  
|-------------------------------|-----------------------|  
|**TABLE_CATALOG**|0x1 (バイナリ 1)|  
|**TABLE_SCHEMA**|0x2 (バイナリ 10)|  
|**TABLE_NAME**|0x4 (バイナリ 100)|  
|**TABLE_TYPE**|0x8 (バイナリ 1000)|  
  
 次に、1 ビットごとの制限があることに注意してください。 サポートするため**TABLE_NAME**のみ、0x4 でを返すと、`rgRestrictions`要素。 サポートする場合**TABLE_CATALOG**と**TABLE_NAME**0x5 (バイナリ 101) を返すとします。  
  
 既定では、実装は、すべての要求の (制約をサポートしません) 0 を返します。 UpdatePV では、制約をサポートするプロバイダーの例を示します。  
  
### <a name="example"></a>例  
 このコードはから取得、 [UpdatePV](http://msdn.microsoft.com/en-us/c8bed873-223c-4a7d-af55-f90138c6f38f)サンプルです。 UpdatePv は、次の 3 つの必要なスキーマ行セットをサポートしています: `DBSCHEMA_TABLES`、 **DBSCHEMA_COLUMNS**、および**DBSCHEMA_PROVIDER_TYPES**です。 プロバイダーでスキーマのサポートを実装する方法の例は、としてこのトピックでを実装する、 **DBSCHEMA_TABLE**行セット。  
  
> [!NOTE]
>  サンプル コードがここでは記載されている内容と異なる場合があります。サンプル コードは、最新のバージョンと見なす必要があります。  
  
 スキーマのサポートを追加する最初の手順をサポートする制限を判断します。 OLE DB 仕様の定義で見て、調べるには、スキーマ行セットの制限がある、 **IDBSchemaRowset**です。 次の主要な定義には、スキーマ行セットの名前、制限事項、数、および制限列を含むテーブル参照してください。 サポートし、制限事項と制限列の数のメモするスキーマ行セットを選択します。 たとえば、 `DBSCHEMA_TABLES` 4 つの制限をサポートしています (**TABLE_CATALOG**、 **、table_schema、**、 **TABLE_NAME**、および**TABLE_TYPE**):  
  
```  
void SetRestrictions(ULONG cRestrictions, GUID* rguidSchema,   
   ULONG* rgRestrictions)  
{  
    for (ULONG l=0; l<cRestrictions; l++)  
    {  
        if (InlineIsEqualGUID(rguidSchema[l], DBSCHEMA_TABLES))  
            rgRestrictions[l] = 0x0C;  
        else if (InlineIsEqualGUID(rguidSchema[l], DBSCHEMA_COLUMNS))  
                 rgRestrictions[l] = 0x04;  
             else if (InlineIsEqualGUID(rguidSchema[l],  
                                        DBSCHEMA_PROVIDER_TYPES))  
                      rgRestrictions[l] = 0x00;  
   }  
}  
```  
  
 ビットは、それぞれの制限列を表します。 制約をサポートする場合は、クエリによって)、そのビットを 1 に設定します。 制約をサポートしない場合は、そのビットを 0 に設定します。 上記のコードの行から UpdatePV サポートしている、 **TABLE_NAME**と**TABLE_TYPE**に関する制限事項、`DBSCHEMA_TABLES`行セット。 これらは、(ビット マスク 100) の 3 番目と 4 番目の (ビット マスク 1000) 制約。 そのため、対応するビットマスクの UpdatePv は 1100 (0x0C) です。  
  
```  
if (InlineIsEqualGUID(rguidSchema[l], DBSCHEMA_TABLES))  
    rgRestrictions[l] = 0x0C;  
```  
  
 次`Execute`関数は、正規行セットのと似ています。 次の 3 つの引数がある: `pcRowsAffected`、 `cRestrictions`、および`rgRestrictions`です。 `pcRowsAffected`変数は、出力パラメーターをプロバイダーがスキーマ行セット内の行数を返すことができます。 `cRestrictions`パラメーターは、コンシューマーによってプロバイダーに渡される制限の番号を含む入力パラメーターです。 `rgRestrictions`パラメーターは配列の**バリアント**を制限値を含む値です。  
  
```  
HRESULT Execute(DBROWCOUNT* pcRowsAffected, ULONG cRestrictions,   
                const VARIANT* rgRestrictions)  
```  
  
 `cRestrictions`変数は、プロバイダーがそれをサポートするかどうかに関係なく、スキーマ行セットの制限の合計数に基づいています。 UpdatePv では、2 つの制限 (3 番目と 4 分) をサポートするため次のコードだけを検索、`cRestrictions`値より大きいか等しいを 3 つまでです。  
  
 値、 **TABLE_NAME**に制限が格納されている`rgRestrictions[2]`(ここでも、0 から始まる配列内の 3 番目の制限は 2)。 制限がないことを確認する必要があります`VT_EMPTY`実際にサポートするようにします。 なお**VT_** は等しくありません`VT_EMPTY`です。 **VT_** 有効な制限値を指定します。  
  
 テーブル名の UpdatePv 定義とは、テキスト ファイルへの完全修飾パス名です。 制限値を抽出しようと、ファイルを開き、ファイルが実際に存在することを確認します。 ファイルが存在しない場合は、返す`S_OK`です。 これは、下位ビットですが、指定された名前によってサポートされているテーブルが含まれていなかったことは、どのようなコードが実際にコンシューマーを示しています。 `S_OK`戻り値はことに正しく実行されるコードを意味します。  
  
```  
USES_CONVERSION;  
enum {  
            sizeOfszFile = 255  
};  
CTABLESRow  trData;  
FILE        *pFile = NULL;  
TCHAR       szFile[ sizeOfszFile ];  
errcode     err = 0;  
  
// Handle any restrictions sent to us. This only handles  
// the TABLE_NAME & TABLE_TYPE restictions (the 3rd and 4th   
// restrictions in DBSCHEMA_TABLES...look in IDBSchemaRowsets   
// in part 2 of the prog. ref) so your restrictions are 0x08 & 0x04   
// for a total of (0x0C)  
if (cRestrictions >= 3 && rgRestrictions[2].vt != VT_EMPTY)  
{  
    CComBSTR bstrName = rgRestrictions[2].bstrVal;  
    if ((rgRestrictions[2].vt == VT_BSTR) && (bstrName != (BSTR)NULL))  
    {  
        // Check to see if the file exists  
        _tcscpy_s(&szFile[0], sizeOfszFile, OLE2T(bstrName));  
        if (szFile[0] == _T('\0') ||   
           ((err = _tfopen(&pFile, &szFile[0], _T("r"))) == 0))  
        {  
            return S_OK;// Their restriction was invalid return no data  
        }  
        else  
        {  
            fclose(pFile);  
        }  
    }  
}  
```  
  
 4 番目の制限をサポートする (**TABLE_TYPE**) は、3 番目の制限に似ています。 値がないことを確認するチェック`VT_EMPTY`です。 この制限は、テーブル型のみを返します**テーブル**です。 有効な値を決定する、 `DBSCHEMA_TABLES`、付録 B のファイルの場所、 *OLE DB プログラマーズ リファレンス*で、**テーブル**行セットのセクションでします。  
  
```  
// TABLE_TYPE restriction:  
if (cRestrictions >=4 && rgRestrictions[3].vt != VT_EMPTY)  
{  
    CComBSTR bstrType = rgRestrictions[3].bstrVal;  
    if ((rgRestrictions[3].vt == VT_BSTR) && (bstrType != (BSTR)NULL))  
    {  
        // This is kind of a blind restriction.  
        // This only actually supports  
        // TABLES so if you get anything else,   
        // just return an empty rowset.  
        if (_tcscmp(_T("TABLE"), OLE2T(bstrType)) != 0)  
            return S_OK;  
    }  
}  
```  
  
 これは、行セットの行エントリを実際に作成します。 変数`trData`に対応する**CTABLESRow**、OLE DB プロバイダー テンプレートで定義されている構造体。 **CTABLESRow**に対応する、**テーブル**OLE DB 仕様の付録 B の行セットの定義。 のみ、一度に 1 つのテーブルをサポートできるため、追加する 1 つの行があるだけです。  
  
```  
// Bring over the data:  
wcspy_s(trData.m_szType, OLESTR("TABLE"), 5);  

wcspy_s(trData.m_szDesc, OLESTR("The Directory Table"), 19);  

wcsncpy_s(trData.m_szTable, T2OLE(szFile), _TRUNCATE());  
```  
  
 UpdatePV のみの 3 つの列の設定: **TABLE_NAME**、 **TABLE_TYPE**、および**説明**です。 実装する場合、この情報が必要なので、情報を返す列のメモをする必要があります`GetDBStatus`:  
  
```  
    _ATLTRY  
    {  
        m_rgRowData.Add(trData);  
    }  
    _ATLCATCHALL()  
    {  
        return E_OUTOFMEMORY;  
    }  
    //if (!m_rgRowData.Add(trData))  
    //    return E_OUTOFMEMORY;  
    *pcRowsAffected = 1;  
    return S_OK;  
}  
```  
  
 `GetDBStatus`関数は、スキーマ行セットの適切な操作を非常に重要です。 各列のデータを返さないため、**テーブル**行セット、のどの列のデータを返すと、これがないを指定する必要があります。  
  
```  
virtual DBSTATUS GetDBStatus(CSimpleRow* , ATLCOLUMNINFO* pColInfo)  
{  
    ATLASSERT(pColInfo != NULL);  
  
    switch(pColInfo->iOrdinal)  
    {  
    case 3:     // TABLE_NAME  
    case 4:     // TABLE_TYPE  
    case 6:     // DESCRIPTION  
        return DBSTATUS_S_OK;  
        break;  
    default:  
        return DBSTATUS_S_ISNULL;  
    break;  
    }  
}  
```  
  
 `Execute`関数のデータを返します、 **TABLE_NAME**、 **TABLE_TYPE**、および**説明**からのフィールド、**テーブル**行セット、OLE DB 仕様の「付録 B で検索して序数 3、4、および 6 である (先頭からカウント ダウン) を決定します。 これらの列のそれぞれについて、返す**DBSTATUS_S_OK**です。 その他のすべての列を返す**DBSTATUS_S_ISNULL**です。 この状態を返すに重要で、コンシューマーは、返された値がであるため**NULL**または、それ以外です。 なお、 **NULL**空のと同じではありません。  
  
 OLE DB スキーマ行セット インターフェイスの詳細については、次を参照してください。、 [IDBSchemaRowset](../../data/oledb/idbschemarowsetimpl-class.md) OLE DB プログラマーズ リファレンスのインターフェイスです。  
  
 コンシューマーが使用する方法について**IDBSchemaRowset**メソッドを参照してください[のスキーマ行セットのメタデータの取得](../../data/oledb/obtaining-metadata-with-schema-rowsets.md)です。  
  
 スキーマ行セットをサポートするプロバイダーの例は、次を参照してください。、 [UpdatePV](http://msdn.microsoft.com/en-us/c8bed873-223c-4a7d-af55-f90138c6f38f)サンプルです。  
  
## <a name="see-also"></a>関連項目  
 [高度なプロバイダー手法](../../data/oledb/advanced-provider-techniques.md)
---
title: スキーマ行セットのサポート |Microsoft Docs
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
ms.openlocfilehash: 7f5c24623e10de23e42041592eb1b2f417f1ed5b
ms.sourcegitcommit: a41c4d096afca1e9b619bbbce045b77135d32ae2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/14/2018
ms.locfileid: "42572882"
---
# <a name="supporting-schema-rowsets"></a>スキーマ行セットのサポート
スキーマ行セットを許可すると、コンシューマーは、基になる構造体またはスキーマを知らなくても、データ ストアに関する情報を取得します。 たとえば、データ ストアを除く、スキーマ情報を読み込むことで、確認方法がなくなるために、ユーザー定義階層に編成されるテーブルがあります。 (別の例としてメモ、Visual C ウィザードでスキーマ行セットを使用して、コンシューマーのアクセサーを生成することです。)これを行うコンシューマーを許可するには、プロバイダーのセッション オブジェクトでメソッドを公開、 [IDBSchemaRowset](/previous-versions/windows/desktop/ms713686\(v=vs.85\))インターフェイス。 Visual C アプリケーションで使用する、 [IDBSchemaRowsetImpl](../../data/oledb/idbschemarowsetimpl-class.md)を実装するクラス`IDBSchemaRowset`します。  
  
 `IDBSchemaRowsetImpl` 次のメソッドをサポートしています。  
  
-   [CheckRestrictions](../../data/oledb/idbschemarowsetimpl-checkrestrictions.md)スキーマ行セットに対する制限の妥当性を確認します。  
  
-   [CreateSchemaRowset](../../data/oledb/idbschemarowsetimpl-createschemarowset.md) COM オブジェクトには、テンプレート パラメーターで指定されたオブジェクトの作成関数を実装します。  
  
-   [SetRestrictions](../../data/oledb/idbschemarowsetimpl-setrestrictions.md)の特定のスキーマ行セットでサポートする制限を指定します。  
  
-   [Idbschemarowset::getrowset](../../data/oledb/idbschemarowsetimpl-getrowset.md) (インターフェイスから継承) スキーマ行セットを返します。  
  
-   [GetSchemas](../../data/oledb/idbschemarowsetimpl-getschemas.md)でアクセスできるスキーマ行セットの一覧を返します`IDBSchemaRowsetImpl::GetRowset`(インターフェイスから継承されます)。  
  
## <a name="atl-ole-db-provider-wizard-support"></a>ATL OLE DB プロバイダー ウィザード サポート  
 ATL OLE DB プロバイダー ウィザードでは、セッションのヘッダー ファイルに次の 3 つのスキーマ クラスを作成します。  
  
-   **C** *ShortName* **SessionTRSchemaRowset**  
  
-   **C** *ShortName* **SessionColSchemaRowset**  
  
-   **C** *ShortName* **SessionPTSchemaRowset**  
  
 これらのクラスは、スキーマ情報のコンシューマーの要求に応答します。OLE DB 仕様は、これらの 3 つのスキーマ行セットをサポートする必要がありますに注意してください。  
  
-   **C** *ShortName* **SessionTRSchemaRowset**テーブル情報の要求を処理 (、`DBSCHEMA_TABLES`スキーマ行セット)。  
  
-   **C** *ShortName* **SessionColSchemaRowset**列情報の要求を処理 (、`DBSCHEMA_COLUMNS`スキーマ行セット)。 ウィザードでは、これらのクラスは、DOS プロバイダーのスキーマ情報を返すサンプル実装を提供します。  
  
-   **C** *ShortName* **SessionPTSchemaRowset**プロバイダーの種類に関するスキーマ情報の要求を処理 (、`DBSCHEMA_PROVIDER_TYPES`スキーマ行セット)。 ウィザードによって提供される既定の実装を返します`S_OK`します。  
  
 ご利用のプロバイダーに対応するスキーマ情報を処理するためにこれらのクラスをカスタマイズできます。  
  
-   **C***ShortName***SessionTRSchemaRowset**、カタログ、テーブル、および説明のフィールドに入力する必要があります (`trData.m_szType`、 `trData.m_szTable`、および`trData.m_szDesc`)。 ウィザードで生成された例では、1 つだけ行 (テーブル) を使用します。 その他のプロバイダーは、1 つ以上のテーブルを返す可能性があります。  
  
-   **C***ShortName***SessionColSchemaRowset**、としてテーブルの名前を渡す、`DBID`します。  
  
## <a name="setting-restrictions"></a>制限を設定します。  
 スキーマ行セットのサポートの重要な概念を設定すると、制限事項を使用して操作を行う`SetRestrictions`します。 制限により、コンシューマーは一致する行だけをフェッチできます (たとえば、テーブル "MyTable" 内のすべての列を検索します)。 制限は省略可能であり、制限がサポートされていない場合 (既定)、常にすべてのデータが返されます。 制約をサポートするプロバイダーの例は、次を参照してください。、 [UpdatePV](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/ATL/OLEDB/Provider/UPDATEPV)サンプル。  
  
## <a name="setting-up-the-schema-map"></a>スキーマ マップを設定  
 UpdatePV で Session.h のようなスキーマ マップを設定します。  
  
```  
BEGIN_SCHEMA_MAP(CUpdateSession)  
    SCHEMA_ENTRY(DBSCHEMA_TABLES, CUpdateSessionTRSchemaRowset)  
    SCHEMA_ENTRY(DBSCHEMA_COLUMNS, CUpdateSessionColSchemaRowset)  
    SCHEMA_ENTRY(DBSCHEMA_PROVIDER_TYPES, CUpdateSessionPTSchemaRowset)  
END_SCHEMA_MAP()  
```  
  
 サポートするために`IDBSchemaRowset`をサポートする必要があります`DBSCHEMA_TABLES`、 `DBSCHEMA_COLUMNS`、および`DBSCHEMA_PROVIDER_TYPES`します。 ユーザーの判断でのスキーマ行セットを追加できます。  
  
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
  
 なお`CUpdateSession`継承`IDBSchemaRowsetImpl`メソッドを処理するすべての制限があるため、します。 使用して`CSchemaRowsetImpl`、(上記のスキーマ マップに表示)、3 つの子クラスを宣言: `CUpdateSessionTRSchemaRowset`、 `CUpdateSessionColSchemaRowset`、および`CUpdateSessionPTSchemaRowset`します。 各子クラスが、`Execute`制約 (検索条件) のそれぞれのセットを処理するメソッド。 各`Execute`メソッドの値を比較し、`cRestrictions`と`rgRestrictions`パラメーター。 これらのパラメーターの説明を参照して[SetRestrictions](../../data/oledb/idbschemarowsetimpl-setrestrictions.md)します。  
  
 特定のスキーマ行セットに対応する制限についての詳細については、スキーマ行セット Guid の表を参照してくださいで[IDBSchemaRowset](/previous-versions/windows/desktop/ms713686\(v=vs.85\))で、 *OLE DB プログラマーズ リファレンス*で、Windows SDK。  
  
 サポートする場合など、 **TABLE_NAME**に制限`DBSCHEMA_TABLES`次の操作します。  
  
 最初に、検索`DBSCHEMA_TABLES`順番で 4 つの制限をサポートしていることを確認します。  
  
|スキーマ行セットの制限|制限値|  
|-------------------------------|-----------------------|  
|**TABLE_CATALOG**|0x1 (バイナリ 1)|  
|**TABLE_SCHEMA**|0x2 (バイナリ 10)|  
|**TABLE_NAME**|0x4 (バイナリ 100)|  
|**TABLE_TYPE**|0x8 (バイナリ 1000)|  
  
 次に、1 つのビットの各制限があることに注意してください。 サポートするため、 **TABLE_NAME**のみ、0x4 でを返すと、`rgRestrictions`要素。 サポートされている場合**TABLE_CATALOG**と**TABLE_NAME**は、0x5 (バイナリ 101) を返します。  
  
 既定では、実装は、すべての要求の (すべての制限をサポートしません) 0 を返します。 UpdatePV 制約をサポートするプロバイダーの例に示します。  
  
### <a name="example"></a>例  
 このコードから取得されますが、 [UpdatePV](http://msdn.microsoft.com/c8bed873-223c-4a7d-af55-f90138c6f38f)サンプル。 UpdatePv は、次の 3 つの必要なスキーマ行セットをサポートしています: `DBSCHEMA_TABLES`、 `DBSCHEMA_COLUMNS`、および`DBSCHEMA_PROVIDER_TYPES`します。 としてご利用のプロバイダーでスキーマのサポートを実装する方法の例は、このトピックでを実装する、`DBSCHEMA_TABLE`行セット。  
  
> [!NOTE]
>  サンプル コードはここでは記載されているものと異なる場合があります。サンプル コードは、最新のバージョンと見なす必要があります。  
  
 スキーマのサポートを追加する最初の手順では、サポートする制限を決定します。 OLE DB 仕様の定義で見て、スキーマ行セットの使用可能な制限を確認するには、`IDBSchemaRowset`します。 次のメインの定義は、スキーマ行セットの名前、制限の数と制限列を含むテーブルを参照してください。 サポートの制限事項と制限列の数をメモするスキーマ行セットを選択します。 たとえば、 `DBSCHEMA_TABLES` 4 つの制限をサポートしています (**TABLE_CATALOG**、 **、table_schema、**、 **TABLE_NAME**、および**TABLE_TYPE**):  
  
```cpp  
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
  
 ビットは、それぞれの制限列を表します。 制約をサポートする場合は、クエリによって)、そのビットを 1 に設定します。 制約をサポートしない場合は、そのビットを 0 に設定します。 上記のコードの行から UpdatePV サポートしている、 **TABLE_NAME**と**TABLE_TYPE**に関する制限事項、`DBSCHEMA_TABLES`行セット。 これらは、(ビット マスク 100) の 3 番目と 4 番目の (ビット マスク 1000) 制約。 そのため、対応するビットマスク UpdatePv は、1100 (または 0x0C) は。  
  
```  
if (InlineIsEqualGUID(rguidSchema[l], DBSCHEMA_TABLES))  
    rgRestrictions[l] = 0x0C;  
```  
  
 次`Execute`関数は、通常の行セットのと似ています。 次の 3 つの引数がある:*入力/出力*、 *cRestrictions*、および*で*します。 *入力/出力*変数は、出力パラメーターをプロバイダーがスキーマ行セットの行の数を返すことができます。 *CRestrictions*パラメーターは、コンシューマーによってプロバイダーに渡された制限の数を格納している入力パラメーターです。 *で*パラメーターが配列の`VARIANT`制限値を含む値。  
  
```  
HRESULT Execute(DBROWCOUNT* pcRowsAffected, ULONG cRestrictions,   
                const VARIANT* rgRestrictions)  
```  
  
 `cRestrictions`変数は、プロバイダーがそれをサポートするかどうかに関係なく、スキーマ行セットの制限の合計数に基づきます。 UpdatePv (3 番目と 4 番目) の 2 つの制限をサポートするため、このコードだけを検索、`cRestrictions`を 3 つ以上の値。  
  
 値、 **TABLE_NAME**に制限が格納されている`rgRestrictions[2]`(再度、0 から始まる配列内の 3 つ目の制限は 2)。 制限が実際にサポートするように VT_EMPTY ではないことを確認する必要があります。 VT_ で VT_EMPTY と等しくないことに注意してください。 VT_ では、有効な制限値を指定します。  
  
 テーブル名の UpdatePv 定義は、テキスト ファイルへの完全修飾パス名です。 制限値を抽出し、ファイルが実際に存在することを確認するファイルを開こうとします。 ファイルが存在しない場合は、S_OK を返します。 ちょっと逆行この思えますが、指定した名前によってサポートされているテーブルが存在しないことが、どのようなコードには、コンシューマーが実際に示しています。 S_OK の戻り値は正しく実行されるコードを意味します。  
  
```cpp  
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
  
 4 番目の制限をサポートしている (**TABLE_TYPE**) は 3 つ目の制限に似ています。 値が VT_EMPTY ではないことを確認します。 この制限は、テーブル型のみを返します**テーブル**します。 有効な値を決定する、 `DBSCHEMA_TABLES`、付録 B のファイルの場所、 *OLE DB プログラマーズ リファレンス*で、**テーブル**行セットのセクション。  
  
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
  
 これは、行セットの行エントリを実際に作成します。 変数`trData`に対応する`CTABLESRow`、OLE DB プロバイダー テンプレートで定義されている構造体。 `CTABLESRow` 対応する、**テーブル**OLE DB 仕様の「付録 B で行セットの定義。 一度に 1 つのテーブルをサポートすることができますのみであるために、追加する 1 つの行があるだけです。  
  
```cpp  
// Bring over the data:  
wcspy_s(trData.m_szType, OLESTR("TABLE"), 5);  

wcspy_s(trData.m_szDesc, OLESTR("The Directory Table"), 19);  

wcsncpy_s(trData.m_szTable, T2OLE(szFile), _TRUNCATE());  
```  
  
 UpdatePV のみの 3 つの列の設定: **TABLE_NAME**、 **TABLE_TYPE**、および**説明**します。 実装する場合、この情報が必要なために、情報を返す対象の列のメモをする必要があります`GetDBStatus`:  
  
```cpp  
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
  
 `GetDBStatus`関数は、スキーマ行セットの適切な操作を非常に重要です。 各列のデータを返さないため、**テーブル**行セットのデータを返す列とは指定する必要があります。  
  
```cpp  
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
  
 `Execute`関数のデータを返します、 **TABLE_NAME**、 **TABLE_TYPE**、および**説明**フィールドから、**テーブル**行セット、OLE DB 仕様の「付録 B で検索して序数 3、4、および 6 である (先頭からカウント ダウン) を決定します。 これらの列のそれぞれについて、DBSTATUS_S_OK を返します。 その他のすべての列には、DBSTATUS_S_ISNULL を返します。 コンシューマーが返された値が NULL またはその他のことを認識していないためですが、この状態を返すため重要です。 ここでも、NULL は空のと同じことに注意してください。  
  
 OLE DB スキーマ行セットのインターフェイスの詳細については、次を参照してください。、 [IDBSchemaRowset](../../data/oledb/idbschemarowsetimpl-class.md) OLE DB プログラマーズ リファレンスのインターフェイス。  
  
 コンシューマーの使用方法については`IDBSchemaRowset`メソッドを参照してください[スキーマ行セットのメタデータの取得](../../data/oledb/obtaining-metadata-with-schema-rowsets.md)します。  
  
 スキーマ行セットをサポートするプロバイダーの例は、次を参照してください。、 [UpdatePV](http://msdn.microsoft.com/c8bed873-223c-4a7d-af55-f90138c6f38f)サンプル。  
  
## <a name="see-also"></a>関連項目  
 [高度なプロバイダー手法](../../data/oledb/advanced-provider-techniques.md)
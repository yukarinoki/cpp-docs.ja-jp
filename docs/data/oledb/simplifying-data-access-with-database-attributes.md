---
title: データベース属性によるデータ アクセスを簡素化する |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- vc-attr.db_param
- vc-attr.db_column
- vc-attr.db_accessor
- vc-attr.db_command
- vc-attr.db_table
- vc-attr.db_source
dev_langs:
- C++
helpviewer_keywords:
- attributes [C++], database
- attributes [C++], data access
- databases [C++], attributes
- data [C++], simplifying access
- data access [C++], database attributes
- database attributes [C++]
- OLE DB consumers [C++], database attributes
- attributes [C++], OLE DB consumer
ms.assetid: 560d2456-e307-4cb7-ba7b-4d0ed674697f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: f8221b44d668a3ca2446913958645bb5e160dc87
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/29/2018
ms.locfileid: "43194905"
---
# <a name="simplifying-data-access-with-database-attributes"></a>データベース属性によるデータ アクセスの簡略化
このトピックでは、データベース操作を簡略化するデータベースの属性の使用を示します。  
  
 データベースの情報にアクセスする基本的な方法では、データベース内のコマンド (またはテーブル) クラスと特定のテーブルのユーザー レコード クラスを作成します。 データベースの属性は、以前行う必要があるテンプレート宣言の一部を簡略化します。  
  
 次のセクションでは、データベースの属性の使用を示すためは、2 つの同等のテーブルとユーザー レコード クラスの宣言の操作を表示する: 最初の属性を使用して、2 つ目は、OLE DB テンプレートを使用します。 このような宣言コードは通常 authors.h、テーブルまたはコマンド オブジェクトのという名前のヘッダー ファイルなど。  
  
 2 つのファイルを比較すると、属性を使用するがどれだけ単純がわかります。 相違点の一部は。  
  
-   属性を使用するだけである 1 つのクラスを宣言する:`CAuthors`テンプレートで 2 つを宣言しているときに、:`CAuthorsNoAttrAccessor`と`CAuthorsNoAttr`します。  
  
-   `db_source`属性付きのバージョンでの呼び出しは、`OpenDataSource()`テンプレートの宣言に呼び出します。  
  
-   `db_table`属性付きのバージョンでの呼び出しは次のテンプレートの宣言と同等です。  
  
    ```  
    class CAuthorsNoAttr : public CTable<CAccessor<CAuthorsNoAttrAccessor>>  
    ```  
  
-   `db_column`属性付きのバージョンでの呼び出しは、列マップに同等です (を参照してください`BEGIN_COLUMN_MAP ... END_COLUMN_MAP`) テンプレートの宣言にします。  
  
 属性は、ユーザー レコード クラスの宣言を挿入します。 ユーザー レコード クラスは`CAuthorsNoAttrAccessor`テンプレート宣言のです。 場合は、テーブル クラス`CAuthors`、挿入されたユーザー レコード クラスの名前は`CAuthorsAccessor`、挿入されたコードではその宣言だけを表示できます。 詳細については、「Attribute-Injected ユーザー レコード クラス」を参照してください[ユーザー レコード](../../data/oledb/user-records.md)します。  
  
 属性と、テンプレート化されたコードの両方でを使用して行セット プロパティを設定する必要がありますに注意してください。`CDBPropSet::AddProperty`します。  
  
 このトピックで説明する属性については、次を参照してください。 [OLE DB コンシューマー属性](../../windows/ole-db-consumer-attributes.md)します。  
  
## <a name="table-and-accessor-declaration-using-attributes"></a>テーブルおよびアクセサーの宣言属性を使用します。  
 次のコード呼び出し`db_source`と`db_table`テーブル クラスにします。 `db_source` データ ソース、使用する接続を指定します。 `db_table` table クラスを宣言する適切なテンプレート コードを挿入します。 `db_column` 列マップを指定し、アクセサーの宣言を挿入します。 ATL をサポートするすべてのプロジェクトで、OLE DB コンシューマー属性を使用することができます。  
  
 属性を使用してテーブルおよびアクセサーの宣言を次に示します。  
  
```cpp
//////////////////////////////////////////////////////////////////////  
// Table and accessor declaration using attributes  
// authors.h  
//////////////////////////////////////////////////////////////////////  
  
// Table class declaration  
// (Note that you must provide your own connection string for db_source.)  
[  
   db_source(L"your connection string"),  
   db_table("Authors")  
]  
class CAuthors  
{  
public:  
   DWORD m_dwAuIDStatus;  
   DWORD m_dwAuthorStatus;  
   DWORD m_dwYearBornStatus;  
   DWORD m_dwAuIDLength;  
   DWORD m_dwAuthorLength;  
   DWORD m_dwYearBornLength;  
   [ db_column(1, status=m_dwAuIDStatus, length=m_dwAuIDLength) ] LONG m_AuID;  
   [ db_column(2, status=m_dwAuthorStatus, length=m_dwAuthorLength) ] TCHAR m_Author[51];  
   [ db_column(3, status=m_dwYearBornStatus, length=m_dwYearBornLength) ] SHORT m_YearBorn;  
   void GetRowsetProperties(CDBPropSet* pPropSet)  
   {  
      pPropSet->AddProperty(DBPROP_CANFETCHBACKWARDS, true);  
      pPropSet->AddProperty(DBPROP_CANSCROLLBACKWARDS, true);  
      pPropSet->AddProperty(DBPROP_IRowsetChange, true);  
   }  
};  
```  
  
## <a name="table-and-accessor-declaration-using-templates"></a>テーブルおよびアクセサーの宣言テンプレートを使用します。  
 テンプレートを使用してテーブルおよびアクセサーの宣言を次に示します。  
  
```cpp
//////////////////////////////////////////////////////////////////////  
// Table and user record class declaration using templates  
// authors.h  
//////////////////////////////////////////////////////////////////////  
  
// User record class declaration  
class CAuthorsNoAttrAccessor  
{  
public:  
   DWORD m_dwAuIDStatus;  
   DWORD m_dwAuthorStatus;  
   DWORD m_dwYearBornStatus;  
   DWORD m_dwAuIDLength;  
   DWORD m_dwAuthorLength;  
   DWORD m_dwYearBornLength;  
   LONG m_AuID;  
   TCHAR m_Author[51];  
   SHORT m_YearBorn;  
   void GetRowsetProperties(CDBPropSet* pPropSet)  
   {  
      pPropSet->AddProperty(DBPROP_CANFETCHBACKWARDS, true);  
      pPropSet->AddProperty(DBPROP_CANSCROLLBACKWARDS, true);  
      pPropSet->AddProperty(DBPROP_IRowsetChange, true);  
   }  
   HRESULT OpenDataSource()  
   {  
      CDataSource _db;  

HRESULT hr;  
      hr = _db.OpenFromInitializationString(L"your connection string");  
      if (FAILED(hr))  
      {  
#ifdef _DEBUG  
         AtlTraceErrorRecords(hr);  
#endif  
         return hr;  
      }  
      return m_session.Open(_db);  
   }  
   void CloseDataSource()  
   {  
      m_session.Close();  
   }  
   operator const CSession&()  
   {  
      return m_session;  
   }  
   CSession m_session;  
   BEGIN_COLUMN_MAP(CAuthorsNoAttrAccessor)  
      COLUMN_ENTRY_LENGTH_STATUS(1, m_AuID, m_dwAuIDLength, m_dwAuIDStatus)  
      COLUMN_ENTRY_LENGTH_STATUS(2, m_Author, m_dwAuthorLength, m_dwAuthorStatus)  
      COLUMN_ENTRY_LENGTH_STATUS(3, m_YearBorn, m_dwYearBornLength, m_dwYearBornStatus)  
   END_COLUMN_MAP()  
};  
class CAuthorsNoAttr : public CTable<CAccessor<CAuthorsNoAttrAccessor>>  
{  
public:  
   HRESULT OpenAll()  
   {  
HRESULT hr;  
      hr = OpenDataSource();  
      if (FAILED(hr))  
         return hr;  
      __if_exists(GetRowsetProperties)  
      {  
         CDBPropSet propset(DBPROPSET_ROWSET);  
         __if_exists(HasBookmark)  
         {  
            propset.AddProperty(DBPROP_IRowsetLocate, true);  
         }  
         GetRowsetProperties(&propset);  
         return OpenRowset(&propset);  
      }  
      __if_not_exists(GetRowsetProperties)  
      {  
         __if_exists(HasBookmark)  
         {  
            CDBPropSet propset(DBPROPSET_ROWSET);  
            propset.AddProperty(DBPROP_IRowsetLocate, true);  
            return OpenRowset(&propset);  
         }  
      }  
      return OpenRowset();  
   }  
   HRESULT OpenRowset(DBPROPSET *pPropSet = NULL)  
   {  
HRESULT hr = Open(m_session, "Authors", pPropSet);  
#ifdef _DEBUG  
      if(FAILED(hr))  
         AtlTraceErrorRecords(hr);  
#endif  
      return hr;  
   }  
   void CloseAll()  
   {  
      Close();  
      CloseDataSource();  
   }  
};  
```  
  
## <a name="see-also"></a>関連項目  
 [OLE DB コンシューマー属性します。](../../windows/ole-db-consumer-attributes.md)   
 [属性のチュートリアル](https://msdn.microsoft.com/73df1d5d-261a-4521-98fb-06dcbf5ec0d0)
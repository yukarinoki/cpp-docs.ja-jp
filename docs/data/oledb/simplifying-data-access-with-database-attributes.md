---
title: データベース属性によるデータ アクセスの簡略化 |Microsoft ドキュメント
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
ms.openlocfilehash: e665369f292a646353d1a180661982ce4c902665
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="simplifying-data-access-with-database-attributes"></a>データベース属性によるデータ アクセスの簡略化
このトピックでは、データベース操作を簡素化するデータベースの属性の使用を示します。  
  
 データベースから情報にアクセスする基本的な方法では、データベース内のコマンド (またはテーブル) クラスと特定のテーブルのユーザー レコード クラスを作成します。 データベースの属性では、いくつかを行うには以前に配置したテンプレートの宣言の簡略化します。  
  
 次のセクションでは、データベースの属性の使用を示すためは、次の 2 つの同等のテーブルとユーザー レコード クラス宣言の操作を表示する: 最初の属性を使用して、2 つ目は、OLE DB テンプレートを使用します。 このような宣言コードは通常 authors.h テーブルまたはコマンドのオブジェクトに対して指定されたヘッダー ファイルなどです。  
  
 2 つのファイルを比較すると、属性を使用するがどれだけ単純がわかります。 相違点の一部は。  
  
-   属性を使用して、だけ宣言する必要が 1 つのクラス:`CAuthors`テンプレートを使用して 2 つを宣言しているときに、:`CAuthorsNoAttrAccessor`と`CAuthorsNoAttr`です。  
  
-   `db_source`属性付きのバージョンでの呼び出しは、`OpenDataSource()`テンプレートの宣言に呼び出します。  
  
-   **Db_table**属性付きのバージョンでの呼び出しは、次のテンプレートの宣言に相当します。  
  
    ```  
    class CAuthorsNoAttr : public CTable<CAccessor<CAuthorsNoAttrAccessor>>  
    ```  
  
-   **Db_column**属性付きのバージョンでの呼び出しは、列マップに相当する (を参照してください`BEGIN_COLUMN_MAP ... END_COLUMN_MAP`) テンプレートの宣言にします。  
  
 属性は、ユーザー レコード クラスの宣言を挿入します。 ユーザー レコード クラスは`CAuthorsNoAttrAccessor`テンプレートの宣言にします。 場合は、テーブル クラス`CAuthors`、挿入されたユーザー レコード クラスの名前は`CAuthorsAccessor`、挿入されたコードでは、宣言だけを表示できます。 詳細についてを参照してください「Attribute-Injected ユーザー レコード クラス」[ユーザー レコード](../../data/oledb/user-records.md)です。  
  
 属性との両方でテンプレートを使ったコードを使用して行セット プロパティを設定する必要がありますに注意してください`CDBPropSet::AddProperty`です。  
  
 このトピックで説明する属性については、次を参照してください。 [OLE DB コンシューマー属性](../../windows/ole-db-consumer-attributes.md)です。  
  
## <a name="table-and-accessor-declaration-using-attributes"></a>テーブルおよびアクセサーの宣言属性の使用  
 次のコード呼び出し`db_source`と**db_table**テーブル クラスにします。 `db_source` 接続を使用するデータ ソースを指定します。 **db_table**テーブル クラスを宣言する適切なテンプレート コードを挿入します。 **db_column**列マップを指定して、アクセサーの宣言を挿入します。 ATL をサポートするすべてのプロジェクトで OLE DB コンシューマー属性を使用することができます。  
  
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
  
## <a name="table-and-accessor-declaration-using-templates"></a>テーブルおよびアクセサーの宣言にテンプレートを使用します。  
 テンプレートを使用したテーブルおよびアクセサーの宣言を次に示します。  
  
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
 [属性のチュートリアル](http://msdn.microsoft.com/en-us/73df1d5d-261a-4521-98fb-06dcbf5ec0d0)
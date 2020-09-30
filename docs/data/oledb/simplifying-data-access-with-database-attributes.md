---
title: データベース属性によるデータ アクセスの簡略化
ms.date: 10/19/2018
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
ms.openlocfilehash: faee3ea47a6d96b09729d9d4b5bfa21584096d31
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/29/2020
ms.locfileid: "91509474"
---
# <a name="simplifying-data-access-with-database-attributes"></a>データベース属性によるデータ アクセスの簡略化

このトピックでは、データベースの属性を使用してデータベース操作を簡略化する方法について説明します。

データベースから情報にアクセスする基本的な方法は、データベース内の特定のテーブルに対して、コマンド (またはテーブル) クラスとユーザーレコードクラスを作成することです。 データベース属性を使用すると、以前に実行していたテンプレート宣言の一部が簡略化されます。

データベース属性の使用方法を示すために、次のセクションでは、2つの同等のテーブルとユーザーレコードクラスの宣言を示します。1つは属性を使用し、もう1つは OLE DB テンプレートを使用します。 通常、このような宣言コードは、テーブルまたはコマンドオブジェクトのという名前のヘッダーファイルに配置されます (例、Authors. h)。

2つのファイルを比較することで、属性をどれほど簡単に使用できるかを確認できます。 違いは次のとおりです。

- 属性を使用する場合、1つのクラスを宣言するだけで済みます。 `CAuthors` テンプレートでは、との2つを宣言する必要があります `CAuthorsNoAttrAccessor` `CAuthorsNoAttr` 。

- `db_source`属性付きバージョンでの呼び出しは、 `OpenDataSource()` テンプレート宣言内の呼び出しに相当します。

- `db_table`属性付きバージョンでの呼び出しは、次のテンプレート宣言と同じです。

    ```cpp
    class CAuthorsNoAttr : public CTable<CAccessor<CAuthorsNoAttrAccessor>>
    ```

- `db_column`属性付きバージョンでの呼び出しは、テンプレート宣言の列マップに相当します (「」を参照してください `BEGIN_COLUMN_MAP ... END_COLUMN_MAP` )。

属性によって、ユーザーレコードクラスの宣言が挿入されます。 ユーザーレコードクラスは、テンプレート宣言のと同じです `CAuthorsNoAttrAccessor` 。 テーブルクラスがの場合 `CAuthors` 、挿入されたユーザーレコードクラスにはという名前が付けられ、挿入され `CAuthorsAccessor` たコードでのみ、その宣言を表示できます。 詳細については、「 [ユーザーレコード](../../data/oledb/user-records.md)」の「属性で挿入されたユーザーレコードクラス」を参照してください。

属性付きコードとテンプレート化されたコードの両方で、を使用して行セットプロパティを設定する必要があり `CDBPropSet::AddProperty` ます。

このトピックで説明する属性の詳細については、「 [OLE DB コンシューマー属性](../../windows/attributes/ole-db-consumer-attributes.md)」を参照してください。

> [!NOTE]
> 以下の `include` 例をコンパイルするには、次のステートメントが必要です。

> ```cpp
> #include <atlbase.h>
> #include <atlplus.h>
> #include <atldbcli.h>
> ```

## <a name="table-and-accessor-declaration-using-attributes"></a>属性を使用したテーブルとアクセサーの宣言

次のコードは `db_source` 、 `db_table` table クラスでおよびを呼び出します。 `db_source` 使用するデータソースと接続を指定します。 `db_table` テーブルクラスを宣言するための適切なテンプレートコードを挿入します。 `db_column` 列マップを指定し、アクセサー宣言を挿入します。 ATL をサポートするプロジェクトでは OLE DB コンシューマー属性を使用できます。

属性を使用したテーブルとアクセサーの宣言を次に示します。

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
   DBSTATUS m_dwAuIDStatus;
   DBSTATUS m_dwAuthorStatus;
   DBSTATUS m_dwYearBornStatus;
   DBLENGTH m_dwAuIDLength;
   DBLENGTH m_dwAuthorLength;
   DBLENGTH m_dwYearBornLength;
   [db_column("1", status = "m_dwAuIDStatus", length = "m_dwAuIDLength")] LONG m_AuID;
   [db_column("2", status = "m_dwAuthorStatus", length = "m_dwAuthorLength")] TCHAR m_Author[51];
   [db_column("3", status = "m_dwYearBornStatus", length = "m_dwYearBornLength")] SHORT m_YearBorn;
   void GetRowsetProperties(CDBPropSet* pPropSet)
   {
      pPropSet->AddProperty(DBPROP_CANFETCHBACKWARDS, true);
      pPropSet->AddProperty(DBPROP_CANSCROLLBACKWARDS, true);
      pPropSet->AddProperty(DBPROP_IRowsetChange, true);
   }
};
```

## <a name="table-and-accessor-declaration-using-templates"></a>テンプレートを使用したテーブルとアクセサーの宣言

テンプレートを使用したテーブルとアクセサーの宣言を次に示します。

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

[OLE DB のコンシューマー属性](../../windows/attributes/ole-db-consumer-attributes.md)

---
title: 単純なコンシューマーの実装
ms.date: 10/12/2018
helpviewer_keywords:
- clients, creating
- OLE DB consumers, implementing
ms.assetid: 13828167-23a4-4e94-8b6c-878262fda464
ms.openlocfilehash: 141c2f48b2069410b14f969171f2b1c185a0506e
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50669028"
---
# <a name="implementing-a-simple-consumer"></a>単純なコンシューマーの実装

次のトピックで作成されたファイルを編集する方法を説明する、 **MFC アプリケーション ウィザード**と**ATL OLE DB コンシューマー ウィザード**単純なコンシューマーを作成します。 この例では、次の部分があります。

- [コンシューマーによるデータの取得](#retrieve)データベース テーブルからすべてのデータ、1 行ずつを読み取るコンシューマーのコードを実装する方法を示します。

- [ブックマークのサポートを追加するコンシューマーに](#bookmark)コンシューマーにブックマークのサポートを追加する方法を示します。

> [!NOTE]
> このセクションで説明されているコンシューマー アプリケーションをテストに使用できる、`MyProv`と`Provider`サンプル プロバイダー。

> [!NOTE]
> テストするためのコンシューマー アプリケーションを構築する`MyProv`(で説明されている、同じプロバイダー[単純な読み取り専用プロバイダーの強化](../../data/oledb/enhancing-the-simple-read-only-provider.md))、」の説明に従って、ブックマークのサポートを含める必要があります[へのブックマーク サポートの追加、コンシューマー](#bookmark)します。

## <a name="retrieve" ></a> コンシューマーによるデータの取得

### <a name="to-modify-the-console-application-to-use-the-ole-db-consumer"></a>OLE DB コンシューマーを使用するコンソール アプリケーションを変更するには

1. `MyCons.cpp`、太字のテキストを次のように挿入してメインのコードを変更します。

    ```cpp
    // MyCons.cpp : Defines the entry point for the console application.
    //
    #include "stdafx.h"
    #include "Products.h"
    ...
    int main(int argc, char* argv[])
    {
       HRESULT hr = CoInitialize(NULL);   // Instantiate rowset
       CProducts rs;
       hr = rs.OpenAll();
       ATLASSERT(SUCCEEDED(hr ) );
       hr = rs.MoveFirst();   // Iterate through the rowset
       while(SUCCEEDED(hr) && hr != DB_S_ENDOFROWSET )   {      // Print out the column information for each row
         printf("Product ID: %d, Name: %s, Unit Price: %d, Quantity per Unit: %d, Units in Stock %d, Reorder Level %d\n",
           rs.m_ProductID, rs.m_ProductName, rs.m_UnitPrice, rs.m_QuantityPerUnit, rs.m_UnitsInStock, rs.m_ReorderLevel );
         hr = rs.MoveNext();   }
       rs.Close();
       rs.ReleaseCommand();
       CoUninitialize();

       return 0;
    }
    ```

## <a name="bookmark" ></a> コンシューマーへのブックマーク サポートの追加

ブックマークは、テーブル内の行を一意に識別する列です。 キーの列が通常とは限りません。これは、プロバイダー固有です。 このセクションでは、ブックマークのサポートを追加する方法を示します。 これを行うには、ユーザー レコード クラスの次の手順を実行する必要があります。

- ブックマークをインスタンス化します。 これらの型のオブジェクトは、 [CBookmark](../../data/oledb/cbookmark-class.md)します。

- ブックマーク列を設定して、プロバイダーから要求、`DBPROP_IRowsetLocate`プロパティ。

- 列マップを使用して、ブックマークのエントリを追加、 [BOOKMARK_ENTRY](../../data/oledb/bookmark-entry.md)マクロ。

前の手順では、ブックマークのサポートと作業に使用して、ブックマーク オブジェクトを指定します。 このコード例では、次のようにブックマークを示します。

- 書き込み用にファイルを開きます。

- ファイルの行ごとに、行セットのデータを出力します。

- 行セットのカーソルを呼び出すことで、ブックマークに移動[MoveToBookmark](../../data/oledb/crowset-movetobookmark.md)します。

- ファイルの末尾に追加すること、ブックマークが設定された行を出力します。

> [!NOTE]
> このコンシューマー アプリケーションを使用してテストする場合、`Provider`サンプル プロバイダー アプリケーションで、このセクションで説明されているブックマークのサポートをそのまま使用します。

### <a name="to-instantiate-the-bookmark"></a>ブックマークをインスタンス化するには

1. 型のオブジェクトを保持するために必要なアクセサー [CBookmark](../../data/oledb/cbookmark-class.md)します。 *NSize*パラメーター (通常、32 ビット プラットフォームの 4) および 64 ビット プラットフォームでの 8 バイトで、ブックマークのバッファーのサイズを指定します。 ユーザー レコード クラスの列のデータ メンバーには、次の宣言を追加します。

    ```cpp
    //////////////////////////////////////////////////////////////////////
    // Products.h
    class CProductsAccessor
    {
    public:
       CBookmark<4> m_bookmark;   // Add bookmark declaration
       LONG m_ProductID;
       ...
    ```

### <a name="to-request-a-bookmark-column-from-the-provider"></a>プロバイダーからブックマーク列を要求するには

1. 次のコードを追加、`GetRowsetProperties`ユーザー レコード クラスのメソッド。

    ```cpp
    // Set the DBPROP_IRowsetLocate property.
    void GetRowsetProperties(CDBPropSet* pPropSet)
    {
       pPropSet->AddProperty(DBPROP_CANFETCHBACKWARDS, true, DBPROPOPTIONS_OPTIONAL);
       pPropSet->AddProperty(DBPROP_CANSCROLLBACKWARDS, true, DBPROPOPTIONS_OPTIONAL);
       // Add DBPROP_IRowsetLocate property to support bookmarks   pPropSet->AddProperty(DBPROP_IRowsetLocate, true);
    }
    ```

### <a name="to-add-a-bookmark-entry-to-the-column-map"></a>列マップにブックマーク エントリを追加するには

1. ユーザー レコード クラス内の列マップには、次のエントリを追加します。

    ```cpp
    // Set a bookmark entry in the column map.
    BEGIN_COLUMN_MAP(CProductsAccessor)
       BOOKMARK_ENTRY(m_bookmark)   // Add bookmark entry
       COLUMN_ENTRY_LENGTH_STATUS(1, m_ProductID, m_dwProductIDLength, m_dwProductIDStatus)
       COLUMN_ENTRY_LENGTH_STATUS(2, m_ProductName, m_dwProductNameLength, m_dwProductNameStatus)
    ...
    END_COLUMN_MAP()
    ```

### <a name="to-use-a-bookmark-in-your-main-code"></a>メイン コード内のブックマークを使用するには

1. `MyCons.cpp`以前に次のようにメインのコードを変更、作成コンソール アプリケーションからのファイル。 ブックマークを使用するメインのコードは、独自のブックマーク オブジェクトをインスタンス化する必要があります (`myBookmark`)。 これは、アクセサーで 1 つから別のブックマーク (`m_bookmark`)。

    ```cpp
    ///////////////////////////////////////////////////////////////////////
    // MyCons.cpp : Defines the entry point for the console application.
    //

    #include "stdafx.h"
    #include "Products.h"
    #include <iostream>
    #include <fstream>
    using namespace std;

    int _tmain(int argc, _TCHAR* argv[])
    {
       HRESULT hr = CoInitialize(NULL);

       // Instantiate rowset
       CProducts rs;

       hr = rs.OpenAll();
       hr = rs.MoveFirst();

       // Cast CURRENCY m_UnitPrice to a long value
       LONGLONG lPrice = rs.m_UnitPrice.int64;

       // Open file output.txt for writing in overwrite mode
       ofstream outfile( "C:\\output.txt", ios::out );

       if (!outfile)      // Test for invalid file
          return -1;

       // Instantiate a bookmark object myBookmark for the main code
       CBookmark<4> myBookmark;
       int nCounter = 0;

       // Iterate through the rowset and output column data to output.txt row by row
       // In the file, mark the beginning of this set of data:
       outfile << "initial row dump" << endl;
       while(SUCCEEDED(hr) && hr != DB_S_ENDOFROWSET )
       {
          nCounter++;
          if(nCounter == 5 )
             myBookmark = rs.m_bookmark;
          // Output the column information for each row:
          outfile << rs.m_ProductID << rs.m_ProductName << lPrice << rs.m_QuantityPerUnit << rs.m_UnitsInStock << rs.m_ReorderLevel << endl;
          hr = rs.MoveNext();
       }

       // Move cursor to bookmark
       hr = rs.MoveToBookmark(myBookmark);

       // Iterate through the rowset and output column data to output.txt row by row
       // In the file, mark the beginning of this set of data:
       outfile << "row dump starting from bookmarked row" << endl;
       while(SUCCEEDED(hr) && hr != DB_S_ENDOFROWSET )
       {
          // Output the column information for each row
          outfile << rs.m_ProductID << rs.m_ProductName << lPrice << rs.m_QuantityPerUnit << rs.m_UnitsInStock << rs.m_ReorderLevel << endl;
          hr = rs.MoveNext();
       }

       rs.CloseAll();
       CoUninitialize();

       return 0;
    }
    ```

ブックマークの詳細については、次を参照してください。[ブックマークを使って](../../data/oledb/using-bookmarks.md)します。 ブックマークの例を示しますも[行セットの更新](../../data/oledb/updating-rowsets.md)します。

## <a name="see-also"></a>関連項目

[ウィザードを使用した OLE DB コンシューマーの作成](../../data/oledb/creating-an-ole-db-consumer-using-a-wizard.md)

---
title: 単純なコンシューマーの実装 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- clients, creating
- OLE DB consumers, implementing
ms.assetid: 13828167-23a4-4e94-8b6c-878262fda464
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 841d982090503a1e72b1d6798a5f0eecdb543fe2
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33112564"
---
# <a name="implementing-a-simple-consumer"></a>単純なコンシューマーの実装
次のトピックでは、単純なコンシューマーを作成するには、MFC アプリケーション ウィザードと ATL OLE DB コンシューマー ウィザードによって作成されたファイルを編集する方法を示します。 この例では、次の部分があります。  
  
-   「コンシューマーによるデータの取得」をデータベース テーブルからすべてのデータを行単位でを読み取ることがコンシューマーにコードを実装する方法を示しています。  
  
-   「追加ブックマーク サポート コンシューマーに」を示します、コンシューマーへのブックマーク サポートを追加する方法。  
  
-   「コンシューマーに XML のサポートを追加」は、XML データとして取得した行セットのデータを出力するコンシューマー コードを変更する方法を示します。  
  
> [!NOTE]
>  このセクションで説明されているコンシューマー アプリケーションを使用して、MyProv およびプロバイダーのサンプルのプロバイダーをテストすることができます。  
  
> [!NOTE]
>  MyProv をテストするためのコンシューマー アプリケーションをビルドする (同じプロバイダーの記載[単純な読み取り専用プロバイダーの向上](../../data/oledb/enhancing-the-simple-read-only-provider.md))、「のブックマーク サポートの追加、コンシューマーにします」」の説明に従って、ブックマーク サポートを含める必要があります。  
  
> [!NOTE]
>  プロバイダーをテストするためのコンシューマー アプリケーションをビルドするには、「のブックマーク サポート コンシューマーへの追加」で説明されているブックマーク サポートを省略して"XML サポートの追加コンシューマーにします"スキップと  
  
## <a name="retrieving-data-with-the-consumer"></a>コンシューマーによるデータの取得  
  
#### <a name="to-modify-the-console-application-to-use-the-ole-db-consumer"></a>OLE DB コンシューマーを使用するコンソール アプリケーションを変更するには  
  
1.  MyCons.cpp では、次のように、太字のテキストを挿入することで、メイン コードを変更します。  
  
    ```  
    // MyCons.cpp : Defines the entry point for the console application.  
    //  
    #include "stdafx.h"  
    #include "Products.h"  
    ...  
    int main(int argc, char* argv[])  
    {  
 HRESULT hr = CoInitialize(NULL);   // Instantiate rowset   CProducts rs;   hr = rs.OpenAll();   ATLASSERT(SUCCEEDED(hr ) );   hr = rs.MoveFirst();   // Iterate through the rowset   while(SUCCEEDED(hr) && hr != DB_S_ENDOFROWSET )   {      // Print out the column information for each row      printf("Product ID: %d, Name: %s, Unit Price: %d, Quantity per Unit: %d, Units in Stock %d, Reorder Level %d\n",             rs.m_ProductID, rs.m_ProductName, rs.m_UnitPrice, rs.m_QuantityPerUnit, rs.m_UnitsInStock, rs.m_ReorderLevel );      hr = rs.MoveNext();   }   rs.Close();   rs.ReleaseCommand();   CoUninitialize();  
  
       return 0;  
    }  
    ```  
  
## <a name="adding-bookmark-support-to-the-consumer"></a>コンシューマーへのブックマーク サポートの追加  
 ブックマークは、テーブル内の行を一意に識別する列です。 通常、キー列は常にではありません。これは、プロバイダーに固有です。 このセクションでは、ブックマーク サポートを追加する方法を示します。 これを行うには、ユーザー レコード クラスに次の操作が必要です。  
  
-   ブックマークのインスタンスを作成します。 これらの型のオブジェクトは、 [CBookmark](../../data/oledb/cbookmark-class.md)です。  
  
-   ブックマーク列を設定して、プロバイダーから要求、 **DBPROP_IRowsetLocate**プロパティです。  
  
-   使用して列マップにブックマーク エントリを追加、 [BOOKMARK_ENTRY](../../data/oledb/bookmark-entry.md)マクロです。  
  
 前の手順では、ブックマーク サポートされ、対象のブックマーク オブジェクトを提供します。 このコード例では、次のようにブックマークを示します。  
  
-   書き込み用にファイルを開きます。  
  
-   ファイルの行ごとに、行セットのデータを出力します。  
  
-   行セット カーソルを呼び出すことによって、ブックマークに移動する[MoveToBookmark](../../data/oledb/crowset-movetobookmark.md)です。  
  
-   ファイルの末尾に追加、ブックマークが付けられた行を出力します。  
  
> [!NOTE]
>  このコンシューマー アプリケーションを使用して、プロバイダーのサンプルのプロバイダー アプリケーションをテストする場合は、このセクションで説明したブックマーク サポートを省略します。  
  
#### <a name="to-instantiate-the-bookmark"></a>ブックマークのインスタンスを作成するには  
  
1.  型のオブジェクトを格納する必要があるアクセサー [CBookmark](../../data/oledb/cbookmark-class.md)です。 `nSize`パラメーターは、(通常、4 つの 32 ビット プラットフォーム) と 64 ビット プラットフォームの場合は 8 バイトでブックマーク バッファーのサイズを指定します。 ユーザー レコード クラスの列のデータ メンバーには、次の宣言を追加します。  
  
    ```  
    //////////////////////////////////////////////////////////////////////  
    // Products.h  
    class CProductsAccessor  
    {  
    public:  
       CBookmark<4> m_bookmark;   // Add bookmark declaration  
       LONG m_ProductID;  
       ...  
    ```  
  
#### <a name="to-request-a-bookmark-column-from-the-provider"></a>プロバイダーからブックマーク列を要求するには  
  
1.  次のコードを追加、`GetRowsetProperties`ユーザー レコード クラスのメソッド。  
  
    ```  
    // Set the DBPROP_IRowsetLocate property.  
    void GetRowsetProperties(CDBPropSet* pPropSet)  
    {  
       pPropSet->AddProperty(DBPROP_CANFETCHBACKWARDS, true, DBPROPOPTIONS_OPTIONAL);  
       pPropSet->AddProperty(DBPROP_CANSCROLLBACKWARDS, true, DBPROPOPTIONS_OPTIONAL);  
       // Add DBPROP_IRowsetLocate property to support bookmarks   pPropSet->AddProperty(DBPROP_IRowsetLocate, true);  
    }  
    ```  
  
#### <a name="to-add-a-bookmark-entry-to-the-column-map"></a>列マップにブックマーク エントリを追加するには  
  
1.  ユーザー レコード クラス内の列マップには、次のエントリを追加します。  
  
    ```  
    // Set a bookmark entry in the column map.  
    BEGIN_COLUMN_MAP(CProductsAccessor)  
       BOOKMARK_ENTRY(m_bookmark)   // Add bookmark entry  
       COLUMN_ENTRY_LENGTH_STATUS(1, m_ProductID, m_dwProductIDLength, m_dwProductIDStatus)  
       COLUMN_ENTRY_LENGTH_STATUS(2, m_ProductName, m_dwProductNameLength, m_dwProductNameStatus)  
    ...  
    END_COLUMN_MAP()  
    ```  
  
#### <a name="to-use-a-bookmark-in-your-main-code"></a>メイン コード内のブックマークで使用するには  
  
1.  以前に作成したコンソール アプリケーションから MyCons.cpp ファイルでは、次のように主要なコードを変更します。 メイン コードをブックマークを使用するのには、独自のブックマークのオブジェクトをインスタンス化する必要があります (`myBookmark`) です。 これは、アクセサー内の 1 つから別のブックマーク (`m_bookmark`)。  
  
    ```  
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
             myBookmark = rs.bookmark;  
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
  
 ブックマークの詳細については、次を参照してください。[を使用してブックマーク](../../data/oledb/using-bookmarks.md)です。 ブックマークの例を示しますも[行セットの更新](../../data/oledb/updating-rowsets.md)です。  
  
## <a name="adding-xml-support-to-the-consumer"></a>コンシューマーへの XML のサポートの追加  
 説明したよう[XML データにアクセスする](../../data/oledb/accessing-xml-data.md)、データ ソースから XML データを取得する 2 つの方法: を使用して[CStreamRowset](../../data/oledb/cstreamrowset-class.md)またはを使用して[CXMLAccessor](../../data/oledb/cxmlaccessor-class.md)です。 この例では`CStreamRowset`、する方が効率的ですが、このサンプル アプリケーションを実行するコンピューターで実行されている SQL Server 2000 が必要です。  
  
#### <a name="to-modify-the-command-class-to-inherit-from-cstreamrowset"></a>CStreamRowset から継承するコマンド クラスを変更するには  
  
1.  コンシューマー アプリケーションで、以前に作成した、変更、`CCommand`を指定する宣言`CStreamRowset`次のように、行セットとしてクラスします。  
  
    ```  
    class CProducts : public CCommand<CAccessor<CProductsAccessor>, CStreamRowset >  
    ```  
  
#### <a name="to-modify-the-main-code-to-retrieve-and-output-the-xml-data"></a>取得し、XML データを出力するには、メイン コードを変更するには  
  
1.  以前に作成したコンソール アプリケーションから MyCons.cpp ファイルでは、次のように主要なコードを変更します。  
  
    ```  
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
  
       // Add variable declarations for the Read method to handle sequential stream data  
       CHAR buffer[1001];  // Pointer to buffer into which data stream is read  
       ULONG cbRead;       // Actual number of bytes read from the data stream  
  
       hr = rs.OpenAll();  
  
       // Open file output.txt for writing in overwrite mode  
       ofstream outfile( "C:\\output.txt", ios::out );  
  
       if (!outfile)      // Test for invalid file  
          return -1;  
  
       // The following loop reads 1000 bytes of the data stream at a time   
       // until it reaches the end of the data stream  
       for (;;)  
       {  
          // Read sequential stream data into buffer  
    HRESULT hr = rs.m_spStream->Read(buffer, 1000, &cbRead);  
          if (FAILED (hr))  
             break;  
          // Output buffer to file  
          buffer[cbRead] = 0;  
          outfile << buffer;  
          // Test for end of data stream  
          if (cbRead < 1000)  
             break;  
       }  
  
       rs.CloseAll();  
       CoUninitialize();  
  
       return 0;  
    }  
    ```  
  
## <a name="see-also"></a>関連項目  
 [ウィザードを使用した OLE DB コンシューマーの作成](../../data/oledb/creating-an-ole-db-consumer-using-a-wizard.md)
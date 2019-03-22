---
title: Visual C++ でのデータ アクセス
ms.date: 03/28/2017
helpviewer_keywords:
- Visual C++, data access applications
- databases [C++]
- OLE DB [C++], data access technologies
- data [C++], data access technologies
- data access [C++], class libraries for databases
ms.assetid: 95da6237-bbe2-480a-ae50-3a520051ceff
ms.openlocfilehash: 7a222100cc7e13ee78f01cf4bb9c376af15f9b0e
ms.sourcegitcommit: c1f646c8b72f330fa8cf5ddb0f8f261ba10d16f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/21/2019
ms.locfileid: "58328780"
---
# <a name="data-access-in-visual-c"></a>Visual C++ でのデータ アクセス

ほぼすべてのデータベース製品 (SQL および NoSQL) には、ネイティブ C++ アプリケーション用のインターフェイスが用意されています。 業界標準のインターフェイスは ODBC です。ODBC は主要な SQL データベース製品と多数の NoSQL 製品でサポートされています。 Microsoft 以外の製品の詳細については、ベンダーにお問い合わせください。 さまざまなライセンス条項のサードパーティのライブラリも使用できます。

Microsoft は、2011 年以降、オンプレミスとクラウドの両方で Microsoft SQL Server データベースに接続するネイティブ アプリケーションの標準として ODBC を調整してきました。 詳細については、「[データ アクセス プログラミング \(MFC-ATL\)](data-access-programming-mfc-atl.md)」を参照してください。 C++/CLI ライブラリでは、ネイティブ ODBC ドライバーまたは ADO.NET を使用できます。 詳細については、「[ADO.NET によるデータ アクセス (C++/CLI)](../dotnet/data-access-using-adonet-cpp-cli.md)」と「[Visual Studio でのデータ アクセス](https://docs.microsoft.com/visualstudio/data-tools/accessing-data-in-visual-studio)」を参照してください。

## <a name="in-this-section"></a>このセクションの内容

[データ アクセス プログラミング (MFC/ATL)](data-access-programming-mfc-atl.md)<br/>
Visual C++ を使用したレガシ データ アクセス プログラミングについて説明します。このプログラミングには、データベース API での処理が簡単になるように、ATL (Active Template Class Library)、MFC (Microsoft Foundation Class) ライブラリなどのクラス ライブラリの 1 つを使用することをお勧めします。

[ODBC (Open Database Connectivity)](odbc/open-database-connectivity-odbc.md)<br/>
MFC (Microsoft Foundation Class) ライブラリには、ODBC (Open Database Connectivity) を使用したプログラミング用のクラスが用意されています。

[OLE DB プログラミング](oledb/ole-db-programming.md)<br/>
具体的には、リンク サーバーに対してプログラミングするときに一部のシナリオで引き続き必要なほとんどの場合のレガシー インターフェイス。

## <a name="related-topics"></a>関連トピック

[C および C++ を使用して SQL Database に接続します。](/azure/sql-database/sql-database-develop-cplusplus-simple)<br/>
C または C++ アプリケーションから Azure SQL Database に接続します。

[C++ 用 Microsoft Azure Storage クライアント ライブラリ](https://github.com/Azure/azure-storage-cpp)<br/>
[Azure Storage](/azure/storage/storage-introduction) は、顧客のニーズに合う耐久性、可用性、スケーラビリティを必要とする最新のアプリケーション向けのクラウド ストレージ ソリューションです。 C++ 用 Azure Storage クライアント ライブラリを使用して C++ から Azure Storage に接続します。

[ODBC Driver 13.1 for SQL Server の Windows リリース](https://blogs.msdn.microsoft.com/sqlnativeclient/2016/08/01/announcing-the-odbc-driver-13-1-for-sql-server)<br/>
最新の ODBC ドライバーには、C/C++ ベースのアプリケーション向けの Microsoft SQL Server 2016 Microsoft Azure SQL Database に対する堅牢なデータ アクセス機能があります。 常に暗号化などの機能のサポート、Azure Active Directory、および AlwaysOn 可用性グループを提供します。 また、Mac OS と Linux でも使用できます。

[SQL Server Native Client](/sql/relational-databases/native-client/sql-server-native-client-programming)<br/>
SQL Server Native Client は、単体のデータ アクセス アプリケーション プログラミング インターフェイス (API) です。OLE DB と ODBC の両方で使用され、SQL Server 2005 から SQL Server 2014 をサポートしています。 新しいアプリケーションでは、ODBC Driver 13.1 for SQL Server を使用することをお勧めします。

[Microsoft Azure C および C++ デベロッパー センター](https://azure.microsoft.com/develop/cpp/)<br/>
Azure を使用すると、柔軟性、スケーラビリティ、信頼性の高い C++ アプリケーションを好みのツールで容易に構築できます。

[C++ から Blob Storage を使用する方法](https://docs.microsoft.com/azure/storage/storage-c-plus-plus-how-to-use-blobs)<br/>
Azure BLOB Storage は、非構造化データをオブジェクト/BLOB としてクラウドに格納するサービスです。 Blob Storage は、ドキュメント、メディア ファイル、アプリケーション インストーラーなど、任意の種類のテキストまたはバイナリ データを格納できます。 Blob Storage は、オブジェクト ストレージとも呼ばれます。

[ ODBC プログラマ リファレンス](https://docs.microsoft.com/sql/odbc/reference/odbc-programmer-s-reference)<br/>
ODBC インターフェイスは、C プログラミング言語で使用するために設計されています。 ODBC インターフェイスの使用では、3 つの領域に します。SQL ステートメント、ODBC 関数呼び出し、C プログラミングします。

## <a name="see-also"></a>関連項目

[Visual C++](../visual-cpp-in-visual-studio.md)

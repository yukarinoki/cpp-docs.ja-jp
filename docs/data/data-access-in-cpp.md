---
title: Visual C でのデータ アクセス |Microsoft ドキュメント
ms.custom: ''
ms.date: 03/28/2017
ms.technology:
- cpp-data
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Visual C++, data access applications
- databases [C++]
- OLE DB [C++], data access technologies
- data [C++], data access technologies
- data access [C++], class libraries for databases
ms.assetid: 95da6237-bbe2-480a-ae50-3a520051ceff
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: bb74d27af485f765e1330bc83ab196e1d9ba6b5c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="data-access-in-visual-c"></a>Visual C++ でのデータ アクセス

ほぼすべてのデータベース製品 (SQL および NoSQL) には、ネイティブ C++ アプリケーション用のインターフェイスが用意されています。 業界標準のインターフェイスは ODBC です。ODBC は主要な SQL データベース製品と多数の NoSQL 製品でサポートされています。 Microsoft 以外の製品の詳細については、ベンダーにお問い合わせください。 さまざまなライセンス条項のサードパーティのライブラリも使用できます。

Microsoft は、2011 年以降、オンプレミスとクラウドの両方で Microsoft SQL Server データベースに接続するネイティブ アプリケーションの標準として ODBC を調整してきました。 詳細については、「[データ アクセス プログラミング \(MFC-ATL\)](data-access-programming-mfc-atl.md)」を参照してください。 C++/CLI ライブラリでは、ネイティブ ODBC ドライバーまたは ADO.NET を使用できます。 詳細については、「[ADO.NET によるデータ アクセス (C++/CLI)](/dotnet/data-access-using-adonet-cpp-cli.md)」と「[Visual Studio でのデータ アクセス](https://docs.microsoft.com/visualstudio/data-tools/accessing-data-in-visual-studio)」を参照してください。

## <a name="in-this-section"></a>このセクションの内容
[データ アクセス プログラミング (MFC/ATL)](data-access-programming-mfc-atl.md)説明レガシ データ アクセス方法をお勧めすることが、ATL Active Template Class ライブラリ () または Microsoft Foundation Class (MFC) ライブラリなどのクラス ライブラリのいずれかを使用して、Visual C でのプログラミングこれには、データベース Api での処理が簡略化します。

[Database Connectivity (ODBC) を開く](odbc/open-database-connectivity-odbc.md)Microsoft Foundation Classes (MFC) ライブラリでのプログラミングとオープン データベース コネクティビティ) クラスを提供します。

[OLE DB プログラミング](oledb/ole-db-programming.md)特にに対してプログラミングを行っているときにも一部のシナリオで必要とする従来のほとんどの場合、インターフェイス リンク サーバー。

## <a name="related-topics"></a>関連トピック
[C および C++ を使用して SQL データベースへの接続](/azure/sql-database/sql-database-develop-cplusplus-simple)C または C++ アプリケーションから Azure SQL Database に接続します。

[C++ 用の Microsoft Azure ストレージ クライアント ライブラリ](https://github.com/Azure/azure-storage-cpp)
[Azure Storage](/azure/storage/storage-introduction)持続性、可用性、およびスケーラビリティのニーズに依存している最新のアプリケーション用のクラウド記憶域ソリューションには、顧客です。 C++ 用 Azure Storage クライアント ライブラリを使用して C++ から Azure Storage に接続します。

[Windows のリリースの SQL Server 用 ODBC Driver 13.1](https://blogs.msdn.microsoft.com/sqlnativeclient/2016/08/01/announcing-the-odbc-driver-13-1-for-sql-server)最新の ODBC ドライバーは、C/C++ ベースのアプリケーションの Microsoft SQL Server 2016 Microsoft Azure SQL データベースに堅牢なデータ アクセスを提供します。 常に暗号化などの機能のサポート、Azure Active Directory、および AlwaysOn 可用性グループを提供します。 また、Mac OS と Linux でも使用できます。     
 
[SQL Server Native Client](/sql/relational-databases/native-client/sql-server-native-client-programming) SQL Server Native Client は、スタンドアロンのデータ アクセス アプリケーション プログラミング インターフェイス (API)、OLE DB と ODBC では、SQL Server 2005 で SQL Server 2014 をサポートするために使用します。 新しいアプリケーションでは、ODBC Driver 13.1 for SQL Server を使用することをお勧めします。

[Microsoft Azure の C および C++ デベロッパー センター](https://azure.microsoft.com/develop/cpp/) Azure 簡単で柔軟性の向上、スケーラビリティと信頼性が気に入ったツールを使用する C++ アプリケーションをビルドします。    

[C++ から Blob ストレージの使用方法](https://docs.microsoft.com/azure/storage/storage-c-plus-plus-how-to-use-blobs)Azure Blob ストレージはオブジェクト/blob として、クラウド内の非構造化データを格納するサービスです。 Blob Storage は、ドキュメント、メディア ファイル、アプリケーション インストーラーなど、任意の種類のテキストまたはバイナリ データを格納できます。 Blob Storage は、オブジェクト ストレージとも呼ばれます。

[ ODBC プログラマ リファレンス](https://docs.microsoft.com/sql/odbc/reference/odbc-programmer-s-reference)の ODBC インターフェイスが、C プログラミング言語で使用するために設計されています。 ODBC インターフェイスは、SQL ステートメント、ODBC 関数呼び出し、C プログラミングという 3 つの領域で使用されます。

## <a name="see-also"></a>関連項目
[Visual C++](../visual-cpp-in-visual-studio.md)

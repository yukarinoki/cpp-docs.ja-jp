---
description: 詳細については、「データアクセスプログラミング (MFC/ATL)」を参照してください。
title: データアクセスプログラミング (MFC-ATL)
ms.date: 11/16/2018
helpviewer_keywords:
- MFC [C++], data access applications
- databases [C++], MFC
- OLE DB [C++], data access technologies
- data [C++], data access technologies
- data access [C++], class libraries for databases
ms.assetid: def97b2c-b5a6-445f-afeb-308050fd4852
ms.openlocfilehash: 7785eb65bd26c6c8bf4b60d5a8a919097627f20c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97136475"
---
# <a name="data-access-programming-mfcatl"></a>データ アクセス プログラミング (MFC/ATL)

長年にわたって、Visual C ++ ではデータベースを操作するいくつかの方法を提供してきました。 2011では、SQL Server 製品にネイティブコードからアクセスするための推奨テクノロジとして Open Database Connectivity (ODBC) に合わせて配置されていることがマイクロソフトに発表されました。 ODBC は業界標準であり、これを使用することで、複数のプラットフォームおよびデータ ソースでのコードの最大の移植性が得られます。 ほとんどの SQL データベース製品および多くの NoSQL 製品で ODBC がサポートされます。 ODBC は、低レベルの ODBC API を呼び出して直接使用できます。あるいは、MFC ODBC ラッパー クラス、またはサードパーティの C++ ラッパー ライブラリを使用することもできます。

OLE DB は、COM 仕様に基づく低レベルで高パフォーマンスの API であり、Windows でのみサポートされます。 プログラムで[リンク サーバー](/sql/relational-databases/linked-servers/linked-servers-database-engine)にアクセスする場合は、OLE DB を使用します。 ATL には OLE DB テンプレートが用意されており、カスタム OLE DB プロバイダーとコンシューマーを容易に作成できます。 Microsoft SQL Server の最新のプロバイダーについては、 [SQL Server 用の OLE DB ドライバー](/sql/connect/oledb/oledb-driver-for-sql-server)のドキュメントを参照してください。

## <a name="porting-data-applications"></a>データアプリケーションの移植

レガシアプリケーションで OLE DB または高レベルの ADO インターフェイスを使用して SQL Server に接続している場合は、最新の SQL Server 機能を利用するために、 [SQL Server 用の最新の OLE DB ドライバー](/sql/connect/oledb/oledb-driver-for-sql-server) への移行を検討する必要があります。 別の方法として、クロスプラットフォームの移植性や最新の SQL Server 機能が不要な場合は、Microsoft OLE DB Provider for ODBC (MSDASQL) を使用することもできます。  MSDASQL では、OLE DB と ADO (内部的に OLEDB を使用する) に構築されたアプリケーションから、ODBC ドライバーを介してデータ ソースにアクセスできます。 変換レイヤーと同様に、MSDASQL はデータベースのパフォーマンスに影響する可能性があります。 ご利用のアプリケーションに対する影響が大きいかどうかを判別するためにテストを行う必要があります。 MSDASQL は Windows オペレーティング システムに付属しており、Windows Server 2008 および Windows Vista SP1 が、64 ビット バージョンのテクノロジを含めるための最初の Windows リリースです。

C++ アプリケーションが ODBC 経由で SQL Server または Azure SQL Database に接続する場合は、 [最新の odbc ドライバー](/sql/connect/odbc/download-odbc-driver-for-sql-server)を使用する必要があります。

C++/CLI を使用する場合は、引き続き、通常どおり ADO.NET を使用できます。 詳細については、「[ADO.NET によるデータ アクセス (C++/CLI)](../dotnet/data-access-using-adonet-cpp-cli.md)」と「[Visual Studio でのデータ アクセス](/visualstudio/data-tools/accessing-data-in-visual-studio)」を参照してください。

- ODBC ラッパー クラスに加え、MFC では、Access データベースに接続するための Data Access Objects (DAO) ラッパー クラスも提供されます。  ただし、DAO は廃止されています。 CDaoDatabase または CDaoRecordset に基づくすべてのコードをアップグレードする必要があります。

Microsoft Windows でのデータ アクセス テクノロジの歴史の詳細については、ウィキペディアの「[Microsoft Data Access Components](https://en.wikipedia.org/wiki/Microsoft_Data_Access_Components)」を参照してください。

## <a name="see-also"></a>関連項目

[データ アクセス](data-access-in-cpp.md)<br/>
[Microsoft Open Database Connectivity (ODBC)](/sql/odbc/microsoft-open-database-connectivity-odbc)<br/>

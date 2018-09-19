---
title: データ アクセス プログラミング (MFC-ATL) |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- MFC [C++], data access applications
- databases [C++], MFC
- OLE DB [C++], data access technologies
- data [C++], data access technologies
- data access [C++], class libraries for databases
ms.assetid: def97b2c-b5a6-445f-afeb-308050fd4852
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: f48413ced50a2b7f086d67f910a7a8135129a2dd
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46111005"
---
# <a name="data-access-programming-mfcatl"></a>データ アクセス プログラミング (MFC/ATL)

長年にわたって、Visual C ++ ではデータベースを操作するいくつかの方法を提供してきました。 2011 年に Microsoft は、ネイティブ コードから SQL Server 製品にアクセスするのに望ましいテクノロジである ODBC に合わせて調整中であると発表しました。 ODBC は業界標準であり、これを使用することで、複数のプラットフォームおよびデータ ソースでのコードの最大の移植性が得られます。 ほとんどの SQL データベース製品および多くの NoSQL 製品で ODBC がサポートされます。 ODBC は、低レベルの ODBC API を呼び出して直接使用できます。あるいは、MFC ODBC ラッパー クラス、またはサードパーティの C++ ラッパー ライブラリを使用することもできます。 

OLE DB は、COM 仕様に基づく低レベルで高パフォーマンスの API であり、Windows でのみサポートされます。 プログラムで[リンク サーバー](/sql/relational-databases/linked-servers/linked-servers-database-engine)にアクセスする場合は、OLE DB を使用します。 ATL には OLE DB テンプレートが用意されており、カスタム OLE DB プロバイダーとコンシューマーを容易に作成できます。 最新バージョンの OLE DB は、SQL Native Client 11 に付属しています。  

レガシ アプリケーションで OLE DB またはより高レベルの ADO インターフェイスを使用して SQL Server に接続し、リンク サーバーにアクセスしない場合は、近い将来に ODBC に移行することを検討する必要があります。 クロスプラット フォームの移植性または最新の SQL Server の機能が不要な場合は、Microsoft OLE DB Provider for ODBC (MSDASQL) を使用できる可能性があります。  MSDASQL では、OLE DB と ADO (内部的に OLEDB を使用する) に構築されたアプリケーションから、ODBC ドライバーを介してデータ ソースにアクセスできます。 変換レイヤーと同様に、MSDASQL はデータベースのパフォーマンスに影響する可能性があります。 アプリケーションに対する影響が大きいかどうかを判別するためにテストする必要があります。 MSDASQL は Windows オペレーティング システムに付属しており、Windows Server 2008 および Windows Vista SP1 が、64 ビット バージョンのテクノロジを含めるための最初の Windows リリースです。

単一の DLL に OLE DB と ODBC ドライバーをパッケージ化する、SQL Native Client コンポーネント (SNAC) は、ODBC アプリケーションでは非推奨とされます。 SQL Server 2012 バージョンの SNAC (SQLNCLI11.DLL) は SQL Server 2016 に付属しています。他の SQL Server コンポーネントがこれに依存しているためです。 ただし、ODBC 経由で SQL Server または Azure SQL Database に接続する新しい C++ アプリケーションでは、[最新の ODBC ドライバー](https://docs.microsoft.com/sql/connect/odbc/download-odbc-driver-for-sql-server)を使用する必要があります。 詳細については、「[SQL Server Native Client プログラミング](/sql/relational-databases/native-client/sql-server-native-client-programming)」を参照してください。

C++/CLI を使用する場合は、引き続き、通常どおり ADO.NET を使用できます。 詳細については、「[ADO.NET によるデータ アクセス (C++/CLI)](../dotnet/data-access-using-adonet-cpp-cli.md)」と「[Visual Studio でのデータ アクセス](/visualstudio/data-tools/accessing-data-in-visual-studio)」を参照してください。  
  
- ODBC ラッパー クラスに加え、MFC では、Access データベースに接続するための Data Access Objects (DAO) ラッパー クラスも提供されます。  ただし、DAO は廃止されています。 CDaoDatabase または CDaoRecordset に基づくすべてのコードをアップグレードする必要があります。 

Microsoft Windows でのデータ アクセス テクノロジの歴史の詳細については、ウィキペディアの「[Microsoft Data Access Components](https://en.wikipedia.org/wiki/Microsoft_Data_Access_Components)」を参照してください。  

## <a name="see-also"></a>関連項目  

[データ アクセス](data-access-in-cpp.md)<br/>
[Microsoft Open Database Connectivity (ODBC)](https://docs.microsoft.com/sql/odbc/microsoft-open-database-connectivity-odbc)<br/>
[データ アクセス テクノロジのロードマップ](https://msdn.microsoft.com/library/ms810810.aspx)
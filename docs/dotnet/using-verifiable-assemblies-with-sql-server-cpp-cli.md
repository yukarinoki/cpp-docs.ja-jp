---
description: '詳細情報: SQL Server での検証可能なアセンブリの使用 (C++/CLI)'
title: SQL Server での確認可能なアセンブリの使用 (C++/CLI)
ms.date: 10/17/2018
helpviewer_keywords:
- verifiable assemblies [C++], with SQL Server
ms.assetid: 5248a60d-aa88-4ff3-b30a-b791c3ea2de9
ms.openlocfilehash: b155fb0360fb373f5931f51de3af557d06858a71
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97204200"
---
# <a name="using-verifiable-assemblies-with-sql-server-ccli"></a>SQL Server での確認可能なアセンブリの使用 (C++/CLI)

ダイナミックリンクライブラリ (Dll) としてパッケージ化された拡張ストアドプロシージャは、Visual C++ を使用して開発された関数を使用して SQL Server 機能を拡張する方法を提供します。 拡張ストアドプロシージャは、Dll 内の関数として実装されます。 関数だけでなく、拡張ストアドプロシージャでは、 [ユーザー定義型](../cpp/classes-and-structs-cpp.md) および集計関数 (SUM や AVG など) を定義することもできます。

クライアントが拡張ストアドプロシージャを実行すると、SQL Server は、拡張ストアドプロシージャに関連付けられている DLL を検索し、DLL を読み込みます。 SQL Server は、要求された拡張ストアドプロシージャを呼び出し、指定されたセキュリティコンテキストで実行します。 その後、拡張ストアドプロシージャは結果セットを渡し、パラメーターをサーバーに戻します。

SQL Server には、検証可能なアセンブリを SQL Server にインストールできるようにするための Transact-sql (T-sql) の拡張機能が用意されています。 SQL Server のアクセス許可セットでは、セキュリティコンテキストを指定します。セキュリティレベルは次のとおりです。

- 無制限モード: 独自のリスクでコードを実行します。コードは、検証可能なタイプセーフである必要はありません。

- セーフモード: 検証可能なタイプセーフなコードを実行します。/clr: safe を使用してコンパイルされます。

> [!IMPORTANT]
> Visual Studio 2015 では非推奨とされ、Visual Studio 2017 では、検証可能なプロジェクトを **/clr: pure** および **/clr: safe** で作成することはできません。 検証可能なコードが必要な場合は、コードを C# に変換することをお勧めします。

検証可能なアセンブリを作成して SQL Server に読み込むには、次のように、Transact-sql コマンド CREATE ASSEMBLY および DROP ASSEMBLY を使用します。

```sql
CREATE ASSEMBLY <assemblyName> FROM <'Assembly UNC Path'> WITH
  PERMISSION_SET <permissions>
DROP ASSEMBLY <assemblyName>
```

PERMISSION_SET コマンドは、セキュリティコンテキストを指定し、無制限、安全、または拡張の値を持つことができます。

また、CREATE FUNCTION コマンドを使用して、クラスのメソッド名にバインドすることもできます。

```sql
CREATE FUNCTION <FunctionName>(<FunctionParams>)
RETURNS returnType
[EXTERNAL NAME <AssemblyName>:<ClassName>::<StaticMethodName>]
```

## <a name="example"></a>例

次の SQL スクリプト (たとえば、"Myscript.sql" という名前を付けた場合) は、アセンブリを SQL Server に読み込んで、クラスのメソッドを使用できるようにします。

```sql
-- Create assembly without external access
drop assembly stockNoEA
go
create assembly stockNoEA
from
'c:\stockNoEA.dll'
with permission_set safe

-- Create function on assembly with no external access
drop function GetQuoteNoEA
go
create function GetQuoteNoEA(@sym nvarchar(10))
returns real
external name stockNoEA:StockQuotes::GetQuote
go

-- To call the function
select dbo.GetQuoteNoEA('MSFT')
go
```

Sql スクリプトは、SQL クエリアナライザーで対話的に実行することも、sqlcmd.exe ユーティリティを使用してコマンドラインで実行することもできます。 次のコマンドラインは、MyServer に接続し、既定のデータベースを使用し、信頼関係接続を使用して、Myscript.sql を入力し、MyResult.txt 出力します。

```cmd
sqlcmd -S MyServer -E -i myScript.sql -o myResult.txt
```

## <a name="see-also"></a>関連項目

[クラスと構造体](../cpp/classes-and-structs-cpp.md)

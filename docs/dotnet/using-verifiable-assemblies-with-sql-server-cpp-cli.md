---
title: SQL Server で検証可能なアセンブリの使用 (C + + CLI) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- verifiable assemblies [C++], with SQL Server
ms.assetid: 5248a60d-aa88-4ff3-b30a-b791c3ea2de9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: f172eea3108771e129636e9aa95d721d45c99609
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="using-verifiable-assemblies-with-sql-server-ccli"></a>SQL Server での確認可能なアセンブリの使用 (C++/CLI)
ダイナミック リンク ライブラリ (Dll) としてパッケージ化、拡張ストアド プロシージャは、Visual C で開発した関数を使用して SQL Server の機能を拡張する手段を提供します。 拡張ストアド プロシージャは、Dll 内で関数として実装されます。 以外の関数、拡張ストアド プロシージャも定義[ユーザー定義型](../cpp/classes-and-structs-cpp.md)と[集計関数](http://msdn.microsoft.com/en-us/de255454-f45e-4281-81f9-bc61893ac5da)(SUM、AVG など)。  
  
 クライアントは、拡張ストアド プロシージャを実行するとき、DLL の SQL Server 検索は、拡張ストアド プロシージャに関連付けられているされ、DLL を読み込みます。 SQL Server では、要求された拡張ストアド プロシージャを呼び出すし、指定したセキュリティ コンテキストで実行します。 拡張格納されているプロシージャ パスの結果が設定され、パラメーターをサーバーに返します。  
  
 [!INCLUDE[sqprsqlong](../dotnet/includes/sqprsqlong_md.md)] TRANSACT-SQL (T-SQL) は、SQL Server に検証可能なアセンブリをインストールすることを許可するのには、拡張機能を提供します。 SQL Server のアクセス許可セットは、次のセキュリティ レベルでセキュリティ コンテキストを指定します。  
  
-   制限なしのモード: ご自身の責任でコードを実行コードはタイプ セーフではありません。  
  
-   セーフ モード: 検証可能なタイプ セーフなコードの実行/clr:safe と共にコンパイル。  
  
 セーフ モードでは、タイプ セーフなする検証可能なアセンブリが実行される必要があります。  
  
 作成し、SQL Server に検証可能なアセンブリを読み込む、次のように TRANSACT-SQL コマンド CREATE ASSEMBLY と DROP ASSEMBLY を使用します。  
  
```  
CREATE ASSEMBLY <assemblyName> FROM <'Assembly UNC Path'> WITH   
  PERMISSION_SET <permissions>  
DROP ASSEMBLY <assemblyName>  
```  
  
 PERMISSION_SET コマンドでは、セキュリティ コンテキストを指定し、無制限、SAFE、または拡張の値を持つことができます。  
  
 さらに、クラスでメソッド名にバインドする関数の作成コマンドを使用することができます。  
  
```  
CREATE FUNCTION <FunctionName>(<FunctionParams>)  
RETURNS returnType  
[EXTERNAL NAME <AssemblyName>:<ClassName>::<StaticMethodName>]  
```  
  
## <a name="example"></a>例  
 次の SQL スクリプト (たとえば、名前付き"MyScript.sql") は、SQL Server にアセンブリを読み込みますおよびクラスのメソッドを使用可能します。  
  
```  
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
  
 SQL スクリプトは、SQL クエリ アナライザーまたは sqlcmd.exe ユーティリティを使用して、コマンドラインで、対話的に実行できます。 次のコマンド ライン MyServer に接続する、既定のデータベースを使用して、信頼関係接続を使用して、入力 MyScript.sql、され MyResult.txt を出力します。  
  
```  
sqlcmd -S MyServer -E -i myScript.sql -o myResult.txt  
```  
  
## <a name="see-also"></a>関連項目  
 [方法:/clr:safe に移行 (C + + CLI)](../dotnet/how-to-migrate-to-clr-safe-cpp-cli.md)   
 [クラスと構造体](../cpp/classes-and-structs-cpp.md)
---
title: ストアド プロシージャの使用
ms.date: 10/24/2018
helpviewer_keywords:
- OLE DB, stored procedures
- stored procedures, Visual C++
- stored procedures, about stored procedures
- OLE DB provider templates, stored procedures
- stored procedures, OLE DB
ms.assetid: 90507e4c-eca2-46c9-ad8c-07e10dc1d41b
ms.openlocfilehash: a7e97781d245e236c57942db15d61080d6418cfa
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80209275"
---
# <a name="using-stored-procedures"></a>ストアド プロシージャの使用

ストアド プロシージャは、データベースに保存される実行可能なオブジェクトです。 ストアドプロシージャの呼び出しは、SQL コマンドの呼び出しと似ています。 クライアントアプリケーションでステートメントを実行したり準備したりするのではなく、データソースでストアドプロシージャを使用すると、パフォーマンスの向上、ネットワークオーバーヘッドの削減、一貫性と正確性の向上など、いくつかの利点が得られます。

ストアドプロシージャは、任意の数 (0 を含む) の入力パラメーターまたは出力パラメーターを持つことができ、戻り値を渡すことができます。 パラメーター値を特定のデータ値としてハードコーディングすることも、パラメーターマーカー (疑問符 '? ') を使用することもできます。

> [!NOTE]
>  Visual C++を使用して作成した CLR SQL Server ストアドプロシージャは、`/clr:safe` コンパイラオプションを使用してコンパイルする必要があります。

OLE DB provider for SQL Server (SQLOLEDB) では、ストアドプロシージャがデータを返すために使用する次のメカニズムがサポートされています。

- プロシージャ内のすべての**SELECT**ステートメントによって結果セットが生成されます。

- プロシージャが出力パラメーターによってデータを返すことができる。

- プロシージャに整数のリターン コードを含めることができる。

> [!NOTE]
> OLE DB provider for Jet でストアドプロシージャを使用することはできません。このプロバイダーはストアドプロシージャをサポートしていないためです。クエリ文字列で使用できるのは定数だけです。

## <a name="see-also"></a>参照

[OLE DB コンシューマー テンプレートの操作](../../data/oledb/working-with-ole-db-consumer-templates.md)

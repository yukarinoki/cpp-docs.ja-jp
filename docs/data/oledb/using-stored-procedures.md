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
ms.openlocfilehash: 436c796b24b0fa498f2b3f45e848392635b22a34
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81376041"
---
# <a name="using-stored-procedures"></a>ストアド プロシージャの使用

ストアド プロシージャは、データベースに保存される実行可能なオブジェクトです。 ストアド プロシージャの呼び出しは、SQL コマンドの呼び出しと似ています。 クライアント アプリケーションでステートメントを実行または準備する代わりに、データ ソースでストアド プロシージャを使用すると、パフォーマンスの向上、ネットワーク オーバーヘッドの削減、一貫性と精度の向上など、いくつかの利点があります。

ストアド プロシージャは、任意の数 (0 を含む) 入力または出力パラメーターを持ち、戻り値を渡すことができます。 パラメーター値を特定のデータ値としてハードコーディングすることも、パラメーター・マーカー (疑問符 「?」) を使用することもできます。

> [!NOTE]
> Visual C++ を使用して作成された CLR SQL Server`/clr:safe`ストアド プロシージャは、コンパイラ オプションを使用してコンパイルする必要があります。

SQL Server (SQLOLEDB) の OLE DB プロバイダは、ストアド プロシージャがデータを返すために使用する次のメカニズムをサポートしています。

- プロシージャ内のすべての**SELECT**ステートメントは、結果セットを生成します。

- プロシージャが出力パラメーターによってデータを返すことができる。

- プロシージャに整数のリターン コードを含めることができる。

> [!NOTE]
> このプロバイダはストアド プロシージャをサポートしていないため、ストアド プロシージャを使用できません。定数はクエリ文字列でしか使用できません。

## <a name="see-also"></a>関連項目

[OLE DB コンシューマー テンプレートの使用](../../data/oledb/working-with-ole-db-consumer-templates.md)

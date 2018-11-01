---
title: 2.1 ディレクティブの書式
ms.date: 11/04/2016
ms.assetid: 918b6445-d35e-4176-9565-b045be941b4d
ms.openlocfilehash: 6ee977005d421a59e71f852be3d78a2caad9b45b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50629490"
---
# <a name="21-directive-format"></a>2.1 ディレクティブの書式

OpenMP ディレクティブの構文は、文法で正式に指定[付録 C](../../parallel/openmp/c-openmp-c-and-cpp-grammar.md)、非公式ようとします。

```
#pragma omp directive-name  [clause[ [,] clause]...] new-line
```

各ディレクティブが始まる **#pragma omp**を同じ名前を持つその他 (openmp OpenMP 以外またはベンダー拡張) プラグマ ディレクティブと競合する可能性を削減する。 ディレクティブの残りの部分では、コンパイラ ディレクティブの C および C++ の標準の規則に従います。 具体的には、前後に空白文字を使用することができます、  **#** ディレクティブで単語を分離することがあります空白文字を使用する必要があります。 プリプロセス トークンは、 **#pragma omp**マクロ置換影響を受けます。

ディレクティブは、大文字小文字を区別します。 ディレクティブの句が表示される順序が重要ではありません。 各句の説明に記載の制限に従い、必要に応じて、ディレクティブの句を繰り返すことがあります。 場合*変数一覧*変数のみを指定する必要がありますが、句に表示されます。 1 つだけ*ディレクティブ名*ディレクティブごとに指定できます。  たとえば、次のディレクティブは許可されていません。

```
/* ERROR - multiple directive names not allowed */
#pragma omp parallel barrier
```

OpenMP ディレクティブは、最大で 1 つの後続のステートメント、構造化ブロックである必要がありますに適用されます。
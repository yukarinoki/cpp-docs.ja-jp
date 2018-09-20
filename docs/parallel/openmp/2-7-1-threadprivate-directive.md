---
title: 2.7.1 threadprivate ディレクティブ |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 08e0b70f-5359-4607-b0ca-38c2d570d7b3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 31c9c70940b558d0b4cc3f77677665235417694d
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46398145"
---
# <a name="271-threadprivate-directive"></a>2.7.1 threadprivate ディレクティブ

`threadprivate`ディレクティブによって、名前付きのファイル スコープ、名前空間スコープ、または静的ブロック スコープの変数で指定された、*変数一覧*スレッドに対してプライベートです。 *変数リスト*不完全な型がない変数のコンマ区切り一覧を示します。 構文、`threadprivate`ディレクティブを次に示します。

```
#pragma omp threadprivate(variable-list) new-line
```

各コピーを`threadprivate`変数が初期化される 1 回、そのコピーが最初に参照する前にプログラムで、通常の方法で指定されていない点の位置 (つまり、プログラムの直列実行では、マスター コピーを初期化すると) とします。 明示的な初期化子でオブジェクトが参照されている場合、`threadprivate`変数、およびオブジェクトの値が、変数のコピーが最初に参照する前に変更し、動作は指定されていません。

ように、任意のプライベート変数のスレッドを参照しないでの別のスレッドのコピーを`threadprivate`オブジェクト。 シリアル領域や、プログラムのマスターの地域において、中には、参照をオブジェクトのマスター スレッドのコピーになります。

最初の並行領域内のデータ実行した後、`threadprivate`オブジェクトを並行領域のすべてのスレッドの数は変更されない場合にのみ、場合は、動的なスレッドのメカニズムを無効になっていますを保持することが保証されます。

制限、`threadprivate`ディレクティブは、次のとおり。

- A`threadprivate`ファイル スコープまたは名前空間スコープの変数のディレクティブは、任意の定義または宣言の外側に表示する必要があり、その一覧で、変数のいずれかに対するすべての参照の前に構文的する必要があります。

- 内の各変数、*変数一覧*の`threadprivate`ファイルまたは名前空間のスコープでディレクティブを指定する必要があります字句ディレクティブの前にあるファイルまたは名前空間のスコープで変数の宣言を参照してください。

- A`threadprivate`と入れ子になったスコープではなく、変数のスコープ内で静的ブロック スコープ変数のディレクティブを表示する必要があります。 構文的ディレクティブは、変数のいずれかにすべての参照を前に、リストにする必要があります。

- 内の各変数、*変数一覧*の`threadprivate`ディレクティブ ブロック スコープでは、字句ディレクティブの前にある同じスコープ内で変数の宣言を指す必要があります。 変数の宣言には、静的ストレージ クラス指定子を使用する必要があります。

- 変数がで指定されている場合、`threadprivate`ディレクティブを 1 つの翻訳単位で、これで指定する必要を`threadprivate`が宣言されている各翻訳単位でディレクティブ。

- A`threadprivate`を除くすべての句に変数がない必要があります、 `copyin`、 `copyprivate`、 `schedule`、 `num_threads`、または**場合**句。

- アドレスを`threadprivate`変数は、アドレスは一定ではありません。

- A`threadprivate`変数は不完全な型または参照型をしなければなりません。

- A`threadprivate`非 POD クラス型の変数は、明示的な初期化子で宣言されている場合、あいまいでないアクセス可能なコピー コンス トラクターにいる必要があります。

次の例では、方法、初期化子に表示される変数を変更する可能性が未定義の動作と補助オブジェクトおよびコピー コンス トラクターを使用してこの問題を回避する方法も示しています。

```
int x = 1;
T a(x);
const T b_aux(x); /* Capture value of x = 1 */
T b(b_aux);
#pragma omp threadprivate(a, b)

void f(int n) {
   x++;
   #pragma omp parallel for
   /* In each thread:
   * Object a is constructed from x (with value 1 or 2?)
   * Object b is copy-constructed from b_aux
   */
   for (int i=0; i<n; i++) {
      g(a, b); /* Value of a is unspecified. */
   }
}
```

## <a name="cross-references"></a>クロス リファレンス

- 動的なスレッドを参照してください[セクション 3.1.7](../../parallel/openmp/3-1-7-omp-set-dynamic-function.md) 39 ページ。

- `OMP_DYNAMIC` 環境変数を参照してください[セクション 4.3](../../parallel/openmp/4-3-omp-dynamic.md) [49] ページ。
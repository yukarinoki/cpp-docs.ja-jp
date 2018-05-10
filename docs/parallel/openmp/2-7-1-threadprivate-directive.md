---
title: 2.7.1 threadprivate ディレクティブ |Microsoft ドキュメント
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
ms.openlocfilehash: c9912ccbfa6f5773ec1e523245f75e675bb82244
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
---
# <a name="271-threadprivate-directive"></a>2.7.1 threadprivate ディレクティブ
`threadprivate`ディレクティブによって、ファイルの名前付きスコープ、名前空間スコープ、または静的ブロック スコープ変数で指定された、*変数一覧*スレッドに対してプライベートです。 *変数リスト*不完全な型を持たない変数のコンマ区切り一覧を示します。 構文、`threadprivate`ディレクティブは、次のようにします。  
  
```  
#pragma omp threadprivate(variable-list) new-line  
```  
  
 各コピー、`threadprivate`変数が初期化される 1 回、そのコピーが最初に参照する前にプログラムでは、通常の方法では指定されていない場所で (つまり、マスター コピーは、プログラムの直列実行で初期化するよう) とします。 明示的な初期化子でオブジェクトが参照されている場合、`threadprivate`変数、およびオブジェクトの値は、変数のコピーが最初に参照する前に変更し、動作は指定されていません。  
  
 参照するため、任意のプライベート変数をスレッド必要がありますいないの別のスレッドのコピー、`threadprivate`オブジェクト。 シリアル領域およびプログラムのマスターの地域では、参照はオブジェクトのマスター スレッドのコピーになります。  
  
 最初の並列領域のデータを実行した後、`threadprivate`オブジェクトが、スレッドの数がすべての並列領域の変更されない場合に場合は動的なスレッドのメカニズムを無効になっているのみを保持することが保証されます。  
  
 制限、`threadprivate`ディレクティブは、次のようにします。  
  
-   A`threadprivate`ファイル スコープまたは名前空間スコープの変数のディレクティブは、任意の定義または宣言の外に置く必要があり、その一覧で、変数のいずれかに対するすべての参照の前に構文的にする必要があります。  
  
-   内の各変数、*変数一覧*の`threadprivate`ファイルまたは名前空間のスコープでディレクティブを指定する必要がありますに構文的に、ディレクティブの前にあるファイルまたは名前空間のスコープで変数の宣言を参照してください。  
  
-   A`threadprivate`変数のスコープでは入れ子になったスコープではなく静的ブロック スコープ変数のディレクティブを指定します。 ディレクティブで、変数のいずれかに対するすべての参照を前に、そのリストにする必要があります構文的になります。  
  
-   内の各変数、*変数一覧*の`threadprivate`ディレクティブ ブロック スコープで必要がありますに構文的に、ディレクティブの前にある同一スコープ内の変数の宣言を参照してください。 変数の宣言には、静的ストレージ クラス指定子を使用する必要があります。  
  
-   変数がで指定されている場合、`threadprivate`ディレクティブを 1 つの翻訳単位で、これで指定されなければなりません、`threadprivate`宣言されている各翻訳単位でディレクティブです。  
  
-   A`threadprivate`を除く任意の句に変数がない必要があります、 `copyin`、 `copyprivate`、 `schedule`、 `num_threads`、または**場合**句。  
  
-   アドレス、`threadprivate`変数は、アドレス定数ではありません。  
  
-   A`threadprivate`変数は、不完全な型または参照型です。  
  
-   A`threadprivate`明示的な初期化子で宣言されている場合、非 POD クラス型の変数は、あいまいでないアクセス可能なコピー コンス トラクターを持つ必要があります。  
  
 次の例は、どのように初期化子に表示される変数を変更することができます未定義の動作とも補助オブジェクトとコピー コンス トラクターを使用してこの問題を回避する方法を示しています。  
  
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
  
-   動的なスレッドを参照してください[セクション 3.1.7](../../parallel/openmp/3-1-7-omp-set-dynamic-function.md)ページ 39 にします。  
  
-   `OMP_DYNAMIC` 環境変数を参照してください[セクション 4.3](../../parallel/openmp/4-3-omp-dynamic.md) 49 ページにします。
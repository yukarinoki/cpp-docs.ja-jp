---
title: 2.7.2.6 削減 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: e7630a15-2978-4dbe-a29b-3a46371a0151
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 05ed97968921692f69f2ff0040ae14dc41ef52b5
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46375603"
---
# <a name="2726-reduction"></a>2.7.2.6 reduction

この句に表示されるスカラー変数でリダクションを実行します*変数一覧*、演算子を含む*op*します。 構文、`reduction`句を次に示します。

> reduction(*op*: *variable-list*)

リダクションは、通常、次の形式のいずれかのステートメントに対して指定します。

> *x* = *x* *op* *expr*
> *x* *binop* =*expr*
> *x* = *expr* *op* *x* (を除く減算) *x*++
> ++*x*
> *x*--
> --*x*

それぞれの文字について以下に説明します。

*x*<br/>
指定されたリダクション変数の 1 つ、`list`します。

*variable-list*<br/>
スカラー リダクション変数のコンマ区切りの一覧。

*expr*<br/>
スカラー型を参照しない式*x*します。

*op*<br/>
オーバー ロードされた演算子ではなく、いずれかの +、 &#42;、-、 &amp;、^、 &#124;、 &amp; &amp;、または&#124;&#124;します。

*binop*<br/>
オーバー ロードされた演算子ではなく、いずれかの +、 &#42;、-、 &amp;、^、または&#124;します。

例を次に、`reduction`句。

```cpp
#pragma omp parallel for reduction(+: a, y) reduction(||: am)
for (i=0; i<n; i++) {
   a += b[i];
   y = sum(y, c[i]);
   am = am || b[i] == c[i];
}
```

例に示すように関数呼び出しの内部で、演算子が非表示に可能性があります。 ユーザーが注意が必要で、演算子が指定されているように、`reduction`句に一致するリダクション演算。

右オペランド、 &#124; &#124;演算子この例では副作用がないが許可されますが、注意して使用する必要があります。 このコンテキストで副作用が順次実行ループの中に発生することが保証される並列実行中に発生します。 この違いは、イテレーションの実行の順序は不確定場合に発生します。

演算子を削減のため、コンパイラによって使用される任意のプライベート変数の初期値を確認し、終了演算子が決定に使用されます。 演算子を明示的に指定すると、構文、コンストラクトの範囲外にあるリダクション ステートメントができます。 任意の数の`reduction`、ディレクティブの句を指定することがありますが、最大で 1 つに、変数が表示されます`reduction`そのディレクティブの句。

内の各変数のプライベート コピーを*変数一覧*作成されると、スレッドごとに 1 つとして、`private`句が使用されている必要があります。 プライベート コピーが、演算子に従って初期化されます (次の表を参照してください)。

対象の領域の最後に、`reduction`句が指定されて、指定された演算子を使用してプライベート コピーのそれぞれの最終的な値で元の値を組み合わせた結果を反映するように、元のオブジェクトが更新されます。 リダクション演算子は、すべて (減算) を除くと、コンパイラは、最終的な値の計算を関連付けし直す自由に。 (減算のリダクションの部分的な結果は、最終的な値をフォームに追加されます)。

最初のスレッドが含む句に達するし、リダクションの計算が完了するまで、維持、元のオブジェクトの値は不確定になります。  通常、計算を; 構造の最後に完了します。ただし場合、`reduction`句を使用して先のコンストラクトに`nowait`も適用すると、元のオブジェクトの値が不確定なバリア同期が実行されるすべてのスレッドが、を完了していることを確認するまで`reduction`句。

次の表は、有効な演算子とその標準的な初期値を示します。 実際の初期値は減少変数のデータ型と一致になります。

|演算子|初期化|
|--------------|--------------------|
|+|0|
|&#42;|1|
|-|0|
|&amp;|~0|
|&#124;|0|
|^|0|
|&amp;&amp;|1|
|&#124;&#124;|0|

制限、`reduction`句は、次のとおり。

- 変数の型、`reduction`ポインター型と参照型が使用できないことを除いて句が有効、減少演算子である必要があります。

- 指定されている変数、`reduction`句がある必要がありますいない**const**-修飾します。

- 並行領域内でプライベート変数に表示される、`reduction`の句、**並列**でディレクティブを指定することはできません、 `reduction` parallel コンストラクトにバインドされる動作共有ディレクティブの句。

   ```cpp
   #pragma omp parallel private(y)
   { /* ERROR - private variable y cannot be specified
                in a reduction clause */
      #pragma omp for reduction(+: y)
      for (i=0; i<n; i++)
         y += b[i];
   }

   /* ERROR - variable x cannot be specified in both
              a shared and a reduction clause */
   #pragma omp parallel for shared(x) reduction(+: x)
   ```

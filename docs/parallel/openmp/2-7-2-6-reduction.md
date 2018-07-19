---
title: 2.7.2.6 削減 |Microsoft ドキュメント
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
ms.openlocfilehash: 759a2ee50f047fbd5777481d009332be998ad359
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
ms.locfileid: "33688805"
---
# <a name="2726-reduction"></a>2.7.2.6 reduction

この句に表示されるスカラー変数の削減を実行する*変数一覧*、演算子で*op*です。 構文、`reduction`句を次に示します。

> reduction(*op*: *variable-list*)

パフォーマンスが低下は、通常、次の種類のいずれかのステートメントの指定します。

> *x* = *x* *op* *expr*  
> *x* *binop* = *expr*  
> *x* = *expr* *op* *x* (減算) を除く  
> *x*++  
> ++*x*  
> *x*--  
> --*x*  

それぞれの文字について以下に説明します。

*x*  
指定されたリダクション変数のいずれか、`list`です。

*variable-list*  
スカラー リダクション変数のコンマ区切りの一覧です。

*expr*  
参照しないスカラーの型を持つ式*x*です。

*op*  
オーバー ロードされた演算子ではなくのいずれかが、+、 &#42;、-、 &amp;、^、 &#124;、 &amp; &amp;、または&#124;&#124;です。

*binop*  
オーバー ロードされた演算子ではなくのいずれかが、+、 &#42;、-、 &amp;、^、または&#124;です。

次の例に示します、`reduction`句。  
  
```cpp  
#pragma omp parallel for reduction(+: a, y) reduction(||: am)  
for (i=0; i<n; i++) {  
   a += b[i];  
   y = sum(y, c[i]);  
   am = am || b[i] == c[i];  
}  
```  
  
例のように、演算子を関数呼び出しの内部隠れることがあります。 ユーザーは、演算子がで指定されているように注意する必要があります、`reduction`句は、リダクション演算に一致します。

右オペランド、 &#124; &#124;演算子この例では副作用がないと、これらが許可されるが、注意を払って使用する必要があります。 このコンテキストで、ループのシーケンシャル実行中に発生するされませんが保証される副作用に並列実行中に発生します。 この違いは、イテレーションの実行の順序が不確定であるために発生します。

演算子では使用の削減のため、コンパイラで使用するプライベート変数の初期値を決定する終了演算子が決定されます。 演算子を明示的に指定すると、リダクション ステートメントをコンス トラクターの構文の範囲外に置くことができます。 任意の数の`reduction`、ディレクティブの句を指定することがありますが、変数は、多くても 1 つに含めることは`reduction`そのディレクティブの句。

内の各変数のプライベート コピー*変数一覧*作成されると、スレッドごとに 1 つとして、`private`句が使用されていた。 プライベート コピーは、演算子に基づいて初期化されます (次の表を参照してください)。

対象の地域の最後に、`reduction`句が指定されて、元のオブジェクトが指定された演算子を使用してプライベート コピーのそれぞれの最終的な値で元の値を組み合わせた結果を反映するように更新されます。 リダクション演算子は、すべて (減算) を除くと、コンパイラは、最終的な値の計算を関連付けし直す自由にします。 (減算の削減の部分的な結果は、最終的な値をフォームに追加されます)。

最初のスレッドを含む句に達するし、リダクションの計算が完了するまで、維持、元のオブジェクトの値は不確定になります。  通常は、計算を; 構造の最後に完了します。ただし場合、`reduction`句を使用する構成体で`nowait`はまた、適用、元のオブジェクトの値のまま不確定、のすべてのスレッドが完了したことを確認するバリア同期が実行されるまで`reduction`句。

次の表は、有効な演算子と標準的な初期値を示します。 実際の初期値は、リダクション変数のデータ型と一致するされます。

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

制限、`reduction`句は、次のようにします。

- 内の変数の型、`reduction`ポインター型と参照型は使用できないする点を除いて、句が、減少演算子に対して有効である必要があります。

- 指定されている変数、`reduction`句は必須**const**で修飾します。

- 変数は、並行領域内でプライベートをまたはに表示される、`reduction`の句、**並列**ディレクティブを指定することはできません、 `reduction` parallel コンストラクトにバインドされる動作共有ディレクティブの句。

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

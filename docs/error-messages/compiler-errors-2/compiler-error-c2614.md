---
title: コンパイラ エラー C2614
ms.date: 11/04/2016
f1_keywords:
- C2614
helpviewer_keywords:
- C2614
ms.assetid: a550c1d5-8718-4e17-a888-b2619e00fe11
ms.openlocfilehash: 71f0fe3211ce253bcf30347658692651e84ab608
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50463597"
---
# <a name="compiler-error-c2614"></a>コンパイラ エラー C2614

'class1': 無効なメンバーの初期化: 'class2' がないと、基本クラスまたはメンバー

基底クラスまたはメンバーのみが、クラスまたは構造体の初期化リストに表示できます。

## <a name="example"></a>例

次の例では、C2614 が生成されます。

```
// C2614.cpp
// compile with: /c
struct A {
   int i;
   A( int ia ) : B( i ) {};   // C2614 B is not a member of A
};

struct A2 {
   int B;
   int i;
   A2( int ia ) : B( i ) {};   // OK
};
```
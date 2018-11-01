---
title: コンパイラ エラー C3160
ms.date: 11/04/2016
f1_keywords:
- C3160
helpviewer_keywords:
- C3160
ms.assetid: a250c433-8adf-43b9-8dee-c3794e09b0a5
ms.openlocfilehash: 96fd97aa5021b7e1bc5226162f9c54ff4d6211b1
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50649746"
---
# <a name="compiler-error-c3160"></a>コンパイラ エラー C3160

'pointer': マネージド クラスまたは WinRT クラスのデータ メンバーにはこの型を指定できません。

内部のガベージ コレクション ポインターは、マネージド クラスまたは WinRT クラスの内部を指す場合があります。 オブジェクト全体のポインターよりも遅く、ガベージ コレクターによる特別な処理を必要とするため、クラスのメンバーとして内部のマネージド ポインターを宣言することはできません。

次の例では C3160 が生成されます。

```
// C3160.cpp
// compile with: /clr
ref struct A {
   // cannot create interior pointers inside a class
   interior_ptr<int> pg;   // C3160
   int g;   // OK
   int* pg2;   // OK
};

int main() {
   interior_ptr<int> pg2;   // OK
}
```

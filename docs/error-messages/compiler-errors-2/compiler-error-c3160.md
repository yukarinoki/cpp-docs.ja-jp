---
description: 詳細については、「コンパイラエラー C3160」を参照してください。
title: コンパイラエラー C3160
ms.date: 11/04/2016
f1_keywords:
- C3160
helpviewer_keywords:
- C3160
ms.assetid: a250c433-8adf-43b9-8dee-c3794e09b0a5
ms.openlocfilehash: 863670f30a6a911977ead0d541dcba825e4f124a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97242328"
---
# <a name="compiler-error-c3160"></a>コンパイラエラー C3160

'pointer': マネージド クラスまたは WinRT クラスのデータ メンバーにはこの型を指定できません。

内部のガベージ コレクション ポインターは、マネージド クラスまたは WinRT クラスの内部を指す場合があります。 オブジェクト全体のポインターよりも遅く、ガベージ コレクターによる特別な処理を必要とするため、クラスのメンバーとして内部のマネージド ポインターを宣言することはできません。

次の例では C3160 が生成されます。

```cpp
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

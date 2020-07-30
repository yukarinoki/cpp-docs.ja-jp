---
title: コンパイラ エラー C2391
ms.date: 11/04/2016
f1_keywords:
- C2391
helpviewer_keywords:
- C2391
ms.assetid: 63a9c6b9-03cc-4517-885c-bdcd048643b3
ms.openlocfilehash: f000287c5934a39d56342bce0f6c9ca2c69e2297
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87212736"
---
# <a name="compiler-error-c2391"></a>コンパイラ エラー C2391

' identifier ': ' friend ' は型定義中には使用できません

宣言には、 **`friend`** 完全なクラス宣言が含まれています。 **`friend`** 宣言では、メンバー関数または詳細な型指定子を指定できますが、完全なクラス宣言は指定できません。

次の例では C2326 が生成されます。

```cpp
// C2391.cpp
// compile with: /c
class D {
   void func( int );
};

class A {
   friend class B { int i; };   // C2391

   // OK
   friend class C;
   friend void D::func(int);
};
```

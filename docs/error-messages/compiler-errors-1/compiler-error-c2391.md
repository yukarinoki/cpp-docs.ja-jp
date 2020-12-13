---
description: 詳細については、「コンパイラエラー C2391」を参照してください。
title: コンパイラ エラー C2391
ms.date: 11/04/2016
f1_keywords:
- C2391
helpviewer_keywords:
- C2391
ms.assetid: 63a9c6b9-03cc-4517-885c-bdcd048643b3
ms.openlocfilehash: 3161cd6ade15817142cc24f38c61fd3e09eb8857
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97337577"
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

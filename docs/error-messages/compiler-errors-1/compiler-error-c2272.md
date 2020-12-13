---
description: 詳細については、「コンパイラエラー C2272」を参照してください。
title: コンパイラ エラー C2272
ms.date: 11/04/2016
f1_keywords:
- C2272
helpviewer_keywords:
- C2272
ms.assetid: 1517706a-9c27-452e-9b10-3424b3d232bc
ms.openlocfilehash: 5a46c68a09eaec9fc33ef4eaa64afaebea411659
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97336247"
---
# <a name="compiler-error-c2272"></a>コンパイラ エラー C2272

' function ': 静的メンバー関数では、修飾子は使用できません

**`static`** メンバー関数は、 [const](../../cpp/const-cpp.md)や [volatile](../../cpp/volatile-cpp.md)などのメモリモデル指定子を使用して宣言されています。このような修飾子は、メンバー関数では使用できません **`static`** 。

次の例では、C2272 が生成されます。

```cpp
// C2272.cpp
// compile with: /c
class CMyClass {
public:
   static void func1() const volatile;   // C2272  func1 is static
   void func2() const volatile;   // OK
};
```

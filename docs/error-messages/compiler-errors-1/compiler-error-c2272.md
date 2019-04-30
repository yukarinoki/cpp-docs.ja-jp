---
title: コンパイラ エラー C2272
ms.date: 11/04/2016
f1_keywords:
- C2272
helpviewer_keywords:
- C2272
ms.assetid: 1517706a-9c27-452e-9b10-3424b3d232bc
ms.openlocfilehash: 1a5a1e47a721cb6edd795012cc45943e63708936
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62388892"
---
# <a name="compiler-error-c2272"></a>コンパイラ エラー C2272

'function': 修飾子は静的メンバー関数では使用できません

A`static`などメンバー関数は、メモリ モデルの指定子で宣言された[const](../../cpp/const-cpp.md)または[揮発性](../../cpp/volatile-cpp.md)でそのような修飾子は許可されず`static`メンバー関数。

次の例では、C2272 が生成されます。

```
// C2272.cpp
// compile with: /c
class CMyClass {
public:
   static void func1() const volatile;   // C2272  func1 is static
   void func2() const volatile;   // OK
};
```
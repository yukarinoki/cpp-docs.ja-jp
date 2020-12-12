---
description: 詳細については、「コンパイラエラー C3269」を参照してください。
title: コンパイラ エラー C3269
ms.date: 11/04/2016
f1_keywords:
- C3269
helpviewer_keywords:
- C3269
ms.assetid: c575f067-244d-4dd5-bf58-9e7630ea58b7
ms.openlocfilehash: 041a0af061e4ddd1a691c396cdd15e86085124c2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97113701"
---
# <a name="compiler-error-c3269"></a>コンパイラ エラー C3269

' function ': マネージまたは WinRTtype のメンバー関数を '... ' と共に宣言することはできません

マネージド クラスと WinRT クラスのメンバー関数では可変長のパラメーター リストを宣言できません。

次の例では C3269 を生成し、その修正方法を示しています。

```cpp
// C3269_2.cpp
// compile with: /clr

ref struct A
{
   void func(int i, ...)   // C3269
   // try the following line instead
   // void func(int i )
   {
   }
};

int main()
{
}
```

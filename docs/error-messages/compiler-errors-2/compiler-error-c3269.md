---
title: コンパイラ エラー C3269
ms.date: 11/04/2016
f1_keywords:
- C3269
helpviewer_keywords:
- C3269
ms.assetid: c575f067-244d-4dd5-bf58-9e7630ea58b7
ms.openlocfilehash: 406b388460b3d449471c884dd6461f2ce59a10f6
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50622951"
---
# <a name="compiler-error-c3269"></a>コンパイラ エラー C3269

'function': マネージまたは WinRTtype のメンバー関数は '...' と共に宣言できません

マネージド クラスと WinRT クラスのメンバー関数では可変長のパラメーター リストを宣言できません。

次の例では C3269 を生成し、その修正方法を示しています。

```
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

---
title: コンパイラ エラー C3640
ms.date: 11/04/2016
f1_keywords:
- C3640
helpviewer_keywords:
- C3640
ms.assetid: fcc56894-0f98-48af-8561-3bf7c7b2b93f
ms.openlocfilehash: 5d9becbdfad2afc8940a9e1ded08a15842607e4b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62385928"
---
# <a name="compiler-error-c3640"></a>コンパイラ エラー C3640

'member': ローカル クラスの参照または仮想メンバー関数を定義する必要があります

コンパイラでは、特定の関数を定義する必要があります。

次の例では、C3640 が生成されます。

```
// C3640.cpp
void f()
{
   struct S
   {
      virtual void f1();   // C3640
      // Try the following line instead:
      // virtual void f1(){}
   };
}
```
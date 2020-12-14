---
description: 詳細については、「コンパイラエラー C3640」を参照してください。
title: コンパイラ エラー C3640
ms.date: 11/04/2016
f1_keywords:
- C3640
helpviewer_keywords:
- C3640
ms.assetid: fcc56894-0f98-48af-8561-3bf7c7b2b93f
ms.openlocfilehash: 7f26a824cc39f2b5509c6d935a95cbc5af48aca0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97239182"
---
# <a name="compiler-error-c3640"></a>コンパイラ エラー C3640

' member ': ローカルクラスの参照または仮想メンバー関数が定義されている必要があります

コンパイラでは、特定の関数を定義する必要があります。

次の例では、C3640 が生成されます。

```cpp
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

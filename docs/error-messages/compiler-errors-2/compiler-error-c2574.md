---
description: 詳細については、「コンパイラエラー C2574」を参照してください。
title: コンパイラ エラー C2574
ms.date: 11/04/2016
f1_keywords:
- C2574
helpviewer_keywords:
- C2574
ms.assetid: 3e1c5c18-ee8b-4dbb-bfc0-d3b8991af71b
ms.openlocfilehash: 361cc52f2a76e5470109db07ccabbe6d78291a43
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97208893"
---
# <a name="compiler-error-c2574"></a>コンパイラ エラー C2574

' デストラクター ': static として宣言することはできません。

デストラクターもコンストラクターも宣言できません **`static`** 。

次の例では、C2574 が生成されます。

```cpp
// C2574.cpp
// compile with: /c
class A {
   virtual static ~A();   // C2574
   //  try the following line instead
   // virtual ~A();
};
```

---
title: コンパイラ エラー C2574
ms.date: 11/04/2016
f1_keywords:
- C2574
helpviewer_keywords:
- C2574
ms.assetid: 3e1c5c18-ee8b-4dbb-bfc0-d3b8991af71b
ms.openlocfilehash: 28e674b9788a8fa9135460e547f743cb2b0075ee
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87212710"
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

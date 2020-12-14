---
description: 詳細については、「コンパイラエラー C2208」を参照してください。
title: コンパイラ エラー C2208
ms.date: 11/04/2016
f1_keywords:
- C2208
helpviewer_keywords:
- C2208
ms.assetid: 9ae704bc-bf70-45f1-8e47-0470f21edd4e
ms.openlocfilehash: 76452c504e5f90857b15c5fc9250923705d3d20c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97245643"
---
# <a name="compiler-error-c2208"></a>コンパイラ エラー C2208

' type ': この型を使用して定義されたメンバーはありません

型名に解決される識別子が集計宣言内にありますが、コンパイラはメンバーを宣言できません。

次の例では、C2208 が生成されます。

```cpp
// C2208.cpp
class C {
   C;   // C2208
   C(){}   // OK
};
```

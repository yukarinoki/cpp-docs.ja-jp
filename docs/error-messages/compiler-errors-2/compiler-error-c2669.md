---
description: 詳細については、「コンパイラエラー C2669」を参照してください。
title: コンパイラエラー C2669
ms.date: 11/04/2016
f1_keywords:
- C2669
helpviewer_keywords:
- C2669
ms.assetid: f9cb8111-bcdc-484b-a863-2c42e15a0496
ms.openlocfilehash: 01b40131a2eef4ff83d10c5088b2cae3eb7e55e0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97210648"
---
# <a name="compiler-error-c2669"></a>コンパイラエラー C2669

メンバー関数は無名共用体では使用できません

[匿名共用体](../../cpp/unions.md#anonymous_unions) にメンバー関数を含めることはできません。

## <a name="example"></a>例

次の例では、C2669 が生成されます。

```cpp
// C2669.cpp
struct X {
   union {
      int i;
      void f() {   // C2669, remove function
         i = 0;
      }
   };
};
```

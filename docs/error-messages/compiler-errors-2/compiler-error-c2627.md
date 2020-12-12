---
description: 詳細については、「コンパイラエラー C2627」を参照してください。
title: コンパイラエラー C2627
ms.date: 11/04/2016
f1_keywords:
- C2627
helpviewer_keywords:
- C2627
ms.assetid: 7fc6c5ac-c7c9-4f0b-ad52-f52252526458
ms.openlocfilehash: 4f09e2b76376871dab93e0736c8a0ca6dbb2b5a6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97174573"
---
# <a name="compiler-error-c2627"></a>コンパイラエラー C2627

' function ': メンバー関数は無名共用体では使用できません

[無名共用体](../../cpp/unions.md#anonymous_unions)にメンバー関数を含めることはできません。

次の例では、C2627 が生成されます。

```cpp
// C2627.cpp
int main() {
   union { void f(){} };   // C2627
   union X { void f(){} };
}
```

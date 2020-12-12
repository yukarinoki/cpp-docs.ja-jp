---
description: 詳細については、「コンパイラエラー C2787」を参照してください。
title: コンパイラエラー C2787
ms.date: 11/04/2016
f1_keywords:
- C2787
helpviewer_keywords:
- C2787
ms.assetid: 34cb57e6-cafe-4ce7-bcc6-53d194629bd0
ms.openlocfilehash: 96a06908012e565bc606bf56f6a1709ee1f265a4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97297810"
---
# <a name="compiler-error-c2787"></a>コンパイラエラー C2787

' identifier ': このオブジェクトに関連付けられた GUID はありません

[__Uuidof](../../cpp/uuidof-operator.md)演算子は、GUID が割り当てられたユーザー定義型、またはそのようなユーザー定義型のオブジェクトを受け取ります。 このエラーは、引数が GUID のないユーザー定義型である場合に発生します。

次の例では、C2787 が生成されます。

```cpp
// C2787.cpp
#include <windows.h>
struct F {};

struct __declspec(uuid("00000000-0000-0000-c000-000000000046")) F2;

int main() {
   __uuidof(F);   // C2787
   __uuidof(F2);   // OK
}
```

---
description: 詳細については、「コンパイラエラー C3272」を参照してください。
title: コンパイラ エラー C3272
ms.date: 11/04/2016
f1_keywords:
- C3272
helpviewer_keywords:
- C3272
ms.assetid: 7cdf254d-f207-4116-a1bf-7386f3b82a6f
ms.openlocfilehash: 1222db43922081efbb8195c29b905d2efc7bbe5d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97185753"
---
# <a name="compiler-error-c3272"></a>コンパイラ エラー C3272

'symbol': シンボルは、StructLayout(LayoutKind::Explicit) で定義された型パラメーターのメンバーであるため、このシンボルには FieldOffset が必要です

`StructLayout(LayoutKind::Explicit)`が有効な場合は、フィールドをでマークする必要があり `FieldOffset` ます。

次の例では C3272 が生成されます。

```cpp
// C3272_2.cpp
// compile with: /clr /c
using namespace System;
using namespace System::Runtime::InteropServices;

[StructLayout(LayoutKind::Explicit)]
ref struct X
{
   int data_;   // C3272
   // try the following line instead
   // [FieldOffset(0)] int data_;
};
```

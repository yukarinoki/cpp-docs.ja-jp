---
description: 詳細については、「コンパイラエラー C3270」を参照してください。
title: コンパイラ エラー C3270
ms.date: 11/04/2016
f1_keywords:
- C3270
helpviewer_keywords:
- C3270
ms.assetid: 70e6e76b-7415-48f5-a61e-2ed50caf08e4
ms.openlocfilehash: 976e4c9e6b1448c01b58b754d6ca4a09a1607fbf
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97185896"
---
# <a name="compiler-error-c3270"></a>コンパイラ エラー C3270

'field': FieldOffset 属性は、必要な場合は StructLayout(Explicit) のコンテキストでのみ使用できます

フィールドが **FieldOffset** でマークされました。これは、 **StructLayout (Explicit)** が有効になっている場合にのみ使用できます。

次の例では C3270 が生成されます。

```cpp
// C3270_2.cpp
// compile with: /clr /c
using namespace System::Runtime::InteropServices;

[ StructLayout(LayoutKind::Sequential) ]
// try the following line instead
// [ StructLayout(LayoutKind::Explicit) ]
public value struct MYUNION
{
   [FieldOffset(0)] int a;   // C3270
   // ...
};
```

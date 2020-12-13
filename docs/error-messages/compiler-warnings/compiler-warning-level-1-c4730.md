---
description: '詳細情報: コンパイラの警告 (レベル 1) C4730'
title: コンパイラの警告 (レベル 1) C4730
ms.date: 11/04/2016
f1_keywords:
- C4730
helpviewer_keywords:
- C4730
ms.assetid: 11303e3f-162b-4b19-970a-479686123a68
ms.openlocfilehash: e026d44bc76d58c934eeccc363f4385f43d15597
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97150658"
---
# <a name="compiler-warning-level-1-c4730"></a>コンパイラの警告 (レベル 1) C4730

' main ': _m64 と浮動小数点式の混合により、正しくないコードが生成される可能性があります

関数は [__m64](../../cpp/m64.md)と型を使用 **`float`** / **`double`** します。 MMX レジスタと浮動小数点レジスタは同じ物理レジスタ領域を共有するため (同時に使用することはできません)、 **`__m64`** 同じ関数で型と型を使用すると、 **`float`** / **`double`** データが破損する可能性があり、例外が発生する可能性があります。

**`__m64`** 同じ関数で型と浮動小数点型を安全に使用するには、いずれかの型を使用する各命令を **_m_empty ()** (MMX の場合) または **_M_femms ()** (3dnow!) の組み込みによって区切る必要があります。

次の例では、C4730 が生成されます。

```cpp
// C4730.cpp
// compile with: /W1
// processor: x86
#include "mmintrin.h"

void func(double)
{
}

int main(__m64 a, __m64 b)
{
   __m64 m;
   double f;
   f = 1.0;
   m = _m_paddb(a, b);
   // uncomment the next line to resolve C4730
   // _m_empty();
   func(f * 3.0);   // C4730
}
```

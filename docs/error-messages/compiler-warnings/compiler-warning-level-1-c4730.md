---
title: コンパイラの警告 (レベル 1) C4730
ms.date: 11/04/2016
f1_keywords:
- C4730
helpviewer_keywords:
- C4730
ms.assetid: 11303e3f-162b-4b19-970a-479686123a68
ms.openlocfilehash: 4da60194deaeac3c79f8c3e9be3bd87d91bc7ca2
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62386357"
---
# <a name="compiler-warning-level-1-c4730"></a>コンパイラの警告 (レベル 1) C4730

'main': _m64 と浮動小数点式は、不適切なコード、可能性があります

関数を使用して[_ _m64](../../cpp/m64.md)と**float**/**double**型。 MMX と浮動小数点レジスタは、同じ物理を共有するためのレジスタ スペース (ことはできません同時に使用) を使用して`__m64`と**float**/**double**同じ型関数は、データの破損、例外を発生させる可能性がある可能性があります。

安全に使用する`__m64`、型のいずれかを使用するそれぞれの命令を指定する型と同じ関数での浮動小数点型の場合は、 **_m_empty()** (MMX) 用または **_m_femms()** (用 3DNow!)組み込み。

次の例では、C4730 が生成されます。

```
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
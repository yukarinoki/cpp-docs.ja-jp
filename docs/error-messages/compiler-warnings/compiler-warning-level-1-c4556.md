---
description: '詳細情報: コンパイラの警告 (レベル 1) C4556'
title: コンパイラの警告 (レベル 1) C4556
ms.date: 08/27/2018
f1_keywords:
- C4556
helpviewer_keywords:
- C4556
ms.assetid: e4c0e296-b747-4db1-9608-30b8b74feac2
ms.openlocfilehash: a0e0780b541b74125135ab84daa6ecab80b57e83
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97265858"
---
# <a name="compiler-warning-level-1-c4556"></a>コンパイラの警告 (レベル 1) C4556

> 組み込みのイミディエイト引数 '*value*' の値が、'*下限バウンド*  -  *上限*' の範囲外です

## <a name="remarks"></a>解説

組み込みは、ハードウェア命令に一致します。 ハードウェア命令には、定数をエンコードするためのビット数が固定されています。 *値* が範囲外の場合は、適切にエンコードされません。 コンパイラは、余分なビットを切り捨てます。

## <a name="example"></a>例

次の例では、C4556 が生成されます。

```cpp
// C4556.cpp
// compile with: /W1
// processor: x86 IPF
#include <xmmintrin.h>

void test()
{
   __m64 m;
   _m_pextrw(m, 5);   // C4556
}

int main()
{
}
```

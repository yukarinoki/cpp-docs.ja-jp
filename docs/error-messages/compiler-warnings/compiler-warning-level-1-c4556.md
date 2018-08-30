---
title: コンパイラの警告 (レベル 1) C4556 |Microsoft Docs
ms.custom: ''
ms.date: 08/27/2018
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- xml
- C4556
dev_langs:
- C++
helpviewer_keywords:
- C4556
ms.assetid: e4c0e296-b747-4db1-9608-30b8b74feac2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 987e4dc3ba6aea7dcb01dc05cd94c45baced05b8
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/29/2018
ms.locfileid: "43211029"
---
# <a name="compiler-warning-level-1-c4556"></a>コンパイラの警告 (レベル 1) C4556

> 組み込みイミディ エイト引数の値 '*値*'が範囲外です'*lowerbound* - *upperbound*'

## <a name="remarks"></a>Remarks

組み込み関数では、ハードウェア命令と一致します。 ハードウェアの命令では、固定数の定数をエンコードするビットがあります。 場合*値*が範囲外には正常にエンコードされません。 コンパイラでは、余分なビットが切り捨てられます。

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
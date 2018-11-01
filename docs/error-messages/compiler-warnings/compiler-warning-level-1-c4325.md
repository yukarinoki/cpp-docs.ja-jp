---
title: コンパイラの警告 (レベル 1) C4325
ms.date: 08/27/2018
f1_keywords:
- C4325
helpviewer_keywords:
- C4325
ms.assetid: 8127a08c-d626-481b-aa7b-04a3fdc9a9ec
ms.openlocfilehash: 293cbbcfe134f6cb4f5e1bf924be7c03fa278833
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50492597"
---
# <a name="compiler-warning-level-1-c4325"></a>コンパイラの警告 (レベル 1) C4325

> 標準のセクションの属性 '*セクション*' は無視されます

## <a name="remarks"></a>Remarks

標準のセクションの属性は変更できません。 例えば:

```cpp
#pragma section(".sdata", long)
```

これは、上書きは、`.sdata`標準のセクションを使用して、**短い**データ型を**長い**データ型。

標準のセクションでは変わらないことがある属性を含めるには、

- .data

- .sdata

- .bss

- .sbss

- .text

- .const

- .sconst

- .rdata

- .srdata

追加のセクションは、後で追加できます。

## <a name="see-also"></a>関連項目

[section](../../preprocessor/section.md)
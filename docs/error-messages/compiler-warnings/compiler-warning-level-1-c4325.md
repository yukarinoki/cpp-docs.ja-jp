---
title: コンパイラの警告 (レベル 1) C4325 |Microsoft Docs
ms.custom: ''
ms.date: 08/27/2018
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4325
dev_langs:
- C++
helpviewer_keywords:
- C4325
ms.assetid: 8127a08c-d626-481b-aa7b-04a3fdc9a9ec
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: cd265938afb51cc402dc84f38b7e95188c6292a7
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/29/2018
ms.locfileid: "43197486"
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
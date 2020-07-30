---
title: コンパイラの警告 (レベル 1) C4325
ms.date: 08/27/2018
f1_keywords:
- C4325
helpviewer_keywords:
- C4325
ms.assetid: 8127a08c-d626-481b-aa7b-04a3fdc9a9ec
ms.openlocfilehash: 551680bc1d24097200a1e641bc4238f883ad94dd
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87230702"
---
# <a name="compiler-warning-level-1-c4325"></a>コンパイラの警告 (レベル 1) C4325

> 標準セクション '*section*' の属性は無視されました

## <a name="remarks"></a>解説

標準セクションの属性を変更することはできません。 次に例を示します。

```cpp
#pragma section(".sdata", long)
```

これにより、データ型がのデータ型を使用する標準のセクションが上書きされ `.sdata` **`short`** **`long`** ます。

変更できない属性を持つ標準セクションには、次のようなものがあります。

- . データ

- .sdata

- bss

- . .sbss

- .text

- . const

- 。 sconst

- . .rdata

- srdata

後で追加のセクションを追加することもできます。

## <a name="see-also"></a>関連項目

[下](../../preprocessor/section.md)

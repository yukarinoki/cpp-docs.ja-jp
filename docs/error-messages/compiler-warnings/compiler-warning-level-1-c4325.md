---
title: コンパイラの警告 (レベル 1) C4325
ms.date: 08/27/2018
f1_keywords:
- C4325
helpviewer_keywords:
- C4325
ms.assetid: 8127a08c-d626-481b-aa7b-04a3fdc9a9ec
ms.openlocfilehash: e0a13761b0657d054065358994638779817dad6a
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80163025"
---
# <a name="compiler-warning-level-1-c4325"></a>コンパイラの警告 (レベル 1) C4325

> 標準セクション '*section*' の属性は無視されました

## <a name="remarks"></a>解説

標準セクションの属性を変更することはできません。 次に例を示します。

```cpp
#pragma section(".sdata", long)
```

これにより、 **long**データ型の**short**データ型を使用する `.sdata` の標準セクションが上書きされます。

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

## <a name="see-also"></a>参照

[section](../../preprocessor/section.md)

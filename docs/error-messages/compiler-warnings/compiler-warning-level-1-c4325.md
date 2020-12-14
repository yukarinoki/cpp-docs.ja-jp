---
description: '詳細情報: コンパイラの警告 (レベル 1) C4325'
title: コンパイラの警告 (レベル 1) C4325
ms.date: 08/27/2018
f1_keywords:
- C4325
helpviewer_keywords:
- C4325
ms.assetid: 8127a08c-d626-481b-aa7b-04a3fdc9a9ec
ms.openlocfilehash: 17e14d4909e4b76d6a0a71d6e77fad1d01e3f41b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97311592"
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

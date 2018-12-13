---
title: ゼロ メモリの割り当て
ms.date: 11/04/2016
helpviewer_keywords:
- memory allocation, zero memory
- zero memory
ms.assetid: 768f2ab9-83a1-4887-8eb5-c094c18489a8
ms.openlocfilehash: c7d5f307a38fff938c94cf2e1660cec99262a10a
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50447308"
---
# <a name="allocating-zero-memory"></a>ゼロ メモリの割り当て

**ANSI 4.10.3** 要求されたサイズがゼロの場合の `calloc`、`malloc`、または `realloc` 関数の動作

`calloc`、`malloc`、および `realloc` 関数は、引数として 0 を受け入れます。 実際のメモリの割り当てはありませんが、有効なポインターが返され、メモリ ブロックは realloc によって後で変更できます。

## <a name="see-also"></a>参照

[ライブラリ関数](../c-language/library-functions.md)
---
description: '詳細情報: ゼロ メモリの割り当て'
title: ゼロ メモリの割り当て
ms.date: 11/04/2016
helpviewer_keywords:
- memory allocation, zero memory
- zero memory
ms.assetid: 768f2ab9-83a1-4887-8eb5-c094c18489a8
ms.openlocfilehash: 7971d9e097d00607af2acf4590ff3daaf67f7127
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97280145"
---
# <a name="allocating-zero-memory"></a>ゼロ メモリの割り当て

**ANSI 4.10.3** 要求されたサイズがゼロの場合の `calloc`、`malloc`、または `realloc` 関数の動作

`calloc`、`malloc`、および `realloc` 関数は、引数として 0 を受け入れます。 実際のメモリの割り当てはありませんが、有効なポインターが返され、メモリ ブロックは realloc によって後で変更できます。

## <a name="see-also"></a>関連項目

[ライブラリ関数](../c-language/library-functions.md)

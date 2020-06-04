---
title: ゼロ メモリの割り当て
ms.date: 11/04/2016
helpviewer_keywords:
- memory allocation, zero memory
- zero memory
ms.assetid: 768f2ab9-83a1-4887-8eb5-c094c18489a8
ms.openlocfilehash: 40f21c0fa9a2a4068cb2592c49ccefed82176a35
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62313494"
---
# <a name="allocating-zero-memory"></a>ゼロ メモリの割り当て

**ANSI 4.10.3** 要求されたサイズがゼロの場合の `calloc`、`malloc`、または `realloc` 関数の動作

`calloc`、`malloc`、および `realloc` 関数は、引数として 0 を受け入れます。 実際のメモリの割り当てはありませんが、有効なポインターが返され、メモリ ブロックは realloc によって後で変更できます。

## <a name="see-also"></a>関連項目

[ライブラリ関数](../c-language/library-functions.md)

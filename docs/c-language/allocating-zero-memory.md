---
title: ゼロ メモリの割り当て | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- memory allocation, zero memory
- zero memory
ms.assetid: 768f2ab9-83a1-4887-8eb5-c094c18489a8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 0de013e9ddd3fb983436bf6ee0db290458936eb5
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32380639"
---
# <a name="allocating-zero-memory"></a>ゼロ メモリの割り当て
**ANSI 4.10.3** 要求されたサイズがゼロの場合の `calloc`、`malloc`、または `realloc` 関数の動作  
  
 `calloc`、`malloc`、および `realloc` 関数は、引数として 0 を受け入れます。 実際のメモリの割り当てはありませんが、有効なポインターが返され、メモリ ブロックは realloc によって後で変更できます。  
  
## <a name="see-also"></a>参照  
 [ライブラリ関数](../c-language/library-functions.md)
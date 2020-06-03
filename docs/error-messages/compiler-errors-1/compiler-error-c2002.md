---
title: コンパイラエラー C2002
ms.date: 11/04/2016
f1_keywords:
- C2002
helpviewer_keywords:
- C2002
ms.assetid: 91982314-203a-4de1-b884-94e39a623f61
ms.openlocfilehash: c37a9b94be837248c8025a4fc069d8a242128542
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80208248"
---
# <a name="compiler-error-c2002"></a>コンパイラエラー C2002

ワイド文字定数が無効です。

マルチバイト文字定数が無効です。

### <a name="to-fix-by-checking-the-following-possible-causes"></a>次のような原因をチェックして問題を解決するには

1. ワイド文字定数には、予想よりも多くのバイトが含まれています。

1. 標準ヘッダー STDDEF.H は含まれていません。

1. ワイド文字を通常の文字列リテラルと連結することはできません。

1. ワイド文字定数の前には、文字 ' L ' を指定しなければなりません。

    ```
    L'mbconst'
    ```

1. Microsoft C++の場合、プリプロセッサディレクティブのテキスト引数は ASCII である必要があります。 たとえば、ディレクティブの `#pragma message(L"string")`が有効ではありません。

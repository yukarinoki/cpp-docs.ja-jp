---
description: 詳細については、「コンパイラエラー C2002」を参照してください。
title: コンパイラエラー C2002
ms.date: 11/04/2016
f1_keywords:
- C2002
helpviewer_keywords:
- C2002
ms.assetid: 91982314-203a-4de1-b884-94e39a623f61
ms.openlocfilehash: acf6e0679f2579d25d37ccf0c11965bc1d8b436a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97298618"
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

1. Microsoft C++ では、プリプロセッサディレクティブのテキスト引数は ASCII である必要があります。 たとえば、ディレクティブが `#pragma message(L"string")` 無効です。

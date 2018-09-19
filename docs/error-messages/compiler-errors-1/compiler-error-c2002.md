---
title: コンパイラ エラー C2002 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2002
dev_langs:
- C++
helpviewer_keywords:
- C2002
ms.assetid: 91982314-203a-4de1-b884-94e39a623f61
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b87a7fe1513c695344676624ae1968060097c885
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46116920"
---
# <a name="compiler-error-c2002"></a>コンパイラ エラー C2002

無効なワイド文字定数

マルチバイト文字定数が無効です。

### <a name="to-fix-by-checking-the-following-possible-causes"></a>次のような原因をチェックして問題を解決するには

1. ワイド文字定数には、予想よりも多くのバイト数が含まれています。

1. 標準ヘッダー STDDEF.h は含まれません。

1. ワイド文字は、通常のリテラル文字列と連結ことはできません。

1. 文字 'L' はワイド文字定数を前する必要があります。

    ```
    L'mbconst'
    ```

1. Microsoft C では、プリプロセッサ ディレクティブのテキストの引数は ASCII である必要があります。 たとえば、次のようなディレクティブがあると、`#pragma message(L"string")`が無効です。
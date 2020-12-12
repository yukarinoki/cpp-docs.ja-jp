---
description: '詳細情報: コメント (C++)'
title: C++ コメント
ms.date: 11/04/2016
helpviewer_keywords:
- code comments, C++
- comments, documenting code
- comments, C++ code
- white space, C++ comments
ms.assetid: 6fcb906c-c264-4083-84bc-373800b2e514
ms.openlocfilehash: b3bbcafe1f18c791fc5935161b6cdbfae0bf03cf
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97239793"
---
# <a name="comments-c"></a>C++ コメント

コメントは、コンパイラは無視しますが、プログラマにとって便利なテキストです。 コメントは、通常、後で参照できるようにコードに注釈を付けるために使用されます。 コンパイラは、それらを空白文字として処理します。 テストでコメントを使用して、特定のコード行を非アクティブにすることができます。ただし、 `#if` / `#endif` プリプロセッサディレクティブは、コメントを含むコードを囲むことはできますが、コメントを入れ子にすることはできないため、このように機能が向上します。

C++ のコメントは、次のいずれかの方法で記述されます。

- `/*` (スラッシュ、アスタリスク) 文字と、それに続く任意の文字シーケンス (改行を含む) と、それに続く `*/`。 この構文は ANSI C と同じです。

- `//` (2 つのスラッシュ) 文字と、それに続く任意の文字シーケンス。 直前に円記号がない新しい行は、この形式のコメントを終了させます。 そのため、この形式は一般に "単一行コメント" と呼ばれます。

コメント文字 (`/*`、`*/`、および `//`) は、文字定数、文字列リテラル、またはコメント内で特別な意味を持ちません。 したがって、最初の構文を使用したコメントを入れ子にすることはできません。

## <a name="see-also"></a>関連項目

[字句表記規則](../cpp/lexical-conventions.md)

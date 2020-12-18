---
description: '詳細情報: 文字型'
title: 文字型
ms.date: 11/04/2016
helpviewer_keywords:
- character data types [C]
- types [C], character
ms.assetid: d3ca8cda-c0d7-43af-9472-697e8ef015ce
ms.openlocfilehash: 270c1831422d81fe88519a2aee3de8306727d0d1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97293535"
---
# <a name="character-types"></a>文字型

前に文字 **L** が付かない整数の文字定数には、 **`int`** 型があります。 単一の文字を含む整数の文字定数の値は整数として解釈される文字の数値です。 たとえば、文字 `a` の数値は、10 進形式では 97 で、16 進形式では 61 です。

構文上、"ワイド文字定数" は、文字 **L** がプレフィックスとして付けられている文字定数です。ワイド文字定数は、 **`wchar_t`** 型 (STDDEF.H ヘッダー ファイルで定義されている整数型) を持ちます。 次に例を示します。

```
char    schar =  'x';   /* A character constant          */
wchar_t wchar = L'x';   /* A wide-character constant for
                            the same character           */
```

ワイド文字定数は、16 ビット幅で、拡張実行文字セットのメンバーを指定します。 これにより、 **`char`** 型で表すには大きすぎる文字をアルファベットで表現することができます。 ワイド文字の詳細については、「[マルチバイト文字とワイド文字](../c-language/multibyte-and-wide-characters.md)」を参照してください。

## <a name="see-also"></a>関連項目

[C 文字定数](../c-language/c-character-constants.md)

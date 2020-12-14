---
description: 詳細については、「マクロにおける特殊文字」を参照してください。
title: マクロの特殊文字
ms.date: 11/04/2016
helpviewer_keywords:
- special characters, in NMAKE macros
ms.assetid: c0a06cfc-7103-4ee2-a585-e8f6e85dccd7
ms.openlocfilehash: 569aedbc474f660894b723f9356355e2360a4e61
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97224661"
---
# <a name="special-characters-in-macros"></a>マクロの特殊文字

定義でコメントを指定した後のシャープ記号 (#)。 マクロでリテラルのシャープ記号を指定するには、^ # のようにカレット (^) を使用します。

ドル記号 ($) は、マクロ呼び出しを指定します。 リテラル $ を指定するには、$ $ を使用します。

定義を新しい行に拡張するには、行の末尾に円記号 () を付け \\ ます。 マクロが呼び出されると、円記号と改行文字がスペースで置き換えられます。 行末にリテラルバックスラッシュを指定するには、その前にカレット (^) を付けるか、コメント指定子 (#) を使用します。

リテラルの改行文字を指定するには、次のようにカレット (^) を使用して行を終了します。

```
CMDS = cls^
dir
```

## <a name="see-also"></a>関連項目

[NMAKE マクロの定義](defining-an-nmake-macro.md)

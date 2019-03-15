---
title: マクロの特殊文字
ms.date: 11/04/2016
helpviewer_keywords:
- special characters, in NMAKE macros
ms.assetid: c0a06cfc-7103-4ee2-a585-e8f6e85dccd7
ms.openlocfilehash: aac7b07500d2a129194e7234210a590cb5d0f19a
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2019
ms.locfileid: "57826678"
---
# <a name="special-characters-in-macros"></a>マクロの特殊文字

コメントを指定する、定義した後のシャープ記号 (#)。 マクロでリテラルの番号記号を指定するようにキャレット (^) を使用して、^ とします。

ドル記号 ($) では、マクロの呼び出しを指定します。 リテラル $を指定するには、$$ を使用します。

新しい行に、定義を拡張するには、円記号行目の最後 (\\)。 マクロが呼び出されたときにバック スラッシュ、および改行文字はスペースで置き換えられます。 行の末尾にリテラル円記号を指定するには、先頭のキャレット (^) か、後にコメント指定子 (#)。

リテラルの改行文字を指定するには、ようにキャレット (^) では、行を終了します。

```
CMDS = cls^
dir
```

## <a name="see-also"></a>関連項目

[NMAKE マクロの定義](defining-an-nmake-macro.md)

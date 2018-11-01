---
title: マクロでの代入
ms.date: 11/04/2016
helpviewer_keywords:
- NMAKE program, macro substitution
- macros, NMAKE
- substitution macros in NMAKE
ms.assetid: 47465cfe-fd92-49db-aebe-7c2d7ecceb73
ms.openlocfilehash: 8daaa55418839fa969cf3a31efa092fcf21487e5
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50616087"
---
# <a name="macro-substitution"></a>マクロでの代入

ときに*macroname*呼び出されると、出現するたび*string1*その定義で文字列が置き換え*string2*します。

## <a name="syntax"></a>構文

```
$(macroname:string1=string2)
```

## <a name="remarks"></a>Remarks

マクロでの代入が大文字小文字を区別、リテラルです。*string1*と*string2*マクロを呼び出すことはできません。 置換では、元の定義は変更されません。 除く任意の定義済みマクロ内のテキストを置き換えることができる[ $$@](../build/filename-macros.md)します。

スペースまたはタブの colon; 前なしコロンの後は、リテラルとして解釈されます。 場合*string2*が出現するすべての null *string1*マクロの定義の文字列から削除されます。

## <a name="see-also"></a>関連項目

[NMAKE マクロの使用](../build/using-an-nmake-macro.md)
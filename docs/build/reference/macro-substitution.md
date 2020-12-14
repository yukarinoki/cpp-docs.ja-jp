---
description: '詳細情報: マクロの置換'
title: マクロでの代入
ms.date: 11/04/2016
helpviewer_keywords:
- NMAKE program, macro substitution
- macros, NMAKE
- substitution macros in NMAKE
ms.assetid: 47465cfe-fd92-49db-aebe-7c2d7ecceb73
ms.openlocfilehash: 5e1531afb210b4671632bca2540bfc7562653139
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97199182"
---
# <a name="macro-substitution"></a>マクロでの代入

*Macroname* が呼び出されると、その定義文字列で *string1* が出現するたびに、 *string2* に置き換えられます。

## <a name="syntax"></a>構文

```
$(macroname:string1=string2)
```

## <a name="remarks"></a>解説

マクロの置換では大文字と小文字が区別され、リテラルになります。 *string1* と *string2* はマクロを呼び出すことができません。 置換では、元の定義は変更されません。 を除く定義済みのマクロでは、テキストを置き換えることができ [$$@](filename-macros.md) ます。

コロンの前にスペースやタブはありません。コロンの後の任意のがリテラルとして解釈されます。 *String2* が null の場合、 *string1* のすべての出現箇所がマクロの定義文字列から削除されます。

## <a name="see-also"></a>関連項目

[NMAKE マクロの使用](using-an-nmake-macro.md)

---
description: '詳細情報: NMAKE マクロの使用'
title: NMAKE マクロの使用
ms.date: 11/04/2016
helpviewer_keywords:
- macros, NMAKE
- NMAKE macros, using
ms.assetid: 95c87fbc-76e6-48c0-8536-9bfe179f328e
ms.openlocfilehash: 14a1856b411bf7608b94caacb1b0b078dd1f5577
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97247008"
---
# <a name="using-an-nmake-macro"></a>NMAKE マクロの使用

マクロを使用するには、次のように、名前をかっこで囲んでドル記号 ($) で囲みます。

## <a name="syntax"></a>構文

```
$(macroname)
```

## <a name="remarks"></a>解説

スペースは使用できません。 *Macroname* が1文字の場合、かっこは省略可能です。 定義文字列は $ (*macroname*) を置き換えます。未定義のマクロは、null 文字列に置き換えられます。

## <a name="what-do-you-want-to-know-more-about"></a>さらに詳しくは次のトピックをクリックしてください

[マクロでの代入](macro-substitution.md)

## <a name="see-also"></a>関連項目

[マクロと NMAKE](macros-and-nmake.md)

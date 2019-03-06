---
title: NMAKE マクロの使用
ms.date: 11/04/2016
helpviewer_keywords:
- macros, NMAKE
- NMAKE macros, using
ms.assetid: 95c87fbc-76e6-48c0-8536-9bfe179f328e
ms.openlocfilehash: a5f0fb9b13c5d5647b8f4ee382951df6282e8d68
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/05/2019
ms.locfileid: "57415644"
---
# <a name="using-an-nmake-macro"></a>NMAKE マクロの使用

マクロを使用するには、ドル記号 ($) を次のように続くかっこ内の名前を囲みます。

## <a name="syntax"></a>構文

```
$(macroname)
```

## <a name="remarks"></a>Remarks

スペースは許可されません。 かっこは省略可能な場合は*macroname*は単一の文字。 定義の文字列に $ が置き換えられます (*macroname*)。 未定義のマクロは、null 文字列に置換されます。

## <a name="what-do-you-want-to-know-more-about"></a>さらに詳しくは次のトピックをクリックしてください

[マクロでの代入](../build/macro-substitution.md)

## <a name="see-also"></a>関連項目

[マクロと NMAKE](../build/macros-and-nmake.md)

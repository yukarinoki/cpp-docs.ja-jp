---
title: NMAKE マクロの使用 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- macros, NMAKE
- NMAKE macros, using
ms.assetid: 95c87fbc-76e6-48c0-8536-9bfe179f328e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e0b68a5f3128b5d3780895f8080411819ed9b538
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2018
ms.locfileid: "45712596"
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
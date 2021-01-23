---
description: pragmaMicrosoft C/c + + での push_macro ディレクティブの詳細については、こちらを参照してください。
title: push_macro pragma
ms.date: 01/22/2021
f1_keywords:
- vc-pragma.push_macro
- push_macro_CPP
helpviewer_keywords:
- pragma, push_macro
- push_macro pragma
no-loc:
- pragma
ms.openlocfilehash: cb97adcb5ce9c0e46a31a9f4926770d4edd658a1
ms.sourcegitcommit: a26a66a3cf479e0e827d549a9b850fad99b108d1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2021
ms.locfileid: "98713299"
---
# <a name="push_macro-no-locpragma"></a>`push_macro` pragma

マクロ *名* マクロの値を、このマクロのスタックの一番上に保存します。

## <a name="syntax"></a>構文

> **`#pragma push_macro("`**_マクロ名_**`")`**

## <a name="remarks"></a>解説

*マクロ名* の値を取得するには、を使用 `pop_macro` します。

サンプル[ `pop_macro` pragma ](../preprocessor/pop-macro.md)については、「」を参照してください。

## <a name="see-also"></a>関連項目

[プラグマディレクティブと `__pragma` `_Pragma` キーワードおよびキーワード](./pragma-directives-and-the-pragma-keyword.md)

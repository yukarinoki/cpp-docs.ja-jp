---
description: pragmaMicrosoft C/c + + での auto_inline ディレクティブの詳細については、こちらを参照してください。
title: auto_inline pragma
ms.date: 01/22/2021
f1_keywords:
- auto_inline_CPP
- vc-pragma.auto_inline
helpviewer_keywords:
- pragma, auto_inline
- auto_inline pragma
no-loc:
- pragma
ms.openlocfilehash: 72c6823acf260d48883142f8568483eb78155da1
ms.sourcegitcommit: a26a66a3cf479e0e827d549a9b850fad99b108d1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2021
ms.locfileid: "98713728"
---
# <a name="auto_inline-no-locpragma"></a>`auto_inline` pragma

が指定されている範囲内で定義されている関数 **`off`** が、自動インライン展開の候補と見なされないようにします。

## <a name="syntax"></a>構文

> **`#pragma auto_inline(`** [ { **`on`** | **`off`** } ] **`)`**

## <a name="remarks"></a>解説

を使用するには、 **`auto_inline`** pragma 関数定義の前と直後ではなく、その直後に配置します。 は pragma 、が表示された後、最初の関数定義のすぐ後に有効になり pragma ます。

## <a name="see-also"></a>関連項目

[プラグマディレクティブと `__pragma` `_Pragma` キーワードおよびキーワード](./pragma-directives-and-the-pragma-keyword.md)

---
description: '詳細については、次を参照してください: auto_inline プラグマ'
title: auto_inline プラグマ
ms.date: 08/29/2019
f1_keywords:
- auto_inline_CPP
- vc-pragma.auto_inline
helpviewer_keywords:
- pragmas, auto_inline
- auto_inline pragma
ms.assetid: f7624cd1-be76-429a-881c-65c9040acf43
ms.openlocfilehash: f629bbe5dc47ba15bba5b2b55541509f421fcd8c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97301049"
---
# <a name="auto_inline-pragma"></a>auto_inline プラグマ

範囲内で定義されているすべての関数を除外します。 **off** は、自動インライン展開の候補として見なされません。

## <a name="syntax"></a>構文

> **#pragma auto_inline (** [{ **on**  |  **off** }] **)**

## <a name="remarks"></a>解説

**Auto_inline** プラグマを使用するには、関数定義の前と直後ではなく、その直後に配置します。 プラグマは、プラグマが表示された後、最初の関数定義のすぐ後に有効になります。

## <a name="see-also"></a>関連項目

[プラグマ ディレクティブと __pragma キーワード](../preprocessor/pragma-directives-and-the-pragma-keyword.md)

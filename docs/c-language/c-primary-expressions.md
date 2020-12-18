---
title: C での一次式
description: C での一次式について説明します
ms.date: 12/08/2020
helpviewer_keywords:
- primary expressions
ms.openlocfilehash: 41f011cc56f4c4fdf58c6a5fd2e3178267995854
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97300204"
---
# <a name="c-primary-expressions"></a>C での一次式

基本式は、より複雑な式のビルド ブロックです。 それらは定数、識別子、[汎用選択](generic_selection.md)、またはかっこで囲まれた式の場合があります。

## <a name="syntax"></a>構文

*`primary-expression`*:\
&nbsp;&nbsp;&nbsp;&nbsp;*`identifier`*\
&nbsp;&nbsp;&nbsp;&nbsp;*`constant`*\
&nbsp;&nbsp;&nbsp;&nbsp;*`string-literal`*\
&nbsp;&nbsp;&nbsp;&nbsp;**(** *`expression`* **)**\
&nbsp;&nbsp;&nbsp;&nbsp;*`generic-selection`*

*expression*:\
&nbsp;&nbsp;&nbsp;&nbsp;*`assignment-expression`*\
&nbsp;&nbsp;&nbsp;&nbsp;*`expression`***,** *`assignment-expression`*

## <a name="see-also"></a>関連項目

[汎用選択](generic_selection.md)
[オペランドと式](../c-language/operands-and-expressions.md)

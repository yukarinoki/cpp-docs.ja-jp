---
description: 詳細については、「」を参照してください。SAVEREG
title: .SAVEREG
ms.date: 12/16/2019
f1_keywords:
- .SAVEREG
helpviewer_keywords:
- .SAVEREG directive
ms.assetid: 1dbc2ef6-a197-40e7-9e55-fddcae8cef29
ms.openlocfilehash: 8b946c9b25c3f4dc6a4696b418e85487e20014eb
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97131184"
---
# <a name="savereg"></a>.SAVEREG

`UWOP_SAVE_NONVOL` `UWOP_SAVE_NONVOL_FAR` 現在のプロローグオフセットを使用して、指定したレジスタ (*reg*) とオフセット (*オフセット*) に対するまたはアンワインドコードエントリを生成します。 MASM は、最も効率的なエンコードを選択します。

## <a name="syntax"></a>構文

> **.SAVEREG** *reg*__、__ *offset*

## <a name="remarks"></a>解説

**.SAVEREG** を使用すると、ml64.exe ユーザーは、フレーム関数をアンワインドする方法を指定できます。プロローグ内では、 [PROC](proc.md) frame 宣言からに拡張され [ます。ENDPROLOG](dot-endprolog.md) ディレクティブ。 これらのディレクティブはコードを生成しません。とだけが生成さ `.xdata` `.pdata` れます。 **.SAVEREG** の前に、アンワインドするアクションを実際に実装する手順を指定する必要があります。 アンワインドディレクティブと、マクロでアンワインドするコードをラップして、アグリーメントを保証することをお勧めします。

詳細については、「 [MASM for x64 (ml64.exe)](masm-for-x64-ml64-exe.md)」を参照してください。

## <a name="see-also"></a>関連項目

[ディレクティブリファレンス](directives-reference.md)\
[MASM BNF 文法](masm-bnf-grammar.md)

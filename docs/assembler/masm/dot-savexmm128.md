---
description: 詳細については、「」を参照してください。SAVEXMM128
title: .SAVEXMM128
ms.date: 12/17/2019
f1_keywords:
- .SAVEXMM128
helpviewer_keywords:
- .SAVEXMM128 directive
ms.assetid: 551eb472-b8d0-47b1-8d82-995d1f485723
ms.openlocfilehash: 697598aa5820b029d19da62a817c60455059865e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97131119"
---
# <a name="savexmm128"></a>.SAVEXMM128

`UWOP_SAVE_XMM128` `UWOP_SAVE_XMM128_FAR` 現在のプロローグオフセットを使用して、指定した XMM register および offset のアンワインドコードエントリを生成します。 MASM は、最も効率的なエンコードを選択します。

## <a name="syntax"></a>構文

> **.SAVEXMM128** *xmmreg* 、 *offset*

## <a name="remarks"></a>解説

**.SAVEXMM128** を使用すると、フレーム関数をアンワインドする方法をユーザーが指定 ml64.exe できるようになります。これは、 [PROC](proc.md) frame 宣言からに拡張されるプロローグ内でのみ使用でき [ます。ENDPROLOG](dot-endprolog.md) ディレクティブ。 これらのディレクティブはコードを生成しません。とだけが生成さ `.xdata` `.pdata` れます。 .SAVEXMM128 の前に、アンワインドするアクションを実際に実装する手順を指定する必要があります。 アンワインドディレクティブと、マクロでアンワインドするコードをラップして、アグリーメントを保証することをお勧めします。

*オフセット* は16の倍数である必要があります。

詳細については、「 [MASM for x64 (ml64.exe)](masm-for-x64-ml64-exe.md)」を参照してください。

## <a name="see-also"></a>関連項目

[ディレクティブリファレンス](directives-reference.md)\
[MASM BNF 文法](masm-bnf-grammar.md)

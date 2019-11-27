---
title: .SAVEXMM128
ms.date: 08/30/2018
f1_keywords:
- .SAVEXMM128
helpviewer_keywords:
- .SAVEXMM128 directive
ms.assetid: 551eb472-b8d0-47b1-8d82-995d1f485723
ms.openlocfilehash: 08bc5ab50e15aa59e0c49992d1810c7de20f364e
ms.sourcegitcommit: 9ee5df398bfd30a42739632de3e165874cb675c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74397950"
---
# <a name="savexmm128"></a>.SAVEXMM128

現在のプロローグオフセットを使用して、指定された XMM register および offset の `UWOP_SAVE_XMM128` または `UWOP_SAVE_XMM128_FAR` アンワインドコードエントリを生成します。 MASM は、最も効率的なエンコードを選択します。

## <a name="syntax"></a>構文

> **.SAVEXMM128** *xmmreg* 、 *offset*

## <a name="remarks"></a>コメント

**.SAVEXMM128**を使用すると、ml64.exe ユーザーは、フレーム関数をアンワインドする方法を指定できます。これは、 [PROC](../../assembler/masm/proc.md) frame 宣言からに拡張されるプロローグ内でのみ使用でき[ます。ENDPROLOG](../../assembler/masm/dot-endprolog.md)ディレクティブ。 これらのディレクティブはコードを生成しません。`.xdata` と `.pdata`のみが生成されます。 .SAVEXMM128 の前に、アンワインドするアクションを実際に実装する手順を指定する必要があります。 アンワインドディレクティブと、マクロでアンワインドするコードをラップして、アグリーメントを保証することをお勧めします。

*オフセット*は16の倍数である必要があります。

詳細については、「 [MASM for x64 (ml64.exe)](../../assembler/masm/masm-for-x64-ml64-exe.md)」を参照してください。

## <a name="see-also"></a>参照

[ディレクティブリファレンス](directives-reference.md)

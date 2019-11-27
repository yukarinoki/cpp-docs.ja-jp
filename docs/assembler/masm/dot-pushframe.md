---
title: .PUSHFRAME
ms.date: 08/30/2018
f1_keywords:
- .PUSHFRAME
helpviewer_keywords:
- .PUSHFRAME directive
ms.assetid: 17b123d0-4c6d-4fd2-85eb-798e8ad0a73c
ms.openlocfilehash: b0f047278f6250d5ef359f7992df4ea23f4bbd9b
ms.sourcegitcommit: 9ee5df398bfd30a42739632de3e165874cb675c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74398044"
---
# <a name="pushframe"></a>.PUSHFRAME

アンワインドコードエントリ `UWOP_PUSH_MACHFRAME` を生成します。 省略可能な*コード*が指定されている場合、アンワインドコードのエントリには1という修飾子が与えられます。 それ以外の場合、修飾子は0です。

## <a name="syntax"></a>構文

> **.PUSHFRAME** ⟦*code*⟧;;

## <a name="remarks"></a>コメント

.PUSHFRAME を使用すると、ml64.exe ユーザーは、フレーム関数をアンワインドする方法を指定できます。プロローグ内では、 [PROC](../../assembler/masm/proc.md) frame 宣言からに拡張され[ます。ENDPROLOG](../../assembler/masm/dot-endprolog.md)ディレクティブ。 これらのディレクティブはコードを生成しません。`.xdata` と `.pdata`のみが生成されます。 **.PUSHFRAME**の前には、アンワインドするアクションを実際に実装する命令が必要です。 アンワインドディレクティブと、マクロでアンワインドするコードをラップして、アグリーメントを保証することをお勧めします。

詳細については、「 [MASM for x64 (ml64.exe)](../../assembler/masm/masm-for-x64-ml64-exe.md)」を参照してください。

## <a name="see-also"></a>参照

[ディレクティブリファレンス](directives-reference.md)

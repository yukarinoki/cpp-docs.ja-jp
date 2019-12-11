---
title: ML の致命的なエラー A1010
ms.date: 08/30/2018
ms.custom: error-reference
f1_keywords:
- A1010
helpviewer_keywords:
- A1010
ms.assetid: 9e0b5241-67f4-4740-8701-3b2d2d1ad9e4
ms.openlocfilehash: 6ec82f7f6d559d977a9aa039ed91689a0ef4d49a
ms.sourcegitcommit: a6d63c07ab9ec251c48bc003ab2933cf01263f19
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "74856879"
---
# <a name="ml-fatal-error-a1010"></a>ML の致命的なエラー A1010

**一致しないブロックの入れ子:**

最初のブロックの終わりに一致するものがないか、またはブロックの末尾に一致する先頭がありませんでした。 次のいずれかが関係している可能性があります。

- などの高レベルのディレクティブ[。の場合は](../../assembler/masm/dot-if.md) [。](../../assembler/masm/dot-repeat.md)またはを繰り返し[ます。しばらくお待ち](../../assembler/masm/dot-while.md)ください。

- [IF](../../assembler/masm/if-masm.md)、 [REPEAT](../../assembler/masm/repeat.md)、 **WHILE**などの条件付きアセンブリディレクティブ。

- 構造体または共用体の定義。

- プロシージャの定義。

- セグメントの定義。

- [Popcontext](../../assembler/masm/popcontext.md)ディレクティブ。

- [If](../../assembler/masm/if-masm.md)と一致することのない、 [ELSE](../../assembler/masm/else-masm.md)、 [ELSEIF](../../assembler/masm/elseif-masm.md)、または**ENDIF**などの条件付きアセンブリディレクティブ。

## <a name="see-also"></a>参照

[ML エラー メッセージ](../../assembler/masm/ml-error-messages.md)<br/>
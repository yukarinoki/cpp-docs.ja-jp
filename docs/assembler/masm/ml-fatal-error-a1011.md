---
title: ML の致命的なエラー A1011
ms.date: 08/30/2018
ms.custom: error-reference
f1_keywords:
- A1011
helpviewer_keywords:
- A1011
ms.assetid: 7fbf092d-4189-4330-a884-dfa2268fc3dd
ms.openlocfilehash: 0d8d3896f7788aa3f51605651ee1b728b0e1d60a
ms.sourcegitcommit: a6d63c07ab9ec251c48bc003ab2933cf01263f19
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "74856853"
---
# <a name="ml-fatal-error-a1011"></a>ML の致命的なエラー A1011

**ディレクティブはコントロールブロック内になければなりません**

アセンブラーは、予期されていない上位レベルのディレクティブを検出しました。 次のいずれかのディレクティブが見つかりました。

- [.それ以外](../../assembler/masm/dot-else.md)の場合は[。IF](../../assembler/masm/dot-if.md)

- [.ENDIF](../../assembler/masm/dot-endif.md)が[ありません。IF](../../assembler/masm/dot-if.md)

- [.ENDW](../../assembler/masm/dot-endw.md)なし[。しばらく](../../assembler/masm/dot-while.md)

- [.UNTILCXZ](../../assembler/masm/dot-untilcxz.md) without [.REPEAT](../../assembler/masm/dot-repeat.md)

- [.](../../assembler/masm/dot-continue.md)を指定せずに続行[します。また](../../assembler/masm/dot-while.md)は[。繰り返し](../../assembler/masm/dot-repeat.md)

- [.](../../assembler/masm/dot-break.md)を使用せずに中断[します。また](../../assembler/masm/dot-while.md)は[。繰り返し](../../assembler/masm/dot-repeat.md)

- [.その他](../../assembler/masm/dot-else.md)の `.ELSE`

## <a name="see-also"></a>参照

[ML エラー メッセージ](../../assembler/masm/ml-error-messages.md)<br/>
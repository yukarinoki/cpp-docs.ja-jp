---
title: ML の致命的なエラー A1011
ms.date: 08/30/2018
ms.topic: error-reference
f1_keywords:
- A1011
helpviewer_keywords:
- A1011
ms.assetid: 7fbf092d-4189-4330-a884-dfa2268fc3dd
ms.openlocfilehash: 591755a1d7066d8251f61d2a22b9601a9ccb9dcb
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62178567"
---
# <a name="ml-fatal-error-a1011"></a>ML の致命的なエラー A1011

**ディレクティブは、コントロール ブロックである必要があります。**

アセンブラーでは、高度なディレクティブを 1 つは必要ありませんでしたが見つかりました。 次のディレクティブのいずれかが検出されました。

- [.ELSE](../../assembler/masm/dot-else.md)せず[します。もし](../../assembler/masm/dot-if.md)

- [.ENDIF](../../assembler/masm/dot-endif.md)せず[します。もし](../../assembler/masm/dot-if.md)

- [.ENDW](../../assembler/masm/dot-endw.md)せず[します。WHILE](../../assembler/masm/dot-while.md)

- [.UNTILCXZ](../../assembler/masm/dot-untilcxz.md) without [.REPEAT](../../assembler/masm/dot-repeat.md)

- [.引き続き](../../assembler/masm/dot-continue.md)せず[します。中に](../../assembler/masm/dot-while.md)または[します。繰り返し](../../assembler/masm/dot-repeat.md)

- [.中断](../../assembler/masm/dot-break.md)せず[します。中に](../../assembler/masm/dot-while.md)または[します。繰り返し](../../assembler/masm/dot-repeat.md)

- [.ELSE](../../assembler/masm/dot-else.md)以下 `.ELSE`

## <a name="see-also"></a>関連項目

[ML エラー メッセージ](../../assembler/masm/ml-error-messages.md)<br/>
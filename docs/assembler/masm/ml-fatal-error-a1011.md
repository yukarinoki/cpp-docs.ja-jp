---
title: ML の致命的なエラー A1011 |Microsoft Docs
ms.custom: ''
ms.date: 08/30/2018
ms.technology:
- cpp-masm
ms.topic: error-reference
f1_keywords:
- A1011
dev_langs:
- C++
helpviewer_keywords:
- A1011
ms.assetid: 7fbf092d-4189-4330-a884-dfa2268fc3dd
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 32949773b869d189516a381ca7df941760a1e4e4
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/04/2018
ms.locfileid: "43690809"
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
---
title: /STACK
ms.date: 11/04/2016
f1_keywords:
- /stack_editbin
helpviewer_keywords:
- -STACK editbin option
- STACK editbin option
- stack, setting size
- /STACK editbin option
ms.assetid: a39bcff0-c945-4355-80cc-8e4f24a5f142
ms.openlocfilehash: 63fcddec8ff8afd81084bb5a2786f394db594b07
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/17/2020
ms.locfileid: "79438888"
---
# <a name="stack"></a>/STACK

```
/STACK:reserve[,commit]
```

## <a name="remarks"></a>コメント

このオプションは、スタックのサイズをバイト単位で設定し、10進数または C 言語表記で引数を受け取ります。 /STACK オプションは、実行可能ファイルにのみ適用されます。

*Reserve*引数は、仮想メモリ内のスタック割り当ての合計を指定します。 EDITBIN は、指定された値を最も近い4バイトに切り上げます。

オプションの `commit` 引数は、オペレーティングシステムによって解釈される可能性があります。 Windows NT、Windows 95、および Windows 98 で `commit` は、一度に割り当てる物理メモリの量を指定します。 仮想メモリがコミットされると、ページング ファイル内にメモリ空間が予約されます。 `commit` 値を大きくすると、アプリケーションに必要なスタック領域が増加しますが、メモリ要件や起動時間が長くなります。

## <a name="see-also"></a>参照

[EDITBIN オプション](editbin-options.md)

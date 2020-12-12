---
description: 詳細情報:/STACK
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
ms.openlocfilehash: 253aec1d760a85f1ebe5dbf7596353b46744cd57
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97224453"
---
# <a name="stack"></a>/STACK

```
/STACK:reserve[,commit]
```

## <a name="remarks"></a>解説

このオプションは、スタックのサイズをバイト単位で設定し、10進数または C 言語表記で引数を受け取ります。 /STACK オプションは、実行可能ファイルにのみ適用されます。

*Reserve* 引数は、仮想メモリ内のスタック割り当ての合計を指定します。 EDITBIN は、指定された値を最も近い4バイトに切り上げます。

オプションの `commit` 引数は、オペレーティングシステムによって解釈される可能性があります。 Windows NT、Windows 95、および Windows 98 では、 `commit` 一度に割り当てる物理メモリの量を指定します。 仮想メモリがコミットされると、ページング ファイル内にメモリ空間が予約されます。 値を大きくする `commit` と、アプリケーションに必要なスタック領域が増加しますが、メモリ要件と起動時間が長くなります。

## <a name="see-also"></a>関連項目

[EDITBIN オプション](editbin-options.md)

---
description: 詳細については、「リンカツール Error LNK2013」を参照してください。
title: リンカ ツール エラー LNK2013
ms.date: 11/04/2016
f1_keywords:
- LNK2013
helpviewer_keywords:
- LNK2013
ms.assetid: 21408e2d-3f56-4d1f-a031-00df70785ed4
ms.openlocfilehash: 51b754e19656ad8ec7ef1686605086b6e4a41853
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97338458"
---
# <a name="linker-tools-error-lnk2013"></a>リンカ ツール エラー LNK2013

fixup type フィックスアップのオーバーフローです。 ターゲット 'symbol name' が範囲を超えています。

ターゲット シンボルが命令の位置から離れすぎているため、リンカーは必要なアドレスまたはオフセットを指定された命令に収めることができません。

この問題を解決するには、複数のイメージを作成するか、または [/order](../../build/reference/order-put-functions-in-order.md) オプションを使用します。これにより、命令とターゲットの距離が狭くなります。

シンボルがユーザー定義シンボルであり、コンパイラが生成したシンボルでない場合は、次の処理を実行して、エラーを解決することもできます。

- 静的関数を非静的関数に変更します。

- 静的関数を含むコード セクションを呼び出し側と同じ名前に変更します。

`DUMPBIN /SYMBOLS` を使用して、関数が静的かどうかを調べます。

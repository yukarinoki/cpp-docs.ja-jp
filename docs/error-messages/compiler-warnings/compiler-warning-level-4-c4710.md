---
title: コンパイラの警告 (レベル 4) C4710
ms.date: 11/04/2016
f1_keywords:
- C4710
helpviewer_keywords:
- C4710
ms.assetid: 76381ec7-3fc1-4bee-9a0a-c2c8307b92e2
ms.openlocfilehash: c30b98204f447f4d9d0ab8d687602a361d909363
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87218066"
---
# <a name="compiler-warning-level-4-c4710"></a>コンパイラの警告 (レベル 4) C4710

' function ': 関数がインライン化されていません。

指定された関数はインライン展開のために選択されましたが、コンパイラはインライン展開を実行しませんでした。

インライン展開は、コンパイラの判断で実行されます。 キーワードは、キーワードのように、 **`inline`** **`register`** コンパイラのヒントとして使用されます。 コンパイラはヒューリスティックを使用して、速度を高めるためにコンパイルするときにコードを高速化するために特定の関数をインライン化する必要があるかどうかを判断します。または、特定の関数をインライン化して、スペース用にコンパイルするときにコードを小さくします。 コンパイラは、スペース用にコンパイルするときに、非常に小さな関数だけをインライン化します。

場合によっては、コンパイラが特定の関数を機械的にインライン化することはありません。 コンパイラが関数をインライン化できない理由の一覧については、「 [C4714](../../error-messages/compiler-warnings/compiler-warning-level-4-c4714.md) 」を参照してください。

既定では、この警告はオフに設定されています。 詳細については、「 [既定で無効になっているコンパイラ警告](../../preprocessor/compiler-warnings-that-are-off-by-default.md) 」を参照してください。

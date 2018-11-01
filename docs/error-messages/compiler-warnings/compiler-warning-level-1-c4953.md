---
title: コンパイラの警告 (レベル 1) C4953
ms.date: 08/27/2018
f1_keywords:
- C4953
helpviewer_keywords:
- C4953
ms.assetid: 3c4f6ac6-3976-41ab-8a27-3c41d7472ea7
ms.openlocfilehash: 1948342e1ff97c38ca3a44694dc7e7d399d96825
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50568042"
---
# <a name="compiler-warning-level-1-c4953"></a>コンパイラの警告 (レベル 1) C4953

> インライン展開先 '*関数*' からプロファイル データが収集されたプロファイル データは使用されませんが編集されました

[/LTCG:PGUPDATE](../../build/reference/ltcg-link-time-code-generation.md)の使用時に、 `/LTCG:PGINSTRUMENT` の後で再コンパイルされた入力モジュールが検出されました。このモジュールには、編集された関数 (*function*) があります。既存のテストの実行では、その関数がインライン展開の候補として識別されました。 ただし、モジュールの再コンパイルの結果、関数はインライン展開の候補ではなくなります。

これは、情報提供の警告です。 この警告を解決するには、 `/LTCG:PGINSTRUMENT`を実行してすべてのテストを再実行し、 `/LTCG:PGOPTIMIZE`を実行します。

`/LTCG:PGOPTIMIZE` が使用されていた場合、この警告はエラーに置き換わります。
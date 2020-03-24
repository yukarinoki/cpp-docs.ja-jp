---
title: コンパイラの警告 (レベル 1) C4953
ms.date: 08/27/2018
f1_keywords:
- C4953
helpviewer_keywords:
- C4953
ms.assetid: 3c4f6ac6-3976-41ab-8a27-3c41d7472ea7
ms.openlocfilehash: 46f07227b5df62938cc51a7be4cf4f3595a0d947
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80174520"
---
# <a name="compiler-warning-level-1-c4953"></a>コンパイラの警告 (レベル 1) C4953

> プロファイルデータが収集されてから、インライン '*function*' が編集されました。プロファイルデータは使用されません

[/LTCG:PGUPDATE](../../build/reference/ltcg-link-time-code-generation.md)の使用時に、 `/LTCG:PGINSTRUMENT` の後で再コンパイルされた入力モジュールが検出されました。このモジュールには、編集された関数 (*function*) があります。既存のテストの実行では、その関数がインライン展開の候補として識別されました。 ただし、モジュールの再コンパイルの結果、関数はインライン展開の候補ではなくなります。

これは、情報提供の警告です。 この警告を解決するには、 `/LTCG:PGINSTRUMENT`を実行してすべてのテストを再実行し、 `/LTCG:PGOPTIMIZE`を実行します。

`/LTCG:PGOPTIMIZE` が使用されていた場合、この警告はエラーに置き換わります。

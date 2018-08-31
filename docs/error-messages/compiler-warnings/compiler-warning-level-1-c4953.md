---
title: コンパイラの警告 (レベル 1) C4953 |Microsoft Docs
ms.custom: ''
ms.date: 08/27/2018
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4953
dev_langs:
- C++
helpviewer_keywords:
- C4953
ms.assetid: 3c4f6ac6-3976-41ab-8a27-3c41d7472ea7
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9e53808d4ad97bad4eccdf81b0a863277f8f7796
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/29/2018
ms.locfileid: "43194633"
---
# <a name="compiler-warning-level-1-c4953"></a>コンパイラの警告 (レベル 1) C4953

> インライン展開先 '*関数*' からプロファイル データが収集されたプロファイル データは使用されませんが編集されました

使用する場合[/LTCG:PGUPDATE](../../build/reference/ltcg-link-time-code-generation.md)、後に再コンパイルされた入力モジュールが検出されました`/LTCG:PGINSTRUMENT`関数であり (*関数*) が編集して、既存のテストが実行されている識別された、機能の候補としてインライン化します。 ただし、モジュールの再コンパイルの結果、関数はインライン展開の候補ではなくなります。

これは、情報提供の警告です。 この警告を解決するには、 `/LTCG:PGINSTRUMENT`を実行してすべてのテストを再実行し、 `/LTCG:PGOPTIMIZE`を実行します。

`/LTCG:PGOPTIMIZE` が使用されていた場合、この警告はエラーに置き換わります。
---
title: 致命的なエラー C1307 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1307
dev_langs:
- C++
helpviewer_keywords:
- C1307
ms.assetid: 6f77d3d4-ba8a-476c-b540-aff19eb4efc4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 65f398dd9885c571ea0d66171889f20d3321a3b9
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46085863"
---
# <a name="fatal-error-c1307"></a>致命的なエラー C1307

プロファイル データが集められてからプログラムが編集されました。

使用する場合[/LTCG:PGOPTIMIZE](../../build/reference/ltcg-link-time-code-generation.md)リンカーは、/LTCG:PGINSTRUMENT 後に再コンパイルされた入力モジュールを検出およびモジュールが、既存のプロファイル データは関連性がなくなった点に変更されました。 たとえば、再コンパイルされたモジュールの呼び出し先が変更された場合、コンパイラは C1307 を生成します。

このエラーを解決するには、/LTCG:PGINSTRUMENT を実行、すべてのテストの実行を再実行および/LTCG:PGOPTIMIZE を実行します。 実行を/LTCG:PGINSTRUMENT とすべてのテストを再に実行することはできない場合、は、最適化されたイメージを作成する/LTCG:PGOPTIMIZE ではなく/LTCG:PGUPDATE を使用します。
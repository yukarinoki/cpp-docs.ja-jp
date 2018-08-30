---
title: コンパイラの警告 (レベル 1) C4952 |Microsoft Docs
ms.custom: ''
ms.date: 08/27/2018
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4952
dev_langs:
- C++
helpviewer_keywords:
- C4952
ms.assetid: 593324f0-5cfe-42fb-b221-2f71308765dd
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f62f4c18380d89eb516a5fa49ef63e92ab79a6f2
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/29/2018
ms.locfileid: "43207152"
---
# <a name="compiler-warning-level-1-c4952"></a>コンパイラの警告 (レベル 1) C4952

> '*関数*': プログラム データベースにプロファイル データが見つかりません'*pgd_fil*'

使用する場合[/LTCG:PGUPDATE](../../build/reference/ltcg-link-time-code-generation.md)、後に再コンパイルされた入力モジュールが検出されました`/LTCG:PGINSTRUMENT`新しい関数であり (*関数*) 存在します。

これは、情報提供の警告です。 この警告を解決するには、 `/LTCG:PGINSTRUMENT`を実行してすべてのテストを再実行し、 `/LTCG:PGOPTIMIZE`を実行します。

`/LTCG:PGOPTIMIZE` が使用されていた場合、この警告はエラーに置き換わります。
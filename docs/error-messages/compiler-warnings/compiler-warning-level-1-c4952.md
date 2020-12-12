---
description: '詳細情報: コンパイラの警告 (レベル 1) C4952'
title: コンパイラの警告 (レベル 1) C4952
ms.date: 08/27/2018
f1_keywords:
- C4952
helpviewer_keywords:
- C4952
ms.assetid: 593324f0-5cfe-42fb-b221-2f71308765dd
ms.openlocfilehash: afbc12f6e4e8219c541acd846a3752a331abe827
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97327951"
---
# <a name="compiler-warning-level-1-c4952"></a>コンパイラの警告 (レベル 1) C4952

> '*function*': プログラムデータベース '*pgd_file*' にプロファイルデータが見つかりませんでした

コンパイラが、 [/LTCG:PGUPDATE](../../build/reference/ltcg-link-time-code-generation.md)の使用時に、 `/LTCG:PGINSTRUMENT` の後で再コンパイルされ、新しい関数 (*function*) を持つ入力モジュールを検出しました。

これは、情報提供の警告です。 この警告を解決するには、 `/LTCG:PGINSTRUMENT`を実行してすべてのテストを再実行し、 `/LTCG:PGOPTIMIZE`を実行します。

`/LTCG:PGOPTIMIZE` が使用されていた場合、この警告はエラーに置き換わります。

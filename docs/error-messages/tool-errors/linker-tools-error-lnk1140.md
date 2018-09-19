---
title: リンカ ツール エラー LNK1140 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK1140
dev_langs:
- C++
helpviewer_keywords:
- LNK1140
ms.assetid: 468d7651-a7cd-47b9-aead-5bb2fab56121
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9f850360bc749a41e548cebae9f58f9fc7d3d420
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46044705"
---
# <a name="linker-tools-error-lnk1140"></a>リンカ ツール エラー LNK1140

プログラム データベース モジュールが多すぎます/pdb:none を指定してリンク: なし

プロジェクトには、4096 を超えるモジュールが含まれています。

### <a name="to-fix-by-using-the-following-possible-solutions"></a>以下の可能性がある解決策を使って修正するには

1. 使用して再リンク[/PDB: NONE](../../build/reference/pdb-use-program-database.md)します。

1. デバッグ情報なしには、一部のモジュールをコンパイルします。

1. モジュールの数を減らします。
---
title: リンカ ツール エラー LNK1140
ms.date: 11/04/2016
f1_keywords:
- LNK1140
helpviewer_keywords:
- LNK1140
ms.assetid: 468d7651-a7cd-47b9-aead-5bb2fab56121
ms.openlocfilehash: 845c796ee9611e921e2fd1707b9bb956ab62a5ac
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80195267"
---
# <a name="linker-tools-error-lnk1140"></a>リンカ ツール エラー LNK1140

プログラムデータベースのモジュールが多すぎます。/PDB を使用したリンク: なし

プロジェクトに4096以上のモジュールが含まれています。

### <a name="to-fix-by-using-the-following-possible-solutions"></a>修復の可能性がある解決策

1. [/Pdb: NONE](../../build/reference/pdb-use-program-database.md)を使用して再リンクします。

1. デバッグ情報を使用せずに、いくつかのモジュールをコンパイルします。

1. モジュールの数を減らします。

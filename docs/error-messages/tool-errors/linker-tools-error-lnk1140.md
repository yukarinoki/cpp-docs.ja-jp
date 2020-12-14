---
description: 詳細については、「リンカツール Error LNK1140」を参照してください。
title: リンカ ツール エラー LNK1140
ms.date: 11/04/2016
f1_keywords:
- LNK1140
helpviewer_keywords:
- LNK1140
ms.assetid: 468d7651-a7cd-47b9-aead-5bb2fab56121
ms.openlocfilehash: cde57e3594035aecc1cc3608d1329c5bc0752624
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97281198"
---
# <a name="linker-tools-error-lnk1140"></a>リンカ ツール エラー LNK1140

プログラムデータベースのモジュールが多すぎます。/PDB を使用したリンク: なし

プロジェクトに4096以上のモジュールが含まれています。

### <a name="to-fix-by-using-the-following-possible-solutions"></a>以下の可能性がある解決策を使って修正するには

1. [/Pdb: NONE](../../build/reference/pdb-use-program-database.md)を使用して再リンクします。

1. デバッグ情報を使用せずに、いくつかのモジュールをコンパイルします。

1. モジュールの数を減らします。

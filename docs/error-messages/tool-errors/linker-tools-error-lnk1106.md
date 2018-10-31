---
title: リンカ ツール エラー LNK1106 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK1106
dev_langs:
- C++
helpviewer_keywords:
- LNK1106
ms.assetid: 528f7e65-04be-4966-b8af-9276837c7cda
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ce6a8b2ef9ac807e48cff42186453666cebda5ee
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/25/2018
ms.locfileid: "50055985"
---
# <a name="linker-tools-error-lnk1106"></a>リンカ ツール エラー LNK1106

無効なファイルまたはディスクがいっぱいです: の場所にシークできません。

ツールの読み取りまたは書き込みがいない`location`メモリ マップト ファイル。

### <a name="to-fix-by-checking-the-following-possible-causes"></a>次のような原因をチェックして問題を解決するには

1. ディスクがいっぱいです。

   領域を解放し、リンクを再度クリックします。

1. ネットワーク経由でリンクしようとしています。

   いくつかのネットワークでは、リンカーで使用されるメモリ マップト ファイルは完全にサポートしていません。 ローカル ディスクでのリンクを再試行してください。

1. ディスクで不良ブロックします。

   オペレーティング システムとディスクのハードウェアでは、このようなエラーが検出が必要、ディスク チェックのプログラムを実行することがあります。

1. ヒープ領域にします。

   参照してください[C1060](../../error-messages/compiler-errors-1/fatal-error-c1060.md)詳細についてはします。
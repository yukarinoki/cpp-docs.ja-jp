---
title: リンカ ツール エラー LNK1106
ms.date: 11/04/2016
f1_keywords:
- LNK1106
helpviewer_keywords:
- LNK1106
ms.assetid: 528f7e65-04be-4966-b8af-9276837c7cda
ms.openlocfilehash: 091d4e173bfb2eff8ffee2b5c30647f4d5e3bc04
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80195371"
---
# <a name="linker-tools-error-lnk1106"></a>リンカ ツール エラー LNK1106

無効なファイルまたはディスクがいっぱいです: 場所をシークできません

このツールでは、メモリマップトファイル内の `location` に対して読み取りまたは書き込みを行うことができませんでした。

### <a name="to-fix-by-checking-the-following-possible-causes"></a>次のような原因をチェックして問題を解決するには

1. ディスクがいっぱいです。

   空き領域を増やしてから、リンクを再度作成してください。

1. ネットワーク経由でリンクを試行しています。

   一部のネットワークでは、リンカーによって使用されるメモリマップトファイルを完全にサポートしていません。 ローカルディスクでリンクを試行します。

1. ディスクのブロックが正しくありません。

   オペレーティングシステムとディスクハードウェアでこのようなエラーが検出されましたが、ディスクチェックプログラムを実行することをお勧めします。

1. ヒープ領域が不足しています。

   詳細については、「 [C1060](../../error-messages/compiler-errors-1/fatal-error-c1060.md) 」を参照してください。

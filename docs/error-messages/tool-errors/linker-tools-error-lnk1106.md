---
description: 詳細については、「リンカツール Error LNK1106」を参照してください。
title: リンカ ツール エラー LNK1106
ms.date: 11/04/2016
f1_keywords:
- LNK1106
helpviewer_keywords:
- LNK1106
ms.assetid: 528f7e65-04be-4966-b8af-9276837c7cda
ms.openlocfilehash: 85f353b6424cdd9ad12a99b29fec4f6119472cdb
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97281406"
---
# <a name="linker-tools-error-lnk1106"></a>リンカ ツール エラー LNK1106

無効なファイルまたはディスクがいっぱいです: 場所をシークできません

このツールでは、 `location` メモリマップトファイルの読み取りまたは書き込みを行うことができませんでした。

### <a name="to-fix-by-checking-the-following-possible-causes"></a>次のような原因をチェックして問題を解決するには

1. ディスクがいっぱいです。

   空き領域を増やしてから、リンクを再度作成してください。

1. ネットワーク経由でリンクを試行しています。

   一部のネットワークでは、リンカーによって使用されるメモリマップトファイルを完全にサポートしていません。 ローカルディスクでリンクを試行します。

1. ディスクのブロックが正しくありません。

   オペレーティングシステムとディスクハードウェアでこのようなエラーが検出されましたが、ディスクチェックプログラムを実行することをお勧めします。

1. ヒープ領域が不足しています。

   詳細については、「 [C1060](../../error-messages/compiler-errors-1/fatal-error-c1060.md) 」を参照してください。

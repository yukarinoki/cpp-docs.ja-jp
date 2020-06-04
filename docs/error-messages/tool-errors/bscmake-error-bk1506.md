---
title: BSCMAKE エラー BK1506
ms.date: 11/04/2016
f1_keywords:
- BK1506
helpviewer_keywords:
- BK1506
ms.assetid: f51f8cea-f8fc-4323-bcf2-b7bd119792ee
ms.openlocfilehash: b272a12e1d729e33794b550c911fd2e56f1af006
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80197796"
---
# <a name="bscmake-error-bk1506"></a>BSCMAKE エラー BK1506

ファイル ' filename ' を開くことができません [: reason]

BSCMAKE でファイルを開くことができません。

### <a name="to-fix-by-checking-the-following-possible-causes"></a>次のような原因をチェックして問題を解決するには

1. ファイルは別のプロセスによってロックされています。 `reason`**アクセス許可が拒否**されている場合は、ブラウザーがファイルを使用している可能性があります。 [参照] ウィンドウを閉じて、ビルドを再試行します。

1. フルディスク。

1. ハードウェアエラー。

1. 指定された出力ファイルには、既存のサブディレクトリと同じ名前が付けられています。

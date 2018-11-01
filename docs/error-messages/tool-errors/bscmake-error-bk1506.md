---
title: BSCMAKE エラー BK1506
ms.date: 11/04/2016
f1_keywords:
- BK1506
helpviewer_keywords:
- BK1506
ms.assetid: f51f8cea-f8fc-4323-bcf2-b7bd119792ee
ms.openlocfilehash: d1f74a90657985a87accc13bc2b576c1d7fd5a4e
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50554701"
---
# <a name="bscmake-error-bk1506"></a>BSCMAKE エラー BK1506

ファイル 'filename' を開くことができません [: 理由]

BSCMAKE では、ファイルを開くことができません。

### <a name="to-fix-by-checking-the-following-possible-causes"></a>次のような原因をチェックして問題を解決するには

1. ファイルが別のプロセスによってロックされています。 場合`reason`という**権限が拒否されました**、ファイル ブラウザーを使用することがあります。 参照ウィンドウを閉じるし、ビルドを再試行してください。

1. ディスクの空き領域。

1. ハードウェア エラーです。

1. 指定された出力ファイルは、既存のサブディレクトリとして同じ名前を持ちます。
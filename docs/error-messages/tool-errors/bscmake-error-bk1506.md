---
description: 詳細については、「BSCMAKE エラー BK1506」を参照してください。
title: BSCMAKE エラー BK1506
ms.date: 11/04/2016
f1_keywords:
- BK1506
helpviewer_keywords:
- BK1506
ms.assetid: f51f8cea-f8fc-4323-bcf2-b7bd119792ee
ms.openlocfilehash: 38911e6a961fdfcc30da1344dc84348aa7530a00
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97322948"
---
# <a name="bscmake-error-bk1506"></a>BSCMAKE エラー BK1506

ファイル ' filename ' を開くことができません [: reason]

BSCMAKE でファイルを開くことができません。

### <a name="to-fix-by-checking-the-following-possible-causes"></a>次のような原因をチェックして問題を解決するには

1. ファイルは別のプロセスによってロックされています。 `reason`**アクセス許可が拒否** された場合、ブラウザーはファイルを使用している可能性があります。 [参照] ウィンドウを閉じて、ビルドを再試行します。

1. フルディスク。

1. ハードウェアエラー。

1. 指定された出力ファイルには、既存のサブディレクトリと同じ名前が付けられています。

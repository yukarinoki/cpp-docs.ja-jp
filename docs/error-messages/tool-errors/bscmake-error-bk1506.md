---
title: BSCMAKE エラー BK1506 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- BK1506
dev_langs:
- C++
helpviewer_keywords:
- BK1506
ms.assetid: f51f8cea-f8fc-4323-bcf2-b7bd119792ee
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 26201a894212701cca19ab2192676b37a69e8b57
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46088697"
---
# <a name="bscmake-error-bk1506"></a>BSCMAKE エラー BK1506

ファイル 'filename' を開くことができません [: 理由]

BSCMAKE では、ファイルを開くことができません。

### <a name="to-fix-by-checking-the-following-possible-causes"></a>次のような原因をチェックして問題を解決するには

1. ファイルが別のプロセスによってロックされています。 場合`reason`という**権限が拒否されました**、ファイル ブラウザーを使用することがあります。 参照ウィンドウを閉じるし、ビルドを再試行してください。

1. ディスクの空き領域。

1. ハードウェア エラーです。

1. 指定された出力ファイルは、既存のサブディレクトリとして同じ名前を持ちます。
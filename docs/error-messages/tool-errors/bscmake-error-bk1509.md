---
title: BSCMAKE エラー BK1509
ms.date: 11/04/2016
f1_keywords:
- BK1509
helpviewer_keywords:
- BK1509
ms.assetid: 53df7037-1913-4b63-b425-c0bf44081792
ms.openlocfilehash: 384f202ea3eb969da2ce3a3b82209c383009c62e
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50475453"
---
# <a name="bscmake-error-bk1509"></a>BSCMAKE エラー BK1509

ヒープ スペースがありません。

BSCMAKE は、仮想メモリを含め、メモリ不足になりました。

### <a name="to-fix-by-using-the-following-possible-solutions"></a>以下の可能性がある解決策を使って修正するには

1. ディスク領域を解放します。

1. スワップ ファイルのサイズを増やします。

1. Windows のスワップ ファイルのサイズを増やします。

1. BSCMAKE は/Ei を使用して必要なメモリを減らすか、一部を排除する/Es 入力ファイルまたはマクロの本体を排除する/Em します。
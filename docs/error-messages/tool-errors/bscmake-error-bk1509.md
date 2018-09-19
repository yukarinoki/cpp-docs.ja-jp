---
title: BSCMAKE エラー BK1509 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- BK1509
dev_langs:
- C++
helpviewer_keywords:
- BK1509
ms.assetid: 53df7037-1913-4b63-b425-c0bf44081792
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 091fab63737c7ee1b3b85753a354bb7214cfa411
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46025244"
---
# <a name="bscmake-error-bk1509"></a>BSCMAKE エラー BK1509

ヒープ スペースがありません。

BSCMAKE は、仮想メモリを含め、メモリ不足になりました。

### <a name="to-fix-by-using-the-following-possible-solutions"></a>以下の可能性がある解決策を使って修正するには

1. ディスク領域を解放します。

1. スワップ ファイルのサイズを増やします。

1. Windows のスワップ ファイルのサイズを増やします。

1. BSCMAKE は/Ei を使用して必要なメモリを減らすか、一部を排除する/Es 入力ファイルまたはマクロの本体を排除する/Em します。
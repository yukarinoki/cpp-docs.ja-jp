---
title: コンパイラの警告 (レベル 2 および 3) C4008
ms.date: 11/04/2016
f1_keywords:
- C4008
helpviewer_keywords:
- C4008
ms.assetid: fb45e535-cb68-4743-80e9-a6e34cfffeca
ms.openlocfilehash: ab51b16331cc6a102c828234d2c2b8be84f2d276
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87225242"
---
# <a name="compiler-warning-levels-2-and-3-c4008"></a>コンパイラの警告 (レベル 2 および 3) C4008

'identifier': 'attribute' 属性は無視されました

コンパイラは **`__fastcall`** 、 **`static`** **`inline`** 関数 (レベル3の警告) またはデータ (レベル2の警告) の、、または属性を無視しました。

### <a name="to-fix-by-checking-the-following-possible-causes"></a>次のような原因をチェックして問題を解決するには

1. **`__fastcall`** データを含む属性。

1. **`static`****`inline`** **main**関数を使用した属性。

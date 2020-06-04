---
title: コンパイラの警告 (レベル 2 および 3) C4008
ms.date: 11/04/2016
f1_keywords:
- C4008
helpviewer_keywords:
- C4008
ms.assetid: fb45e535-cb68-4743-80e9-a6e34cfffeca
ms.openlocfilehash: 9b6fb56045d53cd18689f3903bb3d7a08c3d4e4d
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80198005"
---
# <a name="compiler-warning-levels-2-and-3-c4008"></a>コンパイラの警告 (レベル 2 および 3) C4008

'identifier': 'attribute' 属性は無視されました

コンパイラは、関数 (レベル 3 警告) またはデータ (レベル 2 警告) の `__fastcall`、 **静的**、または **インライン** 属性を無視しました。

### <a name="to-fix-by-checking-the-following-possible-causes"></a>次のような原因をチェックして問題を解決するには

1. データを伴う`__fastcall` 属性。

1. **メイン** 関数の **静的** または **インライン** 属性。

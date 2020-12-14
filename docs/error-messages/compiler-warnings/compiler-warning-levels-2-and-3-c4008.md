---
description: '詳細情報: コンパイラの警告 (レベル2および 3) C4008'
title: コンパイラの警告 (レベル 2 および 3) C4008
ms.date: 11/04/2016
f1_keywords:
- C4008
helpviewer_keywords:
- C4008
ms.assetid: fb45e535-cb68-4743-80e9-a6e34cfffeca
ms.openlocfilehash: 6f13ef60efabeaffe549189431aa04c65a12cbe5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97234424"
---
# <a name="compiler-warning-levels-2-and-3-c4008"></a>コンパイラの警告 (レベル 2 および 3) C4008

'identifier': 'attribute' 属性は無視されました

コンパイラは **`__fastcall`** 、 **`static`** **`inline`** 関数 (レベル3の警告) またはデータ (レベル2の警告) の、、または属性を無視しました。

### <a name="to-fix-by-checking-the-following-possible-causes"></a>次のような原因をチェックして問題を解決するには

1. **`__fastcall`** データを含む属性。

1. **`static`****`inline`** **main** 関数を使用した属性。

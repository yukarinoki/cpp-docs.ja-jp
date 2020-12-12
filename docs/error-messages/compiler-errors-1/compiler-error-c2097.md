---
description: 詳細については、「コンパイラエラー C2097」を参照してください。
title: コンパイラエラー C2097
ms.date: 11/04/2016
f1_keywords:
- C2097
helpviewer_keywords:
- C2097
ms.assetid: 7e5b2fd4-f61c-4b8a-b265-93e987a04bd3
ms.openlocfilehash: b9aa67f85ce9ba60a693500a2d7e3f69014cbba3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97278611"
---
# <a name="compiler-error-c2097"></a>コンパイラエラー C2097

無効な初期化

### <a name="to-fix-by-checking-the-following-possible-causes"></a>次のような原因をチェックして問題を解決するには

1. 非定数値を使用した変数の初期化。

1. 長いアドレスを持つ短いアドレスの初期化。

1. **/Za** を指定してコンパイルする場合の、非定数式を使用したローカル構造体、共用体、または配列の初期化。

1. コンマ演算子を含む式を使用した初期化。

1. 定数でもシンボリックでもない式を使用した初期化。

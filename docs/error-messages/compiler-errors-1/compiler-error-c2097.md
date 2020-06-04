---
title: コンパイラエラー C2097
ms.date: 11/04/2016
f1_keywords:
- C2097
helpviewer_keywords:
- C2097
ms.assetid: 7e5b2fd4-f61c-4b8a-b265-93e987a04bd3
ms.openlocfilehash: cdb14aeef61d136a6992a05a72f382e589e88770
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80207497"
---
# <a name="compiler-error-c2097"></a>コンパイラエラー C2097

無効な初期化

### <a name="to-fix-by-checking-the-following-possible-causes"></a>次のような原因をチェックして問題を解決するには

1. 非定数値を使用した変数の初期化。

1. 長いアドレスを持つ短いアドレスの初期化。

1. **/Za**を指定してコンパイルする場合の、非定数式を使用したローカル構造体、共用体、または配列の初期化。

1. コンマ演算子を含む式を使用した初期化。

1. 定数でもシンボリックでもない式を使用した初期化。

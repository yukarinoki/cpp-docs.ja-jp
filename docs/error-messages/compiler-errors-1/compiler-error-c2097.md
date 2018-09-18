---
title: コンパイラ エラー C2097 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2097
dev_langs:
- C++
helpviewer_keywords:
- C2097
ms.assetid: 7e5b2fd4-f61c-4b8a-b265-93e987a04bd3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2da955f5382a1ebacdb507a69ed02627b11462e5
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46021864"
---
# <a name="compiler-error-c2097"></a>コンパイラ エラー C2097

初期化が正しくありません。

### <a name="to-fix-by-checking-the-following-possible-causes"></a>次のような原因をチェックして問題を解決するには

1. 非定数の値を使用して変数の初期化。

1. 長いアドレスを使用して短いアドレスを初期化します。

1. ローカル構造体、共用体、または非定数の式をコンパイルするときに配列の初期化 **/Za**します。

1. コンマ演算子を含む式で初期化します。

1. 初期化式は定数もシンボルを定義します。
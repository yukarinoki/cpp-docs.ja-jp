---
title: コンパイラ エラー C2828
ms.date: 11/04/2016
f1_keywords:
- C2828
helpviewer_keywords:
- C2828
ms.assetid: d8df6ed4-5954-46c2-b59b-52881d4e923d
ms.openlocfilehash: d6dc742a181d8aebc041d9ffadd6256d3b7c9348
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50535344"
---
# <a name="compiler-error-c2828"></a>コンパイラ エラー C2828

'operator 演算子' は、バイナリ形式でグローバルに上書きすることはできません。

演算子は、オブジェクトの外部でバイナリ形式を持つことはできません。

### <a name="to-fix-by-using-the-following-possible-solutions"></a>以下の可能性がある解決策を使って修正するには

1. オブジェクトにオーバー ロードされた演算子をローカルに行います。

1. 適切な単項演算子をオーバー ロードを選択します。
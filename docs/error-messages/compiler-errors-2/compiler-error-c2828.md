---
description: 詳細については、「コンパイラエラー C2828」を参照してください。
title: コンパイラ エラー C2828
ms.date: 11/04/2016
f1_keywords:
- C2828
helpviewer_keywords:
- C2828
ms.assetid: d8df6ed4-5954-46c2-b59b-52881d4e923d
ms.openlocfilehash: 178b1998510d8119358d63ae0cf6f264efa6c9cb
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97194554"
---
# <a name="compiler-error-c2828"></a>コンパイラ エラー C2828

' operator operator ' は、バイナリ形式でグローバルにオーバーライドすることはできません

演算子は、オブジェクトの外部にバイナリ形式を持つことはできません。

### <a name="to-fix-by-using-the-following-possible-solutions"></a>以下の可能性がある解決策を使って修正するには

1. オーバーロードされた演算子をオブジェクトに対してローカルにします。

1. オーバーロードする適切な単項演算子を選択します。

---
description: 詳細については、「コンパイラエラー C2827」を参照してください。
title: コンパイラ エラー C2827
ms.date: 11/04/2016
f1_keywords:
- C2827
helpviewer_keywords:
- C2827
ms.assetid: cb3e5814-0c92-40e4-b620-98578ae3003a
ms.openlocfilehash: d9aae6fac1f21da2e1f4efad86024e11b94cf8e5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97194567"
---
# <a name="compiler-error-c2827"></a>コンパイラ エラー C2827

' operator operator ' を単項形式でグローバルにオーバーライドすることはできません

演算子は、オブジェクトの外部に単項形式を持つことはできません。

### <a name="to-fix-by-using-the-following-possible-solutions"></a>以下の可能性がある解決策を使って修正するには

1. オーバーロードされた演算子をオブジェクトに対してローカルにします。

1. オーバーロードする適切な単項演算子を選択します。

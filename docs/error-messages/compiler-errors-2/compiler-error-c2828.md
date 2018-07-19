---
title: コンパイラ エラー C2828 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2828
dev_langs:
- C++
helpviewer_keywords:
- C2828
ms.assetid: d8df6ed4-5954-46c2-b59b-52881d4e923d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f4735452f32ee1946119b1b055ed3d9eb08024d0
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33242628"
---
# <a name="compiler-error-c2828"></a>コンパイラ エラー C2828
'operator 演算子' は、バイナリ形式でグローバルに上書きすることはできません。  
  
 演算子は、オブジェクトの外部でバイナリ形式を持つことはできません。  
  
### <a name="to-fix-by-using-the-following-possible-solutions"></a>以下の可能性がある解決策を使って修正するには  
  
1.  オブジェクトにローカルのオーバー ロードされた演算子を加えます。  
  
2.  適切な単項演算子をオーバー ロードを選択します。
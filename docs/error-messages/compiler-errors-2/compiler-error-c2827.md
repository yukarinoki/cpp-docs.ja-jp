---
title: コンパイラ エラー C2827 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2827
dev_langs:
- C++
helpviewer_keywords:
- C2827
ms.assetid: cb3e5814-0c92-40e4-b620-98578ae3003a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0c96f9c3d43a289deb73fdb4414c344b7748da97
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33238590"
---
# <a name="compiler-error-c2827"></a>コンパイラ エラー C2827
単項形式にグローバルに 'operator 演算子' をオーバーライドすることはできません。  
  
 演算子は、オブジェクトの外側で単項形式を持つことはできません。  
  
### <a name="to-fix-by-using-the-following-possible-solutions"></a>以下の可能性がある解決策を使って修正するには  
  
1.  オブジェクトにローカルのオーバー ロードされた演算子を加えます。  
  
2.  適切な単項演算子をオーバー ロードを選択します。
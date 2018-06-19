---
title: 2.7.2.7 copyin |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 76cfb9f8-bf65-4585-adbf-fd933f5606b4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7ee711bfb24e7a2a1cbada1a7e01a243e204f4a8
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
ms.locfileid: "33689377"
---
# <a name="2727-copyin"></a>2.7.2.7 copyin
**Copyin**句に同じ値を代入するメカニズムを提供する**threadprivate**並列領域を実行する、チーム内の各スレッドの変数です。 指定された各変数に対して、 **copyin**並列領域の先頭に、スレッド プライベートなコピーへの代入した場合と同じ句、チームのマスター スレッド内の変数の値をコピーします。 構文、 **copyin**句を次に示します。  
  
```  
  
copyin(  
variable-list  
)  
  
```  
  
 制限、 **copyin**句は、次のようにします。  
  
-   指定されている変数、 **copyin**句は、あいまいでないアクセス可能なコピー代入演算子を持つ必要があります。  
  
-   指定されている変数、 **copyin**句がある必要があります、 **threadprivate**変数。
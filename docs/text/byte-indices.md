---
title: バイト インデックス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- MBCS [C++], byte indices
- byte indices [C++]
ms.assetid: f6e7774a-86c6-41c2-89e3-74fd46432e47
author: ghogen
ms.author: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 509e66c7ea458519eaa9dc4f52c8a6b65c789d0f
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
---
# <a name="byte-indices"></a>バイト インデックス
次のヒントを使用します。  
  
-   バイト単位でインデックスの操作を文字列には、ポインター操作と同様の問題を表示します。 この例では、円記号の文字列をスキャンを考慮してください。  
  
    ```  
    while ( rgch[ i ] != '\\' )  
        i++;  
    ```  
  
     末尾バイト、先行バイトではありません、このインデックスを可能性があり、したがって可能性がありますいないを指している、`character`です。  
  
-   使用して、 [_mbclen](../c-runtime-library/reference/mbclen-mblen-mblen-l.md)上記の問題を解決する関数。  
  
    ```  
    while ( rgch[ i ] != '\\' )  
        i += _mbclen ( rgch + i );  
    ```  
  
     これは、正しくため先行バイトにインデックスを作成する、`character`です。 `_mbclen`関数 (1 つまたは 2 バイト) 文字のサイズが決まります。  
  
## <a name="see-also"></a>関連項目  
 [MBCS のプログラミングについて](../text/mbcs-programming-tips.md)   
 [文字列の最後の文字](../text/last-character-in-a-string.md)
---
title: バイト インデックス |Microsoft Docs
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5beb69ef7d9d3356eddef40c6bce6483079d934a
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2018
ms.locfileid: "42590801"
---
# <a name="byte-indices"></a>バイト インデックス
次のヒントを使用します。  
  
-   バイト単位でインデックスの操作を文字列には、ポインター操作と同様の問題を表示します。 この例では、円記号の文字列をスキャンを検討してください。  
  
    ```  
    while ( rgch[ i ] != '\\' )  
        i++;  
    ```  
  
     末尾バイト、先行バイトではありません、このインデックスの可能性があり、したがってそれを指して可能性がありますいないを`character`します。  
  
-   使用して、 [_mbclen](../c-runtime-library/reference/mbclen-mblen-mblen-l.md)前の問題を解決する関数。  
  
    ```  
    while ( rgch[ i ] != '\\' )  
        i += _mbclen ( rgch + i );  
    ```  
  
     これは、正しくため先行バイトにインデックスを作成する、`character`します。 `_mbclen`関数 (1 つまたは 2 バイト) 文字のサイズを決定します。  
  
## <a name="see-also"></a>関連項目  
 [MBCS のプログラミングについて](../text/mbcs-programming-tips.md)   
 [文字列の最後の文字](../text/last-character-in-a-string.md)
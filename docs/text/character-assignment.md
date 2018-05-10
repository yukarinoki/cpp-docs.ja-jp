---
title: 文字の代入 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- characters [C++], assignments
- MBCS [C++], character assignments
ms.assetid: dcc329cd-92df-4e20-817d-364be62ff28f
author: ghogen
ms.author: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e403a619fc4c900aca51503862ff8f9dc315c2a3
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
---
# <a name="character-assignment"></a>文字の代入
これで、次の例を検討してください、`while`ループが別の文字列に 'X' 以外のすべての文字のコピー、文字列をスキャンします。  
  
```  
while( *sz2 )  
{  
    if( *sz2 != 'X' )  
        *sz1++ = *sz2++;  
    else  
        sz2++;  
}  
```  
  
 コードでは、位置のバイトをコピーする`sz2`によって示される場所に`sz1`、インクリメントし、`sz1`を次のバイトを受信します。 場合の次の文字`sz2`2 バイト文字への割り当ては、`sz1`最初のバイトのみをコピーします。 次のコードを使用してポータブル関数の文字を安全にコピーするもう 1 つをインクリメントする`sz1`と`sz2`正しく。  
  
```  
while( *sz2 )  
{  
    if( *sz2 != 'X' )  
    {  
        _mbscpy_s( sz1, 1, sz2 );  
        sz1 = _mbsinc( sz1 );  
        sz2 = _mbsinc( sz2 );  
    }  
    else  
        sz2 = _mbsinc( sz2 );  
}  
```  
  
## <a name="see-also"></a>関連項目  
 [MBCS のプログラミングについて](../text/mbcs-programming-tips.md)   
 [文字の比較](../text/character-comparison.md)
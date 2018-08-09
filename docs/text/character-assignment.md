---
title: 文字の代入 |Microsoft Docs
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
ms.openlocfilehash: 084cfd69a3742db10e09e9d97974a0666fa31a47
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/09/2018
ms.locfileid: "40010413"
---
# <a name="character-assignment"></a>文字の代入
これで、次の例を検討してください、**中に**ループは、別の文字列に 'X' 以外のすべての文字をコピー、文字列をスキャンします。  
  
```  
while( *sz2 )  
{  
    if( *sz2 != 'X' )  
        *sz1++ = *sz2++;  
    else  
        sz2++;  
}  
```  
  
 コードのコピーにあるバイト`sz2`によって示される場所に`sz1`、インクリメントし、`sz1`次のバイトを受信します。 場合の次の文字`sz2`2 バイト文字への代入は`sz1`最初のバイトのみをコピーします。 次のコードは、文字を安全にコピーする移植可能な関数とにインクリメント`sz1`と`sz2`正しく。  
  
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
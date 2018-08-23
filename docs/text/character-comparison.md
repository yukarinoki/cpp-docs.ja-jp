---
title: 文字の比較 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- comparing characters
- MBCS [C++], character comparison
- characters [C++], comparing
ms.assetid: 18846e44-3e6e-40c4-9b42-3153fb15db20
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 246801abcb04cc8d9c2fd1a005183501bde240d1
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2018
ms.locfileid: "42612327"
---
# <a name="character-comparison"></a>文字の比較
次のヒントを使用します。  
  
-   ASCII 文字と既知の先頭バイトを比較することは正しく動作します。  
  
    ```  
    if( *sz1 == 'A' )  
    ```  
  
-   2 つの不明な文字を比較するには、Mbstring.h で定義されているマクロのいずれかを使用する必要があります。  
  
    ```  
    if( !_mbccmp( sz1, sz2) )  
    ```  
  
     これにより、2 バイト文字の両方のバイトが等しいかどうかと比較されます。  
  
## <a name="see-also"></a>関連項目  
 [MBCS のプログラミングについて](../text/mbcs-programming-tips.md)   
 [バッファー オーバーフロー](../text/buffer-overflow.md)
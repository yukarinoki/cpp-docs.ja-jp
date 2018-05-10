---
title: 文字の比較 |Microsoft ドキュメント
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
author: ghogen
ms.author: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: b969783a19c0836a8ab81d75820fc688df3ef31e
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
---
# <a name="character-comparison"></a>文字の比較
次のヒントを使用します。  
  
-   ASCII 文字で既知の先行バイトを比較することは正しく動作します。  
  
    ```  
    if( *sz1 == 'A' )  
    ```  
  
-   2 つの不明な文字を比較するには、Mbstring.h で定義されているマクロのいずれかを使用する必要があります。  
  
    ```  
    if( !_mbccmp( sz1, sz2) )  
    ```  
  
     これにより、2 バイト文字の両方のバイトが等しいかどうか比較されます。  
  
## <a name="see-also"></a>関連項目  
 [MBCS のプログラミングについて](../text/mbcs-programming-tips.md)   
 [バッファー オーバーフロー](../text/buffer-overflow.md)
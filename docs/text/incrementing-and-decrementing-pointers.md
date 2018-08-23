---
title: インクリメントとデクリメント ポインター |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- incrementing pointers
- MBCS [C++], pointers
- pointers [C++], multibyte characters
- decrementing pointers
ms.assetid: 0872b4a0-e2bd-4004-8319-070efb76f2fd
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f4fff5d7ec20ce052e4d831f1556432186ebc7bb
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2018
ms.locfileid: "42603361"
---
# <a name="incrementing-and-decrementing-pointers"></a>ポインターのインクリメントとデクリメント
次のヒントを使用します。  
  
-   先行バイト、いない後続バイトをポイントします。 末尾バイトへのポインターが、通常は安全ではありません。 通常、逆の順序ではなく、順方向に文字列をスキャンするより安全になります。  
  
-   ポインターのインクリメントまたはデクリメント関数と全体の文字を重ねると使用可能なマクロがあります。  
  
    ```  
    sz1++;  
    ```  
  
     ようになります。  
  
    ```  
    sz1 = _mbsinc( sz1 );  
    ```  
  
     `_mbsinc`と`_mbsdec`関数が正しくインクリメントし、デクリメントで`character`文字のサイズに関係なく、単位。  
  
-   デクリメント、次のように、文字列の先頭へのポインターが必要です。  
  
    ```  
    sz2--;  
    ```  
  
     ようになります。  
  
    ```  
    sz2 = _mbsdec( sz2Head, sz2 );  
    ```  
  
     または、ヘッド ポインターが、文字列で、有効な文字になります。 ように。  
  
    ```  
    sz2Head < sz2  
    ```  
  
     既知の有効な先行バイトへのポインターが必要です。  
  
-   高速の呼び出しの前の文字へのポインターを保持したい場合があります`_mbsdec`します。  
  
## <a name="see-also"></a>関連項目  
 [MBCS のプログラミングについて](../text/mbcs-programming-tips.md)   
 [バイト インデックス](../text/byte-indices.md)
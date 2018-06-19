---
title: バッファー オーバーフローが発生 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- buffers [C++], character sizes
- buffer overflows [C++]
- MBCS [C++], buffer overflow
ms.assetid: f2b7e40a-f02b-46d8-a449-51d26fc0c663
author: ghogen
ms.author: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 13d01460e7ed9cb95d92303d82ea136803737331
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
ms.locfileid: "33854653"
---
# <a name="buffer-overflow"></a>バッファー オーバーフロー
文字のサイズを変更すると、バッファーに文字を配置するときに問題が発生することができます。 次のコードは、文字列から文字をコピー、 `sz`、バッファーに`rgch`:  
  
```  
cb = 0;  
while( cb < sizeof( rgch ) )  
    rgch[ cb++ ] = *sz++;  
```  
  
 この質問が: 最後のバイトが先行バイトをコピーしますか? 次は問題が解決しない、バッファー オーバーフローする可能性がある可能性があるため。  
  
```  
cb = 0;  
while( cb < sizeof( rgch ) )  
{  
    _mbccpy( rgch + cb, sz );  
    cb += _mbclen( sz );  
    sz = _mbsinc( sz );  
}  
```  
  
 `_mbccpy`呼び出しが、正しいことを実現しようとしています。-1 バイトまたは 2 バイトであるかどうか、完全な文字をコピーします。 コピーされる最後の文字可能性がありますで処理できないこと、バッファーの文字が 2 バイト幅である場合に取りません。 解決するには。  
  
```  
cb = 0;  
while( (cb + _mbclen( sz )) <= sizeof( rgch ) )  
{  
    _mbccpy( rgch + cb, sz );  
    cb += _mbclen( sz );  
    sz = _mbsinc( sz );  
}  
```  
  
 このコードは、ループでバッファーのオーバーフローのテストを使用してテスト`_mbclen`によって示される現在の文字のサイズをテストする`sz`です。 呼び出すことによって、`_mbsnbcpy`関数内のコードを置き換えることができます、`while`コードの 1 つの行をループします。 例えば:  
  
```  
_mbsnbcpy( rgch, sz, sizeof( rgch ) );  
```  
  
## <a name="see-also"></a>関連項目  
 [MBCS のプログラミングについて](../text/mbcs-programming-tips.md)
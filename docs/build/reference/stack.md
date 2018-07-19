---
title: -スタック |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /stack
dev_langs:
- C++
helpviewer_keywords:
- -STACK editbin option
- STACK editbin option
- stack, setting size
- /STACK editbin option
ms.assetid: a39bcff0-c945-4355-80cc-8e4f24a5f142
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a82111ce950d14bc6b3e270ee9a658d806b28b62
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32374077"
---
# <a name="stack"></a>/STACK
```  
/STACK:reserve[,commit]  
```  
  
## <a name="remarks"></a>コメント  
 このオプションは、スタックのサイズをバイト単位で設定され、10 進数または C 言語表記で引数を使用します。 /STACK オプションは、実行可能ファイルのみに適用されます。  
  
 *予約*引数は、仮想メモリのスタック割り当ての合計を指定します。 指定した値を最も近い 4 バイトに切り上げられます。  
  
 省略可能な`commit`引数は、オペレーティング システムによって解釈される可能性があります。 Windows NT、Windows 95 および Windows 98 で`commit`に一度に割り当てる物理メモリの量を指定します。 仮想メモリがコミットされると、ページング ファイル内にメモリ空間が予約されます。 高い`commit`値は、アプリケーションがより多くのスタック領域を必要がありますが、メモリ量と起動時間が増加時間を節約します。  
  
## <a name="see-also"></a>関連項目  
 [EDITBIN オプション](../../build/reference/editbin-options.md)
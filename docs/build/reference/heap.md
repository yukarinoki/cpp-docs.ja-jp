---
title: -ヒープ |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /heap
dev_langs:
- C++
helpviewer_keywords:
- heap allocation, setting heap size
- HEAP editbin option
- -HEAP editbin option
- /HEAP editbin option
ms.assetid: 6ce759b5-75b7-44ff-a5fd-3a83a0ba9a48
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5306df647801d7d1467aa0f44bfacca18fccaff3
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32372218"
---
# <a name="heap"></a>/HEAP
ヒープのサイズをバイト単位で設定します。 このオプションは、実行可能ファイルにのみ適用されます。  
  
```  
  
/HEAP:  
reserve[,commit]  
```  
  
## <a name="remarks"></a>コメント  
 `reserve`引数は、仮想メモリの合計の初期ヒープの割り当てを指定します。 既定では、ヒープ サイズは、1 MB です。 [EDITBIN リファレンス](../../build/reference/editbin-reference.md)指定された値を最も近い 4 バイトの倍数に丸められます。  
  
 省略可能な`commit`引数は、オペレーティング システムによって解釈される可能性があります。 Windows オペレーティング システムで最初に割り当てるには、物理メモリの容量と、ヒープを展開しなければならない場合に割り当てるメモリの量を指定します。 仮想メモリがコミットされると、ページング ファイル内にメモリ空間が予約されます。 高い`commit`値により、システムは、アプリは複数のヒープ領域が必要ですがメモリ量とアプリのスタートアップ時間が増加しているときに多くの場合、メモリの少ない割り当てにします。 `commit`値には、以下にする必要があります、`reserve`値。  
  
 指定して、`reserve`と`commit`10 進数または 16 進数または 8 進数の C 言語表記の値。 たとえば、10 進数、1048576 または 16 進数、0x100000 または 04000000 8 進数では、1 MB の値を指定できます。  
  
## <a name="see-also"></a>関連項目  
 [EDITBIN オプション](../../build/reference/editbin-options.md)
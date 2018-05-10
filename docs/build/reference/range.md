---
title: -範囲は |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /RANGE
dev_langs:
- C++
helpviewer_keywords:
- /RANGE dumpbin option
- -RANGE dumpbin option
ms.assetid: 7eeba266-32be-49cc-a350-96bdf541f98a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d06d699500ba3ea441af61a2e2a5a0da3f96903a
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="range"></a>/RANGE
Dumpbin/RAWDATA または/DISASM などその他の dumpbin オプションと共に使用する場合の出力を変更します。  
  
## <a name="syntax"></a>構文  
  
```  
/RANGE:vaMin[,vaMax]  
```  
  
## <a name="flags"></a>フラグ  
 **vaMin**  
 Dumpbin 操作を開始する仮想アドレス。  
  
 **vaMax** (省略可能)  
 Dumpbin 操作を終了する仮想アドレス。 指定しない場合、dumpbin は、ファイルの末尾に移動します。  
  
## <a name="remarks"></a>コメント  
 イメージの仮想アドレスを表示するには、(RVA + ベース)、画像のマップ ファイルを使用して、 **/DISASM**または **/HEADERS** dumpbin、または Visual Studio デバッガーで逆アセンブル ウィンドウのオプションです。  
  
## <a name="example"></a>例  
 この例では**範囲/** の表示を変更するために使用、 **/disasm**オプション。 この例では、開始値が 10 進数として表され、終了値は 16 進数として指定します。  
  
```  
dumpbin /disasm /range:4219334,0x004061CD t.exe  
```  
  
## <a name="see-also"></a>関連項目  
 [DUMPBIN オプション](../../build/reference/dumpbin-options.md)
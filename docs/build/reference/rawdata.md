---
title: -RAWDATA |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /rawdata
dev_langs:
- C++
helpviewer_keywords:
- RAWDATA dumpbin option
- raw data
- -RAWDATA dumpbin option
- /RAWDATA dumpbin option
ms.assetid: 41cba845-5e1f-415e-9fe4-604a52235983
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 28691e636f01174ecfe2a9d48b016523fce67f14
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32375000"
---
# <a name="rawdata"></a>/RAWDATA
```  
/RAWDATA[:{1|2|4|8|NONE[,number]]  
```  
  
## <a name="remarks"></a>コメント  
 このオプションは、ファイル内の各セクションの生の内容を表示します。 引数は、次に示すように、ディスプレイの形式を制御します。  
  
|引数|結果|  
|--------------|------------|  
|1|これが既定値です。 内容は、印刷された表現している場合 (16 進数のバイト単位) とも ASCII 文字として表示されます。|  
|2|内容は、16 進数の 2 バイト値として表示されます。|  
|4|内容は、4 バイトの 16 進数の値として表示されます。|  
|8|内容は、8 バイトの 16 進数の値として表示されます。|  
|[なし]|生データは表示されません。 この引数は出力を制御するのに役立つ/all です。|  
|*数値*|表示されている行を保持する、幅を設定`number`1 行の値。|  
  
 のみ、 [/HEADERS](../../build/reference/headers.md) DUMPBIN オプションはにより生成されるファイルで使用できるよう、 [/GL](../../build/reference/gl-whole-program-optimization.md)コンパイラ オプション。  
  
## <a name="see-also"></a>関連項目  
 [DUMPBIN オプション](../../build/reference/dumpbin-options.md)
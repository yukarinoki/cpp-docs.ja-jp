---
title: -LINKERMEMBER |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /linkermember
dev_langs:
- C++
helpviewer_keywords:
- /LINKERMEMBER dumpbin option
- LINKERMEMBER dumpbin option
- -LINKERMEMBER dumpbin option
ms.assetid: c96868c1-d70e-4651-ae36-c55b58b16406
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ac961f985de65bb7eea9a4ad0f5d10b75fbe60d3
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32371500"
---
# <a name="linkermember"></a>/LINKERMEMBER
```  
/LINKERMEMBER[:{1|2}]  
```  
  
## <a name="remarks"></a>コメント  
 このオプションは、ライブラリで定義されているパブリック シンボルを表示します。 そのオフセットと共に、オブジェクトの順序で記号を表示する 1 つの引数を指定します。 オフセットと、オブジェクトのインデックス番号を表示する 2 つの引数を指定してシンボルごとにオブジェクトのインデックスと共にのアルファベット順に一覧表示されます。 両方の出力を取得するには、数値の引数を指定せず/LINKERMEMBER を指定します。  
  
 のみ、 [/HEADERS](../../build/reference/headers.md) DUMPBIN オプションはにより生成されるファイルで使用できるよう、 [/GL](../../build/reference/gl-whole-program-optimization.md)コンパイラ オプション。  
  
## <a name="see-also"></a>関連項目  
 [DUMPBIN オプション](../../build/reference/dumpbin-options.md)
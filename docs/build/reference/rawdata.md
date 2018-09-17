---
title: -RAWDATA |マイクロソフトのドキュメント
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
ms.openlocfilehash: 38677b0e67ddaec5b6ef0e3fcffed1bed27826b6
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2018
ms.locfileid: "45707175"
---
# <a name="rawdata"></a>/RAWDATA

```
/RAWDATA[:{1|2|4|8|NONE[,number]]
```

## <a name="remarks"></a>Remarks

このオプションは、ファイルの各セクションの生の内容を表示します。 引数は、次に示すように、ディスプレイの形式を制御します。

|引数|結果|
|--------------|------------|
|1|これが既定値です。 内容は、印刷の表現がある場合 (16 進数のバイト単位) とも ASCII 文字として表示されます。|
|2|内容は、2 バイトの 16 進数の値として表示されます。|
|4|内容は、4 バイトの 16 進数の値として表示されます。|
|8|内容は、8 バイトの 16 進数の値として表示されます。|
|なし|生データは表示されません。 出力を制御するのには、この引数すべて/。|
|*数値*|表示行が保持する幅に設定されて`number`1 行の値。|

のみ、 [/HEADERS](../../build/reference/headers.md) DUMPBIN オプションがで生成されたファイルで使用できる、 [/GL](../../build/reference/gl-whole-program-optimization.md)コンパイラ オプション。

## <a name="see-also"></a>関連項目

[DUMPBIN オプション](../../build/reference/dumpbin-options.md)
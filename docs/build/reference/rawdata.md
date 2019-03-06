---
title: /RAWDATA
ms.date: 11/04/2016
f1_keywords:
- /rawdata
helpviewer_keywords:
- RAWDATA dumpbin option
- raw data
- -RAWDATA dumpbin option
- /RAWDATA dumpbin option
ms.assetid: 41cba845-5e1f-415e-9fe4-604a52235983
ms.openlocfilehash: 4e884ba8bca7b3ccdf900c7da2c43dd741c03d12
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/05/2019
ms.locfileid: "57413369"
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

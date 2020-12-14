---
description: 詳細情報:/RAWDATA
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
ms.openlocfilehash: efe2001c0170b8539b98902591849dedaf0fb819
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97225376"
---
# <a name="rawdata"></a>/RAWDATA

```
/RAWDATA[:{1|2|4|8|NONE[,number]]
```

## <a name="remarks"></a>解説

このオプションを選択すると、ファイル内の各セクションの未加工の内容が表示されます。 次に示すように、引数は表示形式を制御します。

|引数|結果|
|--------------|------------|
|1|これが既定値です。 コンテンツは16進バイトで表示されます。また、出力が表現されている場合は、ASCII 文字としても表示されます。|
|2|コンテンツは、16進数の2バイト値として表示されます。|
|4|コンテンツは、16進数の4バイト値として表示されます。|
|8|コンテンツは、16進数の8バイト値として表示されます。|
|NONE|生データは抑制されます。 この引数は、/allの出力を制御するのに役立ちます。|
|*Number*|表示される線は、1行に値を保持する幅に設定され `number` ます。|

[/GL](gl-whole-program-optimization.md) コンパイラ オプションで生成したファイルで使用できるのは、[/HEADERS](headers.md) DUMPBIN オプションだけです。

## <a name="see-also"></a>関連項目

[DUMPBIN オプション](dumpbin-options.md)

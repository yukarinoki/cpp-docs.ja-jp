---
title: /LINKERMEMBER
ms.date: 11/04/2016
f1_keywords:
- /linkermember
helpviewer_keywords:
- /LINKERMEMBER dumpbin option
- LINKERMEMBER dumpbin option
- -LINKERMEMBER dumpbin option
ms.assetid: c96868c1-d70e-4651-ae36-c55b58b16406
ms.openlocfilehash: 8669198ee62032e15e40c821ed2e4caccdebe519
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/05/2019
ms.locfileid: "57417490"
---
# <a name="linkermember"></a>/LINKERMEMBER

```
/LINKERMEMBER[:{1|2}]
```

## <a name="remarks"></a>Remarks

このオプションは、ライブラリで定義されたパブリック シンボルを表示します。 そのオフセットと共に、オブジェクトの順序でシンボルを表示する 1 引数を指定します。 オフセットとオブジェクトのインデックス番号を表示する 2 つの引数を指定し、各オブジェクトのインデックスと共に、アルファベット順にシンボルを一覧表示します。 両方の出力を取得するには、数値の引数なし/LINKERMEMBER を指定します。

のみ、 [/HEADERS](../../build/reference/headers.md) DUMPBIN オプションがで生成されたファイルで使用できる、 [/GL](../../build/reference/gl-whole-program-optimization.md)コンパイラ オプション。

## <a name="see-also"></a>関連項目

[DUMPBIN オプション](../../build/reference/dumpbin-options.md)

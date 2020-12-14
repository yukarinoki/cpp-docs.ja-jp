---
description: 詳細情報:/LINKERMEMBER
title: /LINKERMEMBER
ms.date: 11/04/2016
f1_keywords:
- /linkermember
helpviewer_keywords:
- /LINKERMEMBER dumpbin option
- LINKERMEMBER dumpbin option
- -LINKERMEMBER dumpbin option
ms.assetid: c96868c1-d70e-4651-ae36-c55b58b16406
ms.openlocfilehash: 76c842bcc2299b4245847e7d4e9a64656e88d2d9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97199390"
---
# <a name="linkermember"></a>/LINKERMEMBER

```
/LINKERMEMBER[:{1|2}]
```

## <a name="remarks"></a>解説

このオプションを選択すると、ライブラリで定義されているパブリックシンボルが表示されます。 オブジェクトの順序で記号を表示するには、1個の引数を指定します。 2つの引数を指定して、オブジェクトのオフセットとインデックス番号を表示します。次に、記号をアルファベット順に一覧表示し、それぞれのオブジェクトインデックスを使用します。 両方の出力を取得するには、number 引数を指定せずに/LINKERMEMBER を指定します。

[/GL](gl-whole-program-optimization.md) コンパイラ オプションで生成したファイルで使用できるのは、[/HEADERS](headers.md) DUMPBIN オプションだけです。

## <a name="see-also"></a>関連項目

[DUMPBIN オプション](dumpbin-options.md)

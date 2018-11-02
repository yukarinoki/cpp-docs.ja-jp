---
title: auto_inline
ms.date: 11/04/2016
f1_keywords:
- auto_inline_CPP
- vc-pragma.auto_inline
helpviewer_keywords:
- pragmas, auto_inline
- auto_inline pragma
ms.assetid: f7624cd1-be76-429a-881c-65c9040acf43
ms.openlocfilehash: a3e49941271ec294ddb69861d12e3451332770fe
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50633346"
---
# <a name="autoinline"></a>auto_inline
範囲内で定義された関数を除外で**オフ**自動インライン展開の候補と見なされないように指定します。

## <a name="syntax"></a>構文

```
#pragma auto_inline( [{on | off}] )
```

## <a name="remarks"></a>Remarks

使用する、 **auto_inline**プラグマ前に、と直後後に配置 (にない) 関数の定義。 プラグマは、このプラグマが発生した後の最初の関数呼び出し時に有効になります。

## <a name="see-also"></a>関連項目

[プラグマ ディレクティブと __Pragma キーワード](../preprocessor/pragma-directives-and-the-pragma-keyword.md)
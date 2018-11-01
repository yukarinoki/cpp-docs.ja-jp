---
title: 文字定数化演算子 (#@)
ms.date: 11/04/2016
f1_keywords:
- '#@'
helpviewer_keywords:
- preprocessor, operators
- charizing operator
- '#@ preprocessor operator'
ms.assetid: dee03314-d27c-4063-965c-64756efbef22
ms.openlocfilehash: 7259487a3289173bc77517c8c616638c370041c4
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50568341"
---
# <a name="charizing-operator-"></a>文字定数化演算子 (#@)
**Microsoft 固有の仕様**

文字定数化演算子は、マクロの引数でのみ使用できます。 場合`#@`仮パラメーターの前に、実引数の単一引用符で囲まれているし、マクロが展開されている場合は、文字として扱わマクロの定義でします。 例えば:

```
#define makechar(x)  #@x
```

は、次のステートメント

```
a = makechar(b);
```

を次のように展開します

```
a = 'b';
```

単一引用符文字は charizing 演算子では使用できません。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[プリプロセッサ演算子](../preprocessor/preprocessor-operators.md)
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
ms.openlocfilehash: c9acc9b9872e096cd441b950632c341e975fecb8
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/05/2019
ms.locfileid: "59034336"
---
# <a name="charizing-operator-"></a>文字定数化演算子 (#@)
**Microsoft 固有の仕様**

文字定数化演算子は、マクロの引数でのみ使用できます。 場合`#@`仮パラメーターの前に、実引数の単一引用符で囲まれているし、マクロが展開されている場合は、文字として扱わマクロの定義でします。 例:

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

**END Microsoft 固有の仕様**

## <a name="see-also"></a>関連項目

[プリプロセッサ演算子](../preprocessor/preprocessor-operators.md)
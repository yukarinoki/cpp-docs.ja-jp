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
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62403530"
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

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[プリプロセッサ演算子](../preprocessor/preprocessor-operators.md)
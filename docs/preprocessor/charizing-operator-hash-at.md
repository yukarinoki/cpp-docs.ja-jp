---
description: '詳細情報: 文字化演算子 (# @)'
title: 文字定数化演算子 (#@)
ms.date: 08/29/2019
f1_keywords:
- '#@'
helpviewer_keywords:
- preprocessor, operators
- charizing operator
- '#@ preprocessor operator'
ms.assetid: dee03314-d27c-4063-965c-64756efbef22
ms.openlocfilehash: 6d04aa24c75153957bd6fd09824f4e94e36fd38f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97300867"
---
# <a name="charizing-operator-"></a>文字定数化演算子 (#@)

**Microsoft 固有の仕様**

文字定数化演算子は、マクロの引数でのみ使用できます。 `#@`マクロの定義で仮パラメーターの前にがある場合、実際の引数は単一引用符で囲まれ、マクロが展開されるときに文字として扱われます。 次に例を示します。

```cpp
#define makechar(x)  #@x
```

は、次のステートメント

```cpp
a = makechar(b);
```

を次のように展開します

```cpp
a = 'b';
```

単一引用符文字 () は、文字型の `'` 演算子と共に使用することはできません。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[プリプロセッサ演算子](../preprocessor/preprocessor-operators.md)

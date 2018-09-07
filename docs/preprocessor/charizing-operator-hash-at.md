---
title: 演算子文字定数化 (#@) |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- '#@'
dev_langs:
- C++
helpviewer_keywords:
- preprocessor, operators
- charizing operator
- '#@ preprocessor operator'
ms.assetid: dee03314-d27c-4063-965c-64756efbef22
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d86c49c8d7d0cda91ba2415167cc79c810a96b3d
ms.sourcegitcommit: d10a2382832373b900b1780e1190ab104175397f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/06/2018
ms.locfileid: "43895306"
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
---
title: コンパイラの警告 (レベル 1) C4744
ms.date: 11/04/2016
f1_keywords:
- C4744
helpviewer_keywords:
- C4744
ms.assetid: f2a7d0b5-afd5-4926-abc3-cfbd367e3ff5
ms.openlocfilehash: 38a05c04181efb95ec3e7549c40056b8d223e128
ms.sourcegitcommit: c1fd917a8c06c6504f66f66315ff352d0c046700
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/16/2020
ms.locfileid: "90685555"
---
# <a name="compiler-warning-level-1-c4744"></a>コンパイラの警告 (レベル 1) C4744

' var ' は、' file1 ' および ' file2 ' で異なる型を含んでいます: ' type1 ' と ' type1 '

2つのファイルで参照または定義されている外部変数の型は、これらのファイルによって異なります。  解決するには、型定義を同じにするか、いずれかのファイルで変数名を変更します。

C4744 は、ファイルが/GL. でコンパイルされた場合にのみ生成されます。  詳細については、「[/GL (プログラム全体の最適化)](../../build/reference/gl-whole-program-optimization.md)」を参照してください。

> [!NOTE]
> C4744 は、通常、c++ ではなく C (C++) ファイルで発生します。これは、C++ では変数名が型情報で修飾されるためです。  サンプル (下記参照) が C++ としてコンパイルされると、リンカーエラー LNK2019 が発生します。

## <a name="examples"></a>例

このサンプルには、最初の定義が含まれています。

```c
// C4744.c
// compile with: /c /GL
int global;
```

次の例では、C4744 が生成されます。

```c
// C4744b.c
// compile with: C4744.c /GL /W1
// C4744 expected
#include <stdio.h>

extern unsigned global;

main()
{
    printf_s("%d\n", global);
}
```

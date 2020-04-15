---
title: コンパイラの警告 (レベル 1) C4744
ms.date: 11/04/2016
f1_keywords:
- C4744
helpviewer_keywords:
- C4744
ms.assetid: f2a7d0b5-afd5-4926-abc3-cfbd367e3ff5
ms.openlocfilehash: f932b1bcdf011678d4f85e0edf1e116a954b59fe
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81367379"
---
# <a name="compiler-warning-level-1-c4744"></a>コンパイラの警告 (レベル 1) C4744

'var' は 'file1' と 'file2' で異なる型を持っています: 'type1' と 'type2'

2 つのファイルで参照または定義された外部変数のファイルのタイプは異なります。  解決するには、型定義を同じにするか、いずれかのファイルの変数名を変更します。

C4744 は、ファイルが /GL でコンパイルされる場合にのみ出力されます。  詳細については、「[/GL (プログラム全体の最適化)](../../build/reference/gl-whole-program-optimization.md)」を参照してください。

> [!NOTE]
> C4744 は、C++ では変数名が型情報で修飾されるため、通常 C (C++ ではない) ファイルで発生します。  サンプル (下) が C++ としてコンパイルされると、リンカ エラー LNK2019 が表示されます。

## <a name="example"></a>例

このサンプルには、最初の定義が含まれています。

```c
// C4744.c
// compile with: /c /GL
int global;
```

## <a name="example"></a>例

次のサンプルでは、C4744 が生成されます。

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

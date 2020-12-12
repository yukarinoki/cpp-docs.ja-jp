---
description: '詳細情報: コンパイラの警告 (レベル 3) C4738'
title: コンパイラの警告 (レベル 3) C4738
ms.date: 11/04/2016
f1_keywords:
- C4738
helpviewer_keywords:
- C4738
ms.assetid: 9094895f-7eec-46c2-83d3-249b761d585e
ms.openlocfilehash: d57b992438148b3925b5366747db0b9de53ec87e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97332144"
---
# <a name="compiler-warning-level-3-c4738"></a>コンパイラの警告 (レベル 3) C4738

メモリに 32 ビットの浮動結果を格納します。パフォーマンスが低下する可能性があります

C4738 は、代入、キャスト、渡された引数、またはその他の操作の結果を丸める必要があるか、または操作がレジスタから不足してメモリを使用する必要があることを警告します (書き込む)。 これにより、パフォーマンスが低下する可能性があります。

この警告を解決して丸めを回避するには、 [/fp: fast](../../build/reference/fp-specify-floating-point-behavior.md) でコンパイルするか、ではなくを使用し **`double`** **`float`** ます。

この警告を解決してレジスタが不足しないようにするには、計算の順序を変更し、インライン展開の使用を変更します。

既定では、この警告はオフに設定されています。 詳細については、「 [Compiler Warnings That Are Off by Default](../../preprocessor/compiler-warnings-that-are-off-by-default.md)」を参照してください。

## <a name="example"></a>例

次の例では、C4738 が生成されます。

```cpp
// C4738.cpp
// compile with: /c /fp:precise /O2 /W3
// processor: x86
#include <stdio.h>

#pragma warning(default : 4738)

float func(float f)
{
    return f;
}

int main()
{
    extern float f, f1, f2;
    double d = 0.0;

    f1 = func(d);
    f2 = (float) d;
    f = f1 + f2;   // C4738
    printf_s("%f\n", f);
}
```

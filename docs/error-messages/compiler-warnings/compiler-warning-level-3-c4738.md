---
title: コンパイラの警告 (レベル 3) C4738 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4738
dev_langs:
- C++
helpviewer_keywords:
- C4738
ms.assetid: 9094895f-7eec-46c2-83d3-249b761d585e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8e017ef94dd28de8d4c66ab89b1509f755beeb07
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46053221"
---
# <a name="compiler-warning-level-3-c4738"></a>コンパイラの警告 (レベル 3) C4738

メモリに 32 ビットの浮動結果を格納します。パフォーマンスが低下する可能性があります

C4738 では、キャスト、代入式の結果には引数が渡されること、または他の操作は丸められる必要があります、または、操作がレジスタが不足して、メモリ (書き込み) を使用するために必要な警告が表示されます。 これは、結果、パフォーマンスの低下。

この警告を解決して、丸め処理を避けるためを使用してコンパイル[/fp:fast](../../build/reference/fp-specify-floating-point-behavior.md)使用または`double`の代わりに`float`します。

この警告を解決し、レジスタの不足を回避、計算の順序を変更しの使用を変更インライン展開

既定では、この警告はオフに設定されています。 詳細については、「 [Compiler Warnings That Are Off by Default](../../preprocessor/compiler-warnings-that-are-off-by-default.md)」を参照してください。

## <a name="example"></a>例

次の例では、C4738 が生成されます。

```
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
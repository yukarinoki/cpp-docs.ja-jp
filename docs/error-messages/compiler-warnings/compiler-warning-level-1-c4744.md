---
title: コンパイラの警告 (レベル 1) C4744 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4744
dev_langs:
- C++
helpviewer_keywords:
- C4744
ms.assetid: f2a7d0b5-afd5-4926-abc3-cfbd367e3ff5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1754977486327e06fb56a786be523c1b2fb7b917
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46068976"
---
# <a name="compiler-warning-level-1-c4744"></a>コンパイラの警告 (レベル 1) C4744

'var' が 'file1' および 'file2' に別の種類: 'type1' および 'type2'

または、参照される 2 つのファイルで定義されている外部変数は、これらのファイルにさまざまな種類をいます。  を解決するには、同じ種類の定義を作成するか、ファイルの 1 つの変数名を変更します。

ファイルが/gl コンパイルされるときのみ C4744 が生成されます。  詳細については、「[/GL (プログラム全体の最適化)](../../build/reference/gl-whole-program-optimization.md)」を参照してください。

> [!NOTE]
>  C4744 は、C++ では、変数名が型情報で修飾されたため、通常、C (C++ ではなく) ファイルで発生します。  (以下) のサンプルでは、C++ としてコンパイルが、リンカー エラー lnk2019 エラーが表示されます。

## <a name="example"></a>例

このサンプルには、最初の定義が含まれています。

```
// C4744.c
// compile with: /c /GL
int global;
```

## <a name="example"></a>例

次の例では、C4744 が生成されます。

```
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
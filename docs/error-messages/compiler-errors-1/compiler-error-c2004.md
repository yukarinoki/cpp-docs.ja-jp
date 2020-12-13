---
description: 詳細については、「コンパイラエラー C2004」を参照してください。
title: コンパイラ エラー C2004
ms.date: 11/04/2016
f1_keywords:
- C2004
helpviewer_keywords:
- C2004
ms.assetid: d81526dd-3a00-4593-87b0-d910d3d29bca
ms.openlocfilehash: f418d2c2c372b228cc50b82237d8ebc56321e2c7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97340386"
---
# <a name="compiler-error-c2004"></a>コンパイラ エラー C2004

'defined (id)' の形式にしてください。

プリプロセッサのキーワードに続く識別子は、かっこで囲む必要があります。

このエラーは、Visual Studio .NET 2003 でコンパイラ準拠作業が実施された結果、生成されることもあります。プリプロセッサ ディレクティブにかっこがありません。 プリプロセッサ ディレクティブに閉じかっこがない場合は、コンパイラによってエラーが生成されます。

## <a name="examples"></a>例

次の例では C2004 が生成されます。

```cpp
// C2004.cpp
// compile with: /DDEBUG
#include <stdio.h>

int main()
{
    #if defined(DEBUG   // C2004
        printf_s("DEBUG defined\n");
    #endif
}
```

考えられる解決策:

```cpp
// C2004b.cpp
// compile with: /DDEBUG
#include <stdio.h>

int main()
{
    #if defined(DEBUG)
        printf_s("DEBUG defined\n");
    #endif
}
```

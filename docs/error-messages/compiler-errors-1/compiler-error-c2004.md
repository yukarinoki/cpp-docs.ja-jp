---
title: コンパイラ エラー C2004 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2004
dev_langs:
- C++
helpviewer_keywords:
- C2004
ms.assetid: d81526dd-3a00-4593-87b0-d910d3d29bca
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b560ef96c4fadcb7c5ce57ece13647032ca9e902
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46118753"
---
# <a name="compiler-error-c2004"></a>コンパイラ エラー C2004

'defined (id)' の形式にしてください。

プリプロセッサのキーワードに続く識別子は、かっこで囲む必要があります。

このエラーは、Visual Studio .NET 2003 でコンパイラ準拠作業が実施された結果、生成されることもあります。プリプロセッサ ディレクティブにかっこがありません。 プリプロセッサ ディレクティブに閉じかっこがない場合は、コンパイラによってエラーが生成されます。

## <a name="example"></a>例

次の例では C2004 が生成されます。

```
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

## <a name="example"></a>例

考えられる解決方法:

```
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
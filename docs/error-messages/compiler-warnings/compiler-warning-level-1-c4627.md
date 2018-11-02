---
title: コンパイラの警告 (レベル 1) C4627
ms.date: 09/09/2018
f1_keywords:
- C4627
helpviewer_keywords:
- C4627
ms.assetid: 8840f3e6-b496-423a-8635-eb55d5f854a2
ms.openlocfilehash: e833141020de1aef51a1ea3823dea86b024e077d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50542390"
---
# <a name="compiler-warning-level-1-c4627"></a>コンパイラの警告 (レベル 1) C4627

> '*header_file*': プリコンパイル済みヘッダーの使用を検索するときにスキップ

現在のソース ファイルがある場合、 [/Yu\(プリコンパイル済みヘッダー ファイルを使用して)](../../build/reference/yu-use-precompiled-header-file.md)コンパイラでは、ファイル内のすべてが無視されるプリコンパイル済みヘッダーが含まれる前に、セット オプションします。 警告**C4627**場合に、Visual Studio 2015 と以前のバージョンで生成された*header_file*前、プリコンパイル済みヘッダー ファイルに含まれていることも、プリコンパイル済みヘッダーにが含まれていない場合、*header_file*します。

## <a name="example"></a>例

このサンプルでは、エラーの発生する可能性が、その修正方法を示しています。

```cpp
// c4627.cpp
#include <iostream>       // C4627 - iostream not included by pch.h
#include "pch.h"          // precompiled header file that does not include iostream
// #include <iostream>    // To fix, move the iostream header include here from above
int main()
{
    std::cout << "std::cout is defined!\n";
}
```

## <a name="see-also"></a>関連項目

[プリコンパイル済みヘッダー ファイルの作成](../../build/reference/creating-precompiled-header-files.md)

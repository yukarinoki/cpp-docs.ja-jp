---
description: '詳細情報: コンパイラの警告 (レベル 1) C4627'
title: コンパイラの警告 (レベル 1) C4627
ms.date: 09/09/2018
f1_keywords:
- C4627
helpviewer_keywords:
- C4627
ms.assetid: 8840f3e6-b496-423a-8635-eb55d5f854a2
ms.openlocfilehash: fc4c6c3931775b090dfd4c7c2fd5fd97441d40d3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97281445"
---
# <a name="compiler-warning-level-1-c4627"></a>コンパイラの警告 (レベル 1) C4627

> '*header_file*': プリコンパイル済みヘッダーの使用を検索しているときにスキップされました

現在のソースファイルに [ [/Yu \( Use プリコンパイル済みヘッダーファイルを使用](../../build/reference/yu-use-precompiled-header-file.md) する] オプションが設定されている場合、プリコンパイル済みヘッダーが含まれる前に、コンパイラによってファイル内のすべてが無視されます。 プリコンパイル済みヘッダーファイルの前に *header_file* が含まれている場合、およびプリコンパイル済みヘッダーに *header_file* が含まれていない場合は、Visual Studio 2015 以前のバージョンで警告 **C4627** が生成されます。

## <a name="example"></a>例

このサンプルでは、エラーがどのように発生するかを示し、その修正方法を示します。

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

[プリコンパイル済みヘッダー ファイルの作成](../../build/creating-precompiled-header-files.md)

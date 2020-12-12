---
description: '詳細情報: コンパイラの警告 (レベル 1) C4905'
title: コンパイラの警告 (レベル 1) C4905
ms.date: 11/04/2016
f1_keywords:
- C4905
helpviewer_keywords:
- C4905
ms.assetid: 40240bf4-b14e-4c22-aeb2-52f2851532f6
ms.openlocfilehash: ee2d3aecd26128c69325fdba15bbae44f2de0a8d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97338575"
---
# <a name="compiler-warning-level-1-c4905"></a>コンパイラの警告 (レベル 1) C4905

'LPSTR' にキャストされた幅の広いリテラル文字列

コンパイラにより、安全でないキャストが検出されました。 キャストは成功しましたが、変換ルーチンを使用する必要があります。

既定では、この警告はオフに設定されています。 詳細については、「 [既定で無効になっているコンパイラ警告](../../preprocessor/compiler-warnings-that-are-off-by-default.md) 」を参照してください。

## <a name="example"></a>例

次の例では、C4905 が生成されます。

```cpp
// C4905.cpp
// compile with: /W1
#pragma warning(default : 4905)
#include <windows.h>
#include <stdlib.h>
#include <stdio.h>

int main()
{
    LPSTR y = (LPSTR)L"1234";   // C4905

    // try the following lines instead
    // wchar_t y[128];
    // size_t  sizeOfConverted;
    // errcode err = 0;
    //
    // err = mbstowcs_s(&sizeOfConverted, &y[0], 128, "12345", 4);
    // if (err != 0)
    // {
    //     printf_s("mbstowcs_s failed!");
    //     exit (-1);
    // }
    // wprintf(L"%s\n", y);

    return 0;
}
```

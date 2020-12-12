---
description: 詳細については、「方法:/clr コンパイルを検出する」を参照してください。
title: '方法: clr コンパイルを検出する'
ms.custom: get-started-article
ms.date: 11/04/2016
helpviewer_keywords:
- compilation, detecting /clr
- /clr compiler option [C++], detecting use of
ms.assetid: a9310045-4810-4637-a64a-0b31a08791c1
ms.openlocfilehash: 25cd241a08f79bcae629c05fb3c7982a387120ce
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97175717"
---
# <a name="how-to-detect-clr-compilation"></a>方法: Detect /clr コンパイルを検出する

`_MANAGED`またはマクロを使用し `_M_CEE` て、モジュールが **/clr** でコンパイルされているかどうかを確認します。 詳細については、「 [/clr (共通言語ランタイムのコンパイル)](../build/reference/clr-common-language-runtime-compilation.md)」を参照してください。

マクロの詳細については、「 [定義済みマクロ](../preprocessor/predefined-macros.md)」を参照してください。

## <a name="example"></a>例

```cpp
// detect_CLR_compilation.cpp
// compile with: /clr
#include <stdio.h>

int main() {
   #if (_MANAGED == 1) || (_M_CEE == 1)
      printf_s("compiling with /clr\n");
   #else
      printf_s("compiling without /clr\n");
   #endif
}
```

## <a name="see-also"></a>関連項目

[C++ Interop (暗黙の PInvoke) の使用](../dotnet/using-cpp-interop-implicit-pinvoke.md)

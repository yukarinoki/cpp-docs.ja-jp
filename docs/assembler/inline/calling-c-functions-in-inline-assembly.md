---
description: 詳細については、「インラインアセンブリでの C 関数の呼び出し」を参照してください。
title: インライン アセンブリでの C 関数の呼び出し
ms.date: 08/30/2018
helpviewer_keywords:
- function calls, C functions
- function calls, in inline assembly
- functions [C], calling in inline assembly
- Visual C, functions
- inline assembly, calling functions
- __asm keyword [C++], calling functions
ms.assetid: f8a8d568-d175-4e23-9b24-36ef60a4cab3
ms.openlocfilehash: 5cdace4a909cbc49567988f85085eed5d84eadf0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97117992"
---
# <a name="calling-c-functions-in-inline-assembly"></a>インライン アセンブリでの C 関数の呼び出し

**Microsoft 固有の仕様**

ブロックは c **`__asm`** ライブラリルーチンなどの c 関数を呼び出すことができます。 次の例では、 `printf` ライブラリルーチンを呼び出します。

```cpp
// InlineAssembler_Calling_C_Functions_in_Inline_Assembly.cpp
// processor: x86
#include <stdio.h>

char format[] = "%s %s\n";
char hello[] = "Hello";
char world[] = "world";
int main( void )
{
   __asm
   {
      mov  eax, offset world
      push eax
      mov  eax, offset hello
      push eax
      mov  eax, offset format
      push eax
      call printf
      //clean up the stack so that main can exit cleanly
      //use the unused register ebx to do the cleanup
      pop  ebx
      pop  ebx
      pop  ebx
   }
}
```

関数の引数はスタックで渡されるため、関数を呼び出す前に、必要な引数 (前の例では文字列ポインター) をプッシュするだけです。 引数は逆順にプッシュされるため、目的の順序でスタックから出てきます。 C ステートメントをエミュレートするには

```cpp
printf( format, hello, world );
```

この例では、、、およびへのポインターをこの `world` `hello` `format` 順序でプッシュした後、を呼び出し `printf` ます。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[インラインアセンブラー](../../assembler/inline/inline-assembler.md)<br/>

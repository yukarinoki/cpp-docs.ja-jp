---
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
ms.openlocfilehash: 94bbfda3a5fd15885f3d8276d506541418a9489f
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80169592"
---
# <a name="calling-c-functions-in-inline-assembly"></a>インライン アセンブリでの C 関数の呼び出し

**Microsoft 固有の仕様**

`__asm` ブロックは c ライブラリルーチンなどの C 関数を呼び出すことができます。 次の例では、`printf` ライブラリルーチンを呼び出します。

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

この例では、`world`、`hello`、および `format`へのポインターをその順序でプッシュし、`printf`を呼び出します。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>参照

[インライン アセンブラー](../../assembler/inline/inline-assembler.md)<br/>

---
title: インライン アセンブリで関数を呼び出して C |Microsoft Docs
ms.custom: ''
ms.date: 08/30/2018
ms.technology:
- cpp-masm
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- function calls, C functions
- function calls, in inline assembly
- functions [C], calling in inline assembly
- Visual C, functions
- inline assembly, calling functions
- __asm keyword [C++], calling functions
ms.assetid: f8a8d568-d175-4e23-9b24-36ef60a4cab3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a080c05aee58a2e6ffae17d14e99c66922aa1f17
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/04/2018
ms.locfileid: "43686688"
---
# <a name="calling-c-functions-in-inline-assembly"></a>インライン アセンブリでの C 関数の呼び出し

**Microsoft 固有の仕様**

`__asm`ブロックは、C ライブラリ ルーチンのなどの C 関数を呼び出すことができます。 次の例では、`printf`ライブラリ ルーチン。

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

必要な引数を単にプッシュする関数の引数はスタックに渡される、ため-文字列ポインターは、前の例で、関数を呼び出す前にします。 引数は、目的の順序でスタックからポップも逆の順序でプッシュされます。 C ステートメントをエミュレートするには

```cpp
printf( format, hello, world );
```

例へのポインターをプッシュする`world`、 `hello`、および`format`では、その順序、呼び出し、その後、`printf`します。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[インライン アセンブラー](../../assembler/inline/inline-assembler.md)<br/>
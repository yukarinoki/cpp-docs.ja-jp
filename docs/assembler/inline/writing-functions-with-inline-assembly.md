---
title: インライン アセンブリでの関数の記述
ms.date: 08/30/2018
helpviewer_keywords:
- functions [C++], inline assembly
- inline assembly [C++], writing functions
- assembler [C++], writing functions
- __asm keyword [C++], in functions
ms.assetid: b5df8a04-fdc7-4622-8c9e-e4b618927497
ms.openlocfilehash: 3ce42147693f0c4c180076c627ef88c182745186
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87191002"
---
# <a name="writing-functions-with-inline-assembly"></a>インライン アセンブリでの関数の記述

**Microsoft 固有の仕様**

インラインアセンブラーコードを使用して関数を記述する場合は、関数に引数を渡して、その関数から値を返すのが簡単です。 次の例では、別のアセンブラー用に最初に記述された関数を比較し、インラインアセンブラー用に書き直しました。 という関数は、 `power2` 2 つのパラメーターを受け取り、最初のパラメーターに2を乗算し、2番目のパラメーターのべき乗を返します。 別のアセンブラー用に記述された関数は次のようになります。

```asm
; POWER.ASM
; Compute the power of an integer
;
       PUBLIC _power2
_TEXT SEGMENT WORD PUBLIC 'CODE'
_power2 PROC

        push ebp        ; Save EBP
        mov ebp, esp    ; Move ESP into EBP so we can refer
                        ;   to arguments on the stack
        mov eax, [ebp+4] ; Get first argument
        mov ecx, [ebp+6] ; Get second argument
        shl eax, cl     ; EAX = EAX * ( 2 ^ CL )
        pop ebp         ; Restore EBP
        ret             ; Return with sum in EAX

_power2 ENDP
_TEXT   ENDS
        END
```

別のアセンブラー用に記述されているため、この関数には別のソースファイルと、アセンブリとリンクの手順が必要です。 通常、C および C++ の関数の引数はスタックで渡されるので、このバージョンの関数は、 `power2` スタック上の位置によって引数にアクセスします。 (MASM およびその他のアセンブラーで使用できる**モデル**ディレクティブは、stack 引数とローカルスタック変数に名前でアクセスできることに注意してください)。

## <a name="example"></a>例

このプログラムは、 `power2` インラインアセンブラーコードを使用して関数を書き込みます。

```cpp
// Power2_inline_asm.c
// compile with: /EHsc
// processor: x86

#include <stdio.h>

int power2( int num, int power );

int main( void )
{
    printf_s( "3 times 2 to the power of 5 is %d\n", \
              power2( 3, 5) );
}
int power2( int num, int power )
{
   __asm
   {
      mov eax, num    ; Get first argument
      mov ecx, power  ; Get second argument
      shl eax, cl     ; EAX = EAX * ( 2 to the power of CL )
   }
   // Return with result in EAX
}
```

関数のインラインバージョンでは、 `power2` 引数が名前で参照され、プログラムの残りの部分と同じソースファイルに存在します。 このバージョンでは、必要なアセンブリ命令も少なくなります。

のインラインバージョンでは、 `power2` C ステートメントは実行されないため **`return`** 、警告レベル2以上でコンパイルした場合、無害な警告が発生します。 関数は値を返しますが、コンパイラは、ステートメントが存在しないことを認識できません **`return`** 。 [#Pragma 警告](../../preprocessor/warning.md)を使用して、この警告の生成を無効にすることができます。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[__Asm ブロックでの C または C++ の使用](../../assembler/inline/using-c-or-cpp-in-asm-blocks.md)<br/>

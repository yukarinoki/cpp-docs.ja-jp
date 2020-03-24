---
title: インライン アセンブリでの関数の記述
ms.date: 08/30/2018
helpviewer_keywords:
- functions [C++], inline assembly
- inline assembly [C++], writing functions
- assembler [C++], writing functions
- __asm keyword [C++], in functions
ms.assetid: b5df8a04-fdc7-4622-8c9e-e4b618927497
ms.openlocfilehash: 5416a29477651c496d83e6ee215a2cb88ba26e3b
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80169059"
---
# <a name="writing-functions-with-inline-assembly"></a>インライン アセンブリでの関数の記述

**Microsoft 固有の仕様**

インラインアセンブラーコードを使用して関数を記述する場合は、関数に引数を渡して、その関数から値を返すのが簡単です。 次の例では、別のアセンブラー用に最初に記述された関数を比較し、インラインアセンブラー用に書き直しました。 `power2`と呼ばれる関数は、2つのパラメーターを受け取り、最初のパラメーターに2を乗算して2番目のパラメーターのべき乗を返します。 別のアセンブラー用に記述された関数は次のようになります。

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

別のアセンブラー用に記述されているため、この関数には別のソースファイルと、アセンブリとリンクの手順が必要です。 通常、 C++ C および関数の引数はスタックで渡されるので、このバージョンの `power2` 関数は、スタック上の位置によって引数にアクセスします。 (MASM およびその他のアセンブラーで使用できる**モデル**ディレクティブは、stack 引数とローカルスタック変数に名前でアクセスできることに注意してください)。

## <a name="example"></a>例

このプログラムは、インラインアセンブラーコードを使用して `power2` 関数を書き込みます。

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

インラインバージョンの `power2` 関数は、引数を名前で参照し、プログラムの他の部分と同じソースファイルに表示されます。 このバージョンでは、必要なアセンブリ命令も少なくなります。

`power2` のインラインバージョンでは、C `return` ステートメントは実行されないため、警告レベル2以上でコンパイルした場合、無害な警告が発生します。 関数は値を返しますが、コンパイラは、`return` ステートメントが存在しないことを認識できません。 [#Pragma 警告](../../preprocessor/warning.md)を使用して、この警告の生成を無効にすることができます。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>参照

[__asm ブロックでの C または C++ の使用](../../assembler/inline/using-c-or-cpp-in-asm-blocks.md)<br/>

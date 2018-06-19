---
title: インライン アセンブリでの関数の記述 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-masm
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- functions [C++], inline assembly
- inline assembly [C++], writing functions
- assembler [C++], writing functions
- __asm keyword [C++], in functions
ms.assetid: b5df8a04-fdc7-4622-8c9e-e4b618927497
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c6c6c5b064dfc7d156d4de424e1ab69d74140f90
ms.sourcegitcommit: dbca5fdd47249727df7dca77de5b20da57d0f544
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2018
ms.locfileid: "32052740"
---
# <a name="writing-functions-with-inline-assembly"></a>インライン アセンブリでの関数の記述
## <a name="microsoft-specific"></a>Microsoft 固有の仕様  
 インライン アセンブラー コードを持つ関数を記述する場合は、関数に引数を渡すし、これから値を返すには簡単です。 次の例では、別のアセンブラーの最初に書き込まれ、インライン アセンブラーの再作成し、関数を比較します。 呼び出される関数`power2`、最初のパラメーターを 2 番目のパラメーターの電源を 2 で乗算の 2 つのパラメーターを受け取ります。 別のアセンブラー用に記述された、関数は、ようになります。  
  
```  
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
  
 別のアセンブラーに書き込まれるために、関数には、別のソース ファイルおよびアセンブリとリンクの手順が必要です。 通常、C および C++ の関数の引数はスタックで渡されますのでこのバージョンの`power2`関数がスタック上の位置で引数にアクセスします。 (なお、**モデル**ディレクティブ、MASM およびその他のいくつかのアセンブラーで使用することもできますスタック引数とローカル スタック変数に名前でアクセスします)。  
  
## <a name="example"></a>例  
 このプログラムに書き込みます、`power2`関数をインライン アセンブリ コード。  
  
```  
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
  
 インライン バージョンの`power2`関数名ではその引数を参照し、同じソース ファイル、プログラムの残りの部分に表示されます。 このバージョンでは、アセンブリ命令の数が少ないも必要です。  
  
 のインライン バージョン`power2`C を実行しない`return`ステートメントでは、その警告が発生、影響を与えません 2 以上の警告レベルでコンパイルする場合。 関数は、値を返すには、コンパイラがない場合、`return`ステートメントです。 使用することができます[#pragma 警告](../../preprocessor/warning.md)この警告の生成を無効にします。  
  
 **Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>関連項目  
 [__asm ブロックでの C または C++ の使用](../../assembler/inline/using-c-or-cpp-in-asm-blocks.md)
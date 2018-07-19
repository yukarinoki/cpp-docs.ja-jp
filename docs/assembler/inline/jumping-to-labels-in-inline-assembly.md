---
title: インライン アセンブラーのラベルにジャンプ |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-masm
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- inline assembly, jumping to labels
- labels, in inline assembly
- __asm keyword [C++], labels
- case sensitivity, labels in inline assembly
- labels, in __asm blocks
- jumping to labels in inline assembly
ms.assetid: 36c18b97-8981-4631-9dfd-af6c14a04297
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5a96bd532b5b4f03cb2040dd3157a6224ccf5029
ms.sourcegitcommit: dbca5fdd47249727df7dca77de5b20da57d0f544
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2018
ms.locfileid: "32052240"
---
# <a name="jumping-to-labels-in-inline-assembly"></a>インライン アセンブラーのラベルにジャンプ
## <a name="microsoft-specific"></a>Microsoft 固有の仕様  
 などの通常 C または C++ ラベル、ラベル、`__asm`ブロックはそれが定義されている (ブロック) 内だけでなく、関数全体のスコープを持ちます。 アセンブリの両方の手順と`goto`ステートメントの内側または外側のラベルにジャンプできます、`__asm`ブロックします。  
  
 定義されたラベル`__asm`ブロックは、大文字小文字を区別なく; 両方`goto`ステートメントおよびアセンブリ命令がケースに関係なくそれらのラベルを参照できます。 C および C++ のラベルは、大文字小文字を区別して使用する場合にのみ`goto`ステートメントです。 アセンブリ命令は、ケースに関係なく、C または C++ のラベルにジャンプできます。  
  
 次のコードは、すべての順列を示しています。  
  
```  
void func( void )  
{  
   goto C_Dest;  /* Legal: correct case   */  
   goto c_dest;  /* Error: incorrect case */  
  
   goto A_Dest;  /* Legal: correct case   */  
   goto a_dest;  /* Legal: incorrect case */  
  
   __asm  
   {  
      jmp C_Dest ; Legal: correct case  
      jmp c_dest ; Legal: incorrect case  
  
      jmp A_Dest ; Legal: correct case  
      jmp a_dest ; Legal: incorrect case  
  
      a_dest:    ; __asm label  
   }  
  
   C_Dest:       /* C label */   
   return;  
}  
int main()  
{  
}  
```  
  
 内のラベルとして C ライブラリの関数名を使用しない`__asm`ブロックします。 たとえば、する場合がありますを使用したい`exit`次のように、ラベルとして。  
  
```  
; BAD TECHNIQUE: using library function name as label  
jne exit  
   .  
   .  
   .  
exit:  
   ; More __asm code follows  
```  
  
 **終了**名前は、このコードは C のライブラリ関数へのジャンプを発生する可能性があります、**終了**関数の代わりに目的の場所をします。  
  
 MASM のプログラム]、[ドル記号と同様に (`$`) は、現在の場所カウンターとして機能します。 これは、構築された現在の命令のラベルです。 `__asm`ブロック、その主な用途は条件付き long ジャンプを確認します。  
  
```  
jne $+5 ; next instruction is 5 bytes long  
jmp farlabel  
; $+5  
   .  
   .  
   .  
farlabel:  
```  
  
 **Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>関連項目  
 [インライン アセンブラー](../../assembler/inline/inline-assembler.md)
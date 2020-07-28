---
title: インライン アセンブラーのラベルにジャンプ
ms.date: 08/30/2018
helpviewer_keywords:
- inline assembly, jumping to labels
- labels, in inline assembly
- __asm keyword [C++], labels
- case sensitivity, labels in inline assembly
- labels, in __asm blocks
- jumping to labels in inline assembly
ms.assetid: 36c18b97-8981-4631-9dfd-af6c14a04297
ms.openlocfilehash: 0c411289745466bd6478cc82ab30e6a05be9cc25
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87192003"
---
# <a name="jumping-to-labels-in-inline-assembly"></a>インライン アセンブラーのラベルにジャンプ

**Microsoft 固有の仕様**

通常の C または C++ のラベルと同様に、ブロック内のラベルの **`__asm`** スコープは、それが定義されている関数の中でも制限されます (ブロック内だけではありません)。 アセンブリ命令と **`goto`** ステートメントは、どちらもブロックの内側または外側のラベルにジャンプでき **`__asm`** ます。

ブロックで定義されているラベルで **`__asm`** は大文字と小文字が区別されません。 **`goto`** ステートメントとアセンブリ命令は、大文字小文字に関係なく、これらのラベルを参照できます。 C と C++ のラベルは、ステートメントで使用される場合にのみ、大文字と小文字が区別され **`goto`** ます。 アセンブリ命令は、大文字小文字に関係なく、C または C++ のラベルにジャンプできます。

次のコードは、すべての順列を示しています。

```cpp
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

C ライブラリ関数名をブロック内のラベルとして使用しないで **`__asm`** ください。 たとえば、次のように、をラベルとして使用することが考えられ `exit` ます。

```cpp
; BAD TECHNIQUE: using library function name as label
   jne exit
   .
   .
   .
exit:
   ; More __asm code follows
```

**Exit**は C ライブラリ関数の名前であるため、このコードでは、目的の場所ではなく**exit**関数へのジャンプが発生する可能性があります。

MASM プログラムと同様に、ドル記号 ( `$` ) は現在の位置カウンターとして機能します。 これは、現在アセンブルされている命令のラベルです。 **`__asm`** ブロックでは、次のように、条件付きジャンプを長くすることが主に使用されます。

```cpp
   jne $+5 ; next instruction is 5 bytes long
   jmp farlabel ; $+5
   .
   .
   .
farlabel:
```

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[インラインアセンブラー](../../assembler/inline/inline-assembler.md)<br/>

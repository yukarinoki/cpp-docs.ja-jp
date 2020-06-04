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
ms.openlocfilehash: 199156a08af13f4a70793609b37c70b0c95bf9ba
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80169332"
---
# <a name="jumping-to-labels-in-inline-assembly"></a>インライン アセンブラーのラベルにジャンプ

**Microsoft 固有の仕様**

通常の C またはC++ラベルと同様に、`__asm` ブロック内のラベルは、(ブロック内だけでなく) 定義されている関数全体でスコープを持ちます。 アセンブリ命令と `goto` ステートメントはどちらも、`__asm` ブロックの内側または外側のラベルにジャンプできます。

`__asm` ブロックで定義されているラベルでは大文字と小文字が区別されません。`goto` ステートメントとアセンブリ命令はどちらも、大文字小文字に関係なく、これらのラベルを参照できます。 C とC++ラベルは、`goto` ステートメントで使用される場合にのみ、大文字と小文字が区別されます。 アセンブリ命令は、大文字小文字にC++関係なく、C またはラベルにジャンプできます。

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

C ライブラリ関数名を `__asm` ブロックのラベルとして使用しないでください。 たとえば、次のように、ラベルとして `exit` を使用することが考えられます。

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

MASM プログラムと同様に、ドル記号 (`$`) は現在の位置カウンターとして機能します。 これは、現在アセンブルされている命令のラベルです。 `__asm` ブロックの主な用途は、条件付きジャンプを長くすることです。

```cpp
   jne $+5 ; next instruction is 5 bytes long
   jmp farlabel ; $+5
   .
   .
   .
farlabel:
```

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>参照

[インライン アセンブラー](../../assembler/inline/inline-assembler.md)<br/>

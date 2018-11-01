---
title: 生の擬似演算
ms.date: 11/04/2016
ms.assetid: 4def1a0e-ec28-4736-91fb-fac95fba1f36
ms.openlocfilehash: 04dfe4d59c05dfcf22d0e64063fbc4953cbcb2f8
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50538031"
---
# <a name="raw-pseudo-operations"></a>生の擬似演算

このトピックでは、擬似演算を使用します。

## <a name="remarks"></a>Remarks

|擬似演算|説明|
|----------------------|-----------------|
|PROC フレーム [: ehandler]|原因関数を生成する MASM がテーブルでは、.pdata エントリと .xdata 内の情報を関数の構造化のアンワインドの例外処理のアンワインド動作します。  Ehandler が存在する場合は、このプロシージャは、言語固有のハンドラーとして、.xdata に入力されます。<br /><br /> フレームの属性を使用する場合続けてする必要があります、します。ENDPROLOG ディレクティブです。  関数がリーフ関数の場合 (で定義されている[関数型](../build/function-types.md)) フレーム属性は必要に応じて、これらの擬似演算の残りの部分がありません。|
|.PUSHREG reg|現在のプロローグ内のオフセットを使用して指定のレジスタ番号の UWOP_PUSH_NONVOL アンワインド コードのエントリを生成します。<br /><br /> これは、不揮発性の整数レジスタでのみ使用する必要があります。  Volatile レジスタのプッシュを使用します。ALLOCSTACK 8 では、代わりに|
|.SETFRAME reg、オフセット|フレームの塗りつぶしは、指定されたレジスタおよびオフセットを使用して、アンワインド情報のフィールドとオフセットを登録します。 オフセットは 16 の倍数である必要があります、240 以下。 このディレクティブは、現在のプロローグのオフセットを使用して指定されたレジスタの UWOP_SET_FPREG アンワインド コードのエントリも生成されます。|
|.ALLOCSTACK サイズ|プロローグ内、UWOP_ALLOC_SMALL または現在のオフセットのサイズを指定して、UWOP_ALLOC_LARGE を生成します。<br /><br /> サイズのオペランドは 8 の倍数である必要があります。|
|.SAVEREG reg、オフセット|UWOP_SAVE_NONVOL、または指定されたレジスタとプロローグの現在のオフセットを使用してオフセット UWOP_SAVE_NONVOL_FAR アンワインド コードのエントリを生成します。 MASM は、最も効率的なエンコーディングを選択します。<br /><br /> オフセットは、正の値、および 8 の倍数である必要があります。  オフセットは RSP で一般的には、プロシージャのフレームのベースまたは、フレーム ポインターをスケールなしのフレーム ポインターを使用します。|
|.SAVEXMM128 reg、オフセット|UWOP_SAVE_XMM128、または指定の XMM レジスタとプロローグの現在のオフセットを使用してオフセット UWOP_SAVE_XMM128_FAR アンワインド コードのエントリを生成します。 MASM は、最も効率的なエンコーディングを選択します。<br /><br /> オフセットは、正の数値と 16 の倍数でなければなりません。  オフセットは RSP で一般的には、プロシージャのフレームのベースまたは、フレーム ポインターをスケールなしのフレーム ポインターを使用します。|
|.PUSHFRAME [コード]|UWOP_PUSH_MACHFRAME アンワインド コードのエントリを生成します。 省略可能なコードが指定されている場合、アンワインド コードのエントリには 1 の修飾子が与えられます。 それ以外の場合、修飾子には 0 です。|
|.ENDPROLOG|プロローグの宣言の終了を通知します。  関数の最初の 255 バイト単位で発生する必要があります。|

ほとんどのオペコードの適切な使用方法をサンプル関数のプロローグを次に示します。

```
sample PROC FRAME
   db      048h; emit a REX prefix, to enable hot-patching
push rbp
.pushreg rbp
sub rsp, 040h
.allocstack 040h
lea rbp, [rsp+020h]
.setframe rbp, 020h
movdqa [rbp], xmm7
.savexmm128 xmm7, 020h;the offset is from the base of the frame
;not the scaled offset of the frame
mov [rbp+018h], rsi
.savereg rsi, 038h
mov [rsp+010h], rdi
.savereg rdi, 010h; you can still use RSP as the base of the frame
; or any other register you choose
.endprolog

; you can modify the stack pointer outside of the prologue (similar to alloca)
; because we have a frame pointer.
; if we didn’t have a frame pointer, this would be illegal
; if we didn’t make this modification,
; there would be no need for a frame pointer

sub rsp, 060h

; we can unwind from the following AV because of the frame pointer

mov rax, 0
mov rax, [rax] ; AV!

; restore the registers that weren’t saved with a push
; this isn’t part of the official epilog, as described in section 2.5

movdqa xmm7, [rbp]
mov rsi, [rbp+018h]
mov rdi, [rbp-010h]

; Here’s the official epilog

lea rsp, [rbp-020h]
pop rbp
ret
sample ENDP
```

## <a name="see-also"></a>関連項目

[MASM のアンワインド ヘルパー](../build/unwind-helpers-for-masm.md)
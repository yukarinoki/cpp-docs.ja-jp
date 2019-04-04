---
title: .SETFRAME
ms.date: 08/30/2018
f1_keywords:
- .SETFRAME
helpviewer_keywords:
- .SETFRAME directive
ms.assetid: eaa9b5ed-4daa-4f1e-bdb6-100758007ab3
ms.openlocfilehash: c2c35cdb2889350b27e9fb11c397b684506972c5
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50506880"
---
# <a name="setframe"></a>.SETFRAME

フレームの塗りつぶしで指定されたレジスタを使用して、アンワインド情報のフィールドとオフセットの登録 (`reg`) とオフセット (`offset`)。 オフセットは 16 の倍数である必要があります、240 以下。 このディレクティブも生成されます、`UWOP_SET_FPREG`プロローグの現在のオフセットを使用して、指定した登録コードのエントリをアンワインドします。

## <a name="syntax"></a>構文

> .SETFRAME reg、オフセット

## <a name="remarks"></a>Remarks

.フレームの関数のアンワインドされるとから拡張すると、プロローグ内でのみ許可が指定できる ml64.exe の SETFRAME、 [PROC](../../assembler/masm/proc.md)フレームの宣言、[します。ENDPROLOG](../../assembler/masm/dot-endprolog.md)ディレクティブ。 これらのディレクティブは、コードを生成しませんのみを生成する`.xdata`と`.pdata`します。 .SETFRAME は、実際にアンワインド操作を実装する手順によって先行されなければなりません。 アンワインド ディレクティブと契約を確認します。 マクロでのアンワインドに本来はコードの両方をラップすることをお勧めします。

詳細については、[x64 用 MASM (ml64.exe)](../../assembler/masm/masm-for-x64-ml64-exe.md)を参照してください。

## <a name="sample"></a>サンプル

### <a name="description"></a>説明

次の例では、フレーム ポインターを使用する方法を示します。

### <a name="code"></a>コード

```asm
; ml64 frmex2.asm /link /entry:frmex2 /SUBSYSTEM:CONSOLE
_text SEGMENT
frmex2 PROC FRAME
   push rbp
.pushreg rbp
   sub rsp, 010h
.allocstack 010h
   mov rbp, rsp
.setframe rbp, 0
.endprolog
   ; modify the stack pointer outside of the prologue (similar to alloca)
   sub rsp, 060h

   ; we can unwind from the following AV because of the frame pointer
   mov rax, 0
   mov rax, [rax] ; AV!

   add rsp, 060h
   add rsp, 010h
   pop rbp
   ret
frmex2 ENDP
_text ENDS
END
```

## <a name="see-also"></a>関連項目

[ディレクティブ リファレンス](../../assembler/masm/directives-reference.md)<br/>
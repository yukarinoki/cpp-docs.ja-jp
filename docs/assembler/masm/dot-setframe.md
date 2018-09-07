---
title: .SETFRAME |Microsoft Docs
ms.custom: ''
ms.date: 08/30/2018
ms.technology:
- cpp-masm
ms.topic: reference
f1_keywords:
- .SETFRAME
dev_langs:
- C++
helpviewer_keywords:
- .SETFRAME directive
ms.assetid: eaa9b5ed-4daa-4f1e-bdb6-100758007ab3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 956a49e40c38310819d66e89fa6bf4492443a29c
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/04/2018
ms.locfileid: "43691290"
---
# <a name="setframe"></a>.SETFRAME

フレームの塗りつぶしで指定されたレジスタを使用して、アンワインド情報のフィールドとオフセットの登録 (`reg`) とオフセット (`offset`)。 オフセットは 16 の倍数である必要があります、240 以下。 このディレクティブも生成されます、`UWOP_SET_FPREG`プロローグの現在のオフセットを使用して、指定した登録コードのエントリをアンワインドします。

## <a name="syntax"></a>構文

> .SETFRAME reg、オフセット

## <a name="remarks"></a>Remarks

.フレームの関数のアンワインドされるとから拡張すると、プロローグ内でのみ許可が指定できる ml64.exe の SETFRAME、 [PROC](../../assembler/masm/proc.md)フレームの宣言、[します。ENDPROLOG](../../assembler/masm/dot-endprolog.md)ディレクティブ。 これらのディレクティブは、コードを生成しませんのみを生成する`.xdata`と`.pdata`します。 .SETFRAME は、実際にアンワインド操作を実装する手順によって先行されなければなりません。 アンワインド ディレクティブと契約を確認します。 マクロでのアンワインドに本来はコードの両方をラップすることをお勧めします。

詳細については、次を参照してください。 [x64 用 MASM (ml64.exe)](../../assembler/masm/masm-for-x64-ml64-exe.md)します。

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
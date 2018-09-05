---
title: .ALLOCSTACK |Microsoft Docs
ms.custom: ''
ms.date: 08/30/2018
ms.technology:
- cpp-masm
ms.topic: reference
f1_keywords:
- .ALLOCSTACK
dev_langs:
- C++
helpviewer_keywords:
- .ALLOCSTACK directive
ms.assetid: 9801594b-7ac2-4df2-a49d-07d9dd9af99e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 292a7fcdb0a1d7c4ecccab895c643479397b4a98
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/04/2018
ms.locfileid: "43681932"
---
# <a name="allocstack"></a>.ALLOCSTACK

生成されます、 **UWOP_ALLOC_SMALL**または**UWOP_ALLOC_LARGE**プロローグ内の現在のオフセットのサイズを指定しています。

## <a name="syntax"></a>構文

> .ALLOCSTACK サイズ

## <a name="remarks"></a>Remarks

MASM は最も効率的なエンコーディングを指定されたサイズを選択します。

.ALLOCSTACK が ml64.exe ユーザーは、フレームの関数をアンワインドする方法を指定することしから拡張すると、プロローグ内でのみ使用できますが、 [PROC](../../assembler/masm/proc.md)フレームの宣言、[します。ENDPROLOG](../../assembler/masm/dot-endprolog.md)ディレクティブ。 これらのディレクティブは、コードを生成しませんのみを生成する`.xdata`と`.pdata`します。 .ALLOCSTACK は、実際にアンワインド操作を実装する手順によって先行されなければなりません。 アンワインド ディレクティブと契約を確認します。 マクロでのアンワインドに本来はコードの両方をラップすることをお勧めします。

`size`オペランドは 8 の倍数である必要があります。

詳細については、次を参照してください。 [x64 用 MASM (ml64.exe)](../../assembler/masm/masm-for-x64-ml64-exe.md)します。

## <a name="sample"></a>サンプル

次の例では、アンワインド/例外ハンドラーを指定する方法を示します。

```asm
; ml64 ex3.asm /link /entry:Example1  /SUBSYSTEM:Console
text SEGMENT
PUBLIC Example3
PUBLIC Example3_UW
Example3_UW PROC NEAR
   ; exception/unwind handler body

   ret 0

Example3_UW ENDP

Example3 PROC FRAME : Example3_UW

   sub rsp, 16
.allocstack 16

.endprolog

   ; function body
    add rsp, 16
   ret 0

Example3 ENDP
text ENDS
END
```

## <a name="see-also"></a>関連項目

[ディレクティブ リファレンス](../../assembler/masm/directives-reference.md)<br/>
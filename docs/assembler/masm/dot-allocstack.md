---
title: .ALLOCSTACK
ms.date: 08/30/2018
f1_keywords:
- .ALLOCSTACK
helpviewer_keywords:
- .ALLOCSTACK directive
ms.assetid: 9801594b-7ac2-4df2-a49d-07d9dd9af99e
ms.openlocfilehash: 6d9d86371503992d1bebe738fb6e6773581b10e3
ms.sourcegitcommit: 9ee5df398bfd30a42739632de3e165874cb675c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74398630"
---
# <a name="allocstack"></a>.ALLOCSTACK

プロローグ内の現在のオフセットに対して、指定したサイズの**UWOP_ALLOC_SMALL**または**UWOP_ALLOC_LARGE**を生成します。

## <a name="syntax"></a>構文

> **.ALLOCSTACK** *サイズ*

## <a name="remarks"></a>コメント

MASM は、特定のサイズに対して最も効率的なエンコードを選択します。

**.ALLOCSTACK**を使用すると、ml64.exe ユーザーは、フレーム関数をアンワインドする方法を指定できます。プロローグ内では、 [PROC](../../assembler/masm/proc.md) frame 宣言からに拡張され[ます。ENDPROLOG](../../assembler/masm/dot-endprolog.md)ディレクティブ。 これらのディレクティブはコードを生成しません。`.xdata` と `.pdata`のみが生成されます。 **.ALLOCSTACK**の前には、アンワインドするアクションを実際に実装する命令が必要です。 アンワインドディレクティブと、マクロでアンワインドするコードをラップして、アグリーメントを保証することをお勧めします。

*サイズ*オペランドは8の倍数である必要があります。

詳細については、「 [MASM for x64 (ml64.exe)](../../assembler/masm/masm-for-x64-ml64-exe.md)」を参照してください。

## <a name="sample"></a>サンプル

次の例は、アンワインド/例外ハンドラーを指定する方法を示しています。

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

## <a name="see-also"></a>参照

[ディレクティブ リファレンス](../../assembler/masm/directives-reference.md)

---
title: .PUSHREG
ms.date: 08/30/2018
f1_keywords:
- .PUSHREG
helpviewer_keywords:
- .PUSHREG directive
ms.assetid: e0c83758-dfed-40ea-afe6-cb833c8d2d30
ms.openlocfilehash: 2190bd05667de82dada34a63f11647c653f97247
ms.sourcegitcommit: 9ee5df398bfd30a42739632de3e165874cb675c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74398034"
---
# <a name="pushreg"></a>.PUSHREG

プロローグ内の現在のオフセットを使用して、指定したレジスタ番号に `UWOP_PUSH_NONVOL` アンワインドコードエントリを生成します。

## <a name="syntax"></a>構文

> .PUSHREG レジスタ

## <a name="remarks"></a>コメント

**.PUSHREG**を使用すると、ml64.exe ユーザーは、フレーム関数をアンワインドする方法を指定できます。これは、 [PROC](../../assembler/masm/proc.md) **frame**宣言からに拡張されるプロローグ内でのみ使用でき[ます。ENDPROLOG](../../assembler/masm/dot-endprolog.md)ディレクティブ。 これらのディレクティブはコードを生成しません。`.xdata` と `.pdata`のみが生成されます。 **.PUSHREG**の前には、アンワインドするアクションを実際に実装する手順が必要です。 アンワインドディレクティブと、マクロでアンワインドするコードをラップして、アグリーメントを保証することをお勧めします。

詳細については、「 [MASM for x64 (ml64.exe)](../../assembler/masm/masm-for-x64-ml64-exe.md)」を参照してください。

## <a name="sample"></a>サンプル

### <a name="description"></a>説明

次の例は、非 volatile レジスタをプッシュする方法を示しています。

### <a name="code"></a>コード

```asm
; ml64 ex1.asm /link /entry:Example1 /SUBSYSTEM:CONSOLE
_text SEGMENT
Example1 PROC FRAME
   push r10
.pushreg r10
   push r15
.pushreg r15
   push rbx
.pushreg rbx
   push rsi
.pushreg rsi
.endprolog
   ; rest of function ...
   ret
Example1 ENDP
_text ENDS
END
```

## <a name="see-also"></a>参照

[ディレクティブリファレンス](directives-reference.md)

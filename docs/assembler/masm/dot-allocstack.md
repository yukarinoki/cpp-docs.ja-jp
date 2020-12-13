---
description: 詳細については、「」を参照してください。ALLOCSTACK
title: .ALLOCSTACK
ms.date: 12/17/2019
f1_keywords:
- .ALLOCSTACK
helpviewer_keywords:
- .ALLOCSTACK directive
ms.assetid: 9801594b-7ac2-4df2-a49d-07d9dd9af99e
ms.openlocfilehash: 6075b0900df104ae5faeaaff1dc0de2d3727b437
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97132367"
---
# <a name="allocstack"></a>.ALLOCSTACK

プロローグ内の現在のオフセットに対して、指定したサイズの **UWOP_ALLOC_SMALL** または **UWOP_ALLOC_LARGE** を生成します。

## <a name="syntax"></a>構文

> **.ALLOCSTACK** *サイズ*

## <a name="remarks"></a>解説

MASM は、特定のサイズに対して最も効率的なエンコードを選択します。

**.ALLOCSTACK** を使用すると、ml64.exe ユーザーは、フレーム関数をアンワインド内で使用できるようにする方法を指定できます。プロローグ内では、 [PROC](proc.md) frame 宣言からに拡張され [ます。ENDPROLOG](dot-endprolog.md) ディレクティブ。 これらのディレクティブはコードを生成しません。とだけが生成さ `.xdata` `.pdata` れます。 **.ALLOCSTACK** の前には、アンワインドするアクションを実際に実装する命令が必要です。 アンワインドディレクティブと、マクロでアンワインドするコードをラップして、アグリーメントを保証することをお勧めします。

*size* オペランドは 8 の倍数にする必要があります。

詳細については、「 [MASM for x64 (ml64.exe)](masm-for-x64-ml64-exe.md)」を参照してください。

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

## <a name="see-also"></a>関連項目

[ディレクティブリファレンス](directives-reference.md)\
[MASM BNF 文法](masm-bnf-grammar.md)

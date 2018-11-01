---
title: MASM マクロ
ms.date: 11/04/2016
ms.assetid: 21410432-72fc-4795-bc93-e78123f9f14f
ms.openlocfilehash: 837541706c69f86e376463c373c070316134ebca
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50523240"
---
# <a name="masm-macros"></a>MASM マクロ

使用を簡略化するため、[生の擬似演算](../build/raw-pseudo-operations.md)、一般的な手順のプロローグおよびエピローグを作成するために使用できる、ksamd64.inc で定義されているマクロのセットがあります。

## <a name="remarks"></a>Remarks

|マクロ|説明|
|-----------|-----------------|
|alloc_stack(n)|(サブ rsp、n を使用)、n バイトのスタック フレームを割り当て、出力、適切なアンワインド情報 (.allocstack n)|
|save_reg reg、ローカライズ|スタック上で、rsp オフセット位置、不揮発性レジスタ reg を保存し、出力、適切なアンワインド情報。 (.savereg reg、loc)|
|push_reg reg|不揮発性レジスタ reg をスタックにプッシュし、出力、適切なアンワインド情報。 (.pushreg reg)|
|rex_push_reg reg|2 バイトのプッシュを使用して、スタック上不揮発性レジスタを保存し、出力、適切なアンワインド情報 (.pushreg reg)、プッシュが、関数、関数がホット パッチ可能なことを確認する最初の命令の場合これを使用する必要があります。|
|save_xmm128 reg、ローカライズ|スタック上で、rsp オフセット位置 reg 不揮発性の XMM レジスタを保存し、出力、適切なアンワインド情報 (.savexmm128 reg、loc)|
|set_frame reg、オフセット|フレームのレジスタ reg する、RSP + オフセット (、mov、またはを使用して、元に戻せる) に設定し、出力、適切なアンワインド情報 (.set_frame reg、オフセット)|
|push_eflags|Pushfq 命令では、立てるをプッシュし、出力、適切なアンワインド情報 (.alloc_stack 8)|

次のマクロの適切な使用方法をサンプル関数プロローグに示します。

```asm
SkFrame struct
Fill    dq ?; fill to 8 mod 16
SavedRdi dq ?; saved register RDI
SavedRsi dq ?; saved register RSI
SkFrame ends

sampleFrame struct
Filldq?; fill to 8 mod 16
SavedRdidq?; Saved Register RDI
SavedRsi  dq?; Saved Register RSI
sampleFrame ends

sample2 PROC FRAME
alloc_stack(sizeof sampleFrame)
save_reg rdi, sampleFrame.SavedRdi
save_reg rsi, sampleFrame.SavedRsi
.end_prolog

; function body

    mov rsi, sampleFrame.SavedRsi[rsp]
    mov rdi, sampleFrame.SavedRdi[rsp]

; Here’s the official epilog

    add rsp, (sizeof sampleFrame)
    ret
sample2 ENDP
```

## <a name="see-also"></a>関連項目

[MASM のアンワインド ヘルパー](../build/unwind-helpers-for-masm.md)
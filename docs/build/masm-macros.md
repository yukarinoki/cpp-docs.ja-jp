---
title: MASM マクロ |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 21410432-72fc-4795-bc93-e78123f9f14f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 403220306a2585b1506a990664eaa2ec8f2ac1a3
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32368695"
---
# <a name="masm-macros"></a>MASM マクロ
使用を簡略化するために、[生の擬似演算](../build/raw-pseudo-operations.md)、一般的な手順のプロローグおよびエピローグの作成に使用できる ksamd64.inc で定義されているマクロのセットがあります。  
  
## <a name="remarks"></a>コメント  
  
|マクロ|説明|  
|-----------|-----------------|  
|alloc_stack(n)|(N、sub rsp を使用)、n バイトのスタック フレームを割り当て、出力、適切なアンワインド情報 (.allocstack n)|  
|save_reg reg、loc|Rsp オフセット位置にスタックの不揮発性レジスタ reg を保存し、出力、適切なアンワインド情報。 (.savereg reg、loc)|  
|push_reg reg|不揮発性レジスタ reg をスタックにプッシュし、出力、適切なアンワインド情報。 (.pushreg reg)|  
|rex_push_reg reg|2 バイトのプッシュを使用して、スタックの不揮発性レジスタに保存し、出力、適切なアンワインド情報 (.pushreg reg) の場合は、プッシュ、関数、関数がホット パッチ可能なことを確認する最初の命令は、これを使用する必要があります。|  
|save_xmm128 reg、loc|Rsp オフセット位置にスタックで reg 不揮発性 XMM レジスタを保存し、出力、適切なアンワインド (.savexmm128 reg、loc) の情報|  
|set_frame reg、オフセット|RSP を be + (mov、またはを使用して、戻せる) のオフセットをフレーム レジスタ reg を設定し、出力、適切なアンワインド情報 (.set_frame reg、オフセット)|  
|push_eflags|Pushfq 命令で立てるをプッシュし、出力、適切なアンワインド情報 (.alloc_stack 8)|  
  
 マクロの適切な使用方法をサンプル関数プロローグを次に示します。  
  
```  
SkFrame struct   
Fill    dq ?; fill to 8 mod 16   
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
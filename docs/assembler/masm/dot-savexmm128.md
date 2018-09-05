---
title: .SAVEXMM128 |Microsoft Docs
ms.custom: ''
ms.date: 08/30/2018
ms.technology:
- cpp-masm
ms.topic: reference
f1_keywords:
- .SAVEXMM128
dev_langs:
- C++
helpviewer_keywords:
- .SAVEXMM128 directive
ms.assetid: 551eb472-b8d0-47b1-8d82-995d1f485723
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0d44855d3449000c588f7e840753bd734af4b1af
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/04/2018
ms.locfileid: "43689908"
---
# <a name="savexmm128"></a>.SAVEXMM128

いずれかが生成されます、`UWOP_SAVE_XMM128`または`UWOP_SAVE_XMM128_FAR`アンワインド コードのエントリの指定の XMM レジスタと現在のプロローグのオフセットを使用してオフセットします。 MASM は、最も効率的なエンコーディングを選択します。

## <a name="syntax"></a>構文

> .savexmm128 xmmreg、オフセット

## <a name="remarks"></a>Remarks

.フレームの関数のアンワインドされるとから拡張すると、プロローグ内でのみ許可が指定できる ml64.exe の SAVEXMM128、 [PROC](../../assembler/masm/proc.md)フレームの宣言、[します。ENDPROLOG](../../assembler/masm/dot-endprolog.md)ディレクティブ。 これらのディレクティブは、コードを生成しませんのみを生成する`.xdata`と`.pdata`します。 .SAVEXMM128 は、実際にアンワインド操作を実装する手順によって先行されなければなりません。 アンワインド ディレクティブと契約を確認します。 マクロでのアンワインドに本来はコードの両方をラップすることをお勧めします。

*オフセット*16 の倍数である必要があります。

詳細については、次を参照してください。 [x64 用 MASM (ml64.exe)](../../assembler/masm/masm-for-x64-ml64-exe.md)します。

## <a name="see-also"></a>関連項目

[ディレクティブ リファレンス](../../assembler/masm/directives-reference.md)<br/>
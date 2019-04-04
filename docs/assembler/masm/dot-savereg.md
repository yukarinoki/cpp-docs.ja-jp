---
title: .SAVEREG
ms.date: 08/30/2018
f1_keywords:
- .SAVEREG
helpviewer_keywords:
- .SAVEREG directive
ms.assetid: 1dbc2ef6-a197-40e7-9e55-fddcae8cef29
ms.openlocfilehash: cac7aa7f2bdbf6b60831d2beb062f86559ec0358
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50472823"
---
# <a name="savereg"></a>.SAVEREG

いずれかが生成されます、`UWOP_SAVE_NONVOL`または`UWOP_SAVE_NONVOL_FAR`アンワインド コードのエントリの指定した登録 (`reg`) とオフセット (`offset`) プロローグの現在のオフセットを使用します。 MASM は、最も効率的なエンコーディングを選択します。

## <a name="syntax"></a>構文

> .SAVEREG reg、オフセット

## <a name="remarks"></a>Remarks

.SAVEREG が ml64.exe ユーザーは、フレームの関数をアンワインドする方法を指定することしから拡張すると、プロローグ内でのみ使用できますが、 [PROC](../../assembler/masm/proc.md)フレームの宣言、[します。ENDPROLOG](../../assembler/masm/dot-endprolog.md)ディレクティブ。 これらのディレクティブは、コードを生成しませんのみを生成する`.xdata`と`.pdata`します。 .SAVEREG は、実際にアンワインド操作を実装する手順によって先行されなければなりません。 アンワインド ディレクティブと契約を確認します。 マクロでのアンワインドに本来はコードの両方をラップすることをお勧めします。

詳細については、[x64 用 MASM (ml64.exe)](../../assembler/masm/masm-for-x64-ml64-exe.md)を参照してください。

## <a name="see-also"></a>関連項目

[ディレクティブ リファレンス](../../assembler/masm/directives-reference.md)<br/>
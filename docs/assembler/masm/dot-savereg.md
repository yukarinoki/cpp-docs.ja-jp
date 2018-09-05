---
title: .SAVEREG |Microsoft Docs
ms.custom: ''
ms.date: 08/30/2018
ms.technology:
- cpp-masm
ms.topic: reference
f1_keywords:
- .SAVEREG
dev_langs:
- C++
helpviewer_keywords:
- .SAVEREG directive
ms.assetid: 1dbc2ef6-a197-40e7-9e55-fddcae8cef29
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e7010664cd2e80841d9e35d8fcf72d195cecf796
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/04/2018
ms.locfileid: "43688990"
---
# <a name="savereg"></a>.SAVEREG

いずれかが生成されます、`UWOP_SAVE_NONVOL`または`UWOP_SAVE_NONVOL_FAR`アンワインド コードのエントリの指定した登録 (`reg`) とオフセット (`offset`) プロローグの現在のオフセットを使用します。 MASM は、最も効率的なエンコーディングを選択します。

## <a name="syntax"></a>構文

> .SAVEREG reg、オフセット

## <a name="remarks"></a>Remarks

.SAVEREG が ml64.exe ユーザーは、フレームの関数をアンワインドする方法を指定することしから拡張すると、プロローグ内でのみ使用できますが、 [PROC](../../assembler/masm/proc.md)フレームの宣言、[します。ENDPROLOG](../../assembler/masm/dot-endprolog.md)ディレクティブ。 これらのディレクティブは、コードを生成しませんのみを生成する`.xdata`と`.pdata`します。 .SAVEREG は、実際にアンワインド操作を実装する手順によって先行されなければなりません。 アンワインド ディレクティブと契約を確認します。 マクロでのアンワインドに本来はコードの両方をラップすることをお勧めします。

詳細については、次を参照してください。 [x64 用 MASM (ml64.exe)](../../assembler/masm/masm-for-x64-ml64-exe.md)します。

## <a name="see-also"></a>関連項目

[ディレクティブ リファレンス](../../assembler/masm/directives-reference.md)<br/>
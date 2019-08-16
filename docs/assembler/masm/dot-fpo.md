---
title: .FPO
ms.date: 08/30/2018
f1_keywords:
- .FPO
helpviewer_keywords:
- .FPO directive
ms.assetid: 35f4cd61-32f9-4262-b657-73f04f775d09
ms.openlocfilehash: b793b3efa72a676b800c10b98ea06001ddcf10d5
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/15/2019
ms.locfileid: "69491435"
---
# <a name="fpo"></a>.FPO

、.FPO ディレクティブは、デバッグレコードの出力を. debug $ F セグメントまたはセクションに制御します。

## <a name="syntax"></a>構文

> FPO (*Cdwlocals*、 *cdwlocals*、 *cbprolog*、 *cbRegs*、 *fusebp*、 *cbprolog*)

### <a name="parameters"></a>パラメーター

*cdwLocals*<br/>
ローカル変数の数 (符号なし32ビット値)。

*cdwParams*<br/>
DWORD のパラメーターのサイズ (符号なし16ビット値)。

*cbProlog*<br/>
関数プロローグコード内のバイト数。符号なし8ビット値。

*cbRegs*<br/>
Number レジスタが保存されました。

*fUseBP*<br/>
EBP レジスタが割り当てられているかどうかを示します。 0または1のいずれかです。

*cbFrame*<br/>
フレームの種類を示します。  詳細については、「 [FPO_DATA](/windows/win32/api/winnt/ns-winnt-fpo_data) 」を参照してください。

## <a name="see-also"></a>関連項目

[ディレクティブ リファレンス](../../assembler/masm/directives-reference.md)<br/>

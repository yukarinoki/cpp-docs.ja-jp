---
title: .FPO
ms.date: 11/05/2019
f1_keywords:
- .FPO
helpviewer_keywords:
- .FPO directive
ms.assetid: 35f4cd61-32f9-4262-b657-73f04f775d09
ms.openlocfilehash: 3938d9194c35d567ea670e0b92a731193ccd2254
ms.sourcegitcommit: 45f1d889df633f0f7e4a8e813b46fa73c9858b81
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/06/2019
ms.locfileid: "73703792"
---
# <a name="fpo-32-bit-masm"></a>.FPO (32 ビット MASM)

、.FPO ディレクティブは、デバッグレコードの出力を. debug $ F セグメントまたはセクションに制御します。 (32 ビット MASM のみ。)

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

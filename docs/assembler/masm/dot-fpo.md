---
title: .FPO
ms.date: 08/30/2018
f1_keywords:
- .FPO
helpviewer_keywords:
- .FPO directive
ms.assetid: 35f4cd61-32f9-4262-b657-73f04f775d09
ms.openlocfilehash: 3bdb6af98aa71fef3d4af24091dc7463d917ce15
ms.sourcegitcommit: 46d24d6e70c03e05484923d9efc6ed5150e96a64
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/09/2019
ms.locfileid: "68915955"
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
フレームの種類を示します。  詳細については、「 [FPO_DATA](/windows/desktop/api/winnt/ns-winnt-fpo_data) 」を参照してください。

## <a name="see-also"></a>関連項目

[ディレクティブ リファレンス](../../assembler/masm/directives-reference.md)<br/>

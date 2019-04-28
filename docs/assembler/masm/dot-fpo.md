---
title: .FPO
ms.date: 08/30/2018
f1_keywords:
- .FPO
helpviewer_keywords:
- .FPO directive
ms.assetid: 35f4cd61-32f9-4262-b657-73f04f775d09
ms.openlocfilehash: 83d6e81ea7dd35038f27f2721f3cc41fe49ef1bc
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62204059"
---
# <a name="fpo"></a>.FPO

します。FPO ディレクティブは、.debug$ セグメントまたはセクションをデバッグ レコードの生成を制御します。

## <a name="syntax"></a>構文

> FPO (*cdwLocals*, *cdwParams*, *cbProlog*, *cbRegs*, *fUseBP*, *cbFrame*)

### <a name="parameters"></a>パラメーター

*cdwLocals*<br/>
ローカル変数を符号なし 32 ビット値の数。

*cdwParams*<br/>
DWORD を符号なし 16 ビット値でパラメーターのサイズ。

*cbProlog*<br/>
符号なし 8 ビット値を関数プロローグ コードのバイト数。

*cbRegs*<br/>
保存されたレジスタの数。

*fUseBP*<br/>
EBP レジスタが割り当てられているかどうかを示します。 0 または 1。

*cbFrame*<br/>
フレームの種類を示します。  参照してください[FPO_DATA](/windows/desktop/api/winnt/ns-winnt-_fpo_data)詳細についてはします。

## <a name="see-also"></a>関連項目

[ディレクティブ リファレンス](../../assembler/masm/directives-reference.md)<br/>
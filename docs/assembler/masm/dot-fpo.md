---
title: .FPO
ms.date: 11/05/2019
f1_keywords:
- .FPO
helpviewer_keywords:
- .FPO directive
ms.assetid: 35f4cd61-32f9-4262-b657-73f04f775d09
ms.openlocfilehash: 650c69be17c9271c343360edbb90f093841a1047
ms.sourcegitcommit: 9ee5df398bfd30a42739632de3e165874cb675c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74398257"
---
# <a name="fpo-32-bit-masm"></a>.FPO (32 ビット MASM)

**。FPO**ディレクティブは、デバッグレコードの出力を. debug $ F セグメントまたはセクションに制御します。 (32 ビット MASM のみ。)

## <a name="syntax"></a>構文

> **.FPO** (*cdwlocals*、 *cdwlocals*、 *cbprolog*、 *cbRegs*、 *fusebp*、 *cbprolog*)

### <a name="parameters"></a>パラメーター

*Cdwlocals*\
ローカル変数の数 (符号なし32ビット値)。

*Cdwparams*\
DWORD のパラメーターのサイズ (符号なし16ビット値)。

*Cbprolog*\
関数プロローグコード内のバイト数。符号なし8ビット値。

*cbRegs*\
Number レジスタが保存されました。

*Fusebp*\
EBP レジスタが割り当てられているかどうかを示します。 0または1のいずれかです。

*Cbframe*\
フレームの種類を示します。  詳細については、「 [FPO_DATA](/windows/win32/api/winnt/ns-winnt-fpo_data) 」を参照してください。

## <a name="see-also"></a>参照

[ディレクティブリファレンス](directives-reference.md)

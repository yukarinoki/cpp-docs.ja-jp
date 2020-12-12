---
description: 詳細については、「」を参照してください。FPO (32 ビット MASM)
title: .FPO
ms.date: 11/05/2019
f1_keywords:
- .FPO
helpviewer_keywords:
- .FPO directive
ms.assetid: 35f4cd61-32f9-4262-b657-73f04f775d09
ms.openlocfilehash: 058189329cbe849086a3b1540ac7883ecac4d026
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97131704"
---
# <a name="fpo-32-bit-masm"></a>.FPO (32 ビット MASM)

**。FPO** ディレクティブは、デバッグレコードの出力を. debug $ F セグメントまたはセクションに制御します。 (32 ビット MASM のみ。)

## <a name="syntax"></a>構文

> **.FPO** (*cdwlocals*、 *cdwlocals*、 *cbprolog*、 *cbRegs*、 *fusebp*、 *cbprolog*)

### <a name="parameters"></a>パラメーター

*cdwLocals*\
ローカル変数の数 (符号なし32ビット値)。

*cdwParams*\
DWORD のパラメーターのサイズ (符号なし16ビット値)。

*cbProlog*\
関数プロローグコード内のバイト数。符号なし8ビット値。

*cbRegs*\
Number レジスタが保存されました。

*fUseBP*\
EBP レジスタが割り当てられているかどうかを示します。 0または1のいずれかです。

*cbFrame*\
フレームの種類を示します。  詳細については、「 [FPO_DATA](/windows/win32/api/winnt/ns-winnt-fpo_data) 」を参照してください。

## <a name="see-also"></a>関連項目

[ディレクティブリファレンス](directives-reference.md)\
[MASM BNF 文法](masm-bnf-grammar.md)

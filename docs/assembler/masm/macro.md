---
title: MACRO
ms.date: 12/16/2019
f1_keywords:
- MACRO
helpviewer_keywords:
- MACRO directive
ms.assetid: 89434f7c-bc2c-4e91-8940-fe2db8785233
ms.openlocfilehash: 8eb0afdf73270c3e741f43b2e1fba02fe965846c
ms.sourcegitcommit: 8e285a766523e653aeeb34d412dc6f615ef7b17b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/21/2020
ms.locfileid: "80076148"
---
# <a name="macro"></a>MACRO

マクロブロックを*名前*としてマークし、マクロが呼び出されたときに渡される引数の*パラメーター*のプレースホルダーを確立します。

## <a name="syntax"></a>構文

> *name***マクロ**⟦*parameter* ⟦ **: REQ** |: =*既定* | *args* **: VARARG**⟧...⟧\
> *ステートメント*の\
⟦**GOTO** :*マクロ lab d*⟧ \
> ⟦**Exitm**⟧ \
> **Endm** ⟦*value*⟧

## <a name="remarks"></a>解説

マクロ関数は、呼び出し元のステートメントに*値*を返します。

## <a name="see-also"></a>参照

[ディレクティブリファレンス](directives-reference.md)\
[GOTO (MASM)](goto-masm.md)\
[Endm](endm.md)\
[MASM BNF 文法](masm-bnf-grammar.md)

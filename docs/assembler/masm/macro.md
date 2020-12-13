---
description: '詳細情報: マクロ'
title: MACRO
ms.date: 12/16/2019
f1_keywords:
- MACRO
helpviewer_keywords:
- MACRO directive
ms.assetid: 89434f7c-bc2c-4e91-8940-fe2db8785233
ms.openlocfilehash: 5410357e76d28cddd54f3c90a34d3e85b8629143
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97129741"
---
# <a name="macro"></a>MACRO

マクロブロックを *名前* としてマークし、マクロが呼び出されたときに渡される引数の *パラメーター* のプレースホルダーを確立します。

## <a name="syntax"></a>構文

> *name***マクロ**⟦*parameter* ⟦**: REQ** |: =*既定*  |  の *引数* **: VARARG**⟧...⟧\  
> *命令*\
⟦**GOTO** :*マクロ lab d*⟧ \
> ⟦**Exitm**⟧ \
> **Endm** ⟦*value*⟧

## <a name="remarks"></a>解説

マクロ関数は、呼び出し元のステートメントに *値* を返します。

## <a name="see-also"></a>関連項目

[ディレクティブリファレンス](directives-reference.md)\
[GOTO (MASM)](goto-masm.md)\
[ENDM](endm.md)\
[MASM BNF 文法](masm-bnf-grammar.md)

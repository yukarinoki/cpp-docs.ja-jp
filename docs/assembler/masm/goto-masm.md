---
title: GOTO (MASM)
ms.date: 12/16/2019
helpviewer_keywords:
- GOTO directive
ms.assetid: 6a5f73e7-6784-4eae-ac52-4fc77a7f369f
ms.openlocfilehash: 18f286d8634202b57dea788aa6984755a5afb197
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/17/2020
ms.locfileid: "79440796"
---
# <a name="goto"></a>GOTO

アセンブリを、"_マクロラベル_"**とマークさ**れた行に転送します。

## <a name="syntax"></a>構文

> **GOTO** *マクロラベル*

## <a name="remarks"></a>コメント

**GOTO** [は、](for-masm.md)[マクロ](macro.md)内、 [forc](forc.md)、 [REPEAT](repeat.md)、および[WHILE](while-masm.md)ブロックでのみ許可されます。 *マクロラベル*のターゲットは、行の唯一のディレクティブである必要があります。先頭にはコロンを付ける必要があります。

## <a name="see-also"></a>参照

[ディレクティブリファレンス](directives-reference.md)\
[MASM BNF 文法](masm-bnf-grammar.md)

---
description: '詳細情報: GOTO'
title: GOTO (MASM)
ms.date: 12/16/2019
helpviewer_keywords:
- GOTO directive
ms.assetid: 6a5f73e7-6784-4eae-ac52-4fc77a7f369f
ms.openlocfilehash: ab373d77cbfb660d4cc256e39de38b7f066eac27
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97130261"
---
# <a name="goto"></a>GOTO

アセンブリを、"_マクロラベル_"**とマークさ** れた行に転送します。

## <a name="syntax"></a>構文

> **GOTO** *マクロラベル*

## <a name="remarks"></a>解説

**GOTO** [は、](for-masm.md)[マクロ](macro.md)内、 [forc](forc.md)、 [REPEAT](repeat.md)、および [WHILE](while-masm.md)ブロックでのみ許可されます。 *マクロラベル* のターゲットは、行の唯一のディレクティブである必要があります。先頭にはコロンを付ける必要があります。

## <a name="see-also"></a>関連項目

[ディレクティブリファレンス](directives-reference.md)\
[MASM BNF 文法](masm-bnf-grammar.md)

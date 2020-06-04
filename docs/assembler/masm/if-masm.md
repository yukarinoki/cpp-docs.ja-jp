---
title: IF (MASM)
ms.date: 12/17/2019
helpviewer_keywords:
- IF directive
ms.assetid: 82e43712-4f0c-4bf6-90ce-0663e81af707
ms.openlocfilehash: 6e63f5c8075b3c94370ad8863d224c097cf0ecdf
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/17/2020
ms.locfileid: "79440748"
---
# <a name="if"></a>IF

*Expression1*が true (0 以外) の場合は*ifstatements*のアセンブリを、 *expression1*が false (0)、 *expression2*が true の場合は*elseifstatements*を許可します。

## <a name="syntax"></a>構文

> **IF** *Expression1*\
> *if ステートメント*\
> ⟦**ELSEIF** *expression2*\
> *elseif-ステートメント*⟧ \
> ⟦**ELSE**\
> *else-ステートメント*⟧ \
> **ENDIF**

## <a name="remarks"></a>コメント

次のディレクティブは、 [ELSEIF](elseif-masm.md): **ELSEIFB**、 **ELSEIFDEF**、 **ELSEIFDIF**、 **ELSEIFDIFI**、 **ELSEIFE**、 **ELSEIFIDN**、ELSEIFIDNI、 **ELSEIFIDNI** **ELSEIFNB**、 **ELSEIFNDEF**の代わりに使用できます。 前の式が false の場合は、必要に応じて*else ステートメント*をアセンブルします。 式は、アセンブリ時に評価されることに注意してください。

## <a name="see-also"></a>参照

[ディレクティブリファレンス](directives-reference.md)\
[MASM BNF 文法](masm-bnf-grammar.md)

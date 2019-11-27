---
title: IF (MASM)
ms.date: 08/30/2018
f1_keywords:
- if
helpviewer_keywords:
- IF directive
ms.assetid: 82e43712-4f0c-4bf6-90ce-0663e81af707
ms.openlocfilehash: ed7b9e63bb19dcc16539dbdaaf1f6a7f16566b3c
ms.sourcegitcommit: 9ee5df398bfd30a42739632de3e165874cb675c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74397461"
---
# <a name="if-masm"></a>IF (MASM)

*Expression1*が true (0 以外) の場合は*ifstatements*のアセンブリを、 *expression1*が false (0)、 *expression2*が true の場合は*elseifstatements*を許可します。

## <a name="syntax"></a>構文

> *Expression1*\
> *if ステートメント*\
> ⟦**ELSEIF** *expression2*\
> *elseif-ステートメント*⟧ \
> ⟦**ELSE**\
> *else-ステートメント*⟧ \
> **ENDIF**

## <a name="remarks"></a>コメント

次のディレクティブは、 [ELSEIF](../../assembler/masm/elseif-masm.md): **ELSEIFB**、 **ELSEIFDEF**、 **ELSEIFDIF**、 **ELSEIFDIFI**、 **ELSEIFE**、 **ELSEIFIDN**、ELSEIFIDNI、 **ELSEIFNB**、 **ELSEIFNDEF**の代わりに使用できます。 前の式が false の場合は、必要に応じて*else ステートメント*をアセンブルします。 式は、アセンブリ時に評価されることに注意してください。

## <a name="see-also"></a>参照

[ディレクティブリファレンス](directives-reference.md)

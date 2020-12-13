---
description: '詳細情報: IF'
title: IF (MASM)
ms.date: 12/17/2019
helpviewer_keywords:
- IF directive
ms.assetid: 82e43712-4f0c-4bf6-90ce-0663e81af707
ms.openlocfilehash: 09b4bd09155ef848ad165b4e8b0d3a093ade0008
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97130210"
---
# <a name="if"></a>IF

*Expression1* が true (0 以外) の場合は *ifstatements* のアセンブリを、 *expression1* が false (0)、 *expression2* が true の場合は *elseifstatements* を許可します。

## <a name="syntax"></a>構文

>  *Expression1* の場合\
> *if-ステートメント*\
> ⟦**ELSEIF** *expression2*\
> *elseif-ステートメント*⟧ \
> ⟦**ELSE**\
> *else-ステートメント*⟧ \
> **ENDIF**

## <a name="remarks"></a>解説

次のディレクティブは、 [ELSEIF](elseif-masm.md): **ELSEIFB**、 **ELSEIFDEF**、 **ELSEIFDIF**、 **ELSEIFDIFI**、 **ELSEIFE**、 **ELSEIFIDN**、ELSEIFIDNI、  **ELSEIFNB**、 **ELSEIFNDEF** の代わりに使用できます。 前の式が false の場合は、必要に応じて *else ステートメント* をアセンブルします。 式は、アセンブリ時に評価されることに注意してください。

## <a name="see-also"></a>関連項目

[ディレクティブリファレンス](directives-reference.md)\
[MASM BNF 文法](masm-bnf-grammar.md)

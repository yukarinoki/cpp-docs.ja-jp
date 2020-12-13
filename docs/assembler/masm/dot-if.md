---
description: 詳細については、「」を参照してください。IF (32 ビット MASM)
title: .IF
ms.date: 11/05/2019
f1_keywords:
- .IF
helpviewer_keywords:
- .IF directive
ms.assetid: dccc7615-8fc7-4829-9f39-0ee405f6c1e3
ms.openlocfilehash: e6ce9695f90a90665aee1cdaf15167963360fe04
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97131678"
---
# <a name="if-32-bit-masm"></a>.IF (32 ビット MASM)

*Condition1* (たとえば、AX > 7) をテストし、その条件が true の場合に *ステートメント* を実行するコードを生成します。 (32 ビット MASM のみ。)

## <a name="syntax"></a>構文

> **.** *CONDITION1* の場合\
> *命令*\
> ⟦**。ELSEIF** *condition2*\
> *ステートメント*⟧ \
> ⟦**。その他**\
> *ステートメント*⟧ \
> **.ENDIF**

## <a name="remarks"></a>解説

の場合は [。それ以外](dot-else.md) の場合は、元の条件が false の場合にステートメントが実行されます。 条件は実行時に評価されることに注意してください。

## <a name="see-also"></a>関連項目

[ディレクティブリファレンス](directives-reference.md)\
[MASM BNF 文法](masm-bnf-grammar.md)

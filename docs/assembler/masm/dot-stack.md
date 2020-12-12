---
description: 詳細については、「」を参照してください。スタック (32 ビット MASM)
title: .STACK
ms.date: 11/05/2019
f1_keywords:
- .STACK
helpviewer_keywords:
- .STACK directive
ms.assetid: 70019463-5d4f-41b6-8464-023a8ac2466f
ms.openlocfilehash: a3cae4491cd50cbf039357d515214ebdd9222805
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97131015"
---
# <a name="stack-32-bit-masm"></a>.スタック (32 ビット MASM)

と共に使用 [します。モデル](dot-model.md)は、(セグメント名 **スタック** を持つ) スタックセグメントを定義します。 オプションの *サイズ* は、スタックのバイト数を指定します (既定値は 1024)。 **。Stack ディレクティブは**、stack ステートメントを自動的に閉じます。 (32 ビット MASM のみ。)

## <a name="syntax"></a>構文

> **.STACK** ⟦*size*⟧

## <a name="see-also"></a>関連項目

[ディレクティブリファレンス](directives-reference.md)\
[MASM BNF 文法](masm-bnf-grammar.md)

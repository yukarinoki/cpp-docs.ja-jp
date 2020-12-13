---
description: '詳細情報: EXTERNDEF'
title: EXTERNDEF
ms.date: 12/06/2019
f1_keywords:
- EXTERNDEF
helpviewer_keywords:
- EXTERNDEF directive
ms.assetid: 95a10de6-c345-4428-a2f2-90f7d411dc86
ms.openlocfilehash: b0ffc2154996fc7cea9f0b61917cadf7b776972f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97130326"
---
# <a name="externdef"></a>EXTERNDEF

型が *型* である、*名前* が1つ以上の外部変数、ラベル、またはシンボルを定義します。

## <a name="syntax"></a>構文

> **EXTERNDEF** ⟦*language-* type ⟧ *name*__:__*type* ⟦__,__ ⟦*language-* type ⟧ *name*__:__*type* ...⟧

## <a name="remarks"></a>解説

*言語型* の引数は、32ビットの MASM でのみ有効です。

*名前* がモジュールで定義されている場合は、[パブリック](public-masm.md)として扱われます。 *名前* がモジュールで参照されている場合は、 [EXTERN](extern-masm.md)として扱われます。 *名前* が参照されていない場合は無視されます。 この *型* は [ABS](operator-abs.md)にすることができます。この場合、 *名前* は定数としてインポートされます。 通常はインクルードファイルで使用されます。

## <a name="see-also"></a>関連項目

[ディレクティブリファレンス](directives-reference.md)\
[MASM BNF 文法](masm-bnf-grammar.md)

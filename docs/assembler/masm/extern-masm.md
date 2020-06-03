---
title: EXTERN (MASM)
ms.date: 12/06/2019
helpviewer_keywords:
- EXTERN directive
ms.assetid: 667d703d-3aaf-4139-a586-29bc5dab1aff
ms.openlocfilehash: 2674f358fe22f74c5272d90a0d8cbff234ddcd11
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/17/2020
ms.locfileid: "79440884"
---
# <a name="extern"></a>EXTERN

型が*型*である、*名前*が1つ以上の外部変数、ラベル、またはシンボルを定義します。

## <a name="syntax"></a>構文

> **EXTERN** ⟦*language 型*⟧ *name* ⟦ __(__ *altid* __)__ ⟧ __:__ *type* ⟦ __,__ ⟦*language-type*⟧ *name* ⟦ __(__ *altid* __)__ ⟧ __:__ *type* ...⟧

## <a name="remarks"></a>コメント

*言語型*の引数は、32ビットの MASM でのみ有効です。

この*型*は[ABS](operator-abs.md)にすることができます。この場合、*名前*は定数としてインポートされます。 [Extrn](extrn.md)と同じです。

## <a name="see-also"></a>参照

[ディレクティブリファレンス](directives-reference.md)\
[MASM BNF 文法](masm-bnf-grammar.md)

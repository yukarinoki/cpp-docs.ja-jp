---
description: '詳細情報: EXTERN'
title: EXTERN (MASM)
ms.date: 12/06/2019
helpviewer_keywords:
- EXTERN directive
ms.assetid: 667d703d-3aaf-4139-a586-29bc5dab1aff
ms.openlocfilehash: 354a390a16fb663dc6e907e37022a362c3ab5648
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97130352"
---
# <a name="extern"></a>EXTERN

型が *型* である、*名前* が1つ以上の外部変数、ラベル、またはシンボルを定義します。

## <a name="syntax"></a>構文

> **EXTERN** ⟦*language 型*⟧ *name* ⟦ __(__*altid*__)__ ⟧ __:__ *type* ⟦__,__ ⟦*language-type*⟧ *name* ⟦ __(__*altid*__)__ ⟧ __:__ *type* ...⟧

## <a name="remarks"></a>解説

*言語型* の引数は、32ビットの MASM でのみ有効です。

この *型* は [ABS](operator-abs.md)にすることができます。この場合、 *名前* は定数としてインポートされます。 [Extrn](extrn.md)と同じです。

## <a name="see-also"></a>関連項目

[ディレクティブリファレンス](directives-reference.md)\
[MASM BNF 文法](masm-bnf-grammar.md)

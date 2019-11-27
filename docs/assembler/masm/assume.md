---
title: ASSUME
ms.date: 11/05/2019
f1_keywords:
- ASSUME
helpviewer_keywords:
- ASSUME directive
ms.assetid: cd162070-aee9-4c65-babc-005c6cc73d7c
ms.openlocfilehash: 73ef8bcc33087a56747b80f94482fcd6c50e3bf6
ms.sourcegitcommit: 9ee5df398bfd30a42739632de3e165874cb675c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74399261"
---
# <a name="assume-32-bit-masm"></a>想定 (32 ビット MASM)

レジスタ値のエラーチェックを有効にします。 (32 ビット MASM のみ。)

## <a name="syntax"></a>構文

> *Segregister* __:__ *name* ⟦ __,__ *segregister* __:__ *name*...⟧\
> 次のように*dataregister* __:__ *type* ⟦ __,__ *dataregister* __:__ *type*...⟧\
> *レジスタ* __: error__ ⟦ __、__ *register* __: error__...⟧\
> **⟦** *Register* __:__ ⟧**NOTHING** ⟦ __、__ *register* __: nothing__...⟧

## <a name="remarks"></a>コメント

が有効になる**と**、アセンブラーは、指定されたレジスタの値に対する変更を監視します。 レジスタが使用されている場合、**エラー**によってエラーが生成されます。 レジスタエラーチェックは何も削除され**ません**。 1つのステートメントでさまざまな種類の仮定を組み合わせることができます。

## <a name="see-also"></a>参照

[ディレクティブ リファレンス](../../assembler/masm/directives-reference.md)

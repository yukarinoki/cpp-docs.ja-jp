---
title: EXTERN (MASM)
ms.date: 08/30/2018
f1_keywords:
- extern
helpviewer_keywords:
- EXTERN directive
ms.assetid: 667d703d-3aaf-4139-a586-29bc5dab1aff
ms.openlocfilehash: fc66338d90b54ecb12ef3ab1aa56214fb445cb13
ms.sourcegitcommit: 9ee5df398bfd30a42739632de3e165874cb675c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74397560"
---
# <a name="extern-masm"></a>EXTERN (MASM)

型が*型*である、*名前*が1つ以上の外部変数、ラベル、またはシンボルを定義します。

## <a name="syntax"></a>構文

> **EXTERN** ⟦*language 型*⟧ *name* ⟦ __(__ *altid* __)__ ⟧ __:__ *type* ⟦ __,__ ⟦*language-type*⟧ *name* ⟦ __(__ *altid* __)__ ⟧ __:__ *type* ...⟧

## <a name="remarks"></a>コメント

この*型*は[ABS](../../assembler/masm/operator-abs.md)にすることができます。この場合、*名前*は定数としてインポートされます。 [Extrn](../../assembler/masm/extrn.md)と同じです。

## <a name="see-also"></a>参照

[ディレクティブ リファレンス](../../assembler/masm/directives-reference.md)

---
title: EXTERNDEF
ms.date: 08/30/2018
f1_keywords:
- EXTERNDEF
helpviewer_keywords:
- EXTERNDEF directive
ms.assetid: 95a10de6-c345-4428-a2f2-90f7d411dc86
ms.openlocfilehash: 469b49832c171ee78336a0c457f0d269acd3b59d
ms.sourcegitcommit: 9ee5df398bfd30a42739632de3e165874cb675c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74397541"
---
# <a name="externdef"></a>EXTERNDEF

型が*型*である、*名前*が1つ以上の外部変数、ラベル、またはシンボルを定義します。

## <a name="syntax"></a>構文

> **EXTERNDEF** ⟦*language-* type ⟧ *name* __:__ *type* ⟦ __,__ ⟦*language-* type ⟧ *name* __:__ *type* ...⟧

## <a name="remarks"></a>コメント

*名前*がモジュールで定義されている場合は、[パブリック](../../assembler/masm/public-masm.md)として扱われます。 *名前*がモジュールで参照されている場合は、 [EXTERN](../../assembler/masm/extern-masm.md)として扱われます。 *名前*が参照されていない場合は無視されます。 この*型*は[ABS](../../assembler/masm/operator-abs.md)にすることができます。この場合、*名前*は定数としてインポートされます。 通常はインクルードファイルで使用されます。

## <a name="see-also"></a>参照

[ディレクティブ リファレンス](../../assembler/masm/directives-reference.md)

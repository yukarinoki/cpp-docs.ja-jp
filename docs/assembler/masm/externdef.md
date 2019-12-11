---
title: EXTERNDEF
ms.date: 12/06/2019
f1_keywords:
- EXTERNDEF
helpviewer_keywords:
- EXTERNDEF directive
ms.assetid: 95a10de6-c345-4428-a2f2-90f7d411dc86
ms.openlocfilehash: e757781151bd1bb57940e5c54f7333a5daa93c74
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2019
ms.locfileid: "74987900"
---
# <a name="externdef"></a>EXTERNDEF

型が*型*である、*名前*が1つ以上の外部変数、ラベル、またはシンボルを定義します。

## <a name="syntax"></a>構文

> **EXTERNDEF** ⟦*language-* type ⟧ *name* __:__ *type* ⟦ __,__ ⟦*language-* type ⟧ *name* __:__ *type* ...⟧

## <a name="remarks"></a>Remarks

*言語型*の引数は、32ビットの MASM でのみ有効です。

*名前*がモジュールで定義されている場合は、[パブリック](../../assembler/masm/public-masm.md)として扱われます。 *名前*がモジュールで参照されている場合は、 [EXTERN](../../assembler/masm/extern-masm.md)として扱われます。 *名前*が参照されていない場合は無視されます。 この*型*は[ABS](../../assembler/masm/operator-abs.md)にすることができます。この場合、*名前*は定数としてインポートされます。 通常はインクルードファイルで使用されます。

## <a name="see-also"></a>参照

[ディレクティブ リファレンス](../../assembler/masm/directives-reference.md)

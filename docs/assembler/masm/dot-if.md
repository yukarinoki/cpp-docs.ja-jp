---
title: .IF
ms.date: 11/05/2019
f1_keywords:
- .IF
helpviewer_keywords:
- .IF directive
ms.assetid: dccc7615-8fc7-4829-9f39-0ee405f6c1e3
ms.openlocfilehash: 83c9ff588e2fe273e24e1d0b1c16517c5eee3365
ms.sourcegitcommit: 45f1d889df633f0f7e4a8e813b46fa73c9858b81
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/06/2019
ms.locfileid: "73703779"
---
# <a name="if-32-bit-masm"></a>.IF (32 ビット MASM)

`condition1` をテストするコード (たとえば、AX > 7) を生成し、その条件が true の場合に*ステートメント*を実行します。 (32 ビット MASM のみ。)

## <a name="syntax"></a>構文

> .Condition1 の場合<br/>
> ステートメント<br/>
> [[.ELSEIF condition2<br/>
> ステートメント]]<br/>
> [[.さも<br/>
> ステートメント]]<br/>
> .ENDIF

## <a name="remarks"></a>Remarks

の場合は[。それ以外](../../assembler/masm/dot-else.md)の場合は、元の条件が false の場合にステートメントが実行されます。 条件は実行時に評価されることに注意してください。

## <a name="see-also"></a>関連項目

[ディレクティブ リファレンス](../../assembler/masm/directives-reference.md)<br/>
---
title: .IF
ms.date: 08/30/2018
f1_keywords:
- .IF
helpviewer_keywords:
- .IF directive
ms.assetid: dccc7615-8fc7-4829-9f39-0ee405f6c1e3
ms.openlocfilehash: cf9c594d843c937dd2191bee2a7cebadbc615c82
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62185268"
---
# <a name="if"></a>.IF

テスト コードを生成`condition1`(たとえば、AX > 7 の) 実行と、*ステートメント*その条件が true の場合。

## <a name="syntax"></a>構文

> .IF 条件 1<br/>
> ステートメント<br/>
> [[.ELSEIF condition2<br/>
> ステートメント]<br/>
> [[.ELSE<br/>
> ステートメント]<br/>
> .ENDIF

## <a name="remarks"></a>Remarks

場合、[します。ELSE](../../assembler/masm/dot-else.md)元の条件が false であった場合は、次のように、そのステートメントが実行されます。 実行時に、条件が評価されることに注意してください。

## <a name="see-also"></a>関連項目

[ディレクティブ リファレンス](../../assembler/masm/directives-reference.md)<br/>
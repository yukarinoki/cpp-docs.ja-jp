---
title: .IF |Microsoft Docs
ms.custom: ''
ms.date: 08/30/2018
ms.technology:
- cpp-masm
ms.topic: reference
f1_keywords:
- .IF
dev_langs:
- C++
helpviewer_keywords:
- .IF directive
ms.assetid: dccc7615-8fc7-4829-9f39-0ee405f6c1e3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f7bd5ba5821b4dcfb2d088e31816f50540445018
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/04/2018
ms.locfileid: "43691545"
---
# <a name="if"></a>.IF

テスト コードを生成`condition1`(たとえば、AX > 7 の) 実行と、*ステートメント*その条件が true の場合。

## <a name="syntax"></a>構文

> .IF 条件 1<br/>
> ステートメント<br/>
> [[.ELSEIF condition2<br/>
> ステートメント]<br/>
> [[.その他<br/>
> ステートメント]<br/>
> .ENDIF

## <a name="remarks"></a>Remarks

場合、[します。ELSE](../../assembler/masm/dot-else.md)元の条件が false であった場合は、次のように、そのステートメントが実行されます。 実行時に、条件が評価されることに注意してください。

## <a name="see-also"></a>関連項目

[ディレクティブ リファレンス](../../assembler/masm/directives-reference.md)<br/>
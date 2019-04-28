---
title: IF (MASM)
ms.date: 08/30/2018
f1_keywords:
- if
helpviewer_keywords:
- IF directive
ms.assetid: 82e43712-4f0c-4bf6-90ce-0663e81af707
ms.openlocfilehash: 2b91698640e028bf91d822c12b85ded651a04d8d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62203065"
---
# <a name="if-masm"></a>IF (MASM)

アセンブリの*ifstatements*場合*expression1*が true (0 以外の場合) または*elseifstatements*場合*expression1*が false (0) と*expression2*は true。

## <a name="syntax"></a>構文

> IF *expression1*<br/>
> *ifstatements*<br/>
> [[ELSEIF *expression2*<br/>
> *elseifstatements*]<br/>
> [[ELSE<br/>
> *elsestatements*]<br/>
> ENDIF

## <a name="remarks"></a>Remarks

次のディレクティブを置き換えることがあります[ELSEIF](../../assembler/masm/elseif-masm.md):**ELSEIFB**、 **ELSEIFDEF**、 **ELSEIFDIF**、 **ELSEIFDIFI**、 **ELSEIFE**、 **ELSEIFIDN**、 **ELSEIFIDNI**、 **ELSEIFNB**、および**ELSEIFNDEF**します。 必要に応じて、アセンブル*elsestatements*前の式が false の場合。 アセンブリの時に式が評価されることに注意してください。

## <a name="see-also"></a>関連項目

[ディレクティブ リファレンス](../../assembler/masm/directives-reference.md)<br/>
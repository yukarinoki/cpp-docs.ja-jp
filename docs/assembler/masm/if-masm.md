---
title: IF (MASM) |Microsoft Docs
ms.custom: ''
ms.date: 08/30/2018
ms.technology:
- cpp-masm
ms.topic: reference
f1_keywords:
- if
dev_langs:
- C++
helpviewer_keywords:
- IF directive
ms.assetid: 82e43712-4f0c-4bf6-90ce-0663e81af707
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ca0cce834924f7fc147b1ef301d5bd345dfd2973
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/04/2018
ms.locfileid: "43685308"
---
# <a name="if-masm"></a>IF (MASM)

アセンブリの*ifstatements*場合*expression1*が true (0 以外の場合) または*elseifstatements*場合*expression1*が false (0) と*expression2*は true。

## <a name="syntax"></a>構文

> IF *expression1*<br/>
> *ifstatements*<br/>
> [ELSEIF *expression2*<br/>
> *elseifstatements*]<br/>
> [その他<br/>
> *elsestatements*]<br/>
> ENDIF

## <a name="remarks"></a>Remarks

次のディレクティブを置き換えることがあります[ELSEIF](../../assembler/masm/elseif-masm.md): **ELSEIFB**、 **ELSEIFDEF**、 **ELSEIFDIF**、 **ELSEIFDIFI**、 **ELSEIFE**、 **ELSEIFIDN**、 **ELSEIFIDNI**、 **ELSEIFNB**、および**ELSEIFNDEF**. 必要に応じて、アセンブル*elsestatements*前の式が false の場合。 アセンブリの時に式が評価されることに注意してください。

## <a name="see-also"></a>関連項目

[ディレクティブ リファレンス](../../assembler/masm/directives-reference.md)<br/>
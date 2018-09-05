---
title: GOTO (MASM) |Microsoft Docs
ms.custom: ''
ms.date: 08/30/2018
ms.technology:
- cpp-masm
ms.topic: reference
f1_keywords:
- goto
dev_langs:
- C++
helpviewer_keywords:
- GOTO directive
ms.assetid: 6a5f73e7-6784-4eae-ac52-4fc77a7f369f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b0be678e2d39389cbc551c386c1890f799124b5b
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/04/2018
ms.locfileid: "43694010"
---
# <a name="goto-masm"></a>GOTO (MASM)

マークされた行にアセンブリを転送 **:**_macrolabel_します。

## <a name="syntax"></a>構文

> **GOTO** *macrolabel*

## <a name="remarks"></a>Remarks

**GOTO**内でのみ使用が[マクロ](macro.md)、[の](for-masm.md)、 [FORC](forc.md)、[繰り返します](repeat.md)、および[中に](while-masm.md)ブロックします。 *Macrolabel*ターゲット行でのみのディレクティブである必要があります、先頭のコロンを付ける必要があります。

## <a name="see-also"></a>関連項目

[ディレクティブ リファレンス](../../assembler/masm/directives-reference.md)<br/>

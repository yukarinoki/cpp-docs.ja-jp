---
title: GOTO (MASM)
ms.date: 08/30/2018
f1_keywords:
- goto
helpviewer_keywords:
- GOTO directive
ms.assetid: 6a5f73e7-6784-4eae-ac52-4fc77a7f369f
ms.openlocfilehash: a03cbda5a8ff64f6c167766f416e7744a5382ad5
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62203084"
---
# <a name="goto-masm"></a>GOTO (MASM)

マークされた行にアセンブリを転送 **:**_macrolabel_します。

## <a name="syntax"></a>構文

> **GOTO** *macrolabel*

## <a name="remarks"></a>Remarks

**GOTO**内でのみ使用が[マクロ](macro.md)、[の](for-masm.md)、 [FORC](forc.md)、[繰り返します](repeat.md)、および[中に](while-masm.md)ブロックします。 *Macrolabel*ターゲット行でのみのディレクティブである必要があります、先頭のコロンを付ける必要があります。

## <a name="see-also"></a>関連項目

[ディレクティブ リファレンス](../../assembler/masm/directives-reference.md)<br/>

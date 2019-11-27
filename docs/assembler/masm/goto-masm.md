---
title: GOTO (MASM)
ms.date: 08/30/2018
f1_keywords:
- goto
helpviewer_keywords:
- GOTO directive
ms.assetid: 6a5f73e7-6784-4eae-ac52-4fc77a7f369f
ms.openlocfilehash: 424ff295fe37e7c5ff02897a01b99a7c75876f85
ms.sourcegitcommit: 9ee5df398bfd30a42739632de3e165874cb675c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74397485"
---
# <a name="goto-masm"></a>GOTO (MASM)

アセンブリを、"_マクロラベル_"**とマークさ**れた行に転送します。

## <a name="syntax"></a>構文

> **GOTO** *マクロラベル*

## <a name="remarks"></a>コメント

**GOTO** [は、](for-masm.md)[マクロ](macro.md)内、 [forc](forc.md)、 [REPEAT](repeat.md)、および[WHILE](while-masm.md)ブロックでのみ許可されます。 *マクロラベル*のターゲットは、行の唯一のディレクティブである必要があります。先頭にはコロンを付ける必要があります。

## <a name="see-also"></a>参照

[ディレクティブリファレンス](directives-reference.md)

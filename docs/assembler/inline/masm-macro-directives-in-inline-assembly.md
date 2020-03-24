---
title: インライン アセンブリでの MASM マクロ ディレクティブ
ms.date: 08/30/2018
helpviewer_keywords:
- directives, macros
- inline assembly, macro directives
- macros, directives
- MASM (Microsoft Macro Assembler), inline assembly macro directives
ms.assetid: 83643a09-1699-40a8-8ef2-13502bc4ac2c
ms.openlocfilehash: 38b73346fc52f6b5efe478f8eb960ad049fae924
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80169280"
---
# <a name="masm-macro-directives-in-inline-assembly"></a>インライン アセンブリでの MASM マクロ ディレクティブ

**Microsoft 固有の仕様**

インラインアセンブラーはマクロアセンブラーではありません。 MASM マクロディレクティブ (**マクロ**、`REPT`、 **IRC**、`IRP`、および `ENDM`) またはマクロ演算子 ( **<>** 、 **!** 、 **&** 、`%`、および `.TYPE`) は使用できません。 ただし、`__asm` ブロックは C プリプロセッサディレクティブを使用できます。 詳細については、「 [__Asm ブロックでのC++ C またはの使用](../../assembler/inline/using-c-or-cpp-in-asm-blocks.md)」を参照してください。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>参照

[__asm ブロックでのアセンブリ言語の使用](../../assembler/inline/using-assembly-language-in-asm-blocks.md)<br/>

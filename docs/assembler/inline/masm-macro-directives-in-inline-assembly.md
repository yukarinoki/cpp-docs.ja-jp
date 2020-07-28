---
title: インライン アセンブリでの MASM マクロ ディレクティブ
ms.date: 08/30/2018
helpviewer_keywords:
- directives, macros
- inline assembly, macro directives
- macros, directives
- MASM (Microsoft Macro Assembler), inline assembly macro directives
ms.assetid: 83643a09-1699-40a8-8ef2-13502bc4ac2c
ms.openlocfilehash: 964f70aeef6e0e62ac4b941b2cc26d3e7c7ef466
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87191795"
---
# <a name="masm-macro-directives-in-inline-assembly"></a>インライン アセンブリでの MASM マクロ ディレクティブ

**Microsoft 固有の仕様**

インラインアセンブラーはマクロアセンブラーではありません。 MASM マクロディレクティブ (**macro**、 `REPT` 、 **IRC**、 `IRP` 、および `ENDM` ) またはマクロ演算子 ( **<>** 、 **!**、 **&** 、 `%` 、および) は `.TYPE` 使用できません。 **`__asm`** ただし、ブロックは C プリプロセッサディレクティブを使用できます。 詳細については、「 [__Asm ブロックでの C または C++ の使用](../../assembler/inline/using-c-or-cpp-in-asm-blocks.md)」を参照してください。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[__Asm ブロックでのアセンブリ言語の使用](../../assembler/inline/using-assembly-language-in-asm-blocks.md)<br/>

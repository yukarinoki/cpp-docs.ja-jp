---
description: 詳細については、「インラインアセンブリでの MASM マクロディレクティブ」を参照してください。
title: インライン アセンブリでの MASM マクロ ディレクティブ
ms.date: 08/30/2018
helpviewer_keywords:
- directives, macros
- inline assembly, macro directives
- macros, directives
- MASM (Microsoft Macro Assembler), inline assembly macro directives
ms.assetid: 83643a09-1699-40a8-8ef2-13502bc4ac2c
ms.openlocfilehash: 131066ad117e0f314ba0900e8ecd19eb4843c25b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97117563"
---
# <a name="masm-macro-directives-in-inline-assembly"></a>インライン アセンブリでの MASM マクロ ディレクティブ

**Microsoft 固有の仕様**

インラインアセンブラーはマクロアセンブラーではありません。 MASM マクロディレクティブ (**macro**、 `REPT` 、 **IRC**、 `IRP` 、および `ENDM` ) またはマクロ演算子 ( **<>** 、 **!**、 **&** 、 `%` 、および) は `.TYPE` 使用できません。 **`__asm`** ただし、ブロックは C プリプロセッサディレクティブを使用できます。 詳細については、「 [__Asm ブロックでの C または C++ の使用](../../assembler/inline/using-c-or-cpp-in-asm-blocks.md) 」を参照してください。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[__Asm ブロックでのアセンブリ言語の使用](../../assembler/inline/using-assembly-language-in-asm-blocks.md)<br/>

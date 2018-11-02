---
title: インライン アセンブリでの MASM マクロ ディレクティブ
ms.date: 08/30/2018
helpviewer_keywords:
- directives, macros
- inline assembly, macro directives
- macros, directives
- MASM (Microsoft Macro Assembler), inline assembly macro directives
ms.assetid: 83643a09-1699-40a8-8ef2-13502bc4ac2c
ms.openlocfilehash: 7e1bed782d28a5bf7c934c3f57f50aae70038578
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50508928"
---
# <a name="masm-macro-directives-in-inline-assembly"></a>インライン アセンブリでの MASM マクロ ディレクティブ

**Microsoft 固有の仕様**

インライン アセンブラーはマクロ アセンブラーではありません。 MASM マクロ ディレクティブを使用することはできません (**マクロ**、 `REPT`、 **IRC**、 `IRP`、および`ENDM`) またはマクロの演算子 (**<>**、**!**、 **&**、 `%`、および`.TYPE`)。 `__asm`ブロックがただし、C プリプロセッサ ディレクティブを使用できます。 参照してください[を使用して C または C++ _ _asm ブロックで](../../assembler/inline/using-c-or-cpp-in-asm-blocks.md)詳細についてはします。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[__asm ブロックでのアセンブリ言語の使用](../../assembler/inline/using-assembly-language-in-asm-blocks.md)<br/>
---
title: インライン アセンブリでのデータ ディレクティブと演算子
ms.date: 08/30/2018
helpviewer_keywords:
- data directives [C++]
- __asm keyword [C++], referencing limitations
- MASM (Microsoft Macro Assembler), directives
- directives [C++], MASM
- MASM (Microsoft Macro Assembler), structures
- operators [MASM]
- inline assembly, operators
- inline assembly, data directives
- MASM (Microsoft Macro Assembler), operators
- structures [C++], MASM
ms.assetid: fb7410c7-156a-4131-bcfc-211aa70533e3
ms.openlocfilehash: 916dce0346bebfc5ff65ca558ae75317a187660a
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80169540"
---
# <a name="data-directives-and-operators-in-inline-assembly"></a>インライン アセンブリでのデータ ディレクティブと演算子

**Microsoft 固有の仕様**

`__asm` ブロックは C またはC++データ型およびオブジェクトを参照できますが、MASM ディレクティブや演算子を使用してデータオブジェクトを定義することはできません。 具体的には、定義ディレクティブ**DB**、`DW`、 **DD**、`DQ`、`DT`、`DF`、または演算子 `DUP` または**THIS**を使用することはできません。 MASM の構造とレコードも使用できません。 インラインアセンブラーは、ディレクティブ `STRUC`、`RECORD`、**幅**、または**マスク**を受け入れません。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>参照

[__asm ブロックでのアセンブリ言語の使用](../../assembler/inline/using-assembly-language-in-asm-blocks.md)<br/>

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
ms.openlocfilehash: 52e20c37f3066122a062e3fc9c64ced576b6c302
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50577979"
---
# <a name="data-directives-and-operators-in-inline-assembly"></a>インライン アセンブリでのデータ ディレクティブと演算子

**Microsoft 固有の仕様**

ただし、`__asm`ブロックは、C または C++ のデータ型とオブジェクトを参照できる、データ オブジェクトの MASM ディレクティブと演算子を定義できません。 具体的には、定義のディレクティブを使用することはできません**DB**、 `DW`、 **DD**、 `DQ`、 `DT`、および`DF`、または演算子`DUP`または**これは、** します。 MASM の構造とレコードもご利用いただけません。 インライン アセンブラーは、これらのディレクティブを受け入れません`STRUC`、 `RECORD`、**幅**、または**マスク**します。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[__asm ブロックでのアセンブリ言語の使用](../../assembler/inline/using-assembly-language-in-asm-blocks.md)<br/>
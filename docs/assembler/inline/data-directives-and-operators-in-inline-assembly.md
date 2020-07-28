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
ms.openlocfilehash: bcacb0cdd26181da3cf80a582866c1e30567d043
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87192354"
---
# <a name="data-directives-and-operators-in-inline-assembly"></a>インライン アセンブリでのデータ ディレクティブと演算子

**Microsoft 固有の仕様**

ブロックは、 **`__asm`** C または C++ のデータ型およびオブジェクトを参照できますが、MASM ディレクティブや演算子を使用してデータオブジェクトを定義することはできません。 具体的には、定義ディレクティブ**DB**、 `DW` 、 **DD**、、、およびを使用することはできません。また、 `DQ` `DT` `DF` 演算子 `DUP` や**THIS**を使用することもできません。 MASM の構造とレコードも使用できません。 インラインアセンブラーは、ディレクティブ `STRUC` 、 `RECORD` 、**幅**、または**マスク**を受け入れません。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[__Asm ブロックでのアセンブリ言語の使用](../../assembler/inline/using-assembly-language-in-asm-blocks.md)<br/>

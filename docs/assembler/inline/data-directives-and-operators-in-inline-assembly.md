---
description: 詳細については、「インラインアセンブリのデータディレクティブと演算子」を参照してください。
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
ms.openlocfilehash: a2b11aa95723245fc977f97f42b1de2f6c7306ac
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97117953"
---
# <a name="data-directives-and-operators-in-inline-assembly"></a>インライン アセンブリでのデータ ディレクティブと演算子

**Microsoft 固有の仕様**

ブロックは、 **`__asm`** C または C++ のデータ型およびオブジェクトを参照できますが、MASM ディレクティブや演算子を使用してデータオブジェクトを定義することはできません。 具体的には、定義ディレクティブ **DB**、 `DW` 、 **DD**、、、およびを使用することはできません。また、 `DQ` `DT` `DF` 演算子 `DUP` や **THIS** を使用することもできません。 MASM の構造とレコードも使用できません。 インラインアセンブラーは、ディレクティブ `STRUC` 、 `RECORD` 、 **幅**、または **マスク** を受け入れません。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[__Asm ブロックでのアセンブリ言語の使用](../../assembler/inline/using-assembly-language-in-asm-blocks.md)<br/>

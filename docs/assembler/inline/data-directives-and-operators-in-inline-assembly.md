---
title: インライン アセンブリでのデータ ディレクティブと演算子 |Microsoft Docs
ms.custom: ''
ms.date: 08/30/2018
ms.technology:
- cpp-masm
ms.topic: conceptual
dev_langs:
- C++
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
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6aff2f4c5ce5e7f5592aa9ec707d002c57f0eac0
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/04/2018
ms.locfileid: "43678738"
---
# <a name="data-directives-and-operators-in-inline-assembly"></a>インライン アセンブリでのデータ ディレクティブと演算子

**Microsoft 固有の仕様**

ただし、`__asm`ブロックは、C または C++ のデータ型とオブジェクトを参照できる、データ オブジェクトの MASM ディレクティブと演算子を定義できません。 具体的には、定義のディレクティブを使用することはできません**DB**、 `DW`、 **DD**、 `DQ`、 `DT`、および`DF`、または演算子`DUP`または**これは、** します。 MASM の構造とレコードもご利用いただけません。 インライン アセンブラーは、これらのディレクティブを受け入れません`STRUC`、 `RECORD`、**幅**、または**マスク**します。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[__asm ブロックでのアセンブリ言語の使用](../../assembler/inline/using-assembly-language-in-asm-blocks.md)<br/>
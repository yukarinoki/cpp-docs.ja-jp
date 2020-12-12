---
description: 詳細については、「__asm ブロックでの C または C++ シンボルの使用」を参照してください。
title: __asm ブロックでの C または C++ シンボルの使用
ms.date: 08/30/2018
helpviewer_keywords:
- __asm keyword [C++], syntax
- symbols, in __asm blocks
- Visual C, symbols in __asm blocks
- __asm keyword [C++], C/C++ elements in
- Visual C++, in __asm blocks
ms.assetid: 0758ffdc-dfe9-41c8-a5e1-fd395bcac328
ms.openlocfilehash: 3a2e46ab13bb316cb4761103d34da6c129c97995
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97121889"
---
# <a name="using-c-or-c-symbols-in-__asm-blocks"></a>__asm ブロックでの C または C++ シンボルの使用

**Microsoft 固有の仕様**

ブロックは **`__asm`** 、ブロックが表示されているスコープ内の C または C++ のシンボルを参照できます。 (C と C++ のシンボルは、変数名、関数名、およびラベルです。つまり、シンボル定数またはメンバーではない名前です **`enum`** 。 C++ のメンバー関数を呼び出すことはできません)。

C と C++ のシンボルの使用には、いくつかの制限が適用されます。

- 各アセンブリ言語ステートメントには、C または C++ のシンボルを1つだけ含めることができます。 複数のシンボルは、 **長さ**、 **型**、および **サイズ** の式のみを含む同じアセンブリ命令で使用できます。

- ブロックで参照 **`__asm`** される関数は、プログラムで前に宣言 (プロトタイプ) する必要があります。 それ以外の場合、コンパイラは、ブロック内の関数名とラベルを区別できません **`__asm`** 。

- ブロックは、 **`__asm`** (大文字小文字に関係なく) MASM の予約語と同じスペルで C または C++ のシンボルを使用することはできません。 MASM 予約語には、SI などの **プッシュ** やレジスタ名などの命令名が含まれます。

- 構造体と共用体のタグは、ブロックでは認識されません **`__asm`** 。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[__Asm ブロックでの C または C++ の使用](../../assembler/inline/using-c-or-cpp-in-asm-blocks.md)<br/>

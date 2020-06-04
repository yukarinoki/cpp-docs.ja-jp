---
title: __asm ブロックでの C または C++ シンボルの使用
ms.date: 08/30/2018
helpviewer_keywords:
- __asm keyword [C++], syntax
- symbols, in __asm blocks
- Visual C, symbols in __asm blocks
- __asm keyword [C++], C/C++ elements in
- Visual C++, in __asm blocks
ms.assetid: 0758ffdc-dfe9-41c8-a5e1-fd395bcac328
ms.openlocfilehash: fd9f8b444d263818aca1b16260f70730d5350e7c
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80169111"
---
# <a name="using-c-or-c-symbols-in-__asm-blocks"></a>__asm ブロックでの C または C++ シンボルの使用

**Microsoft 固有の仕様**

`__asm` ブロックは、ブロックが表示されC++ているスコープ内の C またはシンボルを参照できます。 (C とC++記号は、変数名、関数名、およびラベルです。つまり、シンボル定数または `enum` メンバーではない名前です。 メンバー関数をC++呼び出すことはできません)。

C とC++シンボルの使用には、いくつかの制限が適用されます。

- 各アセンブリ言語ステートメントには、C またはC++記号を1つだけ含めることができます。 複数のシンボルは、**長さ**、**型**、および**サイズ**の式のみを含む同じアセンブリ命令で使用できます。

- `__asm` ブロックで参照される関数は、プログラムで前に宣言 (プロトタイプ) する必要があります。 それ以外の場合、コンパイラは、`__asm` ブロック内の関数名とラベルを区別できません。

- `__asm` ブロックでは、(大文字小C++文字に関係なく) MASM の予約語と同じスペルの C や記号を使用することはできません。 MASM 予約語には、SI などの**プッシュ**やレジスタ名などの命令名が含まれます。

- 構造体と共用体のタグは `__asm` ブロックでは認識されません。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>参照

[__asm ブロックでの C または C++ の使用](../../assembler/inline/using-c-or-cpp-in-asm-blocks.md)<br/>

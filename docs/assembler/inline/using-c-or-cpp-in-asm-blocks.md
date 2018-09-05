---
title: _ _Asm ブロックでの C または C++ の使用 |Microsoft Docs
ms.custom: ''
ms.date: 08/30/2018
ms.technology:
- cpp-masm
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- inline assembly, mixing instructions with C/C++ statements
- symbols, in __asm blocks
- macros, __asm blocks
- preprocessor directives, used in __asm blocks
- type names, used in __asm blocks
- preprocessor directives
- preprocessor, directives
- constants, in __asm blocks
- comments, in __asm blocks
- typedef names, used in __asm blocks
- __asm keyword [C++], C/C++ elements in
ms.assetid: ae8b2b52-6b75-42e3-ac0c-ad02d922ed97
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 14b91a7925089f6a6ab747a9fd6a5813f9a14693
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/04/2018
ms.locfileid: "43687100"
---
# <a name="using-c-or-c-in-asm-blocks"></a>__asm ブロックでの C または C++ の使用

* * Microsoft 固有の仕様 * *

インライン アセンブリの命令を C または C++ ステートメントを混在させることができますので、C または C++ の変数を名前で参照し、それらの言語の他の多くの要素を使用できます。

`__asm`ブロックは、次の言語要素を使用できます。

- ラベルと変数と関数の名前を含む、シンボル

- 記号定数を含む定数と`enum`メンバー

- マクロとプリプロセッサ ディレクティブ

- コメント (両方__/ \* \* /__ と__//__ )

- (任意の場所、MASM 型が有効であるなどは) 名前を入力します。

- `typedef` などの演算子で使用される一般に、名**PTR**と**型**または構造体または共用体のメンバーを指定するには

内で、`__asm`ブロック、C の表記またはアセンブラー小数点表記のいずれかで整数の定数を指定することができます (0x100 と h の 100 は同等ですが、たとえば)。 定義することができます (を使用して`#define`) C 内の定数をプログラムの C または C++ とアセンブリの両方の部分で使用します。 使用される定数を指定することもできます。 その前に、0、8 進数。 たとえば、0777 は、8 進数の定数を指定します。

## <a name="what-do-you-want-to-know-more-about"></a>さらに詳しくは次のトピックをクリックしてください

- [__asm ブロックでの演算子の使用](../../assembler/inline/using-operators-in-asm-blocks.md)

- [_ _Asm ブロックの C または C++ Symbols_in を使用します。](../../assembler/inline/using-c-or-cpp-symbols-in-asm-blocks.md)

- [__asm ブロックの C または C++ のデータへのアクセス](../../assembler/inline/accessing-c-or-cpp-data-in-asm-blocks.md)

- [インライン アセンブリでの関数の記述](../../assembler/inline/writing-functions-with-inline-assembly.md)

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[インライン アセンブラー](../../assembler/inline/inline-assembler.md)<br/>

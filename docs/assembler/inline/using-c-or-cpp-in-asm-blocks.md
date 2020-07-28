---
title: __asm ブロックでの C または C++ の使用
ms.date: 08/30/2018
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
ms.openlocfilehash: 05e63d666f3fc39126d6f48e8fc523c4a02e76df
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87191418"
---
# <a name="using-c-or-c-in-__asm-blocks"></a>__asm ブロックでの C または C++ の使用

**Microsoft 固有の仕様**

インラインアセンブリ命令は C または C++ ステートメントと混在させることができるため、C または C++ の変数を名前で参照し、これらの言語の他の多くの要素を使用することができます。

ブロックでは **`__asm`** 、次の言語要素を使用できます。

- ラベル、変数名、関数名を含むシンボル

- 定数 (シンボル定数とメンバーを含む) **`enum`**

- マクロおよびプリプロセッサディレクティブ

- コメント (と__ / \* \* / __の両方 __//__ )

- 型名 (MASM の型が有効である任意の場所)

- **`typedef`** 名前。通常、 **PTR** 、**型**、またはなどの演算子と共に使用して、構造体または共用体のメンバーを指定します。

ブロック内では **`__asm`** 、C 表記またはアセンブラー基数表記 (0x100 と100h は同等) で整数定数を指定できます。 これにより、C で定数を定義 (を使用) して、 `#define` c または C++ とプログラムのアセンブリ部分の両方で使用できます。 また、定数を8進数で指定するには、その前に0を指定します。 たとえば、0777は8進数の定数を指定します。

## <a name="what-do-you-want-to-know-more-about"></a>さらに詳しくは次のトピックをクリックしてください

- [__Asm ブロックでの演算子の使用](../../assembler/inline/using-operators-in-asm-blocks.md)

- [C または C++ Symbols_in __asm ブロックの使用](../../assembler/inline/using-c-or-cpp-symbols-in-asm-blocks.md)

- [__Asm ブロックでの C または C++ データへのアクセス](../../assembler/inline/accessing-c-or-cpp-data-in-asm-blocks.md)

- [インラインアセンブリを使用した関数の作成](../../assembler/inline/writing-functions-with-inline-assembly.md)

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[インラインアセンブラー](../../assembler/inline/inline-assembler.md)<br/>

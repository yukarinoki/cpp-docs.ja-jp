---
description: '詳細情報: 文字列化演算子 (#)'
title: 文字列化演算子 (#)
ms.date: 08/29/2019
f1_keywords:
- '#'
helpviewer_keywords:
- preprocessor, operators
- arguments [C++], converting to strings
- stringizing operator
- preprocessor
- string literals, converting macro parameters to
- macros [C++], converting parameters to strings
- '# preprocessor operator'
ms.assetid: 1175dd19-4538-43b3-ad97-a008ab80e7b1
ms.openlocfilehash: 6b6f938e71e213e57fc6c4ec02b33da02e41ea2e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97136033"
---
# <a name="stringizing-operator-"></a>文字列化演算子 (#)

シャープ記号または "文字列化" 演算子 () は、 **#** パラメーター定義を展開せずにマクロパラメーターを文字列リテラルに変換します。 引数を受け取るマクロでのみ使用されます。 マクロ定義の仮パラメーターの前に指定すると、マクロの呼び出し時に渡される実際の引数は一重引用符で囲まれ、文字列リテラルとして扱われます。 文字列リテラルは、マクロ定義内の文字列化演算子と仮パラメーターの組み合わせをすべて置き換えます。

> [!NOTE]
> Microsoft C (Version 6.0 以前) では、ANSI C 規格を拡張して、文字列リテラルと文字定数の内部に現れるマクロ仮引数を展開していましたが、この拡張機能はサポートされなくなりました。 この拡張機能に依存するコードは、文字列化 () 演算子を使用して書き直す必要があり **#** ます。

最初のトークンの前にあり、実際の引数の最後のトークンの後にある空白は無視されます。 実引数のトークンの間にある空白は、結果の文字列リテラルでは 1 個の空白にまとめられます。 したがって、実際の引数の2つのトークンの間にコメントがある場合、1つの空白に縮小されます。 結果の文字列リテラルは、空白のみで区切られた隣接する文字列リテラルと自動的に連結されます。

さらに、引数に含まれる文字が文字列リテラルで使用されている場合 (引用符 () や円記号 () など) にエスケープシーケンスが必要な場合は、 `"` `\` 文字の前に必要なエスケープ円記号が自動的に挿入されます。

Microsoft C++ の文字列化演算子は、エスケープシーケンスを含む文字列と共に使用されても正しく動作しません。 このような場合は、コンパイラによって [コンパイラエラー C2017](../error-messages/compiler-errors-1/compiler-error-c2017.md)が生成されます。

## <a name="examples"></a>例

次の例は、文字列化演算子を含むマクロ定義と、マクロを呼び出す main 関数を示しています。

```cpp
// stringizer.cpp
#include <stdio.h>
#define stringer( x ) printf_s( #x "\n" )
int main() {
   stringer( In quotes in the printf function call );
   stringer( "In quotes when printed to the screen" );
   stringer( "This: \"  prints an escaped double quote" );
}
```

`stringer`前処理中にマクロが拡張され、次のコードが生成されます。

```cpp
int main() {
   printf_s( "In quotes in the printf function call" "\n" );
   printf_s( "\"In quotes when printed to the screen\"" "\n" );
   printf_s( "\"This: \\\" prints an escaped double quote\"" "\n" );
}
```

```Output
In quotes in the printf function call
"In quotes when printed to the screen"
"This: \"  prints an escaped double quote"
```

次の例は、マクロ パラメーターを展開する方法を示しています。

```cpp
// stringizer_2.cpp
// compile with: /E
#define F abc
#define B def
#define FB(arg) #arg
#define FB1(arg) FB(arg)
FB(F B)
FB1(F B)
```

## <a name="see-also"></a>関連項目

[プリプロセッサ演算子](../preprocessor/preprocessor-operators.md)

---
title: 文字列化演算子 (#)
ms.date: 11/04/2016
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
ms.openlocfilehash: 4f23eea017197ae1f984e097bb3967c1228fef09
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62179647"
---
# <a name="stringizing-operator-"></a>文字列化演算子 (#)

シャープ記号つまり「文字列化」演算子 (**#**) マクロのパラメーターをリテラル文字列をパラメーターの定義を展開せずに変換します。 これは、引数を受け取るマクロでのみ使用されます。 マクロ定義の仮パラメーターの前に指定すると、マクロの呼び出し時に渡される実際の引数は一重引用符で囲まれ、文字列リテラルとして扱われます。 文字列リテラルは、マクロ定義内の文字列化演算子と仮パラメーターの組み合わせをすべて置き換えます。

> [!NOTE]
> Microsoft C (Version 6.0 以前) では、ANSI C 規格を拡張して、文字列リテラルと文字定数の内部に現れるマクロ仮引数を展開していましたが、この拡張機能はサポートされなくなりました。 この拡張機能に依存するコードは、文字列化演算子を使用して書き直す必要があります (**#**) 演算子。

実引数の最初のトークンに先行する空白と、実引数の最後のトークンに後続する空白は無視されます。 実引数のトークンの間にある空白は、結果の文字列リテラルでは 1 個の空白にまとめられます。 したがって、実引数で 2 つのトークンの間にコメントがある場合、コメントは 1 個の空白に置き換えられます。 結果の文字列リテラルは、隣接する任意の文字列リテラルと、空白のみで区切られて自動的に連結されます。

さらに、通常は、引数に含まれる文字が文字列リテラルで使用する場合は、エスケープ シーケンスが必要な場合 (引用符など (**"**) または円記号 (**\\**) 文字)、必要なエスケープ バック スラッシュが文字の前に自動的に挿入されます。

エスケープ シーケンスを含む文字列をと共に使用するときに、Visual C の文字列化演算子は正しく動作しません。 このような状況では、コンパイラが生成されます[コンパイラ エラー C2017](../error-messages/compiler-errors-1/compiler-error-c2017.md)します。

## <a name="examples"></a>使用例

次の例は、文字列化演算子を含むマクロ定義と、そのマクロを呼び出すメイン関数を示しています。

このような呼び出しはプリプロセッサによって展開され、次のコードが生成されます。

```cpp
int main() {
   printf_s( "In quotes in the printf function call\n" "\n" );
   printf_s( "\"In quotes when printed to the screen\"\n" "\n" );
   printf_s( "\"This: \\\" prints an escaped double quote\"" "\n" );
}
```

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
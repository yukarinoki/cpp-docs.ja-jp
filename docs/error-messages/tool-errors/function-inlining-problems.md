---
description: '詳細情報: 関数のインライン展開の問題'
title: 関数インライン展開の問題
ms.date: 11/04/2016
helpviewer_keywords:
- /Ob1 C++ compiler option
- inline functions, problems
- -Ob1 C++ compiler option
- /Ob2 C++ compiler option
- -Ob2 C++ compiler option
- function inlining problems
ms.assetid: 65d59943-4b3c-4a43-aeb6-dccbf7686740
ms.openlocfilehash: 3c9c82c8b948acf7a64600c46fe87e17294fa844
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97261737"
---
# <a name="function-inlining-problems"></a>関数インライン展開の問題

関数のインライン展開を使用する場合は、次のことを行う必要があります。

- インライン関数を、含めるヘッダーファイルに実装します。

- ヘッダーファイルでインライン展開が有効になっていること。

```cpp
// LNK2019_function_inline.cpp
// compile with: /c
// post-build command: lib LNK2019_function_inline.obj
#include <stdio.h>
struct _load_config_used {
   void Test();
   void Test2() { printf("in Test2\n"); }
};

void _load_config_used::Test() { printf("in Test\n"); }
```

この場合、次のようになります。

```cpp
// LNK2019_function_inline_2.cpp
// compile with: LNK2019_function_inline.lib
struct _load_config_used {
   void Test();
   void Test2();
};

int main() {
   _load_config_used x;
   x.Test();
   x.Test2();   // LNK2019
}
```

コンパイラディレクティブを使用している場合は `#pragma inline_depth` 、2以上の値が設定されていることを確認してください。 値を0に設定すると、インライン展開が無効になります。 また、 **/ob1** または **/ob2** コンパイラオプションを使用していることを確認してください。

インラインコンパイルオプションと非インラインコンパイルオプションを異なるモジュールに混在させると、問題が発生することがあります。 関数のインライン展開が有効になっている C++ ライブラリが作成された場合 ([/ob1](../../build/reference/ob-inline-function-expansion.md) または [/ob2](../../build/reference/ob-inline-function-expansion.md))、関数を説明する対応するヘッダーファイルでインライン展開がオフになっている (オプションがない) 場合は、エラー LNK2001 が返されます。 関数はヘッダーファイルのコードにインライン展開されませんが、ライブラリファイルにはないため、参照を解決するアドレスがありません。

同様に、関数のインライン展開を使用するプロジェクトでは、ヘッダーファイルではなく .cpp ファイル内の関数も定義されています。 ヘッダーファイルは、適切と見なされるすべての場所に含まれますが、関数は、.cpp ファイルがコンパイラを通過するときにのみインライン化されます。そのため、他のモジュールで使用されている場合、リンカーは関数を未解決の外部参照として認識します。

```cpp
// LNK2019_FIP.h
struct testclass {
   void PublicStatMemFunc1(void);
};
```

それから

```cpp
// LNK2019_FIP.cpp
// compile with: /c
#include "LNK2019_FIP.h"
inline void testclass::PublicStatMemFunc1(void) {}
```

それから

```cpp
// LNK2019_FIP_2.cpp
// compile with: LNK2019_FIP.cpp
// LNK2019 expected
#include "LNK2019_FIP.h"
int main() {
   testclass testclsObject;

   // module cannot see the implementation of PublicStatMemFunc1
   testclsObject.PublicStatMemFunc1();
}
```

## <a name="see-also"></a>関連項目

[リンカツールエラー LNK2019](../../error-messages/tool-errors/linker-tools-error-lnk2019.md)

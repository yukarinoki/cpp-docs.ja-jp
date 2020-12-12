---
description: '詳細については、/Zc: inline (参照できない COMDAT の削除) に関するページを参照してください。'
title: /Zc:inline (参照されない COMDAT の除去)
ms.date: 09/05/2019
f1_keywords:
- /Zc:inline
- VC.Project.VCCLCompilerTool.RemoveUnreferencedCodeData
helpviewer_keywords:
- -Zc compiler options (C++)
- /Zc compiler options (C++)
- Zc compiler options (C++)
- /Zc:inline
ms.assetid: a4c94224-1d73-4bea-a9d5-4fa73dc924df
ms.openlocfilehash: f9a3ac488057059d53925b8f505b9a3ad7f6674a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97117550"
---
# <a name="zcinline-remove-unreferenced-comdat"></a>/Zc:inline (参照されない COMDAT の除去)

Comdat であるか、または内部リンケージのみを持つ、参照されていないデータまたは関数を削除します。 **/Zc: inline** の下では、インラインデータまたは関数を含む翻訳単位にもその定義が含まれている必要があることをコンパイラが指定しています。

## <a name="syntax"></a>構文

> **/Zc: inline**[ **-** ]

## <a name="remarks"></a>解説

**/Zc: inline** を指定すると、コンパイラは、参照されていない COMDAT 関数またはデータのシンボル情報を生成しません。 内部リンケージのみを持つデータまたは関数の場合は。 この最適化により、リンカーがリリースビルドで実行する作業の一部、または [/opt: REF](opt-optimizations.md) リンカーオプションを指定したときの作業が簡略化されます。 このコンパイラの最適化により、.obj ファイルのサイズを大幅に削減し、リンカーの速度を向上させることができます。 最適化 ([/od](od-disable-debug.md)) を無効にした場合、コンパイラオプションは有効になりません。 または、 [/gl (プログラム全体の最適化)](gl-whole-program-optimization.md)を指定する場合。

既定では、このオプションは、コマンドラインビルドではオフ (**/zc: inline**) に設定されています。 [/Permissive-](permissive-standards-conformance.md)オプションでは **/zc: inline** が有効になっていません。 MSBuild プロジェクトでは、このオプションは **構成プロパティ** の [  >  **C/c + +** 言語] [参照されていない  >    >  **コードとデータの削除**] プロパティによって設定されます。このプロパティは、既定では **[はい]** に設定されます。

**/Zc: inline** が指定されている場合、コンパイラは c++ 11 の要件を適用します。これは、宣言されたすべての関数が、 **`inline`** 使用されている場合、同じ翻訳単位で使用可能である必要があります。 オプションが指定されていない場合、Microsoft コンパイラは、 **`inline`** 定義が表示されない場合でも宣言された関数を呼び出す、準拠していないコードを許可します。 詳細については、C++11 標準のセクション 3.2 およびセクション 7.1.2 を参照してください。 このコンパイラ オプションは、Visual Studio 2013 更新プログラム 2 で導入されました。

**/Zc: inline** オプションを使用するには、準拠していないコードを更新します。

次の例では、既定の **/zc: inline** オプションが使用されている場合でも、定義のないインライン関数宣言の非準拠の使用方法を示しています。

```cpp
// example.h
// Compile by using: cl /W4 /EHsc /O2 zcinline.cpp example.cpp
#pragma once

class Example {
public:
   inline void inline_call(); // declared but not defined inline
   void normal_call();
   Example() {};
};
```

```cpp
// example.cpp
// Compile by using: cl /W4 /EHsc /O2 zcinline.cpp example.cpp
#include <stdio.h>
#include "example.h"

void Example::inline_call() {
   printf("inline_call was called.\n");
}

void Example::normal_call() {
   printf("normal_call was called.\n");
   inline_call(); // with /Zc:inline-, inline_call forced into .obj file
}
```

```cpp
// zcinline.cpp
// Compile by using: cl /W4 /EHsc /O2 zcinline.cpp example.cpp
#include "example.h"

int main() {
   Example example;
   example.inline_call(); // normal call when definition unavailable
}
```

**/Zc: inline** が有効になっている場合、同じコードによって [LNK2019](../../error-messages/tool-errors/linker-tools-error-lnk2019.md)エラーが発生します。これは、コンパイラがたとえば .obj のに非インラインコード本体を生成しないため `Example::inline_call` です。これにより、の非インライン呼び出し `main` によって未定義の外部シンボルが参照されます。

このエラーを解決するには、 **`inline`** の宣言からキーワードを削除する `Example::inline_call` か、の定義を `Example::inline_call` ヘッダーファイルに移動するか、の実装を `Example` メイン .cpp に移動します。 次の例では、定義をヘッダー ファイルに移動します。そこでは、ヘッダーを含む任意の呼び出し元から定義を参照できます。

```cpp
// example2.h
// Compile by using: cl /W4 /EHsc /O2 zcinline2.cpp example2.cpp
#pragma once
#include <stdio.h>

class Example2 {
public:
   inline void inline_call() {
      printf("inline_call was called.\n");
   }
   void normal_call();
   Example2() {};
};
```

```cpp
// example2.cpp
// Compile by using: cl /W4 /EHsc /O2 zcinline2.cpp example2.cpp
#include "example2.h"

void Example2::normal_call() {
   printf("normal_call was called.\n");
   inline_call();
}
```

```cpp
// zcinline2.cpp
// Compile by using: cl /W4 /EHsc /O2 zcinline2.cpp example2.cpp
#include "example2.h"

int main() {
   Example2 example2;
   example2.inline_call(); // normal call when definition unavailable
}
```

Visual C++ の準拠に関する問題について詳しくは、「 [Nonstandard Behavior](../../cpp/nonstandard-behavior.md)」をご覧ください。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、[Visual Studio での C++ コンパイラとビルド プロパティの設定](../working-with-project-properties.md)に関するページを参照してください。

1. [**構成プロパティ**] [  >  **C/c + +**  >  **言語**] プロパティページを選択します。

1. "参照されていない **コードとデータの削除** " プロパティを変更し、[ **OK]** をクリックします。

## <a name="see-also"></a>関連項目

[/Zc (準拠)](zc-conformance.md)<br/>

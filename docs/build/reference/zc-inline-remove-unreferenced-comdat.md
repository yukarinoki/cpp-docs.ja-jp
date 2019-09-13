---
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
ms.openlocfilehash: f0c0d9a4e5e5f52d239f1a8591006b3d9e369778
ms.sourcegitcommit: 180f63704f6ddd07a4172a93b179cf0733fd952d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/06/2019
ms.locfileid: "70740106"
---
# <a name="zcinline-remove-unreferenced-comdat"></a>/Zc:inline (参照されない COMDAT の除去)

COMDAT であるか内部リンケージのみを持つ、参照されていない関数またはデータを削除します。 **/Zc: inline**が指定されている場合、コンパイラでは、インラインデータまたはインライン関数を使用する翻訳単位にデータまたは関数の定義も含める必要があります。

## <a name="syntax"></a>構文

> **/Zc:inline**[ **-** ]

## <a name="remarks"></a>Remarks

**/Zc: inline**を指定すると、コンパイラは、参照されていない COMDAT 関数またはデータ、または内部リンケージのみを持つ関数またはデータのシンボル情報を生成しません。 この最適化により、リリースビルドでリンカーによって実行される作業の一部、またはリンカーオプション[/opt: REF](opt-optimizations.md)が指定された場合の作業が簡略化されます。 コンパイラによってこの最適化が実行されると、.obj ファイルのサイズを大幅に縮小し、リンカーの速度を向上させることができます。 最適化が無効になっている場合 ([/od](od-disable-debug.md))、または[/Gl (プログラム全体の最適化)](gl-whole-program-optimization.md)が指定されている場合、このコンパイラオプションは有効になりません。

既定では、このオプションは、コマンドラインビルドではオフ ( **/zc: inline**) に設定されています。 [/Permissive-](permissive-standards-conformance.md)オプションでは、 **/zc: inline**は使用できません。 MSBuild プロジェクトでは、このオプションは、**構成プロパティ** > の**C/C++**  > **言語** > の "参照されていない**コードとデータの削除**" プロパティによって設定されます。このプロパティは、 **[はい]** に設定されます。標準.

**/Zc: inline**が指定されている場合、コンパイラは c++ 11 の要件を`inline`適用します。これは、宣言されたすべての関数が、使用されている場合、同じ翻訳単位で使用可能である必要があります。 オプションが指定されていない場合、Microsoft コンパイラは、定義が表示され`inline`ない場合でも宣言された関数を呼び出す、準拠していないコードを許可します。 詳細については、C++11 標準のセクション 3.2 およびセクション 7.1.2 を参照してください。 このコンパイラ オプションは、Visual Studio 2013 更新プログラム 2 で導入されました。

**/Zc: inline**オプションを使用するには、準拠していないコードを更新します。

次の例では、既定の **/zc: inline**オプションが使用されている場合でも、定義のないインライン関数宣言の非準拠の使用方法を示しています。

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

void main() {
   Example example;
   example.inline_call(); // normal call when definition unavailable
}
```

**/Zc: inline**が有効になっている場合、同じコードによって[LNK2019](../../error-messages/tool-errors/linker-tools-error-lnk2019.md)エラーが発生します。これは、コンパイラが`Example::inline_call`たとえば .obj のに非インラインコード本体を生成しないためです。これにより、`main` 内のインライン展開されていない呼び出しは、定義されていない外部シンボルを参照します。

このエラーを解決するには、`inline` キーワードを `Example::inline_call` の宣言から削除するか、`Example::inline_call` の定義をヘッダー ファイルに移動するか、`Example` の実装を main.cpp に移動します。 次の例では、定義をヘッダー ファイルに移動します。そこでは、ヘッダーを含む任意の呼び出し元から定義を参照できます。

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

void main() {
   Example2 example2;
   example2.inline_call(); // normal call when definition unavailable
}
```

Visual C++ の準拠に関する問題について詳しくは、「 [Nonstandard Behavior](../../cpp/nonstandard-behavior.md)」をご覧ください。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境において、このコンパイラ オプションを設定する方法

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、[Visual Studio での C++ コンパイラとビルド プロパティの設定](../working-with-project-properties.md)に関するページを参照してください。

1. [**構成プロパティ** > ] [**CC++/**  > **言語**] プロパティページを選択します。

1. "参照されていない**コードとデータの削除**" プロパティを変更し、[ **OK]** をクリックします。

## <a name="see-also"></a>関連項目

[/Zc (準拠)](zc-conformance.md)<br/>

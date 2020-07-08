---
title: /Gh (_penter フック関数の有効化)
description: 指定された _penter 関数を呼び出す/Gh コンパイラオプションについて説明します。
ms.date: 07/06/2020
f1_keywords:
- _penter
helpviewer_keywords:
- /Gh compiler option [C++]
- Gh compiler option [C++]
- _penter function
- -Gh compiler option [C++]
ms.assetid: 1510a082-8a0e-486e-a309-6add814b494f
ms.openlocfilehash: 96597d964e6a341aa25f4d52d34974949eb7b096
ms.sourcegitcommit: 85d96eeb1ce41d9e1dea947f65ded672e146238b
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "86058582"
---
# <a name="gh-enable-_penter-hook-function"></a>/Gh (_penter フック関数の有効化)

`_penter`各メソッドまたは関数の先頭で関数を呼び出します。

## <a name="syntax"></a>構文

> **`/Gh`**

## <a name="remarks"></a>Remarks

`_penter`関数はどのライブラリの一部でもありません。 の定義を指定する必要が `_penter` あります。

明示的にを呼び出す予定がない限り `_penter` 、プロトタイプを提供する必要はありません。 関数は、入力時にすべてのレジスタの内容をプッシュし、終了時に変更されていないコンテンツをポップする必要があります。 次のプロトタイプがあるかのように表示される必要があります。

```cpp
void __declspec(naked) __cdecl _penter( void );
```

この宣言は、64ビットのプロジェクトでは使用できません。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、[Visual Studio での C++ コンパイラとビルド プロパティの設定](../working-with-project-properties.md)に関するページを参照してください。

1. [**構成プロパティ**  >  ] [**C/c + +**  >  **] [コマンドライン**] プロパティページを開きます。

1. [**追加オプション**] ボックスにコンパイラオプションを入力します。

### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには

- 以下を参照してください。<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>

## <a name="example"></a>例

次のコードは、 **/Gh**を使用してコンパイルした場合、が2回呼び出される方法を示して `_penter` います。関数を入力すると、 `main` 関数を入力したときに1回です。 `x` この例は、個別にコンパイルする2つのソースファイルで構成されています。

```cpp
// local_penter.cpp
// compile with: cl /EHsc /c local_penter.cpp
// processor: x86
#include <stdio.h>

extern "C" void __declspec(naked) __cdecl _penter( void ) {
   _asm {
      push eax
      push ebx
      push ecx
      push edx
      push ebp
      push edi
      push esi
    }

   printf_s("\nIn a function!");

   _asm {
      pop esi
      pop edi
      pop ebp
      pop edx
      pop ecx
      pop ebx
      pop eax
      ret
    }
}
```

```cpp
// Gh_compiler_option.cpp
// compile with: cl /EHsc /Gh Gh_compiler_option.cpp local_penter.obj
// processor: x86
#include <stdio.h>

void x() {}

int main() {
   x();
}
```

実行すると、ローカル `_penter` 関数はとのエントリで呼び出され `main` `x` ます。

```Output

In a function!
In a function!
```

## <a name="see-also"></a>関連項目

[MSVC コンパイラ オプション](compiler-options.md)<br/>
[MSVC コンパイラ コマンド ラインの構文](compiler-command-line-syntax.md)<br/>
[`/GH`(_Pexit フック関数を有効にする)](gh-enable-pexit-hook-function.md)

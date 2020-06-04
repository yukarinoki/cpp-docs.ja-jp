---
title: /Gh (_penter フック関数の有効化)
ms.date: 11/04/2016
f1_keywords:
- _penter
helpviewer_keywords:
- /Gh compiler option [C++]
- Gh compiler option [C++]
- _penter function
- -Gh compiler option [C++]
ms.assetid: 1510a082-8a0e-486e-a309-6add814b494f
ms.openlocfilehash: 87815b5f0e0450b84acbe3c35b7ef4f31216ec72
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "81749296"
---
# <a name="gh-enable-_penter-hook-function"></a>/Gh (_penter フック関数の有効化)

すべてのメソッドまたは関数の`_penter`先頭で関数を呼び出します。

## <a name="syntax"></a>構文

```
/Gh
```

## <a name="remarks"></a>解説

この`_penter`関数はライブラリの一部ではなく、 の定義を指定する必要があります`_penter`。

明示的に呼び出`_penter`す場合を除き、プロトタイプを提供する必要はありません。 関数は、次のプロトタイプを持っているかのように見える必要があり、エントリ上のすべてのレジスタの内容をプッシュし、終了時に変更されていない内容をポップする必要があります。

```cpp
void __declspec(naked) __cdecl _penter( void );
```

この宣言は、64 ビット プロジェクトでは使用できません。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、[Visual Studio での C++ コンパイラとビルド プロパティの設定](../working-with-project-properties.md)に関するページを参照してください。

1. **[C/C++]** フォルダーをクリックします。

1. **[コマンド ライン]** プロパティ ページをクリックします。

1. [追加のオプション] **** ボックスにコンパイラ オプションを入力します。

### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには

- 「<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>」を参照してください。

## <a name="example"></a>例

次のコードは **、/Gh**でコンパイルされた場合、2 回の呼び出し方法`_penter`を示しています。関数`main`を入力するとき、関数を入力するときに一度`x`、 .

```cpp
// Gh_compiler_option.cpp
// compile with: /Gh
// processor: x86
#include <stdio.h>
void x() {}

int main() {
   x();
}

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

```Output
In a function!
In a function!
```

## <a name="see-also"></a>関連項目

[MSVC コンパイラ オプション](compiler-options.md)<br/>
[MSVC コンパイラ コマンド ラインの構文](compiler-command-line-syntax.md)

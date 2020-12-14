---
description: 詳細については、次を参照してください:/FC (診断におけるソースコードファイルの完全パス)
title: /FC (診断時のソース コード ファイルの完全パス)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCCLCompilerTool.UseFullPaths
- /FC
helpviewer_keywords:
- /FC compiler option [C++]
- -FC compiler option [C++]
ms.assetid: 1f11414e-cb42-421b-be68-9d369aab036b
ms.openlocfilehash: 01d1148a32179a7c605a19dc7f2856b7697ae6fb
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97200677"
---
# <a name="fc-full-path-of-source-code-file-in-diagnostics"></a>/FC (診断時のソース コード ファイルの完全パス)

診断でコンパイラに渡されるソースコードファイルの完全なパスをコンパイラに表示させます。

## <a name="syntax"></a>構文

> /FC

## <a name="remarks"></a>解説

次のコード例について考えてみましょう。

```cpp
// compiler_option_FC.cpp
int main( ) {
   int i   // C2143
}
```

**/Fc** を指定しない場合、診断テキストは次の診断テキストのようになります。

- compiler_option_FC .cpp (5): エラー C2143: 構文エラー: '; ' が '} ' の前にありません

**/Fc** の場合、診断テキストは次の診断テキストのようになります。

- c:\test\ compiler_option_fc (5): error C2143: 構文エラー: '; ' が '} ' の前にありません

また、 &#95;&#95;ファイル&#95;&#95; マクロを使用する場合に、ファイル名の完全なパスを表示するには、 **/fc** も必要です。  &#95;&#95;ファイル&#95;&#95; の詳細については、「 [定義済みマクロ](../../preprocessor/predefined-macros.md) 」を参照してください。

**/Fc** オプションは、 **/zi** によって暗黙的に指定されます。 **/Zi** の詳細については、「 [/Z7、/zi、/Zi (デバッグ情報の形式)](z7-zi-zi-debug-information-format.md)」を参照してください。

**/Fc** は、小文字で完全なパスを出力します。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、[Visual Studio での C++ コンパイラとビルド プロパティの設定](../working-with-project-properties.md)に関するページを参照してください。

1. [**構成プロパティ**] [  >  **C/c + +**]  >  **[詳細設定**] プロパティページを選択します。

1. " **完全パスの使用** " プロパティを変更します。

### <a name="to-set-this-linker-option-programmatically"></a>このリンカーをコードから設定するには

- 以下を参照してください。<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.UseFullPaths%2A>

## <a name="see-also"></a>関連項目

[MSVC コンパイラ オプション](compiler-options.md)<br/>
[MSVC Compiler Command-Line 構文](compiler-command-line-syntax.md)

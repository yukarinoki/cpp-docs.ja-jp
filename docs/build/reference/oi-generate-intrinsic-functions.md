---
description: 詳細情報:/Oi (組み込み関数の生成)
title: /Oi (組み込み関数の生成)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCCLCompilerTool.EnableIntrinsicFunctions
- /oi
- VC.Project.VCCLWCECompilerTool.EnableIntrinsicFunctions
helpviewer_keywords:
- Oi compiler option [C++]
- intrinsic functions, generate
- /Oi compiler option [C++]
- -Oi compiler option [C++]
- generate intrinsic functions compiler option [C++]
ms.assetid: fa4a3bf6-0ed8-481b-91c0-add7636132b4
ms.openlocfilehash: fc08ff495391092115197fe70e8c3673b77f32e0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97214280"
---
# <a name="oi-generate-intrinsic-functions"></a>/Oi (組み込み関数の生成)

一部の関数呼び出しを組み込み関数またはそれ以外の特殊な形式に置き換えて、アプリケーションの実行速度を向上させることができます。

## <a name="syntax"></a>構文

```
/Oi[-]
```

## <a name="remarks"></a>解説

組み込み関数を使用するプログラムは、関数呼び出しのオーバーヘッドがないため、より高速に実行できますが、追加のコードが作成されるため、より大きな値になる場合があります。

組み込みフォームがある関数の詳細については、「 [組み込み](../../preprocessor/intrinsic.md) 」を参照してください。

**/Oi** は、一部の関数呼び出しを組み込みに置き換えるためのコンパイラへの要求です。コンパイラは、パフォーマンスを向上させるために、関数を呼び出すことができます (関数呼び出しを組み込みに置き換えることはできません)。

**x86 固有の仕様→**

組み込みの浮動小数点関数は、入力値に対して特別なチェックを実行せず、限られた範囲の入力で作業します。また、同じ名前を持つライブラリルーチンとは異なる例外処理と境界条件を持ちます。 真の組み込み形式を使用すると、IEEE 例外処理の損失や機能の損失を意味します。 `_matherr` `errno` 後者は、ANSI 準拠の損失を意味します。 ただし、組み込みフォームでは、浮動小数点を集中的に使用するプログラムを大幅に高速化できます。多くのプログラムでは、準拠に関する問題は実用的ではありません。

[Za](za-ze-disable-language-extensions.md)コンパイラオプションを使用して、真の組み込み浮動小数点オプションの生成をオーバーライドできます。 浮動小数点関数はライブラリ ルーチンとして生成されます。これらのライブラリ ルーチンでは、引数はプログラム スタックにプッシュされずに、数値演算コプロセッサに直接渡されます。

**終了 x86 固有**

また、組み込み関数または[関数 (c/c + +)](../../preprocessor/function-c-cpp.md) [を使用し](../../preprocessor/intrinsic.md)て関数呼び出しを明示的に強制することもできます。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、[Visual Studio での C++ コンパイラとビルド プロパティの設定](../working-with-project-properties.md)に関するページを参照してください。

1. **[C/C++]** フォルダーをクリックします。

1. [ **最適化** ] プロパティページをクリックします。

1. [ **組み込み関数を有効にする** ] プロパティを変更します。

### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには

- 以下を参照してください。<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.EnableIntrinsicFunctions%2A>

## <a name="see-also"></a>関連項目

[/O オプション (コードの最適化)](o-options-optimize-code.md)<br/>
[MSVC コンパイラ オプション](compiler-options.md)<br/>
[MSVC Compiler Command-Line 構文](compiler-command-line-syntax.md)<br/>
[コンパイラの組み込み](../../intrinsics/compiler-intrinsics.md)

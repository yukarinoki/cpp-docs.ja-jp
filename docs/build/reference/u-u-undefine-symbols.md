---
title: /U、/u (シンボルの未定義化)
ms.date: 06/08/2020
f1_keywords:
- VC.Project.VCCLCompilerTool.UndefinePreprocessorDefinitions
- VC.Project.VCCLWCECompilerTool.UndefinePreprocessorDefinitions
- VC.Project.VCCLCompilerTool.UndefineAllPreprocessorDefinitions
- /u
- VC.Project.VCCLWCECompilerTool.UndefineAllPreprocessorDefinitions
helpviewer_keywords:
- -U compiler option [C++]
- Undefine Symbols compiler option
- /U compiler option [C++]
- U compiler option [C++]
ms.assetid: 7bc0474f-6d1f-419b-807d-0d8816763b2a
ms.openlocfilehash: 4d7a2b3d5df2b22dc53eb7b58bfb78cdb1824b26
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "84616661"
---
# <a name="u-u-undefine-symbols"></a>/U、/u (シンボルの未定義化)

**`/U`** コンパイラオプションは、指定されたプリプロセッサシンボルを未定義にします。 コンパイラ **`/u`** オプションは、コンパイラが定義する Microsoft 固有のシンボルを未定義にします。

## <a name="syntax"></a>構文

> **`/U`**\[]*シンボル*\
> **`/u`**

## <a name="arguments"></a>引数

*表す*<br/>
未定義にするプリプロセッサシンボル。

## <a name="remarks"></a>Remarks

とのいずれのオプションでも、 **`/U`** **`/u`** ディレクティブを使用して作成されたシンボルを未定義にすることはできません **`#define`** 。

オプションは、 **`/U`** 以前にオプションを使用して定義されたシンボルを未定義にすることができ **`/D`** ます。

既定では、コンパイラは多くの Microsoft 固有のシンボルを定義できます。 いくつかの一般的な例を次に示します。

| Symbol | 関数 |
|--|--|
| `_CHAR_UNSIGNED` | 既定の char 型は符号なしです。 オプションが指定されている場合に定義され [**`/J`**](j-default-char-type-is-unsigned.md) ます。 |
| `_CPPRTTI` | オプションを使用してコンパイルされたコードに対して定義され [**`/GR`**](gr-enable-run-time-type-information.md) ます。 |
| `_CPPUNWIND` | オプションを使用してコンパイルされたコードに対して定義され [**`/EHsc`**](eh-exception-handling-model.md) ます。 |
| `_DLL` | オプションが指定されている場合に定義され [**`/MD`**](md-mt-ld-use-run-time-library.md) ます。 |
| `_M_IX86` | 既定では、x86 ターゲットの場合は600に定義されます。 |
| `_MSC_VER` | コンパイラのバージョンごとに一意の整数値として定義されます。 詳細については、「[定義済みマクロ](../../preprocessor/predefined-macros.md)」を参照してください。 |
| `_WIN32` | WIN32 アプリケーション用に定義されています。 これは、常に定義されます。 |
| `_MT` | [ **`/MD`** または **`/MT`** ](md-mt-ld-use-run-time-library.md)オプションが指定されている場合に定義されます。 |

Microsoft 固有の定義済みマクロの完全な一覧については、「[定義済みマクロ](../../preprocessor/predefined-macros.md)」を参照してください。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、[Visual Studio での C++ コンパイラとビルド プロパティの設定](../working-with-project-properties.md)に関するページを参照してください。

1. [**構成プロパティ**] [  >  **C/c + +**]  >  **[詳細設定**] プロパティページを選択します。

1. [**プリプロセッサ定義**の無効化] または [**すべてのプリプロセッサ定義**の無効化] プロパティを変更します。

### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには

- 詳細については、「<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.UndefineAllPreprocessorDefinitions%2A>」または「<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.UndefinePreprocessorDefinitions%2A>」を参照してください。

## <a name="see-also"></a>関連項目

[MSVC コンパイラ オプション](compiler-options.md)<br/>
[MSVC コンパイラ コマンド ラインの構文](compiler-command-line-syntax.md)<br/>
[**`/J`**(既定の char 型は符号なしです)](j-default-char-type-is-unsigned.md)<br/>
[**`/GR`**(ランタイム型情報の有効化)](gr-enable-run-time-type-information.md)<br/>
[**`/EH`**(例外処理モデル)](eh-exception-handling-model.md)<br/>
[**`/MD`**、 **`/MT`** 、 **`/LD`** (ランタイムライブラリの使用)](md-mt-ld-use-run-time-library.md)

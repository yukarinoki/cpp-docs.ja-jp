---
title: /Za、/Ze (言語拡張機能の無効化)
ms.date: 02/19/2019
f1_keywords:
- VC.Project.VCCLWCECompilerTool.DisableLanguageExtensions
- /za
- /ze
- VC.Project.VCCLCompilerTool.DisableLanguageExtensions
helpviewer_keywords:
- -Za compiler option [C++]
- Za compiler option [C++]
- language extensions, disabling in compiler
- -Ze compiler option [C++]
- language extensions
- enable language extensions
- /Za compiler option [C++]
- /Ze compiler option [C++]
- Disable Language Extensions compiler option
- Ze compiler option [C++]
ms.assetid: 65e49258-7161-4289-a176-7c5c0656b1a2
ms.openlocfilehash: 9a2584591f6ca22d6767a5c447ffb72bea0a78ea
ms.sourcegitcommit: 6b749db14b4cf3a2b8d581fda6fdd8cb98bc3207
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/05/2020
ms.locfileid: "82825876"
---
# <a name="za-ze-disable-language-extensions"></a>/Za、/Ze (言語拡張機能の無効化)

**/Za**コンパイラオプションは、ANSI C89/ISO C90 と互換性がない Microsoft Extensions for C のエラーを無効にして出力します。 非推奨の **/ze**コンパイラオプションは、Microsoft 拡張機能を有効にします。 Microsoft 拡張機能は既定で有効になっています。

## <a name="syntax"></a>構文

> **/Za**\
> **/Ze**

## <a name="remarks"></a>解説

> [!NOTE]
> C++ としてコードをコンパイルするときは、 **/za**を使用しないことをお勧めします。 **/Ze**オプションは、その動作が既定でオンになっているため、非推奨とされます。 非推奨のコンパイラオプションの一覧については、「[非推奨のコンパイラオプションと削除されたコンパイラオプション](compiler-options-listed-by-category.md#deprecated-and-removed-compiler-options)」を参照してください。

Microsoft C/c + + コンパイラは、次の2つの方法で C コードのコンパイルをサポートしています。

- コンパイラは、ソースファイルの拡張子が *.c*の場合、または[/Tc](tc-tp-tc-tp-specify-source-file-type.md)または[/tc](tc-tp-tc-tp-specify-source-file-type.md)オプションが指定されている場合に、既定で c コンパイルモードを使用します。 C コンパイラは、既定で C 言語に対する Microsoft 拡張機能を有効にする、C89/C90 コンパイラです。 特定の拡張機能の詳細については、「 [Microsoft extensions For C And C++](microsoft-extensions-to-c-and-cpp.md)」を参照してください。 C コンパイルと **/za**オプションの両方が指定されている場合、c コンパイラは厳密に C89/C90 標準に準拠します。 コンパイラは、microsoft 拡張キーワードを単純な識別子として扱い、他の microsoft 拡張機能を無効にし、C プログラムの[ \_ \_STDC\_ ](../../preprocessor/predefined-macros.md)定義済みマクロを自動的に定義します。

- コンパイラは C++ コンパイルモードで C コードをコンパイルできます。 この動作は、拡張子が *.c*でないソースファイルの既定の動作です。また、 [/tp](tc-tp-tc-tp-specify-source-file-type.md)オプションまたは[/tp](tc-tp-tc-tp-specify-source-file-type.md)オプションが指定されている場合は、この動作が使用されます。 C++ コンパイルモードでは、コンパイラは、C++ 標準に組み込まれている ISO C99 および C11 標準の部分をサポートしています。 ほとんどすべての C コードは、有効な C++ コードでもあります。 いくつかの C キーワードとコードコンストラクターが有効な C++ コードではないか、C++ では異なる解釈がされています。 コンパイラは、このような場合に C++ 標準に従って動作します。 C++ コンパイルモードでは、 **/za**オプションを指定すると、予期しない動作が発生し、推奨されません。

その他のコンパイラオプションは、コンパイラが標準への準拠を保証する方法に影響を与える可能性があります。 標準 C および C++ の特定の動作設定を指定する方法については、「 [/zc](zc-conformance.md)コンパイラオプション」を参照してください。 C++ 標準準拠の設定の詳細については、「 [/permissive-](permissive-standards-conformance.md)コンパイラオプションと[/std](std-specify-language-standard-version.md)コンパイラオプション」を参照してください。

Visual C++ の準拠に関する問題の詳細については、「[非標準動作](../../cpp/nonstandard-behavior.md)」を参照してください。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、[Visual Studio での C++ コンパイラとビルド プロパティの設定](../working-with-project-properties.md)に関するページを参照してください。

1. ナビゲーションウィンドウで、[**構成プロパティ** > ] [**C/c + +** > **言語**] の順に選択します。

1. [**言語拡張機能の無効化**] プロパティを変更します。

### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには

「 <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.DisableLanguageExtensions%2A> 」を参照してください。

## <a name="see-also"></a>関連項目

[コンパイラ オプション](compiler-options.md)<br/>
[/Zc (準拠)](zc-conformance.md)<br/>
[/permissive- (標準への準拠)](permissive-standards-conformance.md)<br/>
[/std (言語の標準バージョンの指定)](std-specify-language-standard-version.md)<br/>

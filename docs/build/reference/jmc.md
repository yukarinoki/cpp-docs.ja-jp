---
title: /JMC (マイ コードのみデバッグ)
ms.date: 08/20/2018
f1_keywords:
- VC.Project.VCCLCompilerTool.SupportJustMyCode
helpviewer_keywords:
- /JMC compiler option [C++]
- Just my code [C++]
- -JMC compiler option [C++]
- User code, debugging
- JMC compiler option [C++]
ms.openlocfilehash: 7b22a754f9f49564cd7f76c7d1989cd562f70874
ms.sourcegitcommit: 31a443c9998cf5cfbaff00fcf815b133f55b2426
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/14/2020
ms.locfileid: "86373880"
---
# <a name="jmc-just-my-code-debugging"></a>/JMC (マイ コードのみデバッグ)

Visual Studio デバッガーでのネイティブ*マイコードのみ*デバッグのコンパイラサポートを指定します。 このオプションは、Visual Studio がシステム、フレームワーク、ライブラリ、およびその他の非ユーザーの呼び出しをステップオーバーし、[呼び出し履歴] ウィンドウでそれらの呼び出しを折りたたむことができるようにするユーザー設定をサポートしています。 **/JMC**コンパイラオプションは、Visual Studio 2017 バージョン15.8 以降で使用できます。

## <a name="syntax"></a>Syntax

> **/JMC** \[ **-** ]

## <a name="remarks"></a>解説

Visual studio の[マイコードのみ](/visualstudio/debugger/just-my-code)設定では、visual studio デバッガーがシステム、フレームワーク、ライブラリ、およびその他の非ユーザーの呼び出しをステップオーバーするかどうかを指定します。 **/JMC**コンパイラオプションは、ネイティブ C++ コードでのマイコードのみデバッグのサポートを有効にします。 **/JMC**が有効になっている場合、コンパイラは、関数プロローグにヘルパー関数の呼び出しを挿入 `__CheckForDebuggerJustMyCode` します。 ヘルパー関数には、Visual Studio デバッガーマイコードのみステップ操作をサポートするフックが用意されています。 Visual Studio デバッガーでマイコードのみを有効にするには、メニューバーで [**ツール**] [オプション] の順に選択し、  >  **Options**[**デバッグ**] [全般] [マイコードのみの有効化] のオプションを設定し  >  **General**  >  **Enable Just My Code**ます。

**/JMC**オプションを使用するには、コードが C ランタイムライブラリ (CRT) にリンクされている必要があります。 CRT は、ヘルパー関数を提供し `__CheckForDebuggerJustMyCode` ます。 プロジェクトが CRT にリンクしていない場合、リンカーエラー **LNK2019: 未解決の外部シンボル __CheckForDebuggerJustMyCode**が表示されることがあります。 このエラーを解決するには、CRT にリンクするか、 **/JMC**オプションを無効にします。

既定では、 **/JMC**コンパイラオプションはオフになっています。 ただし、Visual Studio 2017 バージョン15.8 以降では、ほとんどの Visual Studio プロジェクトテンプレートでこのオプションが有効になっています。 このオプションを明示的に無効にするには、コマンドラインで **/JMC-** オプションを使用します。 Visual Studio で、[プロジェクトプロパティページ] ダイアログボックスを開き、[**構成プロパティ**] [C/c + + 全般] プロパティページの [**サポートマイコードのみデバッグ**] プロパティを [いいえ] に変更し  >  **C/C++**  >  **General** **No**ます。

詳細につい[マイコードのみ](/visualstudio/debugger/just-my-code#BKMK_C___Just_My_Code)ては、「 [visual studio でマイコードのみを使用してユーザーコードのみをデバッグするかどうかを指定](/visualstudio/debugger/just-my-code)する」、および「 [visual Studio での C++ マイコードのみステップ](https://devblogs.microsoft.com/cppblog/announcing-jmc-stepping-in-visual-studio/)実行を発表する Visual C++ チームのブログの投稿」を参照してください。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、[Visual Studio での C++ コンパイラとビルド プロパティの設定](../working-with-project-properties.md)に関するページを参照してください。

1. **[構成プロパティ]**  >  **[C/C++]**  >  **[全般]** プロパティ ページを選択します。

1. **サポートマイコードのみデバッグ**プロパティを変更します。

### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには

- [https://docs.microsoft.com/azure/active-directory/develop/scenario-protected-web-api-overview](<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A> ) をご覧ください。

## <a name="see-also"></a>関連項目

[MSVC コンパイラ オプション](compiler-options.md)<br/>
[MSVC コンパイラのコマンドライン構文](compiler-command-line-syntax.md)<br/>

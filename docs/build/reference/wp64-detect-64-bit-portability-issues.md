---
title: /Wp64 (64 ビット移植性の問題の検出)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCCLWCECompilerTool.Detect64BitPortabilityProblems
- VC.Project.VCCLCompilerTool.Detect64BitPortabilityProblems
- /wp64
helpviewer_keywords:
- 64-bit compiler [C++], detecting portability problems
- /Wp64 compiler option [C++]
- -Wp64 compiler option [C++]
- Wp64 compiler option [C++]
ms.assetid: 331ae5aa-e627-4d03-8f63-dd2c2d76dadd
ms.openlocfilehash: e5c30ac9096094948a83195f5b3990794c421685
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81335882"
---
# <a name="wp64-detect-64-bit-portability-issues"></a>/Wp64 (64 ビット移植性の問題の検出)

このコンパイラ オプションは廃止されました。 Visual Studio 2013 より前の Visual Studio のバージョンでは、このオプションは、 [__w64](../../cpp/w64.md) キーワードでもマークされている型の 64 ビット移植性の問題を検出します。

## <a name="syntax"></a>構文

```
/Wp64
```

## <a name="remarks"></a>解説

既定では、Visual Studio 2013 より前のバージョンの Visual Studio では、32 ビット x86 コードをビルドする MSVC コンパイラと、64 ビット x64 コードをビルドする MSVC コンパイラでは **、/Wp64**コンパイラ オプションはオフになっています。

> [!IMPORTANT]
> [/Wp64](wp64-detect-64-bit-portability-issues.md) コンパイラ オプションと [__w64](../../cpp/w64.md) キーワードは、Visual Studio 2010 および Visual Studio 2012 で非推奨となり、Visual Studio 2013 以降ではサポートされません。 このスイッチを使用するプロジェクトを変換すると、変換中にスイッチは移行されません。 このオプションを Visual Studio 2010 または Visual Studio 2012 で使用するには、プロジェクト プロパティの **[コマンド ライン]** セクションの **[追加オプション]** で、コンパイラ スイッチを入力する必要があります。 コマンド ラインから **/Wp64** コンパイラ オプションを使用すると、コンパイラはコマンド ラインの警告 D9002 を発行します。 64 ビットの移植性の問題を検出するためにこのオプションとキーワードを使用する代わりに、64 ビット プラットフォームを対象とする MSVC コンパイラを使用し[、/W4](compiler-option-warning-level.md)オプションを指定します。 詳細については、「 [64 ビット x64 ターゲットの C++ プロジェクトを構成する](../configuring-programs-for-64-bit-visual-cpp.md)」を参照してください。

次の型の変数は、64 ビット オペレーティング システムで使用されている場合と同様に、32 ビットのオペレーティング システムでテストされます。

- INT

- long

- ポインター (pointer)

64 ビット x64 コードをビルドするコンパイラを使用して定期的にアプリケーションをコンパイルする場合は、64 ビット コンパイラがすべての問題を検出するため、32 ビット コンパイルで **/Wp64**を無効にできます。 Windows 64 ビット オペレーティング システムを対象とする方法の詳細については[、「64 ビット x64 ターゲット用の C++ プロジェクトを構成する](../configuring-programs-for-64-bit-visual-cpp.md)」を参照してください。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。

   詳しくは、「[Visual Studio で C++ コンパイラとビルド プロパティを設定する](../working-with-project-properties.md)」をご覧ください。

1. **[C/C++]** フォルダーをクリックします。

1. **[コマンド ライン]** プロパティ ページをクリックします。

1. **/Wp64** を含めるよう [ **詳細オプション**] ボックスを変更します。

### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには

- 「<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.Detect64BitPortabilityProblems%2A>」を参照してください。

## <a name="see-also"></a>関連項目

[MSVC コンパイラ オプション](compiler-options.md)<br/>
[MSVC コンパイラ コマンド ラインの構文](compiler-command-line-syntax.md)<br/>
[64 ビットの x64 ターゲット用に C++ プロジェクトを構成する](../configuring-programs-for-64-bit-visual-cpp.md)

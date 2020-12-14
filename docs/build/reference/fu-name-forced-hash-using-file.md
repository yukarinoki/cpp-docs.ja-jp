---
description: '詳細については、次を参照してください:/FU (強制 #using ファイルに名前を指定)'
title: '/FU (強制 #using ファイルの名前の指定)'
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCCLCompilerTool.ForcedUsingFiles
- /FU
- VC.Project.VCNMakeTool.ForcedUsingAssemblies
helpviewer_keywords:
- -FU compiler option [C++]
- FU compiler option [C++]
- /FU compiler option [C++]
ms.assetid: 698f8603-457f-435a-baff-5ac9243d6ca1
ms.openlocfilehash: 458369e7ff1322d2d2fa2fb37e8915c5a39c8446
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97200378"
---
# <a name="fu-name-forced-using-file"></a>/FU (強制 #using ファイルの名前の指定)

ソースコード内の [#using ディレクティブ](../../preprocessor/hash-using-directive-cpp.md) にファイル名を渡す代わりに使用できるコンパイラオプション。

## <a name="syntax"></a>構文

> **/FU** *ファイル*

## <a name="arguments"></a>引数

*file*<br/>
このコンパイルで参照するメタデータファイルを指定します。

## <a name="remarks"></a>解説

/FU スイッチには、ファイル名を1つだけ指定できます。 複数のファイルを指定するには、それぞれに/FU を使用します。

C++/CLI を使用していて、 [フレンドアセンブリ](../../dotnet/friend-assemblies-cpp.md) 機能を使用するためにメタデータを参照している場合は、 **/fu** を使用できません。 属性と共にを使用して、コード内でメタデータを参照する必要があり `#using` `[as friend]` ます。 フレンドアセンブリは、Visual C++ コンポーネント拡張機能 C++/cxではサポートされていません。

共通言語ランタイム (CLR) のアセンブリまたはモジュールを作成する方法については、「 [/clr (共通言語ランタイムのコンパイル)](clr-common-language-runtime-compilation.md)」を参照してください。 C++/CX でビルドする方法の詳細については、「 [アプリとライブラリ](../../cppcx/building-apps-and-libraries-c-cx.md)のビルド」を参照してください。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、[Visual Studio での C++ コンパイラとビルド プロパティの設定](../working-with-project-properties.md)に関するページを参照してください。

1. [**構成プロパティ**] [  >  **C/c + +**]  >  **[詳細設定**] プロパティページを選択します。

1. **Force #using** プロパティを変更します。

### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには

- 以下を参照してください。<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.ForcedUsingFiles%2A>

## <a name="see-also"></a>関連項目

[出力ファイル (/F) オプション](output-file-f-options.md)<br/>
[MSVC コンパイラ オプション](compiler-options.md)<br/>
[MSVC Compiler Command-Line 構文](compiler-command-line-syntax.md)

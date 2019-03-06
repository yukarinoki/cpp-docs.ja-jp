---
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
ms.openlocfilehash: 1a035be2080d9fe407799122f804668e0fc3ce76
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/05/2019
ms.locfileid: "57413161"
---
# <a name="fu-name-forced-using-file"></a>/FU (強制 #using ファイルの名前の指定)

代替ファイル名を渡す方法として使用できるコンパイラ オプション[#using ディレクティブ](../../preprocessor/hash-using-directive-cpp.md)でソース コード。

## <a name="syntax"></a>構文

> **/FU** *file*

## <a name="arguments"></a>引数

*file*<br/>
このコンパイルで参照するメタデータ ファイルを指定します。

## <a name="remarks"></a>Remarks

/FU スイッチは 1 つだけのファイル名を取得します。 複数のファイルを指定するには、1 つずつ/FU を使用します。

C + を使用している場合/cli CLI を使用するメタデータを参照していると、[フレンド アセンブリ](../../dotnet/friend-assemblies-cpp.md)機能は使用できません **/FU**します。 使用してコード内のメタデータを参照する必要があります`#using`— と共に、`[as friend]`属性。 Visual C コンポーネント拡張 C + では、フレンド アセンブリはサポートされていない/cli CX します。

アセンブリまたは共通言語ランタイム (CLR) のモジュールを作成する方法については、次を参照してください。 [/clr (共通言語ランタイムのコンパイル)](../../build/reference/clr-common-language-runtime-compilation.md)します。 C + で構築する方法については/cli CX を参照してください[アプリとライブラリのビルド](../../cppcx/building-apps-and-libraries-c-cx.md)します。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境において、このコンパイラ オプションを設定する方法

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「[プロジェクトのプロパティの操作](../../ide/working-with-project-properties.md)」を参照してください。

1. 選択、**構成プロパティ** > **C/C++** > **詳細**プロパティ ページ。

1. 変更、 **Force #using**プロパティ。

### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには

- 以下を参照してください。<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.ForcedUsingFiles%2A>

## <a name="see-also"></a>関連項目

[出力ファイル (/F) オプション](../../build/reference/output-file-f-options.md)<br/>
[コンパイラ オプション](../../build/reference/compiler-options.md)<br/>
[コンパイラ オプションの設定](../../build/reference/setting-compiler-options.md)

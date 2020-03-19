---
title: Visual Studio での Clang-Tidy の使用
description: Visual Studio で Clang-Tidy を使用して Microsoft C++コード分析を行う方法について説明します。
ms.date: 02/19/2020
ms.topic: conceptual
f1_keywords:
- vs.codeanalysis.clangtidy
author: frozenpandaman
ms.author: efessler
ms.openlocfilehash: 3dbe66e9d7117c027c0ec867011189824c59ce31
ms.sourcegitcommit: 21e168731b8fe0eaff18f070cee5d54aa5782c2d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/24/2020
ms.locfileid: "79469897"
---
# <a name="using-clang-tidy-in-visual-studio"></a>Visual Studio での Clang-Tidy の使用

::: moniker range="<=vs-2017"

Clang-Tidy のサポートには、Visual Studio 2019 バージョン16.4 以降が必要です。 ドキュメントを表示するには、ドキュメントバージョンセレクターで [Visual Studio 2019] を選択します。

::: moniker-end

::: moniker range=">=vs-2019"

コード分析では、Clang または MSVC ツールセットを使用するかどうかにかかわらず、MSBuild プロジェクトと CMake プロジェクトの両方に対して[clang-Tidy が](https://clang.llvm.org/extra/clang-tidy/)ネイティブでサポートされます。 Clang-Tidy チェックは、バックグラウンドコード分析の一部として実行できます。 これらは、エディター内の警告 (波線) として表示され、エラー一覧に表示されます。

Clang-Tidy support は、Visual Studio 2019 バージョン16.4 以降で使用できます。 Visual Studio インストーラーでワークロードをC++選択すると、自動的に追加されます。

Clang-Tidy は、MSBuild と CMake の両方で使用できる LLVM/clang-cl ツールセットを使用する場合の既定の分析ツールです。 MSVC ツールセットを使用して、標準のコード分析エクスペリエンスと共に実行したり、置き換えたりするときに構成できます。 Clang-cl ツールセットを使用する場合、Microsoft コード分析は使用できません。

Clang-Tidy が正常にコンパイルされた後に実行されます。 場合によっては、ソースコードエラーを解決して Clang-Tidy の結果を取得する必要があります。

## <a name="msbuild"></a>MSBuild

プロジェクトプロパティウィンドウの [**コード分析** > **全般**] ページで、コード分析とビルドの両方の一部として実行するように clang-Tidy を構成できます。 ツールを構成するオプションは、[Clang-Tidy] サブメニューにあります。

詳細については、「[方法: C/C++プロジェクトのコード分析プロパティを設定する](../code-quality/how-to-set-code-analysis-properties-for-c-cpp-projects.md)」を参照してください。

## <a name="cmake"></a>CMake

CMake プロジェクトでは、`CMakeSettings.json`内で Clang-Tidy チェックを構成できます。 開いたら、CMake プロジェクト設定エディターの右上隅にある [JSON の編集] をクリックします。 次のキーが認識されます。

- `enableMicrosoftCodeAnalysis`: Microsoft コード分析を有効にします
- `enableClangTidyCodeAnalysis`: Clang-Tidy 分析を有効にします
- `clangTidyChecks`: Clang-Tidy 構成。コンマ区切りリストとして指定されています。つまり、有効または無効になっていることを確認します。

"Enable" オプションのいずれも指定されていない場合、Visual Studio は、使用されているプラットフォームツールセットと一致する分析ツールを選択します。

## <a name="warning-display"></a>警告の表示

Clang-Tidy を実行すると、エラー一覧に警告が表示されます。また、コードの関連するセクションの下に、エディターの波線が表示されます。 エラー一覧の [カテゴリ] 列を使用して、Clang-Tidy 警告を並べ替えて整理します。 [**ツール** > **オプション**] の [コード分析の波線を無効にする] 設定を切り替えることによって、エディター内の警告を構成できます。

## <a name="clang-tidy-configuration"></a>Clang-Tidy 構成

Clang-tidy**チェック**オプションを使用して、Visual Studio 内で clang-tidy が実行されるかどうかをチェックするように構成できます。 この入力は、ツールの **--チェック**引数に提供されます。 その他の構成は、カスタム *`.clang-tidy`* ファイルに含めることができます。 詳細については、 [LLVM.org にある Clang-Tidy のドキュメント](https://clang.llvm.org/extra/clang-tidy/)を参照してください。

## <a name="see-also"></a>参照

- [Clang/LLVM の MSBuild プロジェクトのサポート](https://devblogs.microsoft.com/cppblog/clang-llvm-support-for-msbuild-projects/)
- [Clang/LLVM での CMake プロジェクトのサポート](https://devblogs.microsoft.com/cppblog/visual-studio-cmake-support-clang-llvm-cmake-3-14-vcpkg-and-performance-improvements/)

::: moniker-end

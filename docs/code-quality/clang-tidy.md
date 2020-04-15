---
title: ビジュアルスタジオでのクランティディの使用
description: マイクロソフトの C++ コード分析のための Visual Studio で Clang-Tidy を使用する方法。
ms.date: 02/19/2020
ms.topic: conceptual
f1_keywords:
- vs.codeanalysis.clangtidy
author: frozenpandaman
ms.author: efessler
ms.openlocfilehash: ff32f522eaacee67e19aedaa1153b2c68edc98d4
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81355157"
---
# <a name="using-clang-tidy-in-visual-studio"></a>ビジュアルスタジオでのクランティディの使用

::: moniker range="<=vs-2017"

Clang-Tidy のサポートには、Visual Studio 2019 バージョン 16.4 以降が必要です。 このバージョンのドキュメントを参照するには、この記事の Visual Studio**バージョン**セレクター コントロールを Visual Studio 2019 に設定します。 このページの目次の上部に表示されます。

::: moniker-end

::: moniker range=">=vs-2019"

コード分析では、Clang ツールセットと MSVC ツールセットのどちらを使用するかにかかわらず、MSBuild プロジェクトと CMake プロジェクトの両方で[Clang-Tidy](https://clang.llvm.org/extra/clang-tidy/)がネイティブにサポートされています。 Clang-Tidy チェックは、バックグラウンド コード分析の一部として実行できます。 これらはエディタ内の警告(波線)として表示され、エラー一覧に表示されます。

Clang-Tidy サポートは、Visual Studio 2019 バージョン 16.4 以降で利用可能です。 Visual Studio インストーラーで C++ ワークロードを選択すると、自動的に含まれます。

Clang-Tidy は、MSBuild と CMake の両方で使用できる LLVM/clang-cl ツールセットを使用する場合の既定の分析ツールです。 MSVC ツールセットを使用して、標準のコード分析エクスペリエンスと並行して実行したり、置き換えたりするように構成できます。 clang-cl ツールセットを使用している場合、Microsoft コード分析は使用できません。

Clang-Tidy はコンパイルが成功した後に実行されます。 Clang-Tidy の結果を得るためにソース コードエラーを解決する必要がある場合があります。

## <a name="msbuild"></a>MSBuild

Clang-Tidy をコード分析の一部として実行するように構成し、[プロジェクトのプロパティ] ウィンドウの [**コード分析** > **全般**] ページでビルドできます。 ツールを構成するオプションは、Clang-Tidy サブメニューにあります。

詳細については、「[方法 : C/C++ プロジェクトのコード分析プロパティを設定する](../code-quality/how-to-set-code-analysis-properties-for-c-cpp-projects.md)」を参照してください。

## <a name="cmake"></a>CMake

CMake プロジェクトでは、 内で Clang-Tidy`CMakeSettings.json`チェックを構成できます。 開いたら、CMake プロジェクト設定エディタの右上隅にある [JSON の編集] をクリックします。 次のキーが認識されます。

- `enableMicrosoftCodeAnalysis`: マイクロソフトコード分析を有効にします。
- `enableClangTidyCodeAnalysis`: Clang-tidy 分析を有効にします。
- `clangTidyChecks`: Clang-Tidy 構成は、コンマ区切りリストとして指定され、有効または無効になっていることを確認します。

どちらのオプションも指定されていない場合、Visual Studio は使用するプラットフォーム ツールセットに一致する分析ツールを選択します。

## <a name="warning-display"></a>警告表示

Clang-Tidy 実行は、エラー一覧に警告を表示し、コードの関連セクションの下にエディタ内の波線として表示されます。 エラー一覧の [カテゴリ] 列を使用して、Clang-Tidy の警告を並べ替えて整理します。 エディタ内の警告を構成するには、[**ツール** > **オプション]** の [コード分析の波線を無効にする] 設定を切り替えます。

## <a name="clang-tidy-configuration"></a>クラング・ティディ構成

Clang-Tidy チェック オプションを使用して、Visual Studio 内で**実行されるチェック**を構成できます。 この入力は、ツールの **--checks**引数に指定されます。 その他の設定は、カスタム*`.clang-tidy`* ファイルに含めることができます。 詳細については[、clang-Tidy のドキュメントを参照LLVM.org。](https://clang.llvm.org/extra/clang-tidy/)

## <a name="see-also"></a>関連項目

- [MSBuild プロジェクトの Clang/LLVM サポート](https://devblogs.microsoft.com/cppblog/clang-llvm-support-for-msbuild-projects/)
- [CMake プロジェクトの Clang/LLVM サポート](https://devblogs.microsoft.com/cppblog/visual-studio-cmake-support-clang-llvm-cmake-3-14-vcpkg-and-performance-improvements/)

::: moniker-end

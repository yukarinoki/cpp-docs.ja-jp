---
description: '詳細については、「方法: C/c + + プロジェクトのコード分析プロパティを設定する」を参照してください。'
title: '方法: C/C++ プロジェクトのコード分析プロパティを設定する'
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- vs.codeanalysis.propertypages.native
- VC.Project.VCCLCompilerTool.EnablePrefast
- VC.Project.VCFxCopTool.EnablePREfast
- VC.Project.VCFxCopTool.IgnoreGeneratedCode
helpviewer_keywords:
- properties, C/C++ Code Analysis
- properties, Code Analysis
- code analysis properties
- C/C++ code analysis properties
ms.assetid: 7af52097-6d44-4785-9b9f-43b7a7d447d7
ms.openlocfilehash: 590254406242c369da9aff91d006313ed797078f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97151568"
---
# <a name="how-to-set-code-analysis-properties-for-cc-projects"></a>方法: C/C++ プロジェクトのコード分析プロパティを設定する

コード分析ツールがプロジェクトの各構成でコードを分析するために使用する規則を構成できます。 さらに、サードパーティのツールによって生成され、プロジェクトに追加されたコードからの警告を表示しないようにコード分析を指示することもできます。

## <a name="code-analysis-property-page"></a>[コード分析] プロパティページ

[ **コード分析** ] プロパティページには、MSBuild プロジェクトのコード分析の構成設定がすべて含まれています。 **ソリューションエクスプローラー** のプロジェクトの [コード分析] プロパティページを開くには、プロジェクトを右クリックし、[**プロパティ**] をクリックします。 次に、[ **構成プロパティ** ] を展開し、[ **コード分析** ] タブを選択します。

## <a name="project-configuration-and-platform"></a>プロジェクト構成とプラットフォーム

ウィンドウの上部にある [ **構成** リスト] と [ **プラットフォーム** ] の一覧を使用すると、プロジェクトの構成とプラットフォームの組み合わせごとに異なるコード分析設定を適用できます。 たとえば、デバッグビルドのプロジェクトに1つのルールセットを適用し、リリースビルド用に別のセットを適用するようにコード分析を指示することができます。

## <a name="enabling-code-analysis"></a>コード分析の有効化

プロジェクトのコード分析を有効にするには、[ **Microsoft コード分析を有効に** し、 **Clang-Tidy** オプションを有効にする] をオンにして、[ **ビルド時にコード分析を有効** にする] を選択してビルド時に実行するかどうかを構成します。 たとえば、 **構成** リストと組み合わせて、デバッグビルドのコード分析を無効にし、リリースビルドに対して有効にすることができます。

コード分析は、コードの品質を向上させ、一般的な落とし穴を回避できるように設計されています。 そのため、コード分析を無効にするかどうかを慎重に検討してください。 通常は、プロジェクトに適用しない規則セット、個々の規則、または個別のチェックを無効にすることをお勧めします。

## <a name="cmake-configuration"></a>CMake の構成

CMake プロジェクトで、内のキーとキーの値を変更して、 `enableMicrosoftCodeAnalysis` `enableClangTidyCodeAnalysis` `CMakeSettings.json` コード分析を有効または無効にします。 詳細については、「 [Visual Studio での Clang-Tidy の使用](../code-quality/clang-tidy.md) 」を参照してください。

## <a name="see-also"></a>関連項目

- [マネージド コードの品質の分析](/visualstudio/code-quality/code-analysis-for-managed-code-overview)
- [C/c + + のコード分析の警告](../code-quality/code-analysis-for-c-cpp-warnings.md)
- [規則セットを使用して、実行する C++ 規則を指定する](using-rule-sets-to-specify-the-cpp-rules-to-run.md)
- [Clang-Tidy の使用](../code-quality/clang-tidy.md)

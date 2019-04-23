---
title: /PROFILE (パフォーマンス ツール プロファイラー)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCLinkerTool.Profile
helpviewer_keywords:
- -PROFILE linker option
- /PROFILE linker option
ms.assetid: e676baa1-5063-47a3-a357-ba0d1f0d1699
ms.openlocfilehash: 23cbccba9a8ec839252d553cc5cbafd37e66bbf9
ms.sourcegitcommit: 14b292596bc9b9b883a9c58cd3e366b282a1f7b3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2019
ms.locfileid: "60124773"
---
# <a name="profile-performance-tools-profiler"></a>/PROFILE (パフォーマンス ツール プロファイラー)

パフォーマンス ツール プロファイラーで使用できる出力ファイルを作成します。

## <a name="syntax"></a>構文

```
/PROFILE
```

## <a name="remarks"></a>Remarks

/プロファイルでは、次のリンカー オプションは意味します。

- [/OPT:REF](opt-optimizations.md)

- /OPT:NOICF

- [/INCREMENTAL:NO](incremental-link-incrementally.md)

- [/FIXED: いいえ](fixed-fixed-base-address.md)

/プロファイルにより、プログラム イメージの再配置セクションを生成します。  再配置セクションは、プロファイル データを取得する、プログラム イメージを変換するプロファイラーを使用できます。

**/プロファイル**はのみ Enterprise (チームの開発) バージョンでのみ使用できます。  PREfast の詳細については、次を参照してください。 [Code Analysis for C と C++ の概要](/visualstudio/code-quality/code-analysis-for-c-cpp-overview)します。

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのリンカー オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、次を参照してください。 [Visual Studio での設定の C++ コンパイラとビルド プロパティ](../working-with-project-properties.md)します。

1. **[構成プロパティ]** ノードを展開します。

1. 展開、**リンカー**ノード。

1. 選択、**詳細**プロパティ ページ。

1. 変更、**プロファイル**プロパティ。

### <a name="to-set-this-linker-option-programmatically"></a>このリンカーをコードから設定するには

1. 以下を参照してください。<xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.Profile%2A>

### <a name="to-set-this-linker-option-within-visual-studio-cmake-project"></a>Visual Studio の CMake プロジェクト内でこのリンカー オプションを設定するには

**CMake**プロジェクトがない、**プロパティ ページ**、リンカー オプションできますして設定を変更する、CMakeLists.txt します。

1. プロジェクトのルート ディレクトリに、CMakeLists.txt を開きます。

1. 次のコードを追加します。 詳細については、次を参照してください[CMake の参照。](https://cmake.org/cmake/help/v3.0/command/set_target_properties.html)

1. ソリューションをリビルドします。

```
SET_TARGET_PROPERTIES(${PROJECT_NAME} PROPERTIES LINK_FLAGS "/PROFILE")
```

## <a name="see-also"></a>関連項目

[MSVC リンカーのリファレンス](linking.md)<br/>
[MSVC リンカー オプション](linker-options.md)


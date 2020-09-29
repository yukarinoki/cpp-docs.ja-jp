---
title: /PROFILE (パフォーマンス ツール プロファイラー)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCLinkerTool.Profile
helpviewer_keywords:
- -PROFILE linker option
- /PROFILE linker option
ms.assetid: e676baa1-5063-47a3-a357-ba0d1f0d1699
ms.openlocfilehash: 07952c979fd66291b1744521d83e4556f010d297
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/29/2020
ms.locfileid: "91500787"
---
# <a name="profile-performance-tools-profiler"></a>/PROFILE (パフォーマンス ツール プロファイラー)

パフォーマンス ツール プロファイラーで使用できる出力ファイルを作成します。

## <a name="syntax"></a>構文

```
/PROFILE
```

## <a name="remarks"></a>解説

/PROFILE は、次のリンカーオプションを意味します。

- [/OPT: REF](opt-optimizations.md)

- /OPT: NOICF

- [/INCREMENTAL: いいえ](incremental-link-incrementally.md)

- [/FIXED: いいえ](fixed-fixed-base-address.md)

/PROFILE は、リンカーによってプログラムイメージに再配置セクションが生成されるようにします。  再配置セクションを使用すると、プロファイラーはプロファイルデータを取得するようにプログラムイメージを変換できます。

**/Profile** は、Enterprise (チーム開発) バージョンでのみ使用できます。  PREfast の詳細については、「 [C/c + + のコード分析の概要](../../code-quality/code-analysis-for-c-cpp-overview.md)」を参照してください。

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのリンカー オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、[Visual Studio での C++ コンパイラとビルド プロパティの設定](../working-with-project-properties.md)に関するページを参照してください。

1. **[構成プロパティ]** ノードを展開します。

1. **[リンカー]** ノードを展開します。

1. **[詳細]** プロパティ ページを選択します。

1. **プロファイル**プロパティを変更します。

### <a name="to-set-this-linker-option-programmatically"></a>このリンカーをコードから設定するには

1. 以下を参照してください。<xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.Profile%2A>

### <a name="to-set-this-linker-option-within-visual-studio-cmake-project"></a>Visual Studio の CMake プロジェクト内でこのリンカーオプションを設定するには

**Cmake** プロジェクトには **プロパティページ**がありません。リンカーオプションを設定するには、CMakeLists.txt を web します。

1. プロジェクトのルートディレクトリにある CMakeLists.txt を開きます。

1. 次のコードを追加します。 詳細については、「 [Cmake の参照](https://cmake.org/cmake/help/v3.0/command/set_target_properties.html)」を参照してください。

1. ソリューションをリビルドします。

```
SET_TARGET_PROPERTIES(${PROJECT_NAME} PROPERTIES LINK_FLAGS "/PROFILE")
```

## <a name="see-also"></a>参照

[MSVC リンカーのリファレンス](linking.md)<br/>
[MSVC リンカー オプション](linker-options.md)

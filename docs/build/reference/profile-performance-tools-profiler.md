---
title: -PROFILE (パフォーマンス ツール Profiler) |マイクロソフトのドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCLinkerTool.Profile
dev_langs:
- C++
helpviewer_keywords:
- -PROFILE linker option
- /PROFILE linker option
ms.assetid: e676baa1-5063-47a3-a357-ba0d1f0d1699
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 859ea4091502fa6c339a809a5b9e439c91462bd7
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2018
ms.locfileid: "45707767"
---
# <a name="profile-performance-tools-profiler"></a>/PROFILE (パフォーマンス ツール プロファイラー)

パフォーマンス ツール プロファイラーで使用できる出力ファイルを作成します。

## <a name="syntax"></a>構文

```
/PROFILE
```

## <a name="remarks"></a>Remarks

/プロファイルでは、次のリンカー オプションは意味します。

- [/OPT: REF](../../build/reference/opt-optimizations.md)

- /OPT: NOICF

- [/INCREMENTAL: いいえ](../../build/reference/incremental-link-incrementally.md)

- [/FIXED: いいえ](../../build/reference/fixed-fixed-base-address.md)

/プロファイルにより、プログラム イメージの再配置セクションを生成します。  再配置セクションは、プロファイル データを取得する、プログラム イメージを変換するプロファイラーを使用できます。

**/プロファイル**はのみ Enterprise (チームの開発) バージョンでのみ使用できます。  PREfast の詳細については、次を参照してください。 [Code Analysis for C と C++ の概要](/visualstudio/code-quality/code-analysis-for-c-cpp-overview)します。

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのリンカー オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「[プロジェクトのプロパティの操作](../../ide/working-with-project-properties.md)」を参照してください。

1. **[構成プロパティ]** ノードを展開します。

1. 展開、**リンカー**ノード。

1. 選択、**詳細**プロパティ ページ。

1. 変更、**プロファイル**プロパティ。

### <a name="to-set-this-linker-option-programmatically"></a>このリンカーをコードから設定するには

1. 以下を参照してください。<xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.Profile%2A>

## <a name="see-also"></a>関連項目

[リンカー オプションの設定](../../build/reference/setting-linker-options.md)<br/>
[リンカー オプション](../../build/reference/linker-options.md)
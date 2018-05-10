---
title: プロファイル (パフォーマンス ツール プロファイラー) |Microsoft ドキュメント
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
ms.openlocfilehash: 15379914b4c4852e3065d1abc03c2ce1b17fb044
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="profile-performance-tools-profiler"></a>/PROFILE (パフォーマンス ツール プロファイラー)
パフォーマンス ツール プロファイラーで使用できる出力ファイルを作成します。  
  
## <a name="syntax"></a>構文  
  
```  
/PROFILE  
```  
  
## <a name="remarks"></a>コメント  
 /プロファイルは、次のリンカー オプションを意味します。  
  
-   [/OPT: REF](../../build/reference/opt-optimizations.md)  
  
-   /OPT: NOICF  
  
-   [/INCREMENTAL: いいえ](../../build/reference/incremental-link-incrementally.md)  
  
-   [/FIXED: いいえ](../../build/reference/fixed-fixed-base-address.md)  
  
 /PROFILE リンカーに、プログラム イメージの再配置セクションを生成します。  再配置セクションでは、プロファイル データを取得する、プログラム イメージを変換するプロファイラーを許可します。  
  
 **/プロファイル**はのみ Enterprise (チーム開発) バージョンでのみ使用できます。  PREfast の詳細については、次を参照してください。 [C と C++ の概要のコード分析](/visualstudio/code-quality/code-analysis-for-c-cpp-overview)です。  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのリンカー オプションを設定するには  
  
1.  プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「[のプロジェクト プロパティの操作](../../ide/working-with-project-properties.md)です。  
  
2.  展開して、**構成プロパティ**ノード。  
  
3.  展開して、**リンカー**ノード。  
  
4.  選択、**詳細**プロパティ ページ。  
  
5.  変更、**プロファイル**プロパティです。  
  
### <a name="to-set-this-linker-option-programmatically"></a>このリンカーをコードから設定するには  
  
1.  「<xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.Profile%2A>」を参照してください。  
  
## <a name="see-also"></a>関連項目  
 [リンカー オプションの設定](../../build/reference/setting-linker-options.md)   
 [リンカー オプション](../../build/reference/linker-options.md)
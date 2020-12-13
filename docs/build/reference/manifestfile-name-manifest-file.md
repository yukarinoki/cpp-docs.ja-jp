---
description: 詳細情報:/manifestfile (マニフェストファイルに名前を付けます)
title: /MANIFESTFILE (マニフェスト ファイルに名前を付ける)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCLinkerTool.ManifestFile
helpviewer_keywords:
- MANIFESTFILE linker option
- -MANIFESTFILE linker option
- /MANIFESTFILE linker option
ms.assetid: befa5ab2-a9cf-4c9b-969a-e7b4a930f08d
ms.openlocfilehash: a0d3a4ba1d17c4aa8c97cb09cc768e614e46c864
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97138022"
---
# <a name="manifestfile-name-manifest-file"></a>/MANIFESTFILE (マニフェスト ファイルに名前を付ける)

```
/MANIFESTFILE:filename
```

## <a name="remarks"></a>解説

/Manifestfile を使用すると、マニフェストファイルの既定の名前を変更できます。  マニフェストファイルの既定の名前は、ファイル名に .manifest が付加されています。

/ [MANIFEST](manifest-create-side-by-side-assembly-manifest.md)にリンクしていない場合、/manifestfile は効果がありません。

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのリンカー オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、[Visual Studio での C++ コンパイラとビルド プロパティの設定](../working-with-project-properties.md)に関するページを参照してください。

1. **[構成プロパティ]** ノードを展開します。

1. **[リンカー]** ノードを展開します。

1. [ **マニフェストファイル** ] プロパティページを選択します。

1. **マニフェストファイル** のプロパティを変更します。

### <a name="to-set-this-linker-option-programmatically"></a>このリンカーをコードから設定するには

1. 以下を参照してください。<xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.ManifestFile%2A>

## <a name="see-also"></a>関連項目

[MSVC リンカーのリファレンス](linking.md)<br/>
[MSVC リンカー オプション](linker-options.md)

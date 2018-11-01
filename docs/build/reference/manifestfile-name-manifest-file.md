---
title: /MANIFESTFILE (マニフェスト ファイルに名前を付ける)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCLinkerTool.ManifestFile
helpviewer_keywords:
- MANIFESTFILE linker option
- -MANIFESTFILE linker option
- /MANIFESTFILE linker option
ms.assetid: befa5ab2-a9cf-4c9b-969a-e7b4a930f08d
ms.openlocfilehash: 9839665c3d74fd9d60afd21a825ffbdb752c7b00
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50656152"
---
# <a name="manifestfile-name-manifest-file"></a>/MANIFESTFILE (マニフェスト ファイルに名前を付ける)

```
/MANIFESTFILE:filename
```

## <a name="remarks"></a>Remarks

/MANIFESTFILE を使用して、マニフェスト ファイルの既定の名前を変更できます。  マニフェスト ファイルの既定の名前は、ファイル名に .manifest です。

/MANIFESTFILE 効果はありませんとしてもリンクしない場合[/manifest](../../build/reference/manifest-create-side-by-side-assembly-manifest.md)します。

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのリンカー オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「[プロジェクトのプロパティの操作](../../ide/working-with-project-properties.md)」を参照してください。

1. **[構成プロパティ]** ノードを展開します。

1. 展開、**リンカー**ノード。

1. 選択、**マニフェスト ファイル**プロパティ ページ。

1. 変更、**マニフェスト ファイル**プロパティ。

### <a name="to-set-this-linker-option-programmatically"></a>このリンカーをコードから設定するには

1. 以下を参照してください。<xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.ManifestFile%2A>

## <a name="see-also"></a>関連項目

[リンカー オプションの設定](../../build/reference/setting-linker-options.md)<br/>
[リンカー オプション](../../build/reference/linker-options.md)
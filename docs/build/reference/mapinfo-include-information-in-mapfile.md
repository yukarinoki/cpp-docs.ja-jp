---
description: 詳細情報:/mapinfo (Mapfile に情報を含める)
title: /MAPINFO (マップ ファイルに含める情報)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCLinkerTool.MapLines
- VC.Project.VCLinkerTool.MapInfoFixups
- VC.Project.VCLinkerTool.MapExports
- /mapinfo
helpviewer_keywords:
- /MAPINFO linker option
- MAPINFO linker option
- -MAPINFO linker option
ms.assetid: 533d2bce-f9b7-4fea-ae1c-0b4864c9d10b
ms.openlocfilehash: 5cf785182bd91923c3398d542d7e60d9afdb4a4e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97137905"
---
# <a name="mapinfo-include-information-in-mapfile"></a>/MAPINFO (マップ ファイルに含める情報)

```
/MAPINFO:EXPORTS
```

## <a name="remarks"></a>解説

/Mapinfo オプションは、指定された情報を mapfile に含めるようにリンカーに指示します。これは、 [/map](map-generate-mapfile.md) オプションを指定した場合に作成されます。  エクスポートは、エクスポートされた関数を含めるようにリンカーに指示します。

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのリンカー オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、[Visual Studio での C++ コンパイラとビルド プロパティの設定](../working-with-project-properties.md)に関するページを参照してください。

1. **[リンカー]** フォルダーをクリックします。

1. [ **デバッグ** ] プロパティページをクリックします。

1. **マップのエクスポート** のプロパティを変更します。

### <a name="to-set-this-linker-option-programmatically"></a>このリンカーをコードから設定するには

- 以下を参照してください。<xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.MapExports%2A>

## <a name="see-also"></a>関連項目

[MSVC リンカーのリファレンス](linking.md)<br/>
[MSVC リンカー オプション](linker-options.md)

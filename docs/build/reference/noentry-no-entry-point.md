---
title: /NOENTRY (エントリ ポイントなし)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCLinkerTool.ResourceOnlyDLL
- /noentry
helpviewer_keywords:
- entry points [C++], linker specifying
- -NOENTRY linker option
- resource-only DLLs [C++], creating
- NOENTRY linker option
- /NOENTRY linker option [C++]
- DLLs [C++], creating
ms.assetid: 0214dd41-35ad-43ab-b892-e636e038621a
ms.openlocfilehash: c750fd94e21eec39a25acf216a452faaa277bf7c
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2019
ms.locfileid: "57811453"
---
# <a name="noentry-no-entry-point"></a>/NOENTRY (エントリ ポイントなし)

```
/NOENTRY
```

## <a name="remarks"></a>Remarks

/NOENTRY オプションは、実行可能コードが含まれていない、リソースだけの DLL を作成するために必要です。 詳細については、[Resource-Only DLL を作成する](../creating-a-resource-only-dll.md)を参照してください。

このオプションを使用すると、`_main` 関数への参照が DLL ファイルにリンクされなくなります。

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのリンカー オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、[Visual Studio での設定の C++ コンパイラとビルド プロパティ](../working-with-project-properties.md)を参照してください。

1. 選択、**リンカー**フォルダー。

1. 選択、**詳細**プロパティ ページ。

1. 変更、**エントリ ポイントなし**プロパティ。

### <a name="to-set-this-linker-option-programmatically"></a>このリンカーをコードから設定するには

1. 以下を参照してください。<xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.ResourceOnlyDLL%2A>

## <a name="see-also"></a>関連項目

[リソースのみの DLL の作成](../creating-a-resource-only-dll.md)<br/>
[MSVC リンカーの参照](linking.md)<br/>
[MSVC リンカー オプション](linker-options.md)

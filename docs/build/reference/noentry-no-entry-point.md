---
title: -NOENTRY (エントリ ポイントなし) |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCLinkerTool.ResourceOnlyDLL
- /noentry
dev_langs:
- C++
helpviewer_keywords:
- entry points [C++], linker specifying
- -NOENTRY linker option
- resource-only DLLs [C++], creating
- NOENTRY linker option
- /NOENTRY linker option [C++]
- DLLs [C++], creating
ms.assetid: 0214dd41-35ad-43ab-b892-e636e038621a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: bd90cb7824050e9bd0110e75f7120c4f004b8b47
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2018
ms.locfileid: "45713467"
---
# <a name="noentry-no-entry-point"></a>/NOENTRY (エントリ ポイントなし)

```
/NOENTRY
```

## <a name="remarks"></a>Remarks

/NOENTRY オプションは、実行可能コードが含まれていない、リソースだけの DLL を作成するために必要です。 詳細については、次を参照してください。 [Resource-Only DLL を作成する](../../build/creating-a-resource-only-dll.md)します。

このオプションを使用すると、`_main` 関数への参照が DLL ファイルにリンクされなくなります。

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのリンカー オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、次を参照してください。 [Visual c プロジェクトのプロパティの設定](../../ide/working-with-project-properties.md)します。

1. 選択、**リンカー**フォルダー。

1. 選択、**詳細**プロパティ ページ。

1. 変更、**エントリ ポイントなし**プロパティ。

### <a name="to-set-this-linker-option-programmatically"></a>このリンカーをコードから設定するには

1. 以下を参照してください。<xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.ResourceOnlyDLL%2A>

## <a name="see-also"></a>関連項目

[リソースのみの DLL の作成](../../build/creating-a-resource-only-dll.md)<br/>
[リンカー オプションの設定](../../build/reference/setting-linker-options.md)<br/>
[リンカー オプション](../../build/reference/linker-options.md)
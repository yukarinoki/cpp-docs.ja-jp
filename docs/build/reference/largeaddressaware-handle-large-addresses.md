---
description: 詳細については、次を参照してください:/LARGEADDRESSAWARE (サイズの大きいアドレスを処理)
title: /LARGEADDRESSAWARE (大きいアドレスの処理)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCLinkerTool.LargeAddressAware
- /largeaddressaware
helpviewer_keywords:
- LARGEADDRESSAWARE linker option
- -LARGEADDRESSAWARE linker option
- /LARGEADDRESSAWARE linker option
ms.assetid: a29756c8-e893-47a9-9750-1f0d25359385
ms.openlocfilehash: 72b2ba20b2ea2b91ecd234497c433bcdd9e9ee42
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97199572"
---
# <a name="largeaddressaware-handle-large-addresses"></a>/LARGEADDRESSAWARE (大きいアドレスの処理)

```
/LARGEADDRESSAWARE[:NO]
```

## <a name="remarks"></a>解説

/LARGEADDRESSAWARE オプションは、アプリケーションが 2 gb を超えるアドレスを処理できることをリンカーに指示します。 64ビットコンパイラでは、このオプションは既定で有効になっています。 32ビットコンパイラでは、リンカー行で/LARGEADDRESSAWARE が指定されていない場合、/LARGEADDRESSAWARE: NO が有効になります。

アプリケーションが/LARGEADDRESSAWARE とリンクされている場合、その効果についての情報が [表示され](headers.md) ます。

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのリンカー オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、[Visual Studio での C++ コンパイラとビルド プロパティの設定](../working-with-project-properties.md)に関するページを参照してください。

1. **[リンカー]** フォルダーをクリックします。

1. [ **システム** ] プロパティページをクリックします。

1. [ **Large Addresses を有効にする** ] プロパティを変更します。

### <a name="to-set-this-linker-option-programmatically"></a>このリンカーをコードから設定するには

- 以下を参照してください。<xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.LargeAddressAware%2A>

## <a name="see-also"></a>関連項目

[MSVC リンカーのリファレンス](linking.md)<br/>
[MSVC リンカー オプション](linker-options.md)

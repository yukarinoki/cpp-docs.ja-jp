---
description: 詳細情報:/swaprun (リンカー出力をスワップファイルに読み込む)
title: /SWAPRUN (リンカー出力をスワップ ファイルに読み込む)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCLinkerTool.SwapRunFromNet
- /swaprun
- VC.Project.VCLinkerTool.SwapRunFromCD
helpviewer_keywords:
- -SWAPRUN linker option
- files [C++], LINK
- LINK tool [C++], output
- linker [C++], copying output to swap file
- swap file for linker output
- output files, linker
- /SWAPRUN linker option
- SWAPRUN linker option
ms.assetid: 4a1e7f46-4399-4161-8dfc-d6a71beaf683
ms.openlocfilehash: f62d5e32432a2c738b7782c0fbf0cd4fd76a7f9a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97230212"
---
# <a name="swaprun-load-linker-output-to-swap-file"></a>/SWAPRUN (リンカー出力をスワップ ファイルに読み込む)

```
/SWAPRUN:{NET|CD}
```

## <a name="remarks"></a>解説

/Swaprun オプションは、最初にリンカー出力をスワップファイルにコピーしてから、そこからイメージを実行するようにオペレーティングシステムに指示します。 これは、Windows NT 4.0 (およびそれ以降) の機能です。

NET が指定されている場合、オペレーティングシステムはまずネットワークからバイナリイメージをスワップファイルにコピーし、そこから読み込みます。 このオプションは、ネットワーク上でアプリケーションを実行する場合に便利です。 CD を指定すると、オペレーティングシステムはリムーバブルディスク上のイメージをページファイルにコピーして読み込みます。

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのリンカー オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、[Visual Studio での C++ コンパイラとビルド プロパティの設定](../working-with-project-properties.md)に関するページを参照してください。

1. **[リンカー]** フォルダーをクリックします。

1. [ **システム** ] プロパティページをクリックします。

1. 次のいずれかのプロパティを変更します。

   - **CD からスワップ実行**

   - **ネットワークからスワップ実行**

### <a name="to-set-this-linker-option-programmatically"></a>このリンカーをコードから設定するには

1. <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.SwapRunFromCD%2A> プロパティおよび <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.SwapRunFromNet%2A> プロパティを参照してください。

## <a name="see-also"></a>関連項目

[MSVC リンカーのリファレンス](linking.md)<br/>
[MSVC リンカー オプション](linker-options.md)

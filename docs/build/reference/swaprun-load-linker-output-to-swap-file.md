---
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
ms.openlocfilehash: bd0b3a46f52ec9b5a292e2f45671523d8c5cdf5e
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2019
ms.locfileid: "57817492"
---
# <a name="swaprun-load-linker-output-to-swap-file"></a>/SWAPRUN (リンカー出力をスワップ ファイルに読み込む)

```
/SWAPRUN:{NET|CD}
```

## <a name="remarks"></a>Remarks

/SWAPRUN オプションは、リンカー出力をスワップ ファイル、およびそこからイメージを実行しを最初のコピーをオペレーティング システムに指示します。 これは、Windows NT 4.0 (以降) の機能です。

NET が指定されている場合、オペレーティング システムは最初バイナリ イメージをネットワークからスワップ ファイルをコピーし、そこから読み込んでいます。 このオプションは、ネットワーク経由でアプリケーションを実行している場合に便利です。 CD を指定すると、オペレーティング システムは、リムーバブル ディスク上のイメージをページファイルにコピーしから読み込みます。

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのリンカー オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、[Visual Studio での設定の C++ コンパイラとビルド プロパティ](../working-with-project-properties.md)を参照してください。

1. をクリックして、**リンカー**フォルダー。

1. をクリックして、**システム**プロパティ ページ。

1. 次のいずれかのプロパティを変更します。

   - **CD からスワップ実行**

   - **ネットワークからスワップ実行**

### <a name="to-set-this-linker-option-programmatically"></a>このリンカーをコードから設定するには

1. <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.SwapRunFromCD%2A> プロパティおよび <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.SwapRunFromNet%2A> プロパティを参照してください。

## <a name="see-also"></a>関連項目

[MSVC リンカーの参照](linking.md)<br/>
[MSVC リンカー オプション](linker-options.md)

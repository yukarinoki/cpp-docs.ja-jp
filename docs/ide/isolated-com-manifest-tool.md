---
title: マニフェスト ツールの分離された COM プロパティ (Visual C++)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCManifestTool.RegistrarScriptFile
- VC.Project.VCManifestTool.ComponentFileName
- VC.Project.VCManifestTool.TypeLibraryFile
- VC.Project.VCManifestTool.ReplacementsFile
ms.assetid: 457582b8-cfde-49c0-92e3-3a6b9e8c08eb
ms.openlocfilehash: 9eea3b2765bad6bd08cc9ee91a801e2b891511e5
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50546522"
---
# <a name="isolated-com-manifest-tool-configuration-properties-ltprojectnamegt-property-pages-dialog-box"></a>[分離された COM] ([&lt;プロジェクト名&gt; プロパティ ページ] ダイアログ ボックス - [構成プロパティ] - [マニフェスト ツール])

このダイアログ ボックスを使用して、[Mt.exe](https://msdn.microsoft.com/library/aa375649) の**分離された COM** オプションを指定します。

このプロパティ ページ ダイアログ ボックスにアクセスするには、自分のプロジェクトまたはプロパティ シートのプロパティ ページを開きます。 **[共通プロパティ]** の下で **[マニフェスト ツール]** ノードを展開して、**[分離された COM]** を選択します。

## <a name="task-list"></a>タスク一覧

- [方法 : COM コンポーネントを使用する分離アプリケーションをビルドする](../build/how-to-build-isolated-applications-to-consume-com-components.md)

## <a name="uielement-list"></a>UIElement の一覧

- **タイプ ライブラリ ファイル**

   /tlb オプションを使用し、マニフェスト ツールによってマニフェスト ファイルの生成に利用されるタイプ ライブラリ ファイル (.tlb ファイル) の名前を指定します。

- **レジスタ スクリプト ファイル**

   /rgs オプションを使用し、マニフェスト ツールによってマニフェスト ファイルの生成に利用されるレジスタ スクリプト ファイル (.rgs ファイル) の名前を指定します。

- **コンポーネント ファイル名**

   /dll オプションを使用し、マニフェスト ツールによって生成されるリソースの名前を指定します。 **タイプ ライブラリ ファイル**か**レジスタ スクリプト ファイル**の値が指定されるとき、このプロパティの値を入力する必要があります。

- **置換ファイル**

   /replacements オプションを使用し、.rgs ファイルの置換可能文字列の値が含まれるファイルの完全パスを指定します。

## <a name="see-also"></a>参照

[分離アプリケーション](/windows/desktop/SbsCs/isolated-applications)<br>
[ClickOnce Application Manifest](/visualstudio/deployment/clickonce-application-manifest)<br>
[[マニフェスト ツール] プロパティ ページ](../ide/manifest-tool-property-pages.md)<br>
[プロジェクトのプロパティの操作](../ide/working-with-project-properties.md)
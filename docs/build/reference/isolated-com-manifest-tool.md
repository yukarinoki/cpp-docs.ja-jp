---
title: マニフェスト ツールの COM プロパティの分離
ms.date: 12/10/2018
f1_keywords:
- VC.Project.VCManifestTool.RegistrarScriptFile
- VC.Project.VCManifestTool.ComponentFileName
- VC.Project.VCManifestTool.TypeLibraryFile
- VC.Project.VCManifestTool.ReplacementsFile
ms.assetid: 457582b8-cfde-49c0-92e3-3a6b9e8c08eb
ms.openlocfilehash: 2fda169ecf304373d27d699bf313bde124dc399f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62269714"
---
# <a name="isolated-com-manifest-tool-configuration-properties-ltprojectnamegt-property-pages-dialog-box"></a>[分離された COM] ([&lt;プロジェクト名&gt; プロパティ ページ] ダイアログ ボックス - [構成プロパティ] - [マニフェスト ツール])

このダイアログ ボックスを使用して、[Mt.exe](https://msdn.microsoft.com/library/aa375649) の**分離された COM** オプションを指定します。

このプロパティ ページ ダイアログ ボックスにアクセスするには、自分のプロジェクトまたはプロパティ シートのプロパティ ページを開きます。 **[共通プロパティ]** の下で **[マニフェスト ツール]** ノードを展開して、**[分離された COM]** を選択します。

## <a name="task-list"></a>タスク一覧

- [方法: COM コンポーネントを使用する分離アプリケーションをビルドする](../how-to-build-isolated-applications-to-consume-com-components.md)

## <a name="uielement-list"></a>UIElement の一覧

- **タイプ ライブラリ ファイル**

   /tlb オプションを使用し、マニフェスト ツールによってマニフェスト ファイルの生成に利用されるタイプ ライブラリ ファイル (.tlb ファイル) の名前を指定します。

- **レジスタ スクリプト ファイル**

   /rgs オプションを使用し、マニフェスト ツールによってマニフェスト ファイルの生成に利用されるレジスタ スクリプト ファイル (.rgs ファイル) の名前を指定します。

- **コンポーネント ファイル名**

   /dll オプションを使用し、マニフェスト ツールによって生成されるリソースの名前を指定します。 **タイプ ライブラリ ファイル**か**レジスタ スクリプト ファイル**の値が指定されるとき、このプロパティの値を入力する必要があります。

- **置換ファイル**

   /replacements オプションを使用し、.rgs ファイルの置換可能文字列の値が含まれるファイルの完全パスを指定します。

## <a name="see-also"></a>関連項目

[分離アプリケーション](/windows/desktop/SbsCs/isolated-applications)<br>
[ClickOnce Application Manifest](/visualstudio/deployment/clickonce-application-manifest)<br>
[[マニフェスト ツール] プロパティ ページ](manifest-tool-property-pages.md)<br>
[Visual Studio で C++ コンパイラとビルド プロパティを設定する](../working-with-project-properties.md)

---
title: マニフェスト ツールの分離された COM プロパティ (Visual C++) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- VC.Project.VCManifestTool.RegistrarScriptFile
- VC.Project.VCManifestTool.ComponentFileName
- VC.Project.VCManifestTool.TypeLibraryFile
- VC.Project.VCManifestTool.ReplacementsFile
dev_langs:
- C++
ms.assetid: 457582b8-cfde-49c0-92e3-3a6b9e8c08eb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: cdb472ce082809a48dd3e42afd4481149eff3a28
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46407558"
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
[ClickOnce アプリケーション マニフェスト](/visualstudio/deployment/clickonce-application-manifest)<br>
[[マニフェスト ツール] プロパティ ページ](../ide/manifest-tool-property-pages.md)<br>
[プロジェクトのプロパティの操作](../ide/working-with-project-properties.md)
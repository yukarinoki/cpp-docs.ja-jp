---
title: '[詳細] ([&lt;プロジェクト名&gt; プロパティ ページ] ダイアログ ボックス - [構成プロパティ] - [マニフェスト ツール]) | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- VC.Project.VCManifestTool.KeyFile
- VC.Project.VCManifestTool.UpdateFileHashes
- VC.Project.VCManifestTool.UpdateFileHashesSearchPath
- VC.Project.VCManifestTool.ValidateSignature
- VC.Project.VCManifestTool.KeyContainer
dev_langs:
- C++
ms.assetid: 3d587366-05ea-4956-a978-313069660735
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1e44ba6065658c085777ada39f75bd5fa1cdc2fb
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46382948"
---
# <a name="advanced-manifest-tool-configuration-properties-ltprojectnamegt-property-pages-dialog-box"></a>[詳細] ([&lt;プロジェクト名&gt; プロパティ ページ] ダイアログ ボックス - [構成プロパティ] - [マニフェスト ツール])

このダイアログ ボックスを使用して、[Mt.exe](https://msdn.microsoft.com/library/aa375649) の詳細オプションを指定します。

このプロパティ ページ ダイアログ ボックスにアクセスするには、自分のプロジェクトまたはプロパティ シートのプロパティ ページを開きます。 **[構成プロパティ]** の下で **[マニフェスト ツール]** ノードを展開して、**[詳細]** を選択します。

## <a name="uielement-list"></a>UIElement の一覧

- **ファイル ハッシュの更新**

   /hashupdate オプションを使用して、マニフェスト ツールによって `<file>` 要素で指定されたファイルのハッシュを計算し、計算された値でハッシュ属性を更新することを指定します。

- **ファイル ハッシュの更新の検索パス**

   `<file>` 要素で参照されるファイルの検索パスを指定します。 このオプションでは、/hashupdate オプションも使用します。

## <a name="see-also"></a>参照

[\<file> 要素](/visualstudio/deployment/file-element-clickonce-application)<br>
[ClickOnce アプリケーション マニフェスト](/visualstudio/deployment/clickonce-application-manifest)<br>
[[マニフェスト ツール] プロパティ ページ](../ide/manifest-tool-property-pages.md)<br>
[プロジェクトのプロパティの操作](../ide/working-with-project-properties.md)
---
title: 詳細、マニフェストのツール構成プロパティ、&lt;プロジェクト名 > プロパティ ページ ダイアログ ボックス
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCManifestTool.KeyFile
- VC.Project.VCManifestTool.UpdateFileHashes
- VC.Project.VCManifestTool.UpdateFileHashesSearchPath
- VC.Project.VCManifestTool.ValidateSignature
- VC.Project.VCManifestTool.KeyContainer
ms.assetid: 3d587366-05ea-4956-a978-313069660735
ms.openlocfilehash: a20e474deb69099c53ad656dda5406e7161a1695
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62295139"
---
# <a name="advanced-manifest-tool-configuration-properties-ltprojectnamegt-property-pages-dialog-box"></a>[詳細] ([&lt;プロジェクト名&gt; プロパティ ページ] ダイアログ ボックス - [構成プロパティ] - [マニフェスト ツール])

このダイアログ ボックスを使用して、[Mt.exe](https://msdn.microsoft.com/library/aa375649) の詳細オプションを指定します。

このプロパティ ページ ダイアログ ボックスにアクセスするには、自分のプロジェクトまたはプロパティ シートのプロパティ ページを開きます。 **[構成プロパティ]** の下で **[マニフェスト ツール]** ノードを展開して、**[詳細]** を選択します。

## <a name="uielement-list"></a>UIElement の一覧

- **ファイル ハッシュの更新**

   /hashupdate オプションを使用して、マニフェスト ツールによって `<file>` 要素で指定されたファイルのハッシュを計算し、計算された値でハッシュ属性を更新することを指定します。

- **ファイル ハッシュの更新の検索パス**

   `<file>` 要素で参照されるファイルの検索パスを指定します。 このオプションでは、/hashupdate オプションも使用します。

## <a name="see-also"></a>関連項目

[\<file> 要素](/visualstudio/deployment/file-element-clickonce-application)<br>
[ClickOnce Application Manifest](/visualstudio/deployment/clickonce-application-manifest)<br>
[[マニフェスト ツール] プロパティ ページ](manifest-tool-property-pages.md)<br>
[Visual Studio で C++ コンパイラとビルド プロパティを設定する](../working-with-project-properties.md)

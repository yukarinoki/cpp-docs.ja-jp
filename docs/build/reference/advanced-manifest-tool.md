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
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2019
ms.locfileid: "57827168"
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
[C++ コンパイラを設定し、Visual Studio でのプロパティのビルド](../working-with-project-properties.md)

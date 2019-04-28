---
title: マニフェスト ツールの C++ の入力と出力プロパティ
ms.date: 08/27/2018
f1_keywords:
- VC.Project.VCManifestTool.OutputManifestFile
- VC.Project.VCManifestTool.InputResourceManifests
- VC.Project.VCManifestTool.EmbedManifest
- VC.Project.VCManifestTool.AdditionalManifestFiles
- VC.Project.VCManifestTool.DependencyInformationFile
- VC.Project.VCManifestTool.OutputResourceManifest
- VC.Project.VCManifestTool.GenerateCatalogFiles
ms.assetid: a8bb20f6-7ace-45ca-bab0-b4f4a5caf170
ms.openlocfilehash: 1731665ffa6117896490115028b4744e195beae2
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62291056"
---
# <a name="input-and-output-manifest-tool-configuration-properties-ltprojectnamegt-property-pages-dialog-box"></a>[入力と出力] ([&lt;プロジェクト名&gt; プロパティ ページ] ダイアログ ボックス - [構成プロパティ] - [マニフェスト ツール])

このダイアログ ボックスを使用して、[Mt.exe](/windows/desktop/SbsCs/mt-exe) の入出力オプションを指定します。

このプロパティ ページ ダイアログ ボックスにアクセスするには、自分のプロジェクトまたはプロパティ シートのプロパティ ページを開きます。 **[構成プロパティ]** の下で **[マニフェスト ツール]** ノードを展開して、**[入力と出力]** を選択します。

## <a name="uielement-list"></a>UIElement の一覧

**追加のマニフェスト ファイル**<br/>
**/manifest** オプションを使用して、マニフェスト ツールで処理またはマージされる追加のマニフェスト ファイルの完全パスを指定します。 完全パスはセミコロンで区切ります。

**入力リソース マニフェスト**<br/>
**/inputresource** オプションを使用して、マニフェスト ツールに入力される RT_MANIFEST 型のリソースの完全パスを指定します。 パスの後には、特定のリソース ID を続けることができます。 例:

`dll_with_manifest.dll;#1`

リソース ID は省略可能であり、既定は winuser.h で CREATEPROCESS_MANIFEST_RESOURCE_ID に設定されています。

**埋め込みマニフェスト**<br/>
- **[はい]** を指定すると、プロジェクト システムによって、アプリケーション マニフェスト ファイルがアセンブリに埋め込まれます。

- **[いいえ]** を指定すると、プロジェクト システムによって、アプリケーション マニフェスト ファイルがスタンドアロン ファイルとして作成されます。

**出力マニフェスト ファイル**<br/>
出力マニフェスト ファイルの名前を指定します。 マニフェスト ツールで操作されるマニフェスト ファイルが 1 つだけの場合、このプロパティは省略できます。

**マニフェスト リソース ファイル**<br/>
マニフェストをプロジェクト出力に埋め込むために使用する出力リソース ファイルを指定します。

**カタログ ファイルの生成**<br/>
**/makecdfs** オプションを使用して、カタログを作成するために使用されるカタログ定義ファイル (.cdf ファイル) をマニフェスト ツールで生成するように指定します。

**ManagedAssembly からのマニフェストの生成**<br/>
マネージド アセンブリからマニフェストを生成します  (**-managedassemblyname:**<em>file</em>)。

**依存要素の抑制**<br/>
**-managedassembly** オプションと共に使用します。 このタグは、最終的なマニフェストでの依存要素の生成を抑制します。

**カタログ タグの生成**<br/>
**-managedassembly** オプションと共に使用します。 このタグにより、カテゴリのタグが生成されます。

**DPI 認識の有効化**<br/>
アプリケーションが DPI 対応かどうかを指定します。 既定では、この設定は MFC プロジェクトの場合は **[はい]**、それ以外の場合は **[いいえ]** に指定されています。これは、MFC プロジェクトのみが DPI 認識でビルドされるためです。 別の DPI 設定を扱うコードを追加すると、この設定をオーバーライドして **[はい]** にすることができます。 DPI 対応ではないのに DPI 対応として設定すると、アプリケーションが不明瞭にまたは小さく見えることがあります。

## <a name="see-also"></a>関連項目

[ClickOnce Application Manifest](/visualstudio/deployment/clickonce-application-manifest)<br/>
[[マニフェスト ツール] プロパティ ページ](manifest-tool-property-pages.md)<br/>
[Visual Studio で C++ コンパイラとビルド プロパティを設定する](../working-with-project-properties.md)<br/>

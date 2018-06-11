---
title: マニフェスト ツールの入力プロパティと出力プロパティ (Visual C++) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- VC.Project.VCManifestTool.OutputManifestFile
- VC.Project.VCManifestTool.InputResourceManifests
- VC.Project.VCManifestTool.EmbedManifest
- VC.Project.VCManifestTool.AdditionalManifestFiles
- VC.Project.VCManifestTool.DependencyInformationFile
- VC.Project.VCManifestTool.OutputResourceManifest
- VC.Project.VCManifestTool.GenerateCatalogFiles
dev_langs:
- C++
ms.assetid: a8bb20f6-7ace-45ca-bab0-b4f4a5caf170
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 15be7636188bb670febd7875974d683c1d78360f
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2018
ms.locfileid: "33331559"
---
# <a name="input-and-output-manifest-tool-configuration-properties-ltprojectnamegt-property-pages-dialog-box"></a>[入力と出力] ([&lt;プロジェクト名&gt; プロパティ ページ] ダイアログ ボックス - [構成プロパティ] - [マニフェスト ツール])
このダイアログ ボックスを使用して、[Mt.exe](http://msdn.microsoft.com/library/aa375649) の入出力オプションを指定します。  
  
 このプロパティ ページ ダイアログ ボックスにアクセスするには、自分のプロジェクトまたはプロパティ シートのプロパティ ページを開きます。 **[構成プロパティ]** の下で **[マニフェスト ツール]** ノードを展開して、**[入力と出力]** を選択します。  
  
## <a name="uielement-list"></a>UIElement の一覧  
 **追加のマニフェスト ファイル**  
 **/manifest** オプションを使用して、マニフェスト ツールで処理またはマージされる追加のマニフェスト ファイルの完全パスを指定します。 完全パスはセミコロンで区切ります。  
  
 **入力リソース マニフェスト**  
 **/inputresource** オプションを使用して、マニフェスト ツールに入力される RT_MANIFEST 型のリソースの完全パスを指定します。 パスの後には、特定のリソース ID を続けることができます。 例:  
  
 `dll_with_manifest.dll;#1`  
  
 リソース ID は省略可能であり、既定は winuser.h で CREATEPROCESS_MANIFEST_RESOURCE_ID に設定されています。  
  
 **埋め込みマニフェスト**  
 **[はい]** を指定すると、プロジェクト システムによって、アプリケーション マニフェスト ファイルがアセンブリに埋め込まれます。  
  
 **[いいえ]** を指定すると、プロジェクト システムによって、アプリケーション マニフェスト ファイルがスタンドアロン ファイルとして作成されます。  
  
 **出力マニフェスト ファイル**  
 出力マニフェスト ファイルの名前を指定します。 マニフェスト ツールで操作されるマニフェスト ファイルが 1 つだけの場合、このプロパティは省略できます。  
  
 **マニフェスト リソース ファイル**  
 マニフェストをプロジェクト出力に埋め込むために使用する出力リソース ファイルを指定します。  
  
 **カタログ ファイルの生成**  
 **/makecdfs** オプションを使用して、カタログを作成するために使用されるカタログ定義ファイル (.cdf ファイル) をマニフェスト ツールで生成するように指定します。  
  
 **ManagedAssembly からのマニフェストの生成**  
 マネージド アセンブリからマニフェストを生成します  (**-managedassemblyname:***file*)。  
  
 **依存要素の抑制**  
 **-managedassembly** オプションと共に使用します。 このタグは、最終的なマニフェストでの依存要素の生成を抑制します。  
  
 **カタログ タグの生成**  
 **-managedassembly** オプションと共に使用します。 このタグにより、カテゴリのタグが生成されます。  
  
 **DPI 認識の有効化**  
 アプリケーションが DPI 対応かどうかを指定します。 既定では、この設定は MFC プロジェクトの場合は **[はい]**、それ以外の場合は **[いいえ]** に指定されています。これは、MFC プロジェクトのみが DPI 認識でビルドされるためです。 別の DPI 設定を扱うコードを追加すると、この設定をオーバーライドして **[はい]** にすることができます。 DPI 対応ではないのに DPI 対応として設定すると、アプリケーションが不明瞭にまたは小さく見えることがあります。  
  
## <a name="see-also"></a>参照  
 [ClickOnce アプリケーション マニフェスト](/visualstudio/deployment/clickonce-application-manifest)   
 [マニフェスト ツールのプロパティ ページ](../ide/manifest-tool-property-pages.md)   
 [プロジェクトのプロパティの操作](../ide/working-with-project-properties.md)   
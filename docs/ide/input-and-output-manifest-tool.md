---
title: マニフェスト ツールの入力と出力プロパティ (Visual C) |Microsoft ドキュメント
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
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="input-and-output-manifest-tool-configuration-properties-ltprojectnamegt-property-pages-dialog-box"></a>入力と出力、ツール、構成プロパティをマニフェスト&lt;Projectname&gt;プロパティ ページ ダイアログ ボックス
入力と出力のオプションを指定するこのダイアログ ボックスを使用して[Mt.exe](http://msdn.microsoft.com/library/aa375649)です。  
  
 このプロパティ ページ ダイアログ ボックスにアクセスするには、プロジェクトまたはプロパティ シートのプロパティ ページを開きます。 展開して、**マニフェスト ツール**ノードの下**構成プロパティ**、し、**の入力し、出力**です。  
  
## <a name="uielement-list"></a>UIElement の一覧  
 **追加のマニフェスト ファイル**  
 使用して、 **/manifest**マニフェスト ツールを処理する追加のマニフェスト ファイルまたはマージの完全パスを指定するにはオプションです。 完全パスは、セミコロンで区切られます。  
  
 **入力リソース マニフェスト**  
 使用して、 **/inputresource**型マニフェスト ツールへの入力に、RT_MANIFEST のリソースの完全なパスを指定するオプションです。 パスの後に、指定されたリソース id です。 例えば:  
  
 `dll_with_manifest.dll;#1`  
  
 リソース ID は省略可能な既定値 CREATEPROCESS_MANIFEST_RESOURCE_ID winuser.h にします。  
  
 **マニフェストを埋め込む**  
 **[はい]** プロジェクト システムがアセンブリに、アプリケーション マニフェスト ファイルを埋め込むことを指定します。  
  
 **いいえ**プロジェクト システムが、スタンドアロン ファイルとして、アプリケーション マニフェスト ファイルを作成することを指定します。  
  
 **出力マニフェスト ファイル**  
 出力マニフェスト ファイルの名前を指定します。 1 つだけのマニフェスト ファイルがマニフェスト ツールで操作したときに、このプロパティはオプションです。  
  
 **マニフェスト リソース ファイル**  
 リソース ファイルをプロジェクト出力に、マニフェストを埋め込むを使用して出力を指定します。  
  
 **カタログ ファイルを生成します。**  
 使用して、 **/makecdfs**マニフェスト ツールがカタログを作成するために使用するカタログの定義ファイル (.cdf ファイル) を生成するを指定するオプションです。  
  
 **ManagedAssembly からマニフェストを生成します。**  
 マネージ アセンブリからマニフェストを生成します。 (**- managedassemblyname: * * * ファイル*)。  
  
 **Dependency 要素を抑制します。**  
 使用される、 **-managedassembly と組み合わせて**オプション。 このタグは、最終的なマニフェストで依存要素の生成を抑制します。  
  
 **カテゴリのタグを生成します。**  
 使用される、 **-managedassembly と組み合わせて**オプション。 このタグをにより、カテゴリ タグが生成されます。  
  
 **DPI 認識を有効にします。**  
 アプリケーションが DPI 対応かどうかを指定します。 設定は、既定では、**はい**MFC プロジェクトのおよび**いいえ**DPI 認識 MFC プロジェクトだけが組み込まれているため、それ以外の場合。 設定を上書きできます**はい**異なる DPI 設定を処理するコードを追加する場合。 アプリケーションは、あいまいまたはとして設定した場合、DPI が認識されていないときは、小規模可能性があります。  
  
## <a name="see-also"></a>関連項目  
 [ClickOnce アプリケーション マニフェスト](/visualstudio/deployment/clickonce-application-manifest)   
 [マニフェスト ツールのプロパティ ページ](../ide/manifest-tool-property-pages.md)   
 [プロジェクトのプロパティの操作](../ide/working-with-project-properties.md)   
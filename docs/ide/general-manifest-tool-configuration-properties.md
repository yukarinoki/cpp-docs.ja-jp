---
title: マニフェスト ツール構成プロパティ (Visual C) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- VC.Project.VCManifestTool.MergeRulesFile
- VC.Project.VCManifestTool.UseUnicodeResponseFiles
- VC.Project.VCManifestTool.SuppressStartupBanner
- VC.Project.VCManifestTool.UseFAT32Workaround
- VC.Project.VCManifestTool.VerboseOutput
- VC.Project.VCManifestTool.AssemblyIdentity
dev_langs:
- C++
ms.assetid: b99368a5-6819-482c-a06e-f2409290cfd1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1953e7c37c07f66845510efe037015a537aa7baa
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="general-manifest-tool-configuration-properties-ltprojectnamegt-property-pages-dialog-box"></a>一般に、マニフェスト ツール、構成プロパティ、 &lt;Projectname&gt;プロパティ ページ ダイアログ ボックス
[全般] オプションを指定するこのダイアログ ボックスを使用して[Mt.exe](http://msdn.microsoft.com/library/aa375649)です。  
  
 このプロパティ ページ ダイアログ ボックスにアクセスするには、プロジェクトまたはプロパティ シートのプロパティ ページを開きます。 展開して、**マニフェスト ツール**ノードの下**構成プロパティ**、し、**全般**です。  
  
## <a name="uielement-list"></a>UIElement の一覧  
 **著作権情報を抑制します。**  
 **はい (/nologo)** マニフェスト ツールを起動すると、標準の Microsoft 著作権情報を非表示にすることを指定します。 ビルド環境またはのビルド プロセスの一部として mt.exe を実行する場合、ログ ファイル、不必要な出力を抑制するのには、このオプションを使用します。  
  
 **詳細出力**  
 **[はい] (/verbose)** マニフェストの生成中に追加のビルド情報が表示されることを指定します。  
  
 **アセンブリ Id**  
 /Identity オプションを使用して、id 文字列を指定の属性はで構成される、 [ \<assemblyIdentity > 要素](/visualstudio/deployment/assemblyidentity-element-clickonce-application)です。 Id 文字列がの値で始まる、`name`属性がありが続く*属性* = *値*ペア。 Id 文字列内の属性は、コンマで区切られます。  
  
 Id 文字列の例を次に示します。  
  
 `Microsoft.Windows.Common-Controls, processorArchitecture=x86, version=6.0.0.0, type=win32, publicKeyToken=6595b64144ccf1df`  
  
## <a name="see-also"></a>関連項目  
 [ClickOnce アプリケーション マニフェスト](/visualstudio/deployment/clickonce-application-manifest)   
 [マニフェスト ツールのプロパティ ページ](../ide/manifest-tool-property-pages.md)   
 [プロジェクトのプロパティの操作](../ide/working-with-project-properties.md)   
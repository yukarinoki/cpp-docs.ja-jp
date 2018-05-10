---
title: XML ドキュメント ジェネレーター プロパティ ページ |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- VC.Project.VCXDCMakeTool.ValidateIntelliSense
- VC.Project.VCXDCMakeTool.SuppressStartupBanner
- VC.Project.VCXDCMakeTool.DocumentLibraryDependencies
- VC.Project.VCXDCMakeTool.OutputDocumentFile
- VC.Project.VCXDCMakeTool.AdditionalDocumentFiles
dev_langs:
- C++
ms.assetid: 645912b5-197a-4c36-ba58-64df09444ca0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 772e9dc6a296873ef27171676ebca0c185c1771c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="xml-document-generator-tool-property-pages"></a>[XML ドキュメント ジェネレーター] プロパティ ページ
XML ドキュメント ジェネレーター ツール プロパティ ページでは、xdcmake.exe の機能を公開します。 xdcmake.exe が、ソース コードには、ドキュメントのコメントが含まれている場合に、.xml ファイルに .xdc ファイルをマージし、 [/doc (ドキュメント コメントの処理) (C/C++)](../build/reference/doc-process-documentation-comments-c-cpp.md)が指定されている。 参照してください[ドキュメント コメントとして推奨されるタグ](../ide/recommended-tags-for-documentation-comments-visual-cpp.md)ソース コードをドキュメントのコメントを追加する方法についてです。  
  
> [!NOTE]
>  開発環境 (プロパティ ページ) で xdcmake.exe オプションは、xdcmake.exe をコマンドラインで使用すると、オプションとは異なります。 コマンドラインで xdcmake.exe の使用方法の詳細については、次を参照してください。 [XDCMake リファレンス](../ide/xdcmake-reference.md)です。  
  
## <a name="uielement-list"></a>UIElement の一覧  
 **著作権情報を抑制します。**  
 著作権メッセージを抑制します。  
  
 **追加のドキュメントのファイル**  
 プロジェクト システムは、.xdc ファイルを検索するディレクトリを追加します。 xdcmake は、常に、プロジェクトによって生成される .xdc ファイルを探します。 複数のディレクトリを指定することができます。  
  
 **出力ドキュメント ファイル**  
 出力の .xml ファイルの名前とディレクトリの場所。 参照してください[のビルドのコマンドとプロパティの一般的なマクロ](../ide/common-macros-for-build-commands-and-properties.md)マクロを使用して、ディレクトリの場所を指定する方法についてはします。  
  
 **ドキュメント ライブラリの依存関係**  
 場合は、プロジェクト、ソリューション内の .lib プロジェクトに依存している、現在のプロジェクトの .xml ファイルに .lib プロジェクトから .xdc ファイルを処理できます。  
  
## <a name="see-also"></a>関連項目  
 [プロパティ ページ](../ide/property-pages-visual-cpp.md)   
 [プロパティ ページ](../ide/property-pages-visual-cpp.md)
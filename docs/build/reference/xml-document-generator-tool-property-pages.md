---
title: '[XML ドキュメント ジェネレーター] プロパティ ページ'
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCXDCMakeTool.ValidateIntelliSense
- VC.Project.VCXDCMakeTool.SuppressStartupBanner
- VC.Project.VCXDCMakeTool.DocumentLibraryDependencies
- VC.Project.VCXDCMakeTool.OutputDocumentFile
- VC.Project.VCXDCMakeTool.AdditionalDocumentFiles
ms.assetid: 645912b5-197a-4c36-ba58-64df09444ca0
ms.openlocfilehash: d17913909532c5bebcac712937af00be3ad98712
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81335767"
---
# <a name="xml-document-generator-tool-property-pages"></a>[XML ドキュメント ジェネレーター] プロパティ ページ

[XML ドキュメント ジェネレーター] プロパティ ページでは、xdcmake.exe の機能が公開されます。 xdcmake.exe は、ソース コードにドキュメントのコメントが含まれていて、[/doc (ドキュメント コメントの処理) (C/C++)](doc-process-documentation-comments-c-cpp.md) が指定されている場合に、.xdc ファイルを .xml ファイルにマージします。 ドキュメントのコメントをソース コードに追加する詳細については、「[ドキュメント コメントとして推奨されるタグ](recommended-tags-for-documentation-comments-visual-cpp.md)」を参照してください。

> [!NOTE]
> 開発環境 (プロパティ ページ) の xdcmake.exe オプションは、コマンド ラインで xdcmake.exe を使用する場合のオプションとは異なります。 コマンド ラインで xdcmake.exe を使用する詳細については、「[XDCMake リファレンス](xdcmake-reference.md)」を参照してください。

## <a name="uielement-list"></a>UI 要素の一覧

- **著作権情報の非表示**

   著作権メッセージを表示しません。

- **追加ドキュメント ファイル**

   プロジェクト システムが .xdc ファイルを検索する追加のディレクトリ。 xdcmake は、常に、プロジェクトによって生成される .xdc ファイルを探します。 複数のディレクトリを指定することができます。

- **出力ドキュメント ファイル**

   .xml 出力ファイルの名前とディレクトリの場所。 マクロを使用してディレクトリの場所を指定する方法については、[ビルド コマンドとプロパティの共通](common-macros-for-build-commands-and-properties.md)マクロを参照してください。

- **ドキュメント ライブラリの依存関係**

   プロジェクトにソリューション内の .lib プロジェクトへの依存関係がある場合は、.lib プロジェクトから現在のプロジェクトの .xml ファイルに .xdc ファイルを処理できます。

## <a name="see-also"></a>関連項目

[C++ プロジェクトのプロパティ ページのリファレンス](property-pages-visual-cpp.md)

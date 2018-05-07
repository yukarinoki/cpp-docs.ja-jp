---
title: '[リンカー] プロパティ ページ |Microsoft ドキュメント'
ms.custom: ''
ms.date: 11/21/2017
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- VC.Project.VCLinkerTool.RegisterOutput
- VC.Project.VCLinkerTool.OVERWRITEImportLibrary
- VC.Project.VCLinkerTool.UseLibraryDependencyInputs
- VC.Project.VCLinkerTool.LinkLibraryDependencies
dev_langs:
- C++
helpviewer_keywords:
- per-user redirection
- Linker property pages
ms.assetid: 7e7671e5-a35a-4e67-9bdb-661d75c4d11e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2cec232bb4e4f2f6ac1ab9af703b368eec0ba5dd
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="linker-property-pages"></a>リンカー プロパティ ページ

このトピックでは、次のプロパティをでに関する、**全般**リンカー プロパティ ページ。 このページの Linux バージョンを参照してください。[リンカー プロパティ (C++ の Linux)](../linux/prop-pages/linker-linux.md)です。

## <a name="general-page-properties"></a>[全般] ページのプロパティ

### <a name="ignore-import-library"></a>[インポート ライブラリの無視]

このプロパティを使用すると、リンカーは、依存プロジェクトには、このビルドから生成された .lib 出力をリンクしないようにします。 このため、プロジェクト システムは、ビルド時に .lib ファイルを生成しない .dll ファイルを処理できます。 プロジェクトは、DLL を生成する別のプロジェクトに依存している場合、プロジェクト システムは、子プロジェクトによって生成される .lib ファイルを自動的にリンクします。 この動作は COM DLL やリソースだけの DLL を生成するプロジェクトには不要な場合があります。これらの DLL には意味のあるエクスポート内容が含まれません。 エクスポートする DLL がない場合は、リンカーは、.lib ファイルを生成しません。 エクスポート .lib ファイルが、ディスクに存在しないと、プロジェクト システム、リンカーはこの DLL とリンクする、リンクが失敗します。 使用して、**インポート ライブラリの無視**この問題を解決するのにはプロパティです。 設定すると**はい**、プロジェクト システムは .lib ファイルの有無を無視し、存在しない .lib ファイルとリンクされないようにするには、このプロジェクトに依存しているプロジェクトは任意です。

プログラムを使用してこのプロパティにアクセスする方法については、「<xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.IgnoreImportLibrary%2A>」を参照してください。

### <a name="register-output"></a>[出力の登録]

実行`regsvr32.exe /s $(TargetPath)`ビルド出力である .dll プロジェクトでのみ有効です。 .exe プロジェクトでは、このプロパティは無視されます。 .Exe 出力を登録するを常に登録済みの .exe ファイルに必要なカスタム登録を行うには、構成でビルド後のイベントを設定します。

プログラムを使用してこのプロパティにアクセスする方法については、「<xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.RegisterOutput%2A>」を参照してください。

### <a name="per-user-redirection"></a>[ユーザーごとのリダイレクト]

Visual Studio での登録には、HKEY_CLASSES_ROOT (HKCR) で処理が行っていました。 HKCR にアクセスすると、Windows Vista 以降のオペレーティング システムに管理者特権モードで Visual Studio を実行する必要があります。 開発者は常にシステム特権のあるモードで実行するわけではありませんが、登録を処理する必要があります。 ユーザーごとのリダイレクトにより、このモードで実行せずに登録を行うことができるようになります。

ユーザーごとのリダイレクトでは、すべての書き込みを強制的に HKEY にリダイレクトする HKCR\_現在\_ユーザー (HKCU)。 ユーザーごとのリダイレクトを無効にすると、発生する可能性が[プロジェクト ビルド エラー PRJ0050](../error-messages/tool-errors/project-build-error-prj0050.md) HKCR への書き込みが開始するとき、プログラムです。

### <a name="link-library-dependencies"></a>ライブラリ依存関係のリンク

依存プロジェクトによって生成される .lib ファイルをリンクするかどうかを指定します。 通常、.lib ファイルにリンクするが、特定の Dll の場合とは限りません。

たとえば、ファイル名と相対パスを提供することによって、.obj ファイルを指定することも"..\\..\MyLibProject\MyObjFile.obj"です。 場合は、.obj ファイルのソース コードに # たとえば pch.h、プリコンパイル済みヘッダーを includes pch.obj ファイルは MyObjFile.obj と同じフォルダーにあり、追加の依存関係として pch.obj を追加することもあります。

### <a name="use-library-dependency-inputs"></a>ライブラリ依存関係の入力の使用

大規模なプロジェクトでは、依存プロジェクトによって .lib ファイルが生成される場合、インクリメンタル リンクは無効にされています。 .lib ファイルを生成する依存プロジェクトが多数存在する場合、アプリケーションのビルドに長時間を要する場合があります。 このプロパティを設定すると**はい**、インクリメンタル リンクが有効に、依存プロジェクトによって生成される .lib の .obj ファイルにプロジェクト システムへのリンク。

アクセスする方法については、**全般**リンカー プロパティ ページを参照してください[のプロジェクト プロパティの操作](../ide/working-with-project-properties.md)です。

## <a name="see-also"></a>関連項目

[[VC++ プロジェクトの設定] ([オプション] ダイアログ ボックス - [プロジェクトおよびソリューション])](/visualstudio/ide/reference/vcpp-project-settings-projects-and-solutions-options-dialog-box)  
[プロパティ ページ](../ide/property-pages-visual-cpp.md)  
---
title: リンカー プロパティ ページ
ms.date: 11/21/2017
f1_keywords:
- VC.Project.VCLinkerTool.RegisterOutput
- VC.Project.VCLinkerTool.OVERWRITEImportLibrary
- VC.Project.VCLinkerTool.UseLibraryDependencyInputs
- VC.Project.VCLinkerTool.LinkLibraryDependencies
helpviewer_keywords:
- per-user redirection
- Linker property pages
ms.assetid: 7e7671e5-a35a-4e67-9bdb-661d75c4d11e
ms.openlocfilehash: 1412531ae0ca9c0f5270df6df7b79ddc9be425ad
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62216646"
---
# <a name="linker-property-pages"></a>リンカー プロパティ ページ

このトピックでは、**[全般]** ([リンカー] プロパティ ページ) の以下のプロパティについて説明します。 このページの Linux バージョンについては、「[リンカー プロパティ (Linux C++)](../../linux/prop-pages/linker-linux.md)」を参照してください。

## <a name="general-page-properties"></a>[全般] ページのプロパティ

### <a name="ignore-import-library"></a>インポート ライブラリの無視

このプロパティは、このビルドから生成された .lib 出力を依存プロジェクトにリンクしないようにリンカーに通知します。 このため、プロジェクト システムは、ビルド時に .lib ファイルを生成しない .dll ファイルを処理できます。 あるプロジェクトが DLL を生成する他のプロジェクトに依存している場合、プロジェクト システムでは子プロジェクトによって生成される .lib ファイルを自動的にリンクします。 この動作は COM DLL やリソースだけの DLL を生成するプロジェクトには不要な場合があります。これらの DLL には意味のあるエクスポート内容が含まれません。 DLL にエクスポート内容が含まれない場合は、リンカーで .lib ファイルが生成されません。 ディスクにエクスポート .lib ファイルがなく、この DLL とリンクするようにプロジェクト システムからリンカーに指示が出された場合は、リンクに失敗します。 この問題を解決するには、**[インポート ライブラリの無視]** プロパティを使用します。 このプロパティを **[はい]** に設定すると、プロジェクト システムは .lib ファイルの有無を無視し、このプロジェクトに依存する他のプロジェクトが、存在しない .lib ファイルとリンクされないようにします。

プログラムを使用してこのプロパティにアクセスする方法については、「<xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.IgnoreImportLibrary%2A>」を参照してください。

### <a name="register-output"></a>出力の登録

.dll プロジェクトでのみ有効なビルド出力で `regsvr32.exe /s $(TargetPath)` を実行します。 .exe プロジェクトでは、このプロパティは無視されます。 .exe 出力を登録するには、構成にビルド後のイベントを設定し、登録済みの .exe ファイルに必要なカスタム登録を行います。

プログラムを使用してこのプロパティにアクセスする方法については、「<xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.RegisterOutput%2A>」を参照してください。

### <a name="per-user-redirection"></a>ユーザーごとのリダイレクト

Visual Studio の登録はこれまで、HKEY_CLASSES_ROOT (HKCR) で行われてきました。 Windows Vista 以降のオペレーティング システムでは、HKCR にアクセスするには、特権モードで Visual Studio を実行する必要があります。 開発者は常にシステム特権のあるモードで実行するわけではありませんが、登録を処理する必要があります。 ユーザーごとのリダイレクトにより、このモードで実行せずに登録を行うことができるようになります。

ユーザーごとのリダイレクトは、HKCR への書き込みが HKEY\_CURRENT\_USER (HKCU) にリダイレクトされるように強制します。 ユーザーごとのリダイレクトをオフにすると、プログラムが HKCR への書き込みを試行するときに[プロジェクト ビルド エラー PRJ0050](../../error-messages/tool-errors/project-build-error-prj0050.md) が発生する場合があります。

### <a name="link-library-dependencies"></a>ライブラリ依存関係のリンク

依存プロジェクトによって生成された .lib ファイルをリンクするかどうかを指定します。 通常、.lib ファイルでリンクしますが、特定の DLL の場合はそうしないことがあります。

また、ファイル名と相対パス (たとえば "..\\..\MyLibProject\MyObjFile.obj") によって .obj ファイルを指定できます。 .obj ファイルのソース コードにプリコンパイル済みヘッダー (たとえば pch.h) が含まれている場合、pch.obj ファイルは MyObjFile.obj と同じフォルダーに置かれ、依存関係として pch.obj を追加する必要があります。

### <a name="use-library-dependency-inputs"></a>ライブラリ依存関係の入力の使用

大規模なプロジェクトでは、依存プロジェクトによって .lib ファイルが生成される場合、インクリメンタル リンクは無効にされています。 .lib ファイルを生成する依存プロジェクトが多数存在する場合、アプリケーションのビルドに長時間を要する場合があります。 このプロパティを **[はい]** に設定すると、プロジェクト システムによってインクリメンタル リンクが有効にされ、依存プロジェクトが生成する .lib ファイルに対して .obj ファイルがリンクされます。

アクセスする方法については、**全般**リンカー プロパティ ページを参照してください[Visual Studio での設定の C++ コンパイラとビルド プロパティ](../working-with-project-properties.md)します。

## <a name="see-also"></a>関連項目

[[VC++ プロジェクトの設定] ([オプション] ダイアログ ボックス - [プロジェクトおよびソリューション])](/visualstudio/ide/reference/vcpp-project-settings-projects-and-solutions-options-dialog-box)<br>
[C++ プロジェクト プロパティ ページの参照](property-pages-visual-cpp.md)
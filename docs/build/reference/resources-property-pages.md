---
description: '詳細情報: Resources プロパティページ'
title: リソース
ms.date: 08/28/2019
ms.topic: article
ms.assetid: dade2f6b-c51f-4c33-9023-41956ae4b5f6
f1_keywords:
- VC.Project.VCResourceCompilerTool.PreprocessorDefinitions
- VC.Project.VCResourceCompilerTool.UndefineProcessorDefinitions
- VC.Project.VCResourceCompilerTool.Culture
- VC.Project.VCResourceCompilerTool.AdditionalIncludeDirectories
- VC.Project.VCResourceCompilerTool.IgnoreStandardIncludePath
- VC.Project.VCResourceCompilerTool.ShowProgress
- VC.Project.VCResourceCompilerTool.SuppressStartupBanner
- VC.Project.VCResourceCompilerTool.ResourceOutputFileName
- VC.Project.VCResourceCompilerTool.NullTerminateStrings
- vc.project.AdditionalOptionsPage
ms.openlocfilehash: d074cbb6035bd138ca322197e50e9a3f892b325b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97225103"
---
# <a name="resources-property-page"></a>[リソース] プロパティページ

ネイティブ Windows デスクトッププログラムの場合、ビルドは [リソースコンパイラ (rc.exe)](/windows/win32/menurc/resource-compiler) を呼び出して、バイナリにイメージ、文字列テーブル、 *.res* ファイルを追加します。 このプロパティページで公開されているプロパティは、C++ コンパイラまたはリンカーではなく、リソースコンパイラに渡されます。 ここに記載されているプロパティの詳細と、それらのプロパティを RC のコマンドラインオプションにマップする方法については、「 [USING rc (Rc コマンドライン)](/windows/win32/menurc/using-rc-the-rc-command-line-)」を参照してください。 **リソース** プロパティページにアクセスする方法の詳細については、「 [Visual Studio での C++ コンパイラとビルドプロパティの設定](../working-with-project-properties.md)」を参照してください。 プログラムを使用してこれらのプロパティにアクセスする方法については、「<xref:Microsoft.VisualStudio.VCProjectEngine.VCResourceCompilerTool>」を参照してください。

C++/CLI アプリケーションでの .NET リソースのプロパティは、[ [マネージリソース] プロパティページ](managed-resources-property-page.md)で公開されます。

## <a name="preprocessor-definitions"></a>プリプロセッサの定義

リソースコンパイラに対して1つ以上の定義を指定します。 (/d [マクロ])

## <a name="undefine-preprocessor-definitions"></a>指定したプリプロセッサ定義の無効化

シンボルを未定義にします。 /u

## <a name="culture"></a>カルチャ

リソースで使用されているカルチャ (米国英語、イタリア語など) を一覧表示します。 (/l [num])

## <a name="additional-include-directories"></a>追加のインクルード ディレクトリ

インクルードパスに追加する1つ以上のディレクトリを指定します。複数の場合は、セミコロンの区切り記号を使用します。 (/I [パス])

## <a name="ignore-standard-include-paths"></a>標準インクルードパスを無視する

INCLUDE 環境変数で指定されたディレクトリ内のインクルードファイルをリソースコンパイラが検索できないようにします。 X

## <a name="show-progress"></a>進行状況の表示

進行状況メッセージを出力ウィンドウに送信します。 /v

## <a name="suppress-startup-banner"></a>著作権情報の非表示

著作権情報と情報メッセージの表示を抑制する (/nologo)

## <a name="resource-file-name"></a>Resource File Name (リソース ファイル名)

リソースファイルの名前を指定します (/fo [ファイル])

## <a name="null-terminate-strings"></a>Null 終了文字列

文字列テーブル内のすべての文字列に null を追加します。 ms-dos

## <a name="see-also"></a>関連項目

[C++ プロジェクトのプロパティ ページのリファレンス](property-pages-visual-cpp.md)

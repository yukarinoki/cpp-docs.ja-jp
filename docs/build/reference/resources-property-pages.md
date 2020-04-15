---
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
ms.openlocfilehash: c4a3048bfa07e9635662534b510fa57caa091f00
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81336076"
---
# <a name="resources-property-page"></a>リソース プロパティ ページ

ネイティブ Windows デスクトップ プログラムの場合、ビルドは[リソース コンパイラ (rc.exe) を](/windows/win32/menurc/resource-compiler)呼び出して、イメージ、文字列テーブル、および *.res*ファイルをバイナリに追加します。 このプロパティ ページで公開されるプロパティは、C++ コンパイラまたはリンカーではなく、リソース コンパイラに渡されます。 ここに示されているプロパティの詳細と、RC コマンド ライン オプションへのマッピング方法については[、「RC (RC コマンド ライン)の使用](/windows/win32/menurc/using-rc-the-rc-command-line-)」を参照してください。 **リソース**プロパティ ページにアクセスする方法については[、「Visual Studio で C++ コンパイラとビルド プロパティを設定](../working-with-project-properties.md)する」を参照してください。 プログラムを使用してこれらのプロパティにアクセスする方法については、「<xref:Microsoft.VisualStudio.VCProjectEngine.VCResourceCompilerTool>」を参照してください。

C++/CLI アプリケーションの .NET リソースのプロパティは、[管理リソースのプロパティ ページ](managed-resources-property-page.md)で公開されます。

## <a name="preprocessor-definitions"></a>プリプロセッサの定義

リソース コンパイラの 1 つ以上の定義を指定します。 (/d[マクロ])

## <a name="undefine-preprocessor-definitions"></a>指定したプリプロセッサ定義の無効化

シンボルの定義を解除します。 (/u)

## <a name="culture"></a>culture

リソースで使用されているカルチャ (米国英語やイタリア語など) を一覧表示します。 (/l [num])

## <a name="additional-include-directories"></a>追加のインクルード ディレクトリ

インクルード パスに追加する 1 つ以上のディレクトリを指定します。セミコロン区切り文字を使用する場合は、複数の場合。 (/I[パス])

## <a name="ignore-standard-include-paths"></a>標準インクルード パスを無視

リソース コンパイラが INCLUDE 環境変数で指定されたディレクトリ内のインクルード ファイルを検索できないようにします。 (/X)

## <a name="show-progress"></a>進行状況の表示

進行状況メッセージを出力ウィンドウに送信します。 (/v)

## <a name="suppress-startup-banner"></a>著作権情報の非表示

スタートアップ バナーと情報メッセージ (/nologo) の表示を抑制する

## <a name="resource-file-name"></a>Resource File Name (リソース ファイル名)

リソース ファイルの名前を指定します (/fo[file])

## <a name="null-terminate-strings"></a>Null 終了文字列

文字列テーブル内のすべての文字列に null を追加します。 (/n)

## <a name="see-also"></a>関連項目

[C++ プロジェクトのプロパティ ページのリファレンス](property-pages-visual-cpp.md)

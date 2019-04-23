---
title: Visual C++ プロジェクトに対して作成されるファイルの種類
ms.date: 04/08/2019
helpviewer_keywords:
- header files [C++], Visual Studio projects
- ActiveX controls [C++], Help files
- def files
- project items [C++], files
- Visual Studio C++ projects, files and directories
- resource files, created by wizard
- files [C++], extensions
- Help files, for ActiveX controls
- Web projects [C++], adding items
- .def files
- licensing ActiveX controls
ms.assetid: 2b0ee2e0-ae81-4185-9bb9-11da3c99a283
ms.openlocfilehash: eee53acbb8b0b8432a7d5819fb773b616f0e8897
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59424094"
---
# <a name="file-types-created-for-visual-studio-c-projects"></a>Visual Studio の C++ プロジェクトに対して作成されるファイルの種類

さまざまな種類のファイルは、従来のデスクトップ アプリケーションの Visual Studio プロジェクトに関連付けられます。 実際にプロジェクトにインクルードされるファイルは、プロジェクトの種類、およびウィザードで選択したオプションによって異なります。

- [プロジェクト ファイルとソリューション ファイル](project-and-solution-files.md)

- [CLR プロジェクト](files-created-for-clr-projects.md)

- [ATL プログラムまたはコントロールのソース ファイルとヘッダー ファイル](atl-program-or-control-source-and-header-files.md)

- [MFC プログラムまたはコントロールのソース ファイルとヘッダー ファイル](mfc-program-or-control-source-and-header-files.md)

- [プリコンパイル済みヘッダー ファイル](../creating-precompiled-header-files.md)

- [リソース ファイル](resource-files-cpp.md)

- [ヘルプ ファイル (WinHelp)](help-files-winhelp.md)

- [ヒント ファイル](hint-files.md)

Visual Studio プロジェクトを作成する場合は、新しいソリューションでは、作成する場合があります。 または既存のソリューションにプロジェクトを追加する場合があります。 通常、複雑なアプリケーションの開発では、1 つのソリューションに複数のプロジェクトを作成します。

プロジェクトでは、通常、EXE ファイルまたは DLL ファイルが生成されます。 プロジェクトを相互に依存することができます。ビルド プロセス中には、Visual Studio 環境は、企業内やプロジェクト間の依存関係を確認します。 通常、各プロジェクトには、core ソース コードがあります。 プロジェクトの種類、によって、プロジェクトのさまざまな側面を格納している他の多くのファイルでその必要があります。 これらのファイルの内容はファイル拡張子によって示されます。 Visual Studio 開発環境では、ファイル拡張子を使用して、ビルド時のファイル内容の処理方法を判断します。

次の表は、Visual Studio プロジェクトで一般的なファイルが表示され、ファイル拡張子であることを示します。

|ファイル拡張子|型|目次|
|--------------------|----------|--------------|
|.asmx|ソース|配置ファイル。|
|.asp|Source|ASP (Active Server Page) ファイル。|
|.atp|プロジェクト|アプリケーション テンプレート プロジェクト ファイル。|
|.bmp、.dib、.gif、.jpg、.jpe、.png|リソース|一般的なイメージ ファイル。|
|.bsc|コンパイル|ブラウザー コード ファイル。|
|.cpp、.c|Source|アプリケーションの主要なソース コード ファイル。|
|.cur|リソース|カーソルのビットマップ グラフィック ファイル。|
|.dbp|プロジェクト|データベース プロジェクト ファイル。|
|.disco|Source|動的探索ドキュメント ファイル。 XML Web サービス探索を処理します。|
|.exe、.dll|プロジェクト|実行可能ファイルまたはダイナミック リンク ライブラリ ファイル。|
|.h|Source|ヘッダー ファイルまたはインクルード ファイル。|
|.htm、.html、.xsp、.asp、.htc、.hta、.xml|リソース|共通 Web ファイル。|
|.HxC|プロジェクト|ヘルプ プロジェクト ファイル。|
|.ico|リソース|アイコンのビットマップ グラフィック ファイル。|
|.idb|コンパイル|状態ファイルは、ソース ファイルとクラス定義間の依存関係情報を格納しています。 インクリメンタル コンパイル中に、コンパイラによって使用できます。 .idb ファイルの名前は [/Fd](fd-program-database-file-name.md) コンパイラ オプションで指定します。|
|.idl|コンパイル|インターフェイス定義言語ファイル。 詳細については、Windows SDK の「[Interface Definition (IDL) File](/windows/desktop/Rpc/the-interface-definition-language-idl-file)」(インターフェイス定義 (IDL) ファイル) を参照してください。|
|.ilk|リンク|インクリメンタル リンク ファイル。 詳細については、次を参照してください。 [/incremental](incremental-link-incrementally.md)します。|
|.map|リンク|リンカー情報を含むテキスト ファイル。 マップ ファイルの名前は、 [/Fm](fm-name-mapfile.md) コンパイラ オプションで指定します。 詳細については、次を参照してください。 [/map](map-generate-mapfile.md)します。|
|.mfcribbon-ms|リソース|リボンの MFC のボタン、コントロール、および属性を定義する XML コードを含むリソース ファイル。 詳細については、「 [Ribbon Designer](../../mfc/ribbon-designer-mfc.md)」を参照してください。|
|.obj、.o||オブジェクト ファイル。コンパイルはされますが、リンクはされません。|
|.pch|デバッグ|プリコンパイル済みヘッダー ファイル。|
|.rc、.rc2|リソース|リソースを生成するための[リソース スクリプト ファイル](../../windows/working-with-resource-files.md) 。|
|.sbr|コンパイル|ソース ブラウザー中間ファイル。 [BSCMAKE](bscmake-options.md)の入力ファイルです。|
|.sln|ソリューション|[ソリューション](/visualstudio/ide/solutions-and-projects-in-visual-studio) ファイル。|
|.suo|ソリューション|ソリューション オプション ファイル。|
|.txt|リソース|テキスト ファイル。通常は README ファイルです。|
|.vap|プロジェクト|Visual Studio Analyzer プロジェクト ファイル。|
|.vbg|ソリューション|互換性のあるプロジェクト グループ ファイル。|
|.vbp、.vip、.vbproj|プロジェクト|Visual Basic プロジェクト ファイル。|
|.vcxitems|プロジェクト|複数の C++ プロジェクト間でコード ファイルを共有するための共有アイテム プロジェクト。 詳細については、次を参照してください。[プロジェクトとソリューション ファイル](project-and-solution-files.md)します。|
|.vcxproj|プロジェクト|Visual Studio プロジェクト ファイル。 詳細については、次を参照してください。[プロジェクトとソリューション ファイル](project-and-solution-files.md)します。|
|.vcxproj.filters|プロジェクト|ソリューション エクスプ ローラーを使用してファイルをプロジェクトに追加するために使用します。 フィルター ファイルは、そのファイル名拡張子に基づいてファイルを追加するソリューション エクスプ ローラーのツリー ビューの場所を定義します。|
|.vdproj|プロジェクト|Visual Studio 配置プロジェクト ファイル。|
|.vmx|プロジェクト|マクロ プロジェクト ファイル。|
|.vup|プロジェクト|ユーティリティ プロジェクト ファイル。|

Visual Studio に関連するその他のファイルの詳細については、「 [Visual Studio .NET のファイルの種類と拡張子](/visualstudio/ide/reference/project-and-solution-file-types)」を参照してください。

プロジェクト ファイルは、ソリューション エクスプローラーで複数のフォルダーに分けて編成されています。 Visual Studio がソース ファイル、ヘッダー ファイル、およびリソース ファイル、フォルダーを作成しますが、これらのフォルダーを再構成または新たに作成することができます。 フォルダーを使用すると、プロジェクト階層内で論理ファイル クラスターを明示的に編成できます。 たとえば、すべてのユーザー インターフェイス ソース ファイルを格納するフォルダーを作成できます。 または、仕様、ドキュメント、またはテスト スイート用のフォルダー。 すべてのファイル フォルダーに一意の名前を指定する必要があります。

プロジェクトに項目を追加する項目をそのプロジェクトのすべての構成に追加します。 それがビルド可能かどうか、項目が追加されます。 たとえば、MyProject というプロジェクトに項目を追加すると、プロジェクトのデバッグ構成とリリース構成の両方にその項目が追加されます。

## <a name="see-also"></a>関連項目

[作成して、Visual Studio の C++ プロジェクトの管理](../creating-and-managing-visual-cpp-projects.md)<br>
[Visual Studio の C++ プロジェクトの種類](visual-cpp-project-types.md)<br>
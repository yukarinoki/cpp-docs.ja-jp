---
title: Visual C++ プロジェクトに対して作成されるファイルの種類
ms.date: 11/04/2016
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
ms.openlocfilehash: c05dd9da5dd17b0e06ace750d34f2c5abcf94380
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2019
ms.locfileid: "57827528"
---
# <a name="file-types-created-for-visual-studio-c-projects"></a>Visual Studio の C++ プロジェクトに対して作成されるファイルの種類

このトピックでは、従来のデスクトップ アプリケーションの Visual Studio プロジェクトに関連付けられているファイルのすべての種類について説明します。 実際にプロジェクトにインクルードされるファイルは、プロジェクトの種類、およびウィザードで選択したオプションによって異なります。

- [プロジェクト ファイルとソリューション ファイル]()

- [CLR プロジェクト](files-created-for-clr-projects.md)

- [ATL プログラムまたはコントロールのソース ファイルとヘッダー ファイル](atl-program-or-control-source-and-header-files.md)

- [MFC プログラムまたはコントロールのソース ファイルとヘッダー ファイル](mfc-program-or-control-source-and-header-files.md)

- [プリコンパイル済みヘッダー ファイル](../creating-precompiled-header-files.md)

- [リソース ファイル](resource-files-cpp.md)

- [ヘルプ ファイル (WinHelp)](help-files-winhelp.md)

- [ヒント ファイル](hint-files.md)

Visual Studio プロジェクトを作成するときに、新しいソリューションを作成する場合や、ソリューションにプロジェクトを追加する場合があります。 通常、複雑なアプリケーションの開発では、1 つのソリューションに複数のプロジェクトを作成します。

プロジェクトでは、通常、EXE ファイルまたは DLL ファイルが生成されます。 プロジェクトを相互に依存することができます。ビルド プロセス中には、Visual Studio 環境は、企業内やプロジェクト間の依存関係を確認します。 各プロジェクトにはコア ソース コードがあります。また、プロジェクトの種類に応じて、プロジェクトのさまざまな要素を格納したファイルが多数含まれることがあります。 これらのファイルの内容はファイル拡張子によって示されます。 Visual Studio 開発環境では、ファイル拡張子を使用して、ビルド時のファイル内容の処理方法を判断します。

次の表は、Visual Studio プロジェクトで一般的なファイルが表示され、ファイル拡張子であることを示します。

|ファイル拡張子|型|目次|
|--------------------|----------|--------------|
|.asmx|ソース|配置ファイル。|
|.asp|ソース|ASP (Active Server Page) ファイル。|
|.atp|Project|アプリケーション テンプレート プロジェクト ファイル。|
|.bmp、.dib、.gif、.jpg、.jpe、.png|リソース|一般的なイメージ ファイル。|
|.bsc|コンパイル|ブラウザー コード ファイル。|
|.cpp、.c|ソース|アプリケーションの主要なソース コード ファイル。|
|.cur|リソース|カーソルのビットマップ グラフィック ファイル。|
|.dbp|Project|データベース プロジェクト ファイル。|
|.disco|ソース|動的探索ドキュメント ファイル。 XML Web サービス探索を処理します。|
|.exe、.dll|Project|実行可能ファイルまたはダイナミック リンク ライブラリ ファイル。|
|.h|ソース|ヘッダー ファイルまたはインクルード ファイル。|
|.htm、.html、.xsp、.asp、.htc、.hta、.xml|リソース|共通 Web ファイル。|
|.HxC|Project|ヘルプ プロジェクト ファイル。|
|.ico|リソース|アイコンのビットマップ グラフィック ファイル。|
|.idb|コンパイル|ソース ファイルとクラス定義との依存関係情報が含まれているステート ファイル。最小リビルドとインクリメンタル コンパイルのときにコンパイラで使用します。 .idb ファイルの名前は [/Fd](fd-program-database-file-name.md) コンパイラ オプションで指定します。 詳細については、「 [/Gm (簡易リビルドの有効化)](gm-enable-minimal-rebuild.md) 」を参照してください。|
|.idl|コンパイル|インターフェイス定義言語ファイル。 詳細については、Windows SDK の「[インターフェイス定義 (IDL) ファイル](/windows/desktop/Rpc/the-interface-definition-language-idl-file)」を参照してください。|
|.ilk|リンク|インクリメンタル リンク ファイル。 詳しくは、「 [/INCREMENTAL](incremental-link-incrementally.md) 」をご覧ください。|
|.map|リンク|リンカー情報を含むテキスト ファイル。 マップ ファイルの名前は、 [/Fm](fm-name-mapfile.md) コンパイラ オプションで指定します。 詳細については、「 [/MAP](map-generate-mapfile.md) 」を参照してください。|
|.mfcribbon-ms|リソース|リボンのボタン、コントロール、および属性を定義する XML コードを含むリソース ファイル。 詳細については、「 [Ribbon Designer (MFC)](../../mfc/ribbon-designer-mfc.md)」を参照してください。|
|.obj、.o||オブジェクト ファイル。コンパイルはされますが、リンクはされません。|
|.pch|デバッグ|プリコンパイル済みヘッダー ファイル。|
|.rc、.rc2|リソース|リソースを生成するための[リソース スクリプト ファイル](../../windows/working-with-resource-files.md) 。|
|.sbr|コンパイル|ソース ブラウザー中間ファイル。 [BSCMAKE](bscmake-options.md)の入力ファイルです。|
|.sln|ソリューション|[ソリューション](/visualstudio/ide/solutions-and-projects-in-visual-studio) ファイル。|
|.suo|ソリューション|ソリューション オプション ファイル。|
|.txt|リソース|テキスト ファイル。通常は README ファイルです。|
|.vap|Project|Visual Studio Analyzer プロジェクト ファイル。|
|.vbg|ソリューション|互換性のあるプロジェクト グループ ファイル。|
|.vbp、.vip、.vbproj|プロジェクト|Visual Basic プロジェクト ファイル。|
|.vcxitems|Project|複数の C++ プロジェクト間でコード ファイルを共有するための共有アイテム プロジェクト。 詳細については、「 [プロジェクト ファイルとメイクファイル]() 」を参照してください。|
|.vcxproj|Project|Visual Studio プロジェクト ファイル。 詳細については、「 [プロジェクト ファイルとメイクファイル]() 」を参照してください。|
|.vcxproj.filters|Project|filters ファイルは、ソリューション エクスプローラーを使用してプロジェクトにファイルを追加するときに、ファイル名拡張子に基づいてソリューション エクスプローラーのツリー ビューでファイルを追加する場所を定義します。|
|.vdproj|Project|Visual Studio 配置プロジェクト ファイル。|
|.vmx|Project|マクロ プロジェクト ファイル。|
|.vup|Project|ユーティリティ プロジェクト ファイル。|

Visual Studio に関連するその他のファイルの詳細については、「 [Visual Studio .NET のファイルの種類と拡張子](/visualstudio/ide/reference/project-and-solution-file-types)」を参照してください。

プロジェクト ファイルは、ソリューション エクスプローラーで複数のフォルダーに分けて編成されています。 Visual Studio がソース ファイル、ヘッダー ファイル、およびリソース ファイル、フォルダーを作成しますが、これらのフォルダーを再構成または新たに作成することができます。 フォルダーを使用すると、プロジェクト階層内で論理ファイル クラスターを明示的に編成できます。 たとえば、ユーザー インターフェイスのすべてのソース ファイル、仕様、ドキュメント、テスト スイートなどを格納するフォルダーを作成できます。 すべてのファイル フォルダーに一意の名前を指定する必要があります。

プロジェクトに項目を追加すると、その項目をビルドできるかどうかにかかわらず、プロジェクトのすべての構成にその項目が追加されます。 たとえば、MyProject というプロジェクトに項目を追加すると、プロジェクトのデバッグ構成とリリース構成の両方にその項目が追加されます。

## <a name="see-also"></a>関連項目

[作成して、Visual Studio の C++ プロジェクトの管理](../creating-and-managing-visual-cpp-projects.md)<br>
[Visual Studio の C++ プロジェクトの種類](visual-cpp-project-types.md)<br>
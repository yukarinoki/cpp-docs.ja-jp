---
title: Visual Studio 2010 でのビルド システムの変更点
ms.date: 11/04/2016
f1_keywords:
- vc.msbuild.changes
helpviewer_keywords:
- Build system changes, project file (.vcxprog)
- Build system changes, custom build rules
- Build system changes, MSBuild
- MSBuild, build system changes
- Build system changes, .vsprops
- Build system changes, $(Inherit)
- Build system changes, $(NoInherit)
ms.assetid: e564d95f-a6cc-4d97-b57e-1a71daf66f4a
ms.openlocfilehash: 621e62379657da66d6eaec7a3ceff780fd610066
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2019
ms.locfileid: "57828174"
---
# <a name="build-system-changes"></a>ビルド システムの変更点

Visual C++ プロジェクトのビルドには MSBuild システムが使用されます。 しかしながら、Visual Studio 2008 以前のリリースでは、VCBuild システムが使用されていました。 VCBuild に依存していた一部のファイルの種類や概念は現在のシステムに存在しないか、別の形で表示されます。 このドキュメントでは、現在のビルド システムにおける違いについて説明します。

## <a name="vcproj-is-now-vcxproj"></a>.vcproj が .vcxproj になりました

プロジェクト ファイルには .vcproj というファイル名拡張子が使用されなくなりました。 Visual Studio では、以前のリリースの Visual C++ で作成されたプロジェクト ファイルが現在のシステムで使用されている形式に自動的に変換されます。 プロジェクトを手動でアップグレードする方法については、「[/Upgrade (devenv.exe)](/visualstudio/ide/reference/upgrade-devenv-exe)」を参照してください。

現在のリリースでは、プロジェクト ファイルのファイル名拡張子は .vcxproj です。

## <a name="vsprops-is-now-props"></a>.vsprops が .props になりました

以前のリリースでは、*プロジェクト プロパティ シート*は、.vsprops というファイル名拡張子が与えられる XML ベースのファイルです。 プロジェクト プロパティ シートを利用すれば、コンパイラやリンカーなどのビルド ツールのスイッチを指定したり、ユーザー定義のマクロを作成したりできます。

現在のリリースでは、プロジェクト プロパティ シートのファイル名拡張子は .props です。

## <a name="custom-build-rules-and-rules-files"></a>カスタム ビルド ルールと .rules ファイル

以前のリリースでは、*ルール ファイル*は、.rules というファイル名拡張子が与えられる XML ベースのファイルです。 ルール ファイルを利用すれば、カスタム ビルド ルールを定義し、それを Visual C++ プロジェクトのビルド プロセスに組み込むことができます。 カスタム ビルド ルールには 1 つまたは複数のファイル名拡張子を関連付けることができるため、このルールを利用すると、1 つまたは複数の出力ファイルを作成するツールに入力ファイルを渡すことができます。

このリリースでは、カスタム ビルド ルールは、.rules ファイルではなく、.xml、.props、.targets という 3 つのファイルの種類で表されます。 以前のリリースの Visual C++ で作成された .rules ファイルを現在のリリースに移行すると、同等の .xml、.props、.targets ファイルが作成され、元の .rules ファイルと共にプロジェクトに保存されます。

> [!IMPORTANT]
>  現在のリリースでは、IDE は新しいルールの作成をサポートしていません。 そのため、以前のリリースの Visual C++ で作成されたプロジェクトのルール ファイルを使用する最も簡単な方法は、プロジェクトを現在のリリースに移行することです。

## <a name="inheritance-macros"></a>継承マクロ

以前のリリースでは、プロジェクト ビルド システムで作成されたコマンド ラインに継承プロパティを表示する順序は **$(Inherit)** マクロによって指定されます。 **$(NoInherit)** マクロを使用すると、$(Inherit) が出現しても無視され、$(NoInherit) を使用しなければ継承されるプロパティがすべて継承されません。 たとえば、$(Inherit) マクロの既定では、[/I (Additional Include Directories)](../build/reference/i-additional-include-directories.md) コンパイラ オプションで指定されるファイルがコマンド ラインに追加されます。

現在のリリースでは、1 つまたは複数のリテラル値とプロパティ マクロを連結してプロパティ値を指定することで継承がサポートされます。 **$(Inherit)** マクロと **$(NoInherit)** マクロはサポートされていません。

次の例では、プロパティ ページのプロパティにセミコロンで区切られた一覧が割り当てられています。 この一覧は *\<value>* リテラルと `MyProperty` プロパティの値を連結したもので構成されます。このプロパティは **$(**<em>MyProperty</em>**)** というマクロ表記でアクセスされます。

```
Property=<value>;$(MyProperty)
```

## <a name="vcxprojuser-files"></a>.vcxproj.user ファイル

ユーザー ファイル (.vcxproj.user) によって、デバッグ設定やデプロイ設定など、ユーザー固有のプロパティが保管されます。 vcxproj.user ファイルは、特定のユーザーのすべてのファイルに適用されます。

## <a name="vcxprojfilters-file"></a>.vcxproj.filters ファイル

filters ファイル (.vcxproj.filters) は、**ソリューション エクスプローラー**を使用してプロジェクトにファイルを追加するときに、ファイル名拡張子に基づいて**ソリューション エクスプローラー**のツリー ビューでファイルを追加する場所を定義します。

## <a name="vc-directories-settings"></a>VC++ ディレクトリ設定

Visual C++ ディレクトリ設定は [[VC++ ディレクトリ プロパティ ページ]](../ide/vcpp-directories-property-page.md) で指定されます。 以前のリリースの Visual Studio では、ディレクトリ設定はユーザー別に適用され、除外ディレクトリの一覧が sysincl.dat ファイルに指定されます。

コマンド ラインで [devenv /resetsettings](/visualstudio/ide/reference/resetsettings-devenv-exe) を実行する場合、VC++ ディレクトリ設定を変更できません。 **[ツール]** メニューを開き、**[設定のインポートとエクスポート]** をクリックし、**[すべての設定をリセット]** オプションを選択した場合も設定を変更できません。

以前のリリースの Visual C++ で作成された .vssettings ファイルから VC++ ディレクトリ設定を移行します。 **[ツール]** メニューを開き、**[設定のインポートとエクスポート]** をクリックし、**[選択された環境設定をインポート]** を選択し、ウィザードの指示に従いします。 あるいは、Visual Studio を初めて起動するとき、**[既定の環境設定の選択]** ダイアログ ボックスで **[以前のバージョンから有効な設定を移行し、以下で選択した既定の設定と合わせて適用する]** を選択します。

## <a name="see-also"></a>関連項目

[コマンド ラインでの MSBuild - C++](../build/msbuild-visual-cpp.md)

---
title: ビルド システムの変更 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
f1_keywords:
- vc.msbuild.changes
dev_langs:
- C++
helpviewer_keywords:
- Build system changes, project file (.vcxprog)
- Build system changes, custom build rules
- Build system changes, MSBuild
- MSBuild, build system changes
- Build system changes, .vsprops
- Build system changes, $(Inherit)
- Build system changes, $(NoInherit)
ms.assetid: e564d95f-a6cc-4d97-b57e-1a71daf66f4a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 01eb3a38ddaf7cdb1d54061e48680396f16b25e0
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32363322"
---
# <a name="build-system-changes"></a>ビルド システムの変更点
MSBuild システムを使用すると、Visual C プロジェクトをビルドします。 ただし、Visual Studio 2008 以前のリリースで、VCBuild システムが使用されます。 特定ファイルの種類と VCBuild に依存していたの概念は、存在しないかは現在のシステムで異なる方法で表されます。 このドキュメントでは、現在のビルド システムの違いについて説明します。  
  
## <a name="vcproj-is-now-vcxproj"></a>.vcproj は .vcxproj はようになりました。  
 プロジェクト ファイルは、不要になった .vcproj ファイル名拡張子を使用します。 Visual Studio には、以前のリリースの Visual C は、現在のシステムによって使用される形式にして作成されたプロジェクト ファイルに自動的に変換します。 プロジェクトを手動でアップグレードする方法の詳細については、次を参照してください。 [/Upgrade (devenv.exe)](/visualstudio/ide/reference/upgrade-devenv-exe)です。  
  
 現在のリリースでは、プロジェクト ファイルのファイル名拡張子は、.vcxproj がします。  
  
## <a name="vsprops-is-now-props"></a>.vsprops は .props はようになりました。  
 以前のリリースで、*プロジェクト プロパティ シートの*.vsprops ファイル名拡張子を持つ XML ベースのファイルです。 プロジェクトのプロパティ シートでは、コンパイラやリンカーなどのビルド ツールのスイッチを指定し、ユーザー定義のマクロを作成することができます。  
  
 現在のリリースでは、プロジェクトのプロパティ シートのファイル名拡張子は、.props です。  
  
## <a name="custom-build-rules-and-rules-files"></a>カスタム ビルド規則と .rules ファイル  
 以前のリリースで、*規則ファイル*.rules ファイル名拡張子を持つ XML ベースのファイルです。 規則ファイルでは、カスタム ビルド規則を定義して、Visual C プロジェクトのビルド プロセスに組み込むことができます。 指定できますが、1 つまたは複数のファイル名拡張子に関連付けられているカスタム ビルド規則では、1 つ作成するツールへの入力ファイルを渡すことができます、または以上の出力ファイル。  
  
 このリリースでは、カスタム ビルド規則は次の 3 つのファイルの種類、.xml、.props、および .rules ファイルではなく、.targets によって表されます。 Visual C の以前のリリースを使用して作成された .rules ファイルを現在のリリースに移行すると、同等の .xml、.props、および .targets ファイルが作成され、元の .rules ファイルと共に、プロジェクトに格納します。  
  
> [!IMPORTANT]
>  現在のリリースで、[!INCLUDE[TLA2#tla_ide](../build/includes/tla2sharptla_ide_md.md)]新しい規則の作成をサポートしていません。 そのため、Visual C の以前のリリースを使用して作成されたプロジェクトの規則ファイルを使用する最も簡単な方法は、プロジェクトに移行する、現在のリリースです。  
  
## <a name="inheritance-macros"></a>継承マクロ  
 以前のリリースで、 **$ (inherit)** マクロは、プロジェクトのビルド システムによって作成されているコマンド ラインで継承されたプロパティの表示順序を指定します。 **$ (Noinherit)** マクロする任意のプロパティの継承される、いないことを継承して無視するように $ (inherit) の出現します。 たとえば、既定では、$ (inherit) マクロを使用して指定されたファイル、 [/I (追加インクルード ディレクトリ)](../build/reference/i-additional-include-directories.md)コンパイラ オプションをコマンドラインに追加されます。  
  
 現在のリリースでは、継承がリテラル値とプロパティのマクロの 1 つまたは複数の連結としてプロパティの値を指定することによってサポートされます。 **$ (Inherit)** と **$ (noinherit)** マクロはサポートされていません。  
  
 次の例では、セミコロン区切りのリストは、[プロパティ] ページのプロパティに割り当てられます。 一覧から成るの連結、 *\<値 >* リテラルのパスと値の`MyProperty`マクロ表記を使用してアクセスされるプロパティ **$(***MyProperty***)**.  
  
```  
Property=<value>;$(MyProperty)  
```  
  
## <a name="vcxprojuser-files"></a>.vcxproj.user Files  
 ユーザー ファイル (. vcxproj.user) の例、デバッグと配置の設定、ユーザー固有のプロパティを格納します。 Vcxproj.user ファイルは、特定のユーザーのすべてのプロジェクトに適用されます。  
  
## <a name="vcxprojfilters-file"></a>。 vcxproj.filters ファイル  
 ときに**ソリューション エクスプ ローラー**フィルター ファイル、プロジェクトにファイルを追加するために使用 (. vcxproj.filters) 内の場所を定義、**ソリューション エクスプ ローラー**ツリー ビューでファイルを追加すると、そのファイル名拡張子に基づいて。  
  
## <a name="vc-directories-settings"></a>Vc++ ディレクトリの設定  
 Visual C ディレクトリの設定で指定された、 [vc++ ディレクトリ プロパティ ページ](../ide/vcpp-directories-property-page.md)です。 Visual Studio の以前のリリースでディレクトリの設定、ユーザーごとの適用し、sysincl.dat ファイルで除外されているディレクトリの一覧を指定します。  
  
 実行する場合は、vc++ ディレクトリの設定を変更することはできません[devenv/resetsettings](/visualstudio/ide/reference/resetsettings-devenv-exe)コマンドライン。 変更することもできません、設定を開く場合、**ツール** メニューのをクリックして**のインポートとエクスポートの設定**、クリックして、**すべての設定をリセット**オプション。  
  
 Visual C の以前のリリースによって作成される .vssettings ファイルから vc++ ディレクトリの設定を移行します。 開いている、**ツール**] メニューのをクリックして**インポートおよびエクスポート設定**[**選択された環境設定をインポート**、ウィザードの指示に従います。 時、または起動時 Visual Studio を初めて、上、 **既定の環境設定**ダイアログ ボックスで、**以前のバージョンから有効な設定を移行し、既定の設定だけでなく、それらを適用以下の選択**です。  
  
## <a name="see-also"></a>関連項目  
 [MSBuild (Visual C++)](../build/msbuild-visual-cpp.md)
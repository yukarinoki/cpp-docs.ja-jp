---
title: ビルド システムの変更 |Microsoft Docs
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
ms.openlocfilehash: a3d6dffb4a4b0b4f5ef3a373cf2dcd0d93d1bd12
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2018
ms.locfileid: "42613202"
---
# <a name="build-system-changes"></a>ビルド システムの変更点
MSBuild システムは、Visual C プロジェクトのビルドに使用されます。 ただし、Visual Studio 2008 以前のリリースで、VCBuild システム使用されました。 特定のファイルの種類と VCBuild に依存していた概念存在しないか、現在のシステムで異なる方法で表現されます。 このドキュメントでは、現在のビルド システムの違いについて説明します。  
  
## <a name="vcproj-is-now-vcxproj"></a>.vcproj .vcxproj になります  
 プロジェクト ファイルは、不要になった .vcproj ファイル名拡張子を使用します。 Visual Studio には、現在のシステムで使用される形式に Visual C の以前のリリースによって作成されたプロジェクト ファイル自動的に変換します。 プロジェクトを手動でアップグレードする方法の詳細については、次を参照してください。 [/Upgrade (devenv.exe)](/visualstudio/ide/reference/upgrade-devenv-exe)します。  
  
 現在のリリースでは、プロジェクト ファイルのファイル名拡張子は .vcxproj が。  
  
## <a name="vsprops-is-now-props"></a>.vsprops は .props はようになりました。  
 以前のリリースで、*プロジェクト プロパティ シートの*.vsprops ファイル名拡張子を持つ XML ベースのファイルです。 プロジェクトのプロパティ シートでは、コンパイラやリンカーなどのビルド ツールのスイッチを指定し、ユーザー定義マクロを作成することができます。  
  
 現在のリリースでは、プロジェクトのプロパティ シートのファイル名拡張子は、.props が。  
  
## <a name="custom-build-rules-and-rules-files"></a>カスタム ビルド規則および .rules ファイル  
 以前のリリースで、*規則ファイル*.rules ファイル名拡張子を持つ XML ベースのファイルです。 規則ファイルでは、カスタム ビルド規則を定義し、Visual C プロジェクトのビルド プロセスに組み込むことできます。 以上の出力ファイルや 1 つまたは複数のファイル名拡張子に関連付けることができます、カスタム ビルド規則を使用して、入力ファイルを 1 つを作成するツールに渡すできます。  
  
 このリリースでは、カスタム ビルド規則は次の 3 つのファイルの種類、.xml、.props、および .rules ファイルではなく、.targets で表されます。 Visual C の以前のリリースを使用して作成された .rules ファイルが現在のリリースに移行されると、同等の .xml、.props および .targets ファイルが作成され、元の .rules ファイルと共に、プロジェクトに格納します。  
  
> [!IMPORTANT]
>  現在のリリースでは、IDE は新しいルールの作成機能をサポートしていません。 そのため、Visual C の以前のリリースを使用して作成されたプロジェクトから規則ファイルを使用する最も簡単な方法ではプロジェクトを現在のリリースに移行します。  
  
## <a name="inheritance-macros"></a>継承マクロ  
 以前のリリースで、 **$ (inherit)** マクロによって、プロジェクト ビルド システムで構成されるコマンド ラインで継承されたプロパティの表示順序を指定します。 **$ (Noinherit)** マクロにより無視する $ (inherit) の出現しプロパティ継承される、いないを継承するようにします。 たとえば、既定では、$ (inherit) マクロを使用して指定されたファイル、 [/I (追加インクルード ディレクトリ)](../build/reference/i-additional-include-directories.md)コンパイラ オプションをコマンドラインに追加されます。  
  
 現在のリリースでは、リテラル値とプロパティのマクロの 1 つまたは複数の連結プロパティの値を指定することで継承がサポートされています。 **$ (Inherit)** と **$ (noinherit)** マクロがサポートされていません。  
  
 次の例では、セミコロン区切りのリストはプロパティ ページのプロパティに割り当てられます。 リストの連結から成る、 *\<値 >* リテラル文字列との値、`MyProperty`マクロ表記を使用してアクセスされるプロパティ、 **$(***MyProperty***)**.  
  
```  
Property=<value>;$(MyProperty)  
```  
  
## <a name="vcxprojuser-files"></a>.vcxproj.user Files  
 ユーザー ファイル (. vcxproj.user) の使用例、デバッグと配置の設定、ユーザー固有のプロパティを格納します。 Vcxproj.user ファイルは、特定のユーザーのすべてのプロジェクトに適用されます。  
  
## <a name="vcxprojfilters-file"></a>。 vcxproj.filters ファイル  
 ときに**ソリューション エクスプ ローラー**フィルター ファイルをプロジェクトにファイルを追加するために使用 (. vcxproj.filters) の場所を定義、**ソリューション エクスプ ローラー**ツリー ビューのファイルを追加すると、そのファイル名拡張子に基づいて。  
  
## <a name="vc-directories-settings"></a>Vc++ ディレクトリの設定  
 Visual C ディレクトリの設定がで指定された、 [vc++ Directories Property Page](../ide/vcpp-directories-property-page.md)します。 Visual Studio の以前のリリースでディレクトリの設定、ユーザーごとの適用し、除外ディレクトリの一覧が sysincl.dat ファイルで指定されました。  
  
 実行する場合は、vc++ ディレクトリの設定を変更することはできません[devenv/resetsettings](/visualstudio/ide/reference/resetsettings-devenv-exe)コマンドライン。 変更することもできない設定を開く場合、**ツール** メニューのをクリックして**インポートおよびエクスポート設定**を選び、**すべての設定をリセット**オプション。  
  
 Visual C の以前のリリースによって作成される .vssettings ファイルから、vc++ ディレクトリの設定を移行します。 開く、**ツール** メニューのをクリックして**インポートおよびエクスポート設定**を選択します**選択された環境設定のインポート**、ウィザードの指示に従います。 ときに Visual Studio を起動する初めてで、または、 **既定の環境設定**ダイアログ ボックスで、**以前のバージョンから対象となる設定を移行して、既定の設定の適用以下の選択**します。  
  
## <a name="see-also"></a>関連項目  
 [MSBuild (Visual C++)](../build/msbuild-visual-cpp.md)
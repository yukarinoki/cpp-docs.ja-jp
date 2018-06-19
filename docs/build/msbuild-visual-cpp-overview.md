---
title: MSBuild (Visual C) の概要 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- MSBuild overview
ms.assetid: dd258f6f-ab51-48d9-b274-f7ba911d05ca
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ae6e6d826f4bc1e8c9ab6cc28686e4ad1e6e3b02
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32379264"
---
# <a name="msbuild-visual-c-overview"></a>MSBuild (Visual C++) の概要  
  
MSBuild は、Visual C++ プロジェクト用の標準のビルド システムです。 Visual Studio 統合開発環境 (IDE: Integrated Development Environment) でプロジェクトをビルドするときには、msbuild.exe ツール、XML ベースのプロジェクト ファイル、およびオプションの設定ファイルが使用されます。 msbuild.exe とプロジェクト ファイルをコマンド ラインで使用することもできますが、IDE にはユーザー インターフェイスが用意されているため、設定の構成とプロジェクトのビルドをより簡単に行うことができます。 ここでは、Visual C++ で MSBuild システムを使用する方法について説明します。  
  
## <a name="prerequisites"></a>必須コンポーネント  
  
MSBuild に関する次のドキュメントを参照してください。  
  
- [MSBuild](/visualstudio/msbuild/msbuild)  
 MSBuild の概念の概要。  
  
- [MSBuild リファレンス](/visualstudio/msbuild/msbuild-reference)  
 MSBuild システムに関するリファレンス情報。  
  
- [プロジェクト ファイル スキーマ リファレンス](/visualstudio/msbuild/msbuild-project-file-schema-reference)  
 MSBuild XML スキーマ要素の一覧を、それぞれの属性、親要素、および子要素と共に示します。 特に注意してください、 [ItemGroup](/visualstudio/msbuild/itemgroup-element-msbuild)、 [PropertyGroup](/visualstudio/msbuild/propertygroup-element-msbuild)、[ターゲット](/visualstudio/msbuild/target-element-msbuild)、および[タスク](/visualstudio/msbuild/task-element-msbuild)要素。  
  
- [Command-Line Reference (コマンド ライン リファレンス)](/visualstudio/msbuild/msbuild-command-line-reference)  
 msbuild.exe で使用できるコマンド ライン引数とコマンド ライン オプションについて説明します。  
  
- [Task Reference (タスク リファレンス)](/visualstudio/msbuild/msbuild-task-reference)  
 MSBuild タスクについて説明します。 これらのタスクでは、Visual C に固有に特に注意してください: [BscMake タスク](/visualstudio/msbuild/bscmake-task)、 [CL タスク](/visualstudio/msbuild/cl-task)、 [CPPClean タスク](/visualstudio/msbuild/cppclean-task)、 [LIB タスク](/visualstudio/msbuild/lib-task)、 [タスク リンク](/visualstudio/msbuild/link-task)、 [MIDL タスク](/visualstudio/msbuild/midl-task)、 [MT タスク](/visualstudio/msbuild/mt-task)、 [RC タスク](/visualstudio/msbuild/rc-task)、 [SetEnv タスク](/visualstudio/msbuild/setenv-task)、 [VCMessage タスク](/visualstudio/msbuild/vcmessage-task)、 [XDCMake タスク](/visualstudio/msbuild/xdcmake-task)、 [XSD タスク](/visualstudio/msbuild/xsd-task)です。  
  
## <a name="msbuild-on-the-command-line"></a>コマンド ラインでの MSBuild  
  
次のステートメント、 [MSBuild コマンド ライン リファレンス](/visualstudio/msbuild/msbuild-command-line-reference)msbuild.exe ツールが、暗黙的または明示的なを取ることを示しています*project_file*引数 (Visual c プロジェクト .vcxproj ファイル)。0 個または複数のコマンド ライン*オプション*引数。  
  
> **msbuild.exe** [ *project_file* ] [*オプション*]  
  
使用して、 **/target** (または **/t**) および **/property** (または **/p**) 特定のプロパティとは、ターゲットをオーバーライドするコマンド ライン オプションプロジェクト ファイルで指定します。  
  
プロジェクト ファイルの重要な機能を指定する、*ターゲット*、これは、プロジェクトと、入力とその操作を実行するために必要な出力に適用される特定の操作です。 プロジェクト ファイルでは 1 つ以上のターゲットを指定でき、既定のターゲットを含めることができます。  
  
各ターゲットは、1 つ以上のシーケンスで構成されます*タスク*です。 各タスクは、実行可能なコマンドを 1 つ含む .NET Framework クラスによって表されます。 たとえば、 [CL タスク](/visualstudio/msbuild/cl-task)が含まれています、 [cl.exe](../build/reference/compiling-a-c-cpp-program.md)コマンド。  
  
A*タスク パラメーター*クラス タスクのプロパティでは、通常、実行可能コマンドのコマンド ライン オプションを表します。 たとえば、`FavorSizeOrSpeed`のパラメーター、`CL`に対応するタスク、 **/Os**と **/Ot**コンパイラ オプション。  
  
追加のタスク パラメーターは、MSBuild インフラストラクチャをサポートします。 たとえば、`Sources` タスク パラメーターは、他のタスクで使用できる一連のタスクを指定します。 MSBuild タスクの詳細については、次を参照してください。[タスク リファレンス](/visualstudio/msbuild/msbuild-task-reference)です。  
  
ほとんどのタスクには入力と出力が必要です。これには、ファイル名、パス、文字列パラメーター、数値パラメーター、ブール値パラメーターなどがあります。 たとえば、一般的な入力は、コンパイルする .cpp ソース ファイルの名前です。 重要な入力パラメーターは、たとえば、ビルド構成とプラットフォームを指定する文字列"デバッグ\|Win32"です。 入力と出力は、`Item` 要素に含まれる 1 つ以上のユーザー定義の XML `ItemGroup` 要素で指定します。  
  
プロジェクト ファイルは、ユーザー定義も指定できます*プロパティ*と`ItemDefinitionGroup`*項目*です。 プロパティと項目は、ビルドで変数として使用できる名前と値のペアを形成します。 ペアの名前のコンポーネントで定義、*マクロ*、値コンポーネントを宣言し、*マクロ値*です。 $ を使用してプロパティのマクロにアクセス (*名前*) 表記法、および、項目マクロは %(を使用してアクセス*名前*) 表記します。  
  
プロジェクト ファイル内の他の XML 要素では、マクロをテストし、条件に従ってマクロの値を設定したり、ビルドの実行を制御したりできます。 マクロ名とリテラル文字列を連結して、パスとファイル名などの構成要素を生成することもできます。 コマンド ラインで、 **/property**オプションを設定またはプロジェクトのプロパティをオーバーライドします。 コマンド ラインで項目を参照することはできません。  
  
MSBuild システムでは、あるターゲットを、条件に従って別のターゲットの前または後に実行できます。 また、ターゲットで使用されるファイルが出力されるファイルよりも新しいかどうかに基づいて、ターゲットをビルドすることもできます。  
  
## <a name="msbuild-in-the-ide"></a>IDE での MSBuild  
  
IDE でプロジェクト プロパティを設定し、プロジェクトを保存すると、Visual C++ によってプロジェクト設定がプロジェクト ファイルに書き込まれます。 プロジェクト ファイルにはプロジェクトに固有の設定が含まれますが、プロジェクトのビルドに必要な設定がすべて含まれているわけではありません。 プロジェクト ファイルを含む`Import`、追加のネットワークを含む要素*ファイルをサポートします。* サポート ファイルには、プロジェクトのビルドに必要なその他のプロパティ、ターゲット、および設定が含まれます。  
  
サポート ファイル内のほとんどのターゲットとプロパティは、ビルド システムを実装するためだけに用意されています。 次のセクションでは、MSBuild コマンド ラインで指定できる便利なターゲットとプロパティについて説明します。 その他のターゲットおよびプロパティについては、サポート ファイル ディレクトリ内のファイルを参照してください。  
  
### <a name="support-file-directories"></a>サポート ファイル ディレクトリ  
  
既定では、Visual C++ の主要なサポート ファイルは、次のディレクトリに配置されています。 Microsoft Visual Studio の下のディレクトリは、MSBuild の下のディレクトリは Visual Studio 2015 と以前のバージョンで使用中に、Visual Studio 2017 およびそれ以降のバージョンで使用されます。  
  
|ディレクトリ|説明|  
|---------------|-----------------|  
|*ドライブ*: \Program Files *(x86)* \Microsoft Visual Studio\\*年*\\*エディション*\Common7\IDE\VC\VCTargets\ <br /><br />*ドライブ*: \Program Files *(x86)* \MSBuild\Microsoft.Cpp (x86) \v4.0\\*バージョン*\ |ターゲットによって使用される主要なターゲット ファイル (.targets) およびプロパティ ファイル (.props) があります。 既定では、$(VCTargetsPath) マクロはこのディレクトリを参照します。|  
|*ドライブ*: \Program Files *(x86)* \Microsoft Visual Studio\\*年*\\*エディション*\Common7\IDE\VC\VCTargets\プラットフォーム\\*プラットフォーム*\ <br /><br />*ドライブ*: \Program Files *(x86)* \MSBuild\Microsoft.Cpp\v4.0\\*バージョン*\Platforms\\*プラットフォーム*\ |親ディレクトリ内のターゲットおよびプロパティをオーバーライドする、プラットフォーム固有のターゲット ファイルおよびプロパティ ファイルがあります。 また、このディレクトリには、このディレクトリ内のターゲットによって使用されるタスクを定義する DLL が含まれています。<br /><br /> *プラットフォーム*ARM、Win32、または x64 を表すプレース ホルダー サブディレクトリです。|  
|*ドライブ*: \Program Files *(x86)* \Microsoft Visual Studio\\*年*\\*エディション*\Common7\IDE\VC\VCTargets\プラットフォーム\\*プラットフォーム*\PlatformToolsets\\*ツールセット*\ <br /><br />*ドライブ*: \Program Files *(x86)* \MSBuild\Microsoft.Cpp\v4.0\\*バージョン*\Platforms\\*プラットフォーム*\PlatformToolsets\\*ツールセット*\ <br /><br />*ドライブ*: \Program Files *(x86)* \MSBuild\Microsoft.Cpp\v4.0\Platforms\\*プラットフォーム*\PlatformToolsets\\*ツールセット*\ |使用して、指定した、Visual C アプリケーションを生成するビルドを有効にするディレクトリを含む*ツールセット*です。<br /><br /> *年*と*エディション*プレース ホルダーは、Visual Studio 2017 および以降のエディションで使用されます。 *バージョン*プレース ホルダーは、Visual Studio 2012 用 V110、V120 for Visual Studio 2013、または Visual Studio 2015 用 V140 です。 *プラットフォーム*ARM、Win32、または x64 を表すプレース ホルダー サブディレクトリです。 *ツールセット*ツールセット サブディレクトリ、Visual Studio 2015 のツールセット、Visual Studio 2013 のツールセット、またはに v110_wp80 を使用して Windows XP 用にビルドする v120_xp を使用して Windows アプリを構築するための v140 などを表すプレース ホルダーVisual Studio 2012 ツールセットを使用して Windows Phone 8.0 アプリをビルドします。<br /><br />Visual C 2008 または Visual C 2010 のいずれかのアプリケーションを生成するビルドを有効にするディレクトリを含むパスに含まれていない、*バージョン*、および*プラットフォーム*を表すプレース ホルダーItanium、Win32、または x64 サブディレクトリです。 *ツールセット*v90 または v100 ツールセット サブディレクトリを表すプレース ホルダーです。|  
  
### <a name="support-files"></a>サポート ファイル  
  
サポート ファイル ディレクトリには、これらの拡張子を持つファイルが含まれます。  
  
|拡張子|説明|  
|---------------|-----------------|  
|.targets|ターゲットによって実行されるタスクを指定する `Target` XML 要素が含まれます。 タスク パラメーターにファイルとコマンド ライン オプションを割り当てるために使用される、`PropertyGroup`、`ItemGroup`、`ItemDefinitionGroup`、およびユーザー定義の `Item` の各要素が含まれることもあります。<br /><br /> 詳細については、次を参照してください。 [Target 要素 (MSBuild)](/visualstudio/msbuild/target-element-msbuild)です。|  
|.props|ビルド時に使用されるファイル設定とパラメーター設定を指定する `Property Group` XML 要素およびユーザー定義の `Property` XML 要素が含まれます。<br /><br /> 追加の設定を指定する `ItemDefinitionGroup` XML 要素およびユーザー定義の `Item` XML 要素が含まれることもあります。 項目定義グループに定義されている項目はプロパティに似ていますが、コマンド ラインからはアクセスできません。 Visual C++ プロジェクト ファイルでは、プロパティではなく項目を使用して設定を表すことがよくあります。<br /><br /> 詳細については、次を参照してください。 [ItemGroup 要素 (MSBuild)](/visualstudio/msbuild/itemgroup-element-msbuild)、 [ItemDefinitionGroup 要素 (MSBuild)](/visualstudio/msbuild/itemdefinitiongroup-element-msbuild)、および[Item 要素 (MSBuild)](/visualstudio/msbuild/item-element-msbuild)です。|  
|.xml|プロパティ シート、プロパティ ページ、テキスト ボックス コントロール、リスト ボックス コントロールなどの IDE ユーザー インターフェイス要素を宣言および初期化する XML 要素が含まれます。<br /><br /> .xml ファイルは、MSBuild ではなく IDE を直接サポートします。 ただし、IDE プロパティの値は、ビルド プロパティおよび項目に割り当てられます。<br /><br /> ほとんどの .xml ファイルは、ロケール固有のサブディレクトリにあります。 たとえば、英語 (米国) 地域のファイルは $(VCTargetsPath) \1033\\です。|  
  
## <a name="user-targets-and-properties"></a>ユーザー ターゲットおよびプロパティ  
  
コマンド ラインで MSBuild をより効果的に使用するためには、どのプロパティとターゲットが役に立ち、どれが関係しているかを知っておくと便利です。 ほとんどのプロパティとターゲットは、Visual C++ ビルド システムを実装するために使用されるもので、ユーザーには関係がありません。 ここでは、ユーザー指向の有用なプロパティとターゲットについて説明します。  

### <a name="platformtoolset-property"></a>PlatformToolset プロパティ  
  
`PlatformToolset` プロパティは、ビルドでどの Visual C++ ツールセットを使用するか決定します。 既定では、現在のツールセットが使用されます。 このプロパティが設定されている場合、プロパティの値は、特定のプラットフォームのプロジェクトをビルドするために必要なプロパティおよびターゲット ファイルを格納するディレクトリのパスを形成するリテラル文字列と連結されます。 そのプラットフォーム ツールセットのバージョンを使用して作成するプラットフォーム ツールセットをインストールする必要があります。  
  
たとえば、設定、`PlatformToolset`プロパティを`v140`を Visual C 2015 ツールとライブラリを使用して、アプリケーションをビルドします。  
  
`msbuild myProject.vcxproj /p:PlatformToolset=v140`  
  
### <a name="preferredtoolarchitecture-property"></a>PreferredToolArchitecture プロパティ  
  
`PreferredToolArchitecture` プロパティは、ビルドで使用されているコンパイラとツールが 32 ビットか 64 ビットかを判定します。 このプロパティは、出力プラットフォームのアーキテクチャおよび構成には影響しません。 既定では、MSBuild は、x86 を使用してバージョンのコンパイラおよびツールがこのプロパティが設定されていない場合。  
  
たとえば、設定、`PreferredToolArchitecture`プロパティを`x64`を 64 ビットのコンパイラおよびツールを使用してアプリケーションをビルドします。  
  
`msbuild myProject.vcxproj /p:PreferredToolArchitecture=x64`  
  
### <a name="useenv-property"></a>UseEnv プロパティ  
  
既定では、現在のプロジェクトのプラットフォーム固有の設定によって、PATH、INCLUDE、LIB、LIBPATH、CONFIGURATION、および PLATFORM の各環境変数がオーバーライドされます。 環境変数がオーバーライドされないようにするには、`UseEnv` プロパティを `true` に設定します。  
  
`msbuild myProject.vcxproj /p:UseEnv=true`  
  
### <a name="targets"></a>ターゲット  
  
Visual C++ のサポート ファイル内には、ターゲットが数多く存在します。 ただし、ほとんどはシステム指向のターゲットであり、ユーザーは無視できます。 ほとんどのシステム ターゲットは、先頭にアンダースコア (_) が付くか、"PrepareFor"、"Compute"、"Before"、"After"、"Pre"、または "Post" で始まる名前が付いています。  
  
次の表には、いくつかの便利ユーザー指向のターゲットが一覧表示します。  
  
|ターゲット|説明|  
|------------|-----------------|  
|BscMake|Microsoft Browse Information Maintenance Utility ツール (bscmake.exe) を実行します。|  
|ビルド|プロジェクトをビルドします。<br /><br /> プロジェクトの既定のターゲットです。|  
|ClCompile|Visual C++ コンパイラ ツール (cl.exe) を実行します。|  
|クリーン|一時ビルド ファイルおよび中間ビルド ファイルを削除します。|  
|Lib|Microsoft 32-Bit Library Manager ツール (lib.exe) を実行します。|  
|リンク|Visual C++ リンカー ツール (link.exe) を実行します。|  
|ManifestResourceCompile|マニフェストからリソースの一覧を抽出し、Microsoft Windows リソース コンパイラ ツール (rc.exe) を実行します。|  
|Midl|Microsoft インターフェイス定義言語 (MIDL: Microsoft Interface Definition Language) コンパイラ ツール (midl.exe) を実行します。|  
|リビルド|プロジェクトを消去してからビルドします。|  
|ResourceCompile|Microsoft Windows リソース コンパイラ ツール (rc.exe) を実行します。|  
|XdcMake|XML ドキュメント ツール (xdcmake.exe) を実行します。|  
|Xsd|XML スキーマ定義ツール (Xsd.exe) を実行します。|  
  
## <a name="see-also"></a>関連項目  
  
[MSBuild (Visual C++)](../build/msbuild-visual-cpp.md)

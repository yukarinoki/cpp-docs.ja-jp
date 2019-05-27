---
title: Visual Studio の C++ プロジェクトの MSBuild の内部
ms.date: 05/16/2019
helpviewer_keywords:
- MSBuild overview
ms.assetid: dd258f6f-ab51-48d9-b274-f7ba911d05ca
ms.openlocfilehash: b3348320a1468fea03f39e43cc847f1085f3d319
ms.sourcegitcommit: a10c9390413978d36b8096b684d5ed4cf1553bc8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/17/2019
ms.locfileid: "65837228"
---
# <a name="msbuild-internals-for-c-projects"></a>C++ プロジェクトの MSBuild の内部

IDE でプロジェクト プロパティを設定し、プロジェクトを保存すると、Visual Studio によってプロジェクト設定がプロジェクト ファイルに書き込まれます。 プロジェクト ファイルにはプロジェクトに固有の設定が含まれますが、プロジェクトのビルドに必要な設定がすべて含まれているわけではありません。 プロジェクト ファイルには、追加の*サポート ファイル*とのつながりを表す `Import` 要素が含まれます。 サポート ファイルには、プロジェクトのビルドに必要なその他のプロパティ、ターゲット、および設定が含まれます。

サポート ファイル内のほとんどのターゲットとプロパティは、ビルド システムを実装するためだけに用意されています。 次のセクションでは、MSBuild コマンド ラインで指定できる便利なターゲットとプロパティについて説明します。 その他のターゲットおよびプロパティについては、サポート ファイル ディレクトリ内のファイルを参照してください。

## <a name="support-file-directories"></a>サポート ファイル ディレクトリ

既定では、Visual Studio の主要なサポート ファイルは、次のディレクトリに配置されています。 Microsoft Visual Studio の下のディレクトリは Visual Studio 2017 以降のバージョンで使用され、MSBuild の下のディレクトリは Visual Studio 2015 以前のバージョンで使用されます。

|ディレクトリ|説明|
|---------------|-----------------|
|*<ドライブ>* :\Program Files *(x86)* \Microsoft Visual Studio\\*year*\\*edition*\Common7\IDE\VC\VCTargets\ <br /><br />*<ドライブ>* :\Program Files *(x86)* \MSBuild\Microsoft.Cpp (x86)\v4.0\\*version*\ |ターゲットによって使用される主要なターゲット ファイル (.targets) およびプロパティ ファイル (.props) があります。 既定では、$(VCTargetsPath) マクロはこのディレクトリを参照します。|
|*<ドライブ>* :\Program Files *(x86)* \Microsoft Visual Studio\\*year*\\*edition*\Common7\IDE\VC\VCTargets\Platforms\\*platform*\ <br /><br />*<ドライブ>* :\Program Files *(x86)* \MSBuild\Microsoft.Cpp\v4.0\\*version*\Platforms\\*platform*\ |親ディレクトリ内のターゲットおよびプロパティをオーバーライドする、プラットフォーム固有のターゲット ファイルおよびプロパティ ファイルがあります。 このディレクトリ内のターゲットによって使用されるタスクを定義する DLL も含まれています。<br /><br /> *platform* プレースホルダーは、ARM、Win32、または x64 サブディレクトリを表します。|
|*<ドライブ>* :\Program Files *(x86)* \Microsoft Visual Studio\\*year*\\*edition*\Common7\IDE\VC\VCTargets\Platforms\\*platform*\PlatformToolsets\\*toolset*\ <br /><br />*<ドライブ>* :\Program Files *(x86)* \MSBuild\Microsoft.Cpp\v4.0\\*version*\Platforms\\*platform*\PlatformToolsets\\*toolset*\ <br /><br />*<ドライブ>* :\Program Files *(x86)* \MSBuild\Microsoft.Cpp\v4.0\Platforms\\*platform*\PlatformToolsets\\*toolset*\ |指定の *toolset* を使用してビルドで Visual C++ アプリケーションを生成するためのディレクトリが含まれています。<br /><br /> *year* プレースホルダーと *edition* プレースホルダーは、Visual Studio 2017 以降のエディションで使用されます。 *version* プレースホルダーは、Visual Studio 2012 の場合は v110、Visual Studio 2013 の場合は v120、Visual Studio 2015 の場合は v140、Visual Studio 2017 の場合は v141、Visual Studio 2019 の場合は v142 となります。 *platform* プレースホルダーは、ARM、Win32、または x64 サブディレクトリを表します。 *toolset* プレースホルダーは、たとえば、Visual Studio 2015 ツールセットを使用して Windows アプリをビルドする場合は v140、Visual Studio 2013 ツールセットを使用して Windows XP 用にビルドする場合は v120_xp となります。<br /><br />ビルドで Visual Studio 2008 または Visual Studio 2010 のアプリケーションを生成するためのディレクトリを含むパスには、*version* は含まれず、*platform* プレースホルダーは Itanium、Win32、または x64 サブディレクトリを表します。 *toolset* プレースホルダーは、v90 または v100 ツールセット サブディレクトリを表します。|

## <a name="support-files"></a>サポート ファイル

サポート ファイル ディレクトリには、次の拡張子を持つファイルが含まれます。

|拡張子|説明|
|---------------|-----------------|
|.targets|ターゲットによって実行されるタスクを指定する `Target` XML 要素が含まれます。 タスク パラメーターにファイルとコマンド ライン オプションを割り当てるために使用される、`PropertyGroup`、`ItemGroup`、`ItemDefinitionGroup`、およびユーザー定義の `Item` の各要素が含まれることもあります。<br /><br /> 詳細については、「[Target 要素 (MSBuild)](/visualstudio/msbuild/target-element-msbuild)」を参照してください。|
|.props|ビルド時に使用されるファイル設定とパラメーター設定を指定する `Property Group` XML 要素およびユーザー定義の `Property` XML 要素が含まれます。<br /><br /> 追加の設定を指定する `ItemDefinitionGroup` XML 要素およびユーザー定義の `Item` XML 要素が含まれることもあります。 項目定義グループに定義されている項目はプロパティに似ていますが、コマンド ラインからはアクセスできません。 Visual Studio プロジェクト ファイルでは、プロパティではなく項目を使用して設定を表すことがよくあります。<br /><br /> 詳細については、「[ItemGroup 要素 (MSBuild)](/visualstudio/msbuild/itemgroup-element-msbuild)」、 
「[ItemDefinitionGroup 要素 (MSBuild)](/visualstudio/msbuild/itemdefinitiongroup-element-msbuild)」、および「[Item 要素 (MSBuild)](/visualstudio/msbuild/item-element-msbuild)」を参照してください。|
|.xml|プロパティ シート、プロパティ ページ、テキスト ボックス コントロール、リスト ボックス コントロールなどの IDE ユーザー インターフェイス要素を宣言および初期化する XML 要素が含まれます。<br /><br /> .xml ファイルは、MSBuild ではなく IDE を直接サポートします。 ただし、IDE プロパティの値は、ビルド プロパティおよび項目に割り当てられます。<br /><br /> ほとんどの .xml ファイルは、ロケール固有のサブディレクトリにあります。 たとえば、英語 (米国) 地域のファイルは $(VCTargetsPath)\1033\\ にあります。|

## <a name="user-targets-and-properties"></a>ユーザー ターゲットおよびプロパティ

コマンド ラインで MSBuild をより効果的に使用するためには、どのプロパティとターゲットが役に立ち、どれが関係しているかを知っておくと便利です。 ほとんどのプロパティとターゲットは、Visual Studio ビルド システムを実装するために使用されるもので、ユーザーには関係がありません。 ここでは、ユーザー指向の有用なプロパティとターゲットについて説明します。

### <a name="platformtoolset-property"></a>PlatformToolset プロパティ

`PlatformToolset` プロパティでは、ビルドでどの MSVC ツールセットを使用するかを決定します。 既定では、現在のツールセットが使用されます。 このプロパティを設定すると、プロパティの値がリテラル文字列と連結され、特定のプラットフォームでプロジェクトをビルドするために必要なプロパティ ファイルとターゲット ファイルのあるディレクトリのパスを形成します。 特定のバージョンのプラットフォーム ツールセットを使用してビルドするには、そのプラットフォーム ツールセットをインストールする必要があります。

たとえば、Visual Studio 2015 のツールおよびライブラリを使用してアプリケーションをビルドするには、`PlatformToolset` プロパティを `v140` に設定します。

`msbuild myProject.vcxproj /p:PlatformToolset=v140`

### <a name="preferredtoolarchitecture-property"></a>PreferredToolArchitecture プロパティ

`PreferredToolArchitecture` プロパティは、ビルドで使用されているコンパイラとツールが 32 ビットか 64 ビットかを判定します。 このプロパティは、出力プラットフォームのアーキテクチャおよび構成には影響しません。 このプロパティが設定されていない場合、MSBuild では、既定でバージョン x86 のコンパイラおよびツールが使用されます。

たとえば、64 ビットのコンパイラおよびツールを使用してアプリケーションをビルドするには、`PreferredToolArchitecture` プロパティを `x64` に設定します。

`msbuild myProject.vcxproj /p:PreferredToolArchitecture=x64`

### <a name="useenv-property"></a>UseEnv プロパティ

既定では、現在のプロジェクトのプラットフォーム固有の設定によって、PATH、INCLUDE、LIB、LIBPATH、CONFIGURATION、および PLATFORM の各環境変数がオーバーライドされます。 環境変数がオーバーライドされないようにするには、`UseEnv` プロパティを **true** に設定します。

`msbuild myProject.vcxproj /p:UseEnv=true`

### <a name="targets"></a>ターゲット

Visual Studio のサポート ファイル内には、ターゲットが数多く存在します。 ただし、ほとんどはシステム指向のターゲットであり、ユーザーは無視できます。 ほとんどのシステム ターゲットは、先頭にアンダースコア (_) が付くか、"PrepareFor"、"Compute"、"Before"、"After"、"Pre"、または "Post" で始まる名前が付いています。

ユーザー指向の有用なターゲットを次の表に示します。

|Target|説明|
|------------|-----------------|
|BscMake|Microsoft Browse Information Maintenance Utility ツール (bscmake.exe) を実行します。|
|ビルド|プロジェクトをビルドします。<br /><br /> プロジェクトの既定のターゲットです。|
|ClCompile|MSVC コンパイラ ツール (cl.exe) を実行します。|
|Clean|一時ビルド ファイルおよび中間ビルド ファイルを削除します。|
|Lib|Microsoft 32-Bit Library Manager ツール (lib.exe) を実行します。|
|Link|MSVC リンカー ツール (link.exe) を実行します。|
|ManifestResourceCompile|マニフェストからリソースの一覧を抽出し、Microsoft Windows リソース コンパイラ ツール (rc.exe) を実行します。|
|Midl|Microsoft インターフェイス定義言語 (MIDL: Microsoft Interface Definition Language) コンパイラ ツール (midl.exe) を実行します。|
|リビルド|プロジェクトを消去してからビルドします。|
|ResourceCompile|Microsoft Windows リソース コンパイラ ツール (rc.exe) を実行します。|
|XdcMake|XML ドキュメント ツール (xdcmake.exe) を実行します。|
|Xsd|XML スキーマ定義ツール (Xsd.exe) を実行します。 *下記のメモをご覧ください。*|

> [!NOTE]
> Visual Studio 2017 以降では、C++ プロジェクトでの **xsd** ファイルのサポートは非推奨です。 **CppCodeProvider.dll** を手動で GAC に追加して、**Microsoft.VisualC.CppCodeProvider** を引き続き使用できます。

## <a name="see-also"></a>関連項目

[MSBuild タスク リファレンス](/visualstudio/msbuild/msbuild-task-reference)<br/>
[BscMake タスク](/visualstudio/msbuild/bscmake-task)<br/>
[CL タスク](/visualstudio/msbuild/cl-task)<br/>
[CPPClean タスク](/visualstudio/msbuild/cppclean-task)<br/>
[LIB タスク](/visualstudio/msbuild/lib-task)<br/>
[Link タスク](/visualstudio/msbuild/link-task)<br/>
[MIDL タスク](/visualstudio/msbuild/midl-task)<br/>
[MT タスク](/visualstudio/msbuild/mt-task)<br/>
[RC タスク](/visualstudio/msbuild/rc-task)<br/>
[SetEnv タスク](/visualstudio/msbuild/setenv-task)<br/>
[VCMessage タスク](/visualstudio/msbuild/vcmessage-task)<br/>
[XDCMake タスク](/visualstudio/msbuild/xdcmake-task)<br/>

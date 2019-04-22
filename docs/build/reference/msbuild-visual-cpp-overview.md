---
title: Visual Studio での C++ の内部を MSBuild プロジェクトします。
ms.date: 12/08/2018
helpviewer_keywords:
- MSBuild overview
ms.assetid: dd258f6f-ab51-48d9-b274-f7ba911d05ca
ms.openlocfilehash: 6c8e891f6bf6ed6b3bb3d1c84dbc13b64ab7b868
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59021905"
---
# <a name="msbuild-internals-for-c-projects"></a>C++ プロジェクトの MSBuild の内部

IDE でプロジェクトのプロパティを設定し、プロジェクトを保存すると、Visual Studio はプロジェクトの設定をプロジェクト ファイルに書き込みます。 プロジェクト ファイルにはプロジェクトに固有の設定が含まれますが、プロジェクトのビルドに必要な設定がすべて含まれているわけではありません。 プロジェクト ファイルには`Import`、その他のネットワークを含む要素*ファイルをサポートします。* サポート ファイルには、プロジェクトのビルドに必要なその他のプロパティ、ターゲット、および設定が含まれます。

サポート ファイル内のほとんどのターゲットとプロパティは、ビルド システムを実装するためだけに用意されています。 次のセクションでは、MSBuild コマンド ラインで指定できる便利なターゲットとプロパティについて説明します。 その他のターゲットおよびプロパティについては、サポート ファイル ディレクトリ内のファイルを参照してください。

## <a name="support-file-directories"></a>サポート ファイル ディレクトリ

既定では、プライマリの Visual Studio のサポート ファイルは、次のディレクトリにあります。 Microsoft Visual Studio の下のディレクトリは、MSBuild の下のディレクトリは Visual Studio 2015 と以前のバージョンで使用されるときに、Visual Studio 2017 およびそれ以降のバージョンで使用されます。

|ディレクトリ|説明|
|---------------|-----------------|
|*ドライブ*: \Program Files *(x86)* \Microsoft Visual Studio\\*年*\\*edition*\Common7\IDE\VC\VCTargets\ <br /><br />*drive*:\Program Files *(x86)* \MSBuild\Microsoft.Cpp (x86)\v4.0\\*version*\ |ターゲットによって使用される主要なターゲット ファイル (.targets) およびプロパティ ファイル (.props) があります。 既定では、$(VCTargetsPath) マクロはこのディレクトリを参照します。|
|*ドライブ*: \Program Files *(x86)* \Microsoft Visual Studio\\*年*\\*edition*\Common7\IDE\VC\VCTargets\プラットフォーム\\*プラットフォーム*\ <br /><br />*drive*:\Program Files *(x86)* \MSBuild\Microsoft.Cpp\v4.0\\*version*\Platforms\\*platform*\ |親ディレクトリ内のターゲットおよびプロパティをオーバーライドする、プラットフォーム固有のターゲット ファイルおよびプロパティ ファイルがあります。 このディレクトリには、このディレクトリ内のターゲットによって使用されるタスクを定義する DLL も含まれています。<br /><br /> *プラットフォーム*ARM、Win32、または x64 を表すプレース ホルダーのサブディレクトリ。|
|*ドライブ*: \Program Files *(x86)* \Microsoft Visual Studio\\*年*\\*edition*\Common7\IDE\VC\VCTargets\プラットフォーム\\*プラットフォーム*\PlatformToolsets\\*ツールセット*\ <br /><br />*ドライブ*: \Program Files *(x86)* \MSBuild\Microsoft.Cpp\v4.0\\*バージョン*\Platforms\\*プラットフォーム*\PlatformToolsets\\*ツールセット*\ <br /><br />*ドライブ*: \Program Files *(x86)* \MSBuild\Microsoft.Cpp\v4.0\Platforms\\*プラットフォーム*\PlatformToolsets\\*ツールセット*\ |指定したを使用して C++ アプリケーションを生成するビルドを有効にするディレクトリを含む*ツールセット*します。<br /><br /> *年*と*edition*プレース ホルダーは、Visual Studio 2017 と以降のエディションで使用されます。 *バージョン*プレース ホルダーは、Visual Studio 2012 用 V110、V120 for Visual Studio 2013、または Visual Studio 2015 は V140 です。 *プラットフォーム*ARM、Win32、または x64 を表すプレース ホルダーのサブディレクトリ。 *ツールセット*v120_xp ツールセットを使用して、Visual Studio 2013、v110_wp80 に Windows XP 用にビルドする Visual Studio 2015 ツールセットを使用して Windows アプリを構築するための v140 など、ツールセット サブディレクトリを表すプレース ホルダーVisual Studio 2012 のツールセットを使用して Windows Phone 8.0 アプリをビルドします。<br /><br />Visual Studio 2008 または Visual Studio 2010 のいずれかのアプリケーションを生成するビルドを有効にするディレクトリを含むパスを含まない、*バージョン*、および*プラットフォーム*プレース ホルダーItanium、Win32、または x64 のサブディレクトリ。 *ツールセット*v90 または v100 ツールセット サブディレクトリを表すプレース ホルダーです。|

## <a name="support-files"></a>サポート ファイル

サポート ファイル ディレクトリには、これらの拡張機能を持つファイルが含まれます。

|拡張子|説明|
|---------------|-----------------|
|.targets|ターゲットによって実行されるタスクを指定する `Target` XML 要素が含まれます。 タスク パラメーターにファイルとコマンド ライン オプションを割り当てるために使用される、`PropertyGroup`、`ItemGroup`、`ItemDefinitionGroup`、およびユーザー定義の `Item` の各要素が含まれることもあります。<br /><br /> 詳細については、次を参照してください。 [Target 要素 (MSBuild)](/visualstudio/msbuild/target-element-msbuild)します。|
|.props|ビルド時に使用されるファイル設定とパラメーター設定を指定する `Property Group` XML 要素およびユーザー定義の `Property` XML 要素が含まれます。<br /><br /> 追加の設定を指定する `ItemDefinitionGroup` XML 要素およびユーザー定義の `Item` XML 要素が含まれることもあります。 項目定義グループに定義されている項目はプロパティに似ていますが、コマンド ラインからはアクセスできません。 Visual Studio プロジェクト ファイルは、項目をプロパティではなく、設定を表す頻繁に使用します。<br /><br /> 詳細については、次を参照してください[ItemGroup 要素 (MSBuild)](/visualstudio/msbuild/itemgroup-element-msbuild)、。 
[ItemDefinitionGroup 要素 (MSBuild)](/visualstudio/msbuild/itemdefinitiongroup-element-msbuild)、および[Item 要素 (MSBuild)](/visualstudio/msbuild/item-element-msbuild)します。|
|.xml|プロパティ シート、プロパティ ページ、テキスト ボックス コントロール、リスト ボックス コントロールなどの IDE ユーザー インターフェイス要素を宣言および初期化する XML 要素が含まれます。<br /><br /> .xml ファイルは、MSBuild ではなく IDE を直接サポートします。 ただし、IDE プロパティの値は、ビルド プロパティおよび項目に割り当てられます。<br /><br /> ほとんどの .xml ファイルは、ロケール固有のサブディレクトリにあります。 たとえば、英語-米国リージョンのファイルは $(VCTargetsPath) \1033\\します。|

## <a name="user-targets-and-properties"></a>ユーザー ターゲットおよびプロパティ

コマンド ラインで MSBuild をより効果的に使用するためには、どのプロパティとターゲットが役に立ち、どれが関係しているかを知っておくと便利です。 ほとんどのプロパティとターゲットは、Visual Studio のビルド システムの実装に役立つ、その結果、ユーザーに関連するではありません。 ここでは、ユーザー指向の有用なプロパティとターゲットについて説明します。

### <a name="platformtoolset-property"></a>PlatformToolset プロパティ

`PlatformToolset`どの MSVC ツールセットがビルドに使用されるプロパティを決定します。 既定では、現在のツールセットが使用されます。 このプロパティが設定されている場合、プロパティの値は、特定のプラットフォーム プロジェクトをビルドするために必要なプロパティとターゲット ファイルを含むディレクトリのパスを形成するリテラル文字列と連結します。 そのプラットフォーム ツールセットのバージョンを使用して作成するプラットフォーム ツールセットをインストールする必要があります。

たとえば、設定、`PlatformToolset`プロパティを`v140`Visual Studio 2015 ツールとライブラリを使用して、アプリケーションを構築します。

`msbuild myProject.vcxproj /p:PlatformToolset=v140`

### <a name="preferredtoolarchitecture-property"></a>PreferredToolArchitecture プロパティ

`PreferredToolArchitecture` プロパティは、ビルドで使用されているコンパイラとツールが 32 ビットか 64 ビットかを判定します。 このプロパティは、出力プラットフォームのアーキテクチャおよび構成には影響しません。 既定では、MSBuild は、x86 を使用してバージョンのコンパイラおよびツールがこのプロパティが設定されていない場合。

たとえば、設定、`PreferredToolArchitecture`プロパティを`x64`64 ビットのコンパイラおよびツールを使用して、アプリケーションを構築します。

`msbuild myProject.vcxproj /p:PreferredToolArchitecture=x64`

### <a name="useenv-property"></a>UseEnv プロパティ

既定では、現在のプロジェクトのプラットフォーム固有の設定によって、PATH、INCLUDE、LIB、LIBPATH、CONFIGURATION、および PLATFORM の各環境変数がオーバーライドされます。 設定、`UseEnv`プロパティを**true**環境変数がオーバーライドされていないことを保証するためにします。

`msbuild myProject.vcxproj /p:UseEnv=true`

### <a name="targets"></a>ターゲット

何百もの Visual Studio のサポート ファイル内のターゲットがあります。 ただし、ほとんどはシステム指向のターゲットであり、ユーザーは無視できます。 ほとんどのシステム ターゲットは、先頭にアンダースコア (_) が付くか、"PrepareFor"、"Compute"、"Before"、"After"、"Pre"、または "Post" で始まる名前が付いています。

次の表は、いくつかの便利なユーザー指向のターゲットを一覧表示します。

|ターゲット|説明|
|------------|-----------------|
|BscMake|Microsoft Browse Information Maintenance Utility ツール (bscmake.exe) を実行します。|
|ビルド|プロジェクトをビルドします。<br /><br /> プロジェクトの既定のターゲットです。|
|ClCompile|MSVC コンパイラ ツールを実行します。 cl.exe します。|
|Clean|一時ビルド ファイルおよび中間ビルド ファイルを削除します。|
|Lib|Microsoft 32-Bit Library Manager ツール (lib.exe) を実行します。|
|リンク|MSVC リンカー ツールの実行 link.exe します。|
|ManifestResourceCompile|マニフェストからリソースの一覧を抽出し、Microsoft Windows リソース コンパイラ ツール (rc.exe) を実行します。|
|Midl|Microsoft インターフェイス定義言語 (MIDL: Microsoft Interface Definition Language) コンパイラ ツール (midl.exe) を実行します。|
|リビルド|プロジェクトを消去してからビルドします。|
|ResourceCompile|Microsoft Windows リソース コンパイラ ツール (rc.exe) を実行します。|
|XdcMake|XML ドキュメント ツール (xdcmake.exe) を実行します。|
|Xsd|XML スキーマ定義ツール (Xsd.exe) を実行します。 *下記のメモをご覧ください。*|

> [!NOTE]
> Visual Studio 2017 で C++ プロジェクトのサポート**xsd**ファイルが非推奨とされます。 使用することもできます**Microsoft.VisualC.CppCodeProvider**を追加して**CppCodeProvider.dll**を GAC に手動でします。

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

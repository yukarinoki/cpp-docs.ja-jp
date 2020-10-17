---
title: Visual Studio の C++ プロジェクトの MSBuild の内部
description: MSBuild for Visual Studio C++ プロジェクトで使用されるサポートファイル、プロパティ、およびターゲット。
ms.date: 10/14/2020
helpviewer_keywords:
- MSBuild overview
ms.openlocfilehash: b08db751bfe04c7cd3ce2c2f4741c9ee8956cf74
ms.sourcegitcommit: 6e5429e076e552b32e8bdc49480c51498d7924c1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2020
ms.locfileid: "92099681"
---
# <a name="msbuild-internals-for-c-projects"></a>C++ プロジェクトの MSBuild の内部

IDE でプロジェクト プロパティを設定し、プロジェクトを保存すると、Visual Studio によってプロジェクト設定がプロジェクト ファイルに書き込まれます。 プロジェクトファイルには、プロジェクトに固有の設定が含まれています。 ただし、プロジェクトのビルドに必要なすべての設定が含まれているわけではありません。 プロジェクト ファイルには、追加の*サポート ファイル*とのつながりを表す `Import` 要素が含まれます。 サポートファイルには、プロジェクトのビルドに必要なその他のプロパティ、ターゲット、および設定が含まれています。

サポート ファイル内のほとんどのターゲットとプロパティは、ビルド システムを実装するためだけに用意されています。 この記事では、MSBuild コマンドラインで指定できる便利なターゲットとプロパティについて説明します。 その他のターゲットおよびプロパティについては、サポート ファイル ディレクトリ内のファイルを参照してください。

## <a name="support-file-directories"></a>サポート ファイル ディレクトリ

既定では、Visual Studio の主要なサポート ファイルは、次のディレクトリに配置されています。 この情報はバージョン固有です。

::: moniker range=">=vs-2019"

### <a name="visual-studio-2019"></a>Visual Studio 2019

- *`%VSINSTALLDIR%MSBuild\Microsoft\VC\<version>\`*

  ターゲットによって使用される主要なターゲット ファイル (.targets) およびプロパティ ファイル (.props) があります。 既定では、$(VCTargetsPath) マクロはこのディレクトリを参照します。 このプレースホルダーは、visual studio の *`<version>`* バージョン: v160 For visual studio 2019、v150 For Visual studio 2017 を参照しています。

- *`%VSINSTALLDIR%MSBuild\Microsoft\VC\<version>\Platforms\<platform>\`*

  親ディレクトリ内のターゲットおよびプロパティをオーバーライドする、プラットフォーム固有のターゲット ファイルおよびプロパティ ファイルがあります。 このディレクトリ内のターゲットによって使用されるタスクを定義する DLL も含まれています。 プレースホルダーは、 *`<platform>`* ARM、ARM64、Win32、または x64 サブディレクトリを表します。

- *`%VSINSTALLDIR%MSBuild\Microsoft\VC\<version>\Platforms\<platform>\PlatformToolsets\<toolset>\`*

  指定されたを使用してビルドが C++ アプリケーションを生成できるようにするディレクトリを格納し *`<toolset>`* ます。 プレースホルダーは、 *`<platform>`* ARM、ARM64、Win32、または x64 サブディレクトリを表します。 プレースホルダーは、 *`<toolset>`* ツールセットサブディレクトリを表します。

::: moniker-end

::: moniker range=">=vs-2017"

### <a name="visual-studio-2017"></a>Visual Studio 2017

- *`%VSINSTALLDIR%Common7\IDE\VC\VCTargets\`*

  ターゲットによって使用されるプライマリターゲットファイル ( *`.targets`* ) とプロパティファイル () を格納し *`.props`* ます。 既定では、 `$(VCTargetsPath)` マクロはこのディレクトリを参照します。

- *`%VSINSTALLDIR%Common7\IDE\VC\VCTargets\Platforms\<platform>\`*

  親ディレクトリ内のターゲットおよびプロパティをオーバーライドする、プラットフォーム固有のターゲット ファイルおよびプロパティ ファイルがあります。 このディレクトリ内のターゲットによって使用されるタスクを定義する DLL も含まれています。 プレースホルダーは、 *`<platform>`* ARM、ARM64、Win32、または x64 サブディレクトリを表します。

- *`%VSINSTALLDIR%Common7\IDE\VC\VCTargets\Platforms\<platform>\PlatformToolsets\<toolset>\`*

  指定されたを使用してビルドが C++ アプリケーションを生成できるようにするディレクトリを格納し *`<toolset>`* ます。 プレースホルダーは、 *`<platform>`* ARM、Win32、または x64 サブディレクトリを表します。 プレースホルダーは、 *`<toolset>`* ツールセットサブディレクトリを表します。

::: moniker-end

### <a name="visual-studio-2015-and-earlier"></a>Visual Studio 2015 以前

- *`<drive>:\Program Files (x86)\MSBuild\Microsoft.Cpp\v4.0\<version>\`*

  ターゲットによって使用される主要なターゲット ファイル (.targets) およびプロパティ ファイル (.props) があります。 既定では、$(VCTargetsPath) マクロはこのディレクトリを参照します。

- *`<drive>:\Program Files (x86)\MSBuild\Microsoft.Cpp\v4.0\<version>\Platforms\<platform>\`*

  親ディレクトリ内のターゲットおよびプロパティをオーバーライドする、プラットフォーム固有のターゲット ファイルおよびプロパティ ファイルがあります。 このディレクトリ内のターゲットによって使用されるタスクを定義する DLL も含まれています。 プレースホルダーは、 *`<platform>`* ARM、Win32、または x64 サブディレクトリを表します。

- *`<drive>:\Program Files (x86)\MSBuild\Microsoft.Cpp\v4.0\<version>\Platforms\<platform>\PlatformToolsets\<toolset>\`*

  指定されたを使用してビルドが C++ アプリケーションを生成できるようにするディレクトリを格納し *`<toolset>`* ます。 *`<version>`* プレースホルダーは V110 For Visual studio 2012、V120 for Visual Studio 2013、および V140 For Visual studio 2015 です。 プレースホルダーは、 *`<platform>`* ARM、Win32、または x64 サブディレクトリを表します。 プレースホルダーは、 *`<toolset>`* ツールセットサブディレクトリを表します。 たとえば、Visual Studio 2015 ツールセットを使用して Windows アプリをビルドするのは v140 です。 または、Visual Studio 2013 ツールセットを使用して Windows XP 用にビルド v120_xp ます。

- *`<drive>:\Program Files (x86)\MSBuild\Microsoft.Cpp\v4.0\Platforms\<platform>\PlatformToolsets\<toolset>\`*

  ビルドが Visual Studio 2008 または Visual Studio 2010 アプリケーションを生成できるようにするためのパスには、が含まれていません *`<version>`* 。 これらのバージョンでは、 *`<platform>`* プレースホルダーは Itanium、Win32、または x64 サブディレクトリを表します。 *`<toolset>`* プレースホルダーは、v90 または v100 ツールセットサブディレクトリを表します。

## <a name="support-files"></a>サポート ファイル

サポート ファイル ディレクトリには、次の拡張子を持つファイルが含まれます。

| 拡張機能 | 説明 |
| --------- | ----------- |
| *`.targets`* | ターゲットによって実行されるタスクを指定する `Target` XML 要素が含まれます。 タスク パラメーターにファイルとコマンド ライン オプションを割り当てるために使用される、`PropertyGroup`、`ItemGroup`、`ItemDefinitionGroup`、およびユーザー定義の `Item` の各要素が含まれることもあります。<br /><br /> 詳細については、「[Target 要素 (MSBuild)](/visualstudio/msbuild/target-element-msbuild)」を参照してください。 |
| *`.props`* | ビルド時に使用されるファイル設定とパラメーター設定を指定する `Property Group` XML 要素およびユーザー定義の `Property` XML 要素が含まれます。<br /><br /> 追加の設定を指定する `ItemDefinitionGroup` XML 要素およびユーザー定義の `Item` XML 要素が含まれることもあります。 項目定義グループで定義された項目はプロパティと似ていますが、コマンドラインからはアクセスできません。 Visual Studio プロジェクト ファイルでは、プロパティではなく項目を使用して設定を表すことがよくあります。<br /><br /> 詳細については、「 [ItemGroup 要素 (msbuild)](/visualstudio/msbuild/itemgroup-element-msbuild)」、「 [Itemdefinitiongroup 要素 (msbuild)](/visualstudio/msbuild/itemdefinitiongroup-element-msbuild)」、および「 [Item 要素 (msbuild)](/visualstudio/msbuild/item-element-msbuild)」を参照してください。 |
| *`.xml`* | IDE ユーザーインターフェイス要素を宣言および初期化する XML 要素が含まれています。 たとえば、プロパティシート、プロパティページ、テキストボックスコントロール、および listbox コントロールなどです。<br /><br /> ファイルは、 *`.xml`* MSBuild ではなく IDE を直接サポートします。 ただし、IDE プロパティの値は、ビルド プロパティおよび項目に割り当てられます。<br /><br /> ほとんどの *`.xml`* ファイルは、ロケール固有のサブディレクトリにあります。 たとえば、英語-米国地域のファイルはに `$(VCTargetsPath)\1033\` あります。 |

## <a name="user-targets-and-properties"></a>ユーザー ターゲットおよびプロパティ

MSBuild を効果的に使用するために、役に立つプロパティとターゲットを把握することができます。 ほとんどのプロパティとターゲットは、Visual Studio ビルドシステムを実装するのに役立ちます。そのため、ユーザーには関係ありません。 ここでは、について理解しておくべきユーザー指向のプロパティとターゲットについて説明します。

### <a name="platformtoolset-property"></a>`PlatformToolset` プロパティ

`PlatformToolset` プロパティでは、ビルドでどの MSVC ツールセットを使用するかを決定します。 既定では、現在のツールセットが使用されます。 このプロパティを設定すると、その値がリテラル文字列と連結され、パスが形成されます。 これは、特定のプラットフォーム用にプロジェクトをビルドするために必要なプロパティとターゲットファイルが格納されているディレクトリです。 特定のバージョンのプラットフォーム ツールセットを使用してビルドするには、そのプラットフォーム ツールセットをインストールする必要があります。

たとえば、Visual Studio 2015 のツールおよびライブラリを使用してアプリケーションをビルドするには、`PlatformToolset` プロパティを `v140` に設定します。

`msbuild myProject.vcxproj /p:PlatformToolset=v140`

### <a name="preferredtoolarchitecture-property"></a>`PreferredToolArchitecture` プロパティ

`PreferredToolArchitecture` プロパティは、ビルドで使用されているコンパイラとツールが 32 ビットか 64 ビットかを判定します。 このプロパティは、出力プラットフォームのアーキテクチャや構成には影響しません。 既定では、このプロパティが設定されていない場合、MSBuild は x86 バージョンのコンパイラおよびツールを使用します。

たとえば、64 ビットのコンパイラおよびツールを使用してアプリケーションをビルドするには、`PreferredToolArchitecture` プロパティを `x64` に設定します。

`msbuild myProject.vcxproj /p:PreferredToolArchitecture=x64`

### <a name="useenv-property"></a>`UseEnv` プロパティ

既定では、現在のプロジェクトのプラットフォーム固有の設定によって、PATH、INCLUDE、LIB、LIBPATH、CONFIGURATION、および PLATFORM の各環境変数がオーバーライドされます。 `UseEnv` **`true`** 環境変数がオーバーライドされないことを保証するために、プロパティをに設定します。

> `msbuild myProject.vcxproj /p:UseEnv=true`

### <a name="targets"></a>対象サーバー

Visual Studio のサポート ファイル内には、ターゲットが数多く存在します。 ただし、ほとんどはシステム指向のターゲットであり、ユーザーは無視できます。 ほとんどのシステムターゲットには、先頭にアンダースコア () が付いているか、または、、、、、 `_` またはで始まる名前が付いてい `PrepareFor` `Compute` `Before` `After` `Pre` `Post` ます。

ユーザー指向の有用なターゲットを次の表に示します。

| Target | 説明 |
| ------ | ----------- |
| BscMake | Microsoft Browse Information Maintenance Utility ツール (bscmake.exe) を実行します。 |
| Build | プロジェクトをビルドします。<br /><br /> このターゲットは、プロジェクトの既定値です。 |
| ClCompile | MSVC コンパイラ ツール (cl.exe) を実行します。 |
| Clean | 一時ビルド ファイルおよび中間ビルド ファイルを削除します。 |
| Lib | Microsoft 32-Bit Library Manager ツール (lib.exe) を実行します。 |
| Link | MSVC リンカー ツール (link.exe) を実行します。 |
| ManifestResourceCompile | マニフェストからリソースの一覧を抽出し、Microsoft Windows リソース コンパイラ ツール (rc.exe) を実行します。 |
| Midl | Microsoft インターフェイス定義言語 (MIDL: Microsoft Interface Definition Language) コンパイラ ツール (midl.exe) を実行します。 |
| [再構築] | プロジェクトを消去してからビルドします。 |
| ResourceCompile | Microsoft Windows リソース コンパイラ ツール (rc.exe) を実行します。 |
| XdcMake | XML ドキュメント ツール (xdcmake.exe) を実行します。 |
| Xsd | XML スキーマ定義ツール (Xsd.exe) を実行します。 *注を参照してください。* |

> [!NOTE]
> Visual Studio 2017 以降では、C++ プロジェクトでの **xsd** ファイルのサポートは非推奨です。 **CppCodeProvider.dll** を手動で GAC に追加して、**Microsoft.VisualC.CppCodeProvider** を引き続き使用できます。

## <a name="see-also"></a>関連項目

[MSBuild タスクリファレンス](/visualstudio/msbuild/msbuild-task-reference)\
[BscMake タスク](/visualstudio/msbuild/bscmake-task)\
[CL タスク](/visualstudio/msbuild/cl-task)\
[CPPClean タスク](/visualstudio/msbuild/cppclean-task)\
[LIB タスク](/visualstudio/msbuild/lib-task)\
[リンクタスク](/visualstudio/msbuild/link-task)\
[MIDL タスク](/visualstudio/msbuild/midl-task)\
[MT タスク](/visualstudio/msbuild/mt-task)\
[RC タスク](/visualstudio/msbuild/rc-task)\
[SetEnv タスク](/visualstudio/msbuild/setenv-task)\
[VCMessage タスク](/visualstudio/msbuild/vcmessage-task)\
[XDCMake タスク](/visualstudio/msbuild/xdcmake-task)

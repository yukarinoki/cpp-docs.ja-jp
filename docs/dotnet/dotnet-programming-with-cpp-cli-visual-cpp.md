---
title: C++/CLI による .NET プログラミング
description: C++/CLI を使用して、Visual Studio で .NET アプリとコンポーネントを作成する方法について説明します。
ms.date: 12/08/2020
helpviewer_keywords:
- programming [C++], .NET programming
- .NET Framework [C++]
- .NET applications [C++]
- Visual C++, .NET programming
ms.openlocfilehash: 80a9743016976e307158608134155dc7272d44a8
ms.sourcegitcommit: 754df5278f795f661d4eeb0d4cacc908aa630159
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96933184"
---
# <a name="net-programming-with-ccli"></a>C++/CLI による .NET プログラミング

::: moniker range="msvc-140"

既定で、Visual Studio 2015 で作成された CLR プロジェクトは .NET Framework 4.5.2 を対象とします。 新しいプロジェクトを作成するときに、.NET Framework 4.6 をターゲットにすることができます。 [ **新しいプロジェクト** ] ダイアログボックスで、ダイアログの上部中央にあるドロップダウンリストでターゲットフレームワークを変更します。 既存のプロジェクトのターゲットフレームワークを変更するには、プロジェクトを閉じて、プロジェクトファイル () を編集 *`.vcxproj`* し、ターゲットフレームワークのバージョンの値を4.6 に変更します。 変更は、次にプロジェクトを開いたときに有効になります。

::: moniker-end
::: moniker range="msvc-150"

Visual Studio 2017 では、既定のターゲット .NET Framework は4.6.1 です。 [ **新しいプロジェクト** ] ダイアログボックスの下部にフレームワークのバージョンセレクターがあります。

## <a name="install-ccli-support-in-visual-studio-2017"></a>Visual Studio 2017 で C++/CLI サポートをインストールする

C++/CLI 自体は、Visual Studio C++ ワークロードをインストールするときに既定でインストールされません。 Visual Studio のインストール後にコンポーネントをインストールするには、Visual Studio インストーラーを開きます。 インストールされている Visual Studio のバージョンの横にある [ **変更** ] ボタンをクリックします。 [ **インストールされているコンポーネント** ] タブを選択します。[ **コンパイラ]、[ビルドツール** ]、[ランタイム] セクションまで下にスクロールし、[ **C++/cli サポート**] を選択します。 Visual Studio を更新するには、[ **変更** ] を選択します。

::: moniker-end
::: moniker range="msvc-160"

Visual Studio 2019 では、.NET Core プロジェクトの既定のターゲットフレームワークは5.0 です。 .NET Framework プロジェクトの場合、既定値は4.7.2 です。 .NET Framework バージョンセレクターは、[**新しいプロジェクトの作成**] ダイアログの [**新しいプロジェクトの構成**] ページにあります。
## <a name="install-ccli-support-in-visual-studio-2019"></a>Visual Studio 2019 で C++/CLI サポートをインストールする

C++/CLI 自体は、Visual Studio C++ ワークロードをインストールするときに既定でインストールされません。 Visual Studio のインストール後にコンポーネントをインストールするには、Visual Studio インストーラーを開きます。 インストールされている Visual Studio のバージョンの横にある [ **変更** ] ボタンをクリックします。 [ **インストールされているコンポーネント** ] タブを選択します。[ **コンパイラ]、[ビルドツール]、[ランタイム** ] セクションまで下にスクロールし、最新の **C++/cli support for v142 build tools** コンポーネントを選択します。 Visual Studio を更新するには、[ **変更** ] を選択します。

::: moniker-end

## <a name="in-this-section"></a>このセクションの内容

[C++/CLI タスク](../dotnet/cpp-cli-tasks.md)

[ネイティブと .NET の相互運用性](../dotnet/native-and-dotnet-interoperability.md)

[純粋で検証可能なコード (C++/CLI)](../dotnet/pure-and-verifiable-code-cpp-cli.md)

[正規表現 (C++/CLI)](../dotnet/regular-expressions-cpp-cli.md)

[ファイル処理と i/o (C++/CLI)](../dotnet/file-handling-and-i-o-cpp-cli.md)

[グラフィックス操作 (C++/CLI)](../dotnet/graphics-operations-cpp-cli.md)

[Windows の操作 (C++/CLI)](../dotnet/windows-operations-cpp-cli.md)

[ADO.NET を使用したデータアクセス (C++/CLI)](../dotnet/data-access-using-adonet-cpp-cli.md)

[他の .NET 言語との相互運用性 (C++/CLI)](../dotnet/interoperability-with-other-dotnet-languages-cpp-cli.md)

[シリアル化 (C++/CLI)](../dotnet/serialization-cpp-cli.md)

[マネージ型 (C++/CLI)](../dotnet/managed-types-cpp-cli.md)

[リフレクション (C++/CLI)](../dotnet/reflection-cpp-cli.md)

[厳密名アセンブリ (アセンブリ署名) (C++/CLI)](../dotnet/strong-name-assemblies-assembly-signing-cpp-cli.md)

[Debug クラス (C++/CLI)](../dotnet/debug-class-cpp-cli.md)

[STL/CLR ライブラリ リファレンス](../dotnet/stl-clr-library-reference.md)

[C++ のサポート ライブラリ](../dotnet/cpp-support-library.md)

[C++/CLI の例外](../dotnet/exceptions-in-cpp-cli.md)

[ボックス化 (C++/CLI)](../dotnet/boxing-cpp-cli.md)

## <a name="see-also"></a>関連項目

[ネイティブと .NET の相互運用性](../dotnet/native-and-dotnet-interoperability.md)

---
description: '詳細情報: 方法:ターゲット フレームワークおよびプラットフォームのツールセットを変更する'
title: '方法: ターゲット フレームワークおよびプラットフォームのツールセットを変更する'
ms.custom: contperf-fy21q3
ms.date: 03/31/2021
helpviewer_keywords:
- 'msbuild (c++), howto: modify target framework and platform toolset'
ms.openlocfilehash: 3242b79f2b939d2b668a9bcd7d13ea80c424d2fe
ms.sourcegitcommit: 82a0d23b04d0776c00209d885689cbc5be36d3b9
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/31/2021
ms.locfileid: "106099327"
---
# <a name="how-to-modify-the-target-framework-and-platform-toolset"></a>方法: ターゲット フレームワークおよびプラットフォームのツールセットを変更する

Visual Studio C++ プロジェクト ファイルを編集して、別のバージョンの C++ プラットフォーム ツールセットをターゲットにすることができます。 Windows SDK と、使用される .NET Framework も編集できます。 (.NET Framework は C++/CLI プロジェクトにのみ適用されます)。 新しいプロジェクトでは、プロジェクトの作成に使用する Visual Studio のバージョンの既定の .NET Framework とツールセットが使用されます。 .vcxproj ファイルでこれらの値を変更すると、すべてのコンパイル ターゲットで同じコード ベースを使用できます。

## <a name="platform-toolset"></a>プラットフォームのツールセット

プラットフォームのツールセットは、C++ コンパイラ (cl.exe) とリンカー (link.exe)、そして C/C++ 標準ライブラリで構成されます。 Visual Studio 2015、Visual Studio 2017、Visual Studio 2019 には、バイナリ互換性があります。 ツールセットのメジャー バージョンごとに表示されますが、14 のままになっています。 Visual Studio 2019 または Visual Studio 2017 でコンパイルされたプロジェクトは、2017 および 2015 プロジェクトの ABI と下位互換性があります。 マイナー バージョンは、Visual Studio 2015 以降、バージョンごとに 1 ずつ更新されています。

- Visual Studio 2015: v140
- Visual Studio 2017: v141
- Visual Studio 2019: v142

これらのツールセットでは、.NET Framework 4.5 以降がサポートされています。

Visual Studio では、C++ プロジェクトの複数バージョン対応もサポートされています。 最新の Visual Studio IDE を使用して、古いバージョンの Visual Studio で作成されたプロジェクトを編集し、ビルドすることができます。 新しいバージョンのツールセットを使用するためにプロジェクトをアップグレードする必要はありません。 古いツールセットがコンピューターにインストールされている必要があります。 詳細については、[Visual Studio でネイティブの複数バージョン対応を使用する方法](../porting/use-native-multi-targeting.md)に関する記事を参照してください。 たとえば、Visual Studio 2015 では、.NET Framework 2.0 を "*ターゲット*" にできますが、それをサポートする以前のツールセットを使用する必要があります。

## <a name="target-framework-ccli-project-only"></a>ターゲット フレームワーク (C++/CLI プロジェクトのみ)

ターゲット フレームワークを変更すると、プラットフォーム ツールセットのバージョンもそのターゲット フレームワークをサポートするように変更されます。 たとえば、.NET Framework 4.5 をターゲットとする場合、互換性のあるプラットフォーム ツールセットを使用する必要があります。 これらのツールセットには、Visual Studio 2015 (v140)、Visual Studio 2013 (v120)、または Visual Studio 2012 (v110) が含まれます。 [Windows 7.1 SDK](https://www.microsoft.com/download/details.aspx?id=8279) を使用すると、.NET Framework 2.0、3.0、3.5、および 4 をターゲットにすることができます。

カスタム プラットフォーム ツールセットを作成することで、さらにターゲット フレームワークを拡張できます。 詳細については、Visual C++ チーム ブログの [C++ Native Multi-Targeting (C++ ネイティブ マルチ ターゲット)](https://devblogs.microsoft.com/cppblog/c-native-multi-targeting/) をご覧ください。

### <a name="to-change-the-target-framework"></a>ターゲット フレームワークを変更するには

1. Visual Studio の **ソリューション エクスプローラー** で、プロジェクトを選びます。 メニュー バーで **[プロジェクト]** メニューを開き、 **[プロジェクトのアンロード]** を選択します。 このコマンドによって、プロジェクトのプロジェクト (.vcxproj) ファイルがアンロードされます。

   > [!NOTE]
   >  Visual Studio ではプロジェクト ファイルの編集中に C++ プロジェクトを読み込むことはできません。 ただし、プロジェクトが Visual Studio に読み込まれるとき、メモ帳などの別のエディターを使用して、プロジェクト ファイルを変更することができます。 Visual Studio はプロジェクト ファイルが変更されたことを検知して、プロジェクトを再度読み込むように求めるメッセージが表示されます。

1. メニュー バーで、 **[ファイル]** 、 **[開く]** 、 **[ファイル]** の順に選択します。 **[ファイルを開く]** のダイアログ ボックスで、プロジェクトのフォルダーに移動し、プロジェクト (.vcxproj) ファイルを開きます。

1. プロジェクト ファイルで、ターゲット フレームワークのバージョンに対するエントリを見つけます。 たとえば、.NET Framework 4.5 を使用するプロジェクトの場合は、 `<TargetFrameworkVersion>v4.5</TargetFrameworkVersion>` 要素の `<PropertyGroup Label="Globals">` 要素の中の `<Project>` を探します。 `<TargetFrameworkVersion>` 要素が存在しない場合には、プロジェクトは .NET Framework を使用しないため、変更の必要はありません。

1. その値を、使用するフレームワークのバージョン (v3.5 または v4.6 など) に更新します。

1. 変更を保存してエディターを閉じます。

1. **ソリューション エクスプローラー** で、プロジェクトのショートカット メニューを開き、 **[プロジェクトの再読み込み]** をクリックします。

1. 変更を確認するには、メニュー バーで **[プロジェクト]**  >  **[プロパティ]** を選択して、プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 ダイアログ ボックスで、 **[構成プロパティ]**  >  **[全般]** プロパティ ページを選択します。 **.NET Target 対象バージョン** が新しいバージョンのフレームワークを示していることを確認します。

### <a name="to-change-the-platform-toolset"></a>プラットフォームのツールセットを変更するには

1. Visual Studio のメニュー バーで **[プロジェクト]**  >  **[プロパティ]** を選択して、プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。

1. **[プロパティ ページ]** ダイアログ ボックスの上部で、 **[構成]** ドロップダウン リストを開き、 **[すべての構成]** を選択します。

1. ダイアログ ボックスで、 **[構成プロパティ]**  >  **[全般]** プロパティ ページを選択します。

1. [プロパティ] ページで、 **[プラットフォーム ツールセット]** を選択して、ドロップダウン リストから使用するツールセットを選択します。 たとえば、Visual Studio 2010 ツール セットをインストールした場合は、 **[Visual Studio 2010 (v100)]** を選択してプロジェクト用に使います。

1. **[OK]** を選択して変更内容を保存します。

## <a name="next-steps"></a>次の手順

[チュートリアル: プロジェクトとソリューションの使用 (C++)](../ide/walkthrough-working-with-projects-and-solutions-cpp.md)

## <a name="see-also"></a>関連項目

[コマンド ラインでの MSBuild - C++](msbuild-visual-cpp.md)

---
title: Visual Studio で新しい C++ Linux プロジェクトを作成する
ms.date: 06/11/2019
ms.assetid: 5d7c1d67-bc31-4f96-8622-2b4cf91372fd
ms.openlocfilehash: 0377e21177b29d998fc3e66bb1863dbc127c1fbe
ms.sourcegitcommit: fde637f823494532314790602c2819f889706ff6
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/13/2019
ms.locfileid: "67042714"
---
# <a name="create-a-new-linux-project"></a>新しい Linux プロジェクトを作成する

::: moniker range="vs-2015"

Linux プロジェクトは Visual Studio 2017 以降で使用できます。

::: moniker-end

最初に、Visual Studio 対応の **Linux 開発ワークロード**を必ずインストールします。 詳細については、「[Linux ワークロードのダウンロード、インストール、セットアップ](download-install-and-setup-the-linux-development-workload.md)」を参照してください。

Visual Studio で Linux の新しい C++ プロジェクトを作成する場合、Visual Studio のプロジェクトを作成するか、CMake のプロジェクトを作成するか選択することができます。 この記事では、Visual Studio のプロジェクトを作成する方法について説明します。 既存の CMake プロジェクトの作成と操作に関する詳細については、[Linux CMake プロジェクトの作成と構成](cmake-linux-project.md)に関するページを参照してください。

## <a name="to-create-a-new-linux-project"></a>新しい Linux プロジェクトを作成するには

Visual Studio で新しい Linux プロジェクトを作成するには、次のように操作します。

::: moniker range="vs-2019"

1. Visual Studio で **[ファイル]、[新しいプロジェクト]** の順に選択するか、**Ctrl + Shift + N** キーを押します。
1. **[言語]** を **[C++]** に設定し、「Linux」を検索します。 作成するプロジェクトの種類を選択し、 **[次へ]** を選択します。 **[名前]** と **[場所]** を入力し、 **[作成]** を選択します。

   ![新しい Linux プロジェクト](media/newproject-vs2019.png)

::: moniker-end

::: moniker range="vs-2017"

1. Visual Studio で **[ファイル]、[新しいプロジェクト]** の順に選択するか、**Ctrl + Shift + N** キーを押します。
1. **[Visual C++]、[クロス プラットフォーム]、[Linux]** ノードの順に選択し、作成するプロジェクト タイプを選択します。 **[名前]** と **[場所]** を入力し、 **[OK]** を選択します。

   ![新しい Linux プロジェクト](media/newproject.png)

::: moniker-end

   | プロジェクトの種類 | 説明 |
   | ------------ | --- |
   | **点滅 (Raspberry)**           | Raspberry Pi デバイスを対象とするプロジェクト。LED を点滅させるようにサンプル コードが記述されています。 |
   | **C++ コンソール アプリケーション (Linux)** | すべての Linux コンピューターを対象とするプロジェクト。コンソールにテキストを出力するようにサンプル コードが記述されています。 |
   | **空のプロジェクト (Linux)**       | すべての Linux コンピューターを対象とするプロジェクト。サンプル コードは記述されていません。 |
   | **メイクファイル プロジェクト (Linux)**    | 標準のメイクファイル ビルド システムを使用して構築する、すべての Linux コンピューターを対象とするプロジェクト。 |

   ::: moniker range="vs-2019"

   Visual Studio 2019 で、新しい CMake プロジェクトを作成できます。 詳細については、[Linux CMake プロジェクトの作成と構成](cmake-linux-project.md)に関するページを参照してください。
   
   ::: moniker-end

## <a name="next-steps"></a>次の手順

[Linux プロジェクトを構成する](configure-a-linux-project.md)

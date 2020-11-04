---
title: Visual Studio に C11 および C17 サポートをインストールする
description: Visual Studio に C11 と C17 の Windows SDK と CRT のサポートをインストールする
ms.date: 09/11/2020
helpviewer_keywords:
- Install preview Windows SDK
ms.assetid: 45138d70-719d-42dc-90d7-1d0ca31a2f54
ms.openlocfilehash: 9310b0dbb4e436245de820622ec9dd0f52292871
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/29/2020
ms.locfileid: "92924421"
---
# <a name="install-c11-and-c17-support-in-visual-studio"></a>Visual Studio に C11 および C17 サポートをインストールする

::: moniker range="<=msvc-150"

C11 および C17 標準のサポートには、Visual Studio 2019 バージョン 16.8 以降が必要です。 このバージョンのドキュメントを表示するには、この記事の Visual Studio の **[バージョン]** セレクター コントロールを Visual Studio 2019 に設定してください。 このページの目次の一番上にあります。

::: moniker-end

::: moniker range="msvc-160"

C11 および C17 標準のサポートは、Visual Studio 2019 バージョン 16.8 以降で使用できます。 サポートには、準拠するプリプロセッサ ([`/Zc:preprocessor`](../build/reference/zc-preprocessor.md)) で正常に動作するために、更新されたユニバーサル C ランタイム (UCRT) と最新の Windows SDK 更新プログラムが必要です。

Windows SDK のリリースは、Windows OS のリリースに対応しています。 これらの変更が加えられた Windows リリースがないため、 *Insider Preview Windows SDK* が必要になります。 これは、Windows Insider によって現在 " *フライト化* " (テスト) されている Windows ビルドに対応する Windows SDK のプレビュー版です。 Insider Preview Windows 10 SDK をインストールした後は、最新の Windows SDK を使用するように Visual Studio プロジェクトを構成すると、Insider Preview が使用されます。

## <a name="prerequisites"></a>前提条件

- コンピューターに Visual Studio 2019 バージョン 16.8 Preview 3 以降がインストールされ、実行されていること。 インストールには、C++ ワークロードによるデスクトップ開発を含めます。 最新のプレビューは、[Visual Studio Preview](https://visualstudio.microsoft.com/vs/preview/) ページからダウンロードできます。 Visual Studio がまだインストールされていない場合、インストール手順については、[Visual studio に C++ サポートのインストール](../build/vscpp-step-0-installation.md)に関する記事を参照してください。

## <a name="step-1-sign-in-by-using-an-insider-microsoft-account"></a>手順 1: Insider Microsoft アカウントを使用してサインインする

だれでも、無料の [Microsoft アカウント](https://signup.live.com/)を作成し、Insider プログラムを選択できます。 [開発者向け Windows Insider Program](https://insider.windows.com/for-developers) ページにアクセスし、 **[Register]\(登録\)** を選択してサインインします。

登録すると、Insider バージョンの Windows のフライトを起動するオプションが示されます。 この手順は、Insider Windows 10 SDK をダウンロードして使用するためには必要ありません。 Windows Insider に登録しても、お使いのマシンで、新しい Windows フライトをダウンロードするように自動的に選択されることはありません。

**[Welcome to the Windows Insider Program]\(Windows Insider Program へようこそ\)** ページが表示されたら、 **[Flight now]\(今すぐフライト\)** を選択する必要はなくなります。 次の手順に進み、Insider Preview Windows 10 SDK をダウンロードします。

## <a name="step-2-download-the-insider-preview-windows-10-sdk"></a>手順 2: Insider Preview Windows 10 SDK をダウンロードする

Insider Preview Windows SDK は、[Windows Insider Preview ダウンロード](https://www.microsoft.com/software-download/windowsinsiderpreviewSDK) ページからインストールできます。 "Windows Insider プログラムのメンバーである必要があります" というメッセージが表示された場合は、サインインしていることを確認してください。 Insider プログラムに使用したのと同じ Microsoft アカウントを使用します。 "We are sorry, the page you requested cannot be found" ("申し訳ございません。要求したページが見つかりません") というメッセージが表示された場合は、URL のロケールを *en-us* に変更してみてください。

Insider ページでは、Windows 10 Insider Preview OS を使用する必要があります。 これは、Windows SDK に含まれる一部のコンテンツに対してのみ当てはまります。 そのコンテンツは、以前のバージョンの Windows には存在しない新しい API に依存している可能性があります。 ただし、Windows とユニバーサル C ランタイムのヘッダーは、Insider OS なしでインストールでき、使用することができます。

ダウンロードを開始するには、 **[Get SDK Insider Preview – Build 20211]\(SDK Insider Preview – ビルド 20211 の取得\)** (またはそれ以降) を選択します。 新しいバージョンの Windows SDK も機能します。

## <a name="step-3-install-the-insider-preview-windows-10-sdk"></a>手順 3: Insider Preview Windows 10 SDK をインストールする

Insider Preview Windows SDK は、 *`.iso`* ファイルとしてダウンロードされます。 ファイル エクスプローラーで、ダウンロードしたファイルが格納されているフォルダーを開きます。 *`.iso`* ファイルをマウントし、 *`WinSDKSetup.exe`* を実行してインストールを開始します。

**[場所の指定]** ページで、 **[Install the Windows Software Development Kit - \<version> to this computer]\(Windows ソフトウェア開発キット - \<version> をこのコンピューターにインストールする\)** を選択し、 **[次へ]** を選択します。 **[Windows キット プライバシー]** ページで、Microsoft が Windows 10 キットの分析情報の収集することを許可するかどうかを選択し、 **[次へ]** を選択します。 **[同意する]** を選択して、使用許諾契約書に同意します。 **[インストールする機能を選択してください]** ページで、次の機能のみを選択します。  

- デスクトップ アプリ用 Windows SDK 署名ツール

- UWP マネージド アプリ用 Windows SDK

- UWP C++ アプリ用 Windows SDK

- デスクトップ C++ x86 アプリ用 Windows SDK (x86 用にビルドする予定の場合)

- デスクトップ C++ amd64 アプリ用 Windows SDK (amd64 用にビルドする予定の場合)

- デスクトップ C++ arm アプリ用 Windows SDK (arm 用にビルドする予定の場合)

- デスクトップ C++ arm64 アプリ用 Windows SDK (arm64 用にビルドする予定の場合)

![Windows SDK インストーラーでインストールするコンポーネントが選択されたスクリーンショット](media/c11-7-windows-sdk-installer-select-features.png)

**[インストール]** を選択して、選択した SDK コンポーネントをインストールします。 SDK でインストールを完了するのに数分かかります。 完了したら、Visual Studio を開きます。

## <a name="step-4-configuring-c11-or-c17-mode-in-visual-studio"></a>手順 4: Visual Studio で C11 または C17 モードを構成する

Visual Studio で、新規または既存の C プロジェクトを開き、プロジェクトの **[プロパティ ページ]** ダイアログを開きます。

Insider Preview Windows 10 SDK を使用するようにプロジェクトを設定します。 **[構成プロパティ]**  >  **[全般]** ページで、 **[Windows SDK バージョン]** プロパティを **10.0 (最新のインストール済みバージョン)** に設定するか、インストールした特定のプレビュー バージョンに設定します。

新しいオプションも表示されます: **C 言語標準** 。 このプロパティを **[ISO C11 Standard (`/std:c11`)]\(ISO C11 標準 (`/std:c11`)\)** または **[ISO C17 (2018) Standard (`/std:c17`)]\(ISO C17 (2018) 標準 (`/std:c17`)\)** に設定します。  

![[構成プロパティ] の [全般] ページの [プロパティ ページ] ダイアログで、[C 言語の標準] プロパティのドロップダウンで ISO C 17 が選択されていることを示すスクリーンショット](media/c11-9-project-property-page-c-language-standard.png)

言語が C++ の場合、C++ 言語標準が使用されます。 ファイル拡張子が *`.cpp`* の場合の既定値です。 言語が C の場合、C 言語の標準バージョンが使用されます。ファイル拡張子が *`.c`* の場合の既定値です。 C11 または C17 を使用してビルドするには、ソース コードを *`.c`* ファイルに配置するか、C としてコンパイルするようにコードを設定します。このプロパティは、プロジェクトの **[構成プロパティ]**  >  **[C/C++]**  >  **[詳細]** ページで設定できます。 **[コンパイル言語の選択]** プロパティを **[C コードとしてコンパイル (/TC)]** に設定します。

これで、Visual Studio 2019 バージョン 16.8 Preview 3 で C11 と C17 のコードをビルドするために必要なすべての設定が完了しました。

## <a name="see-also"></a>関連項目

[`/std` (言語の標準バージョンの指定)](../build/reference/std-specify-language-standard-version.md)

::: moniker-end

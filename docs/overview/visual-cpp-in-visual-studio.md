---
title: Visual Studio での C++
description: Visual Studio の Microsoft C/C++ コンパイラ、コード エディター、関連ツールを使用、Windows、Linux、Android、iOS 向けのプログラムを開発する方法について説明します。
ms.date: 11/05/2020
ms.technology: cpp-ide
helpviewer_keywords:
- Visual C++, home page
ms.openlocfilehash: 32d8f45c1ae0ffeabcfd7b22988f125b138c1f4d
ms.sourcegitcommit: 12eb6a824dd7187a065d44fceca4c410f58e121e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/06/2020
ms.locfileid: "94334157"
---
# <a name="c-in-visual-studio"></a>Visual Studio での C++

:::moniker range="msvc-160"

> [!NOTE]
> この開発者向けドキュメントは、Visual Studio 2019 に適用されます。 優先するバージョンの Visual Studio のドキュメントを表示するには、 **[バージョン]** セレクター コントロールを使用します。 このページの目次の一番上にあります。
>
> プログラムを実行できるように Visual C++ 2019 再頒布可能パッケージを探している場合は、Microsoft Visual Studio のサイトの[ダウンロード](https://visualstudio.microsoft.com/downloads/) ページにアクセスします。 **[すべてのダウンロード]** の下で、 **[その他のツールとフレームワーク]** セクションを展開します。 対象のアーキテクチャを選択してから、 **[ダウンロード]** ボタンを選択します。
>
> 以前の再頒布可能パッケージの場合は、[[古いバージョンのダウンロード]](https://visualstudio.microsoft.com/vs/older-downloads/) ページを開きます。 **[再頒布可能パッケージおよびビルド ツール]** セクションを展開します。 ダウンロードする再頒布可能パッケージのバージョンを見つけて、対象のアーキテクチャを選択し、 **[ダウンロード]** ボタンを選択します。

:::moniker-end

:::moniker range="msvc-150"

> [!NOTE]
> この開発者向けドキュメントは、Visual Studio 2017 に適用されます。 優先するバージョンの Visual Studio のドキュメントを表示するには、 **[バージョン]** セレクター コントロールを使用します。 このページの目次の一番上にあります。
>
> プログラムを実行できるように Visual C++ 2017 以前の再頒布可能パッケージを探している場合は、Microsoft Visual Studio のサイトの[古いバージョンのダウンロード](https://visualstudio.microsoft.com/vs/older-downloads/)のページにアクセスします。 **[再頒布可能パッケージおよびビルド ツール]** セクションを展開します。 ダウンロードする再頒布可能パッケージのバージョンを見つけて、対象のアーキテクチャを選択し、 **[ダウンロード]** ボタンを選択します。

:::moniker-end

:::moniker range="msvc-140"

> [!NOTE]
> この開発者向けドキュメントは、Visual Studio 2015 に適用されます。 優先するバージョンの Visual Studio のドキュメントを表示するには、 **[バージョン]** セレクター コントロールを使用します。 このページの目次の一番上にあります。
>
> プログラムを実行できるように Visual C++ 2015 以前の再頒布可能パッケージを探している場合は、Microsoft Visual Studio のサイトの[古いバージョンのダウンロード](https://visualstudio.microsoft.com/vs/older-downloads/)のページにアクセスします。 **[再頒布可能パッケージおよびビルド ツール]** セクションを展開します。 ダウンロードする再頒布可能パッケージのバージョンを見つけて、対象のアーキテクチャを選択し、 **[ダウンロード]** ボタンを選択します。

:::moniker-end

Microsoft Visual C++ (MSVC) とは、Windows 上で Visual Studio の一部として利用できる C++、C、およびアセンブリ言語の開発ツールおよびライブラリのことです。 これらのツールとライブラリでは、ユニバーサル Windows プラットフォーム (UWP) アプリ、ネイティブ Windows デスクトップおよびサーバー アプリケーション、Windows、Linux、Android、iOS 上で実行されるクロスプラットフォーム ライブラリおよびアプリに加えて、.NET Framework を使用する管理対象のアプリおよびライブラリを作成できます。 MSVC を使用すると、単純なコンソール アプリから最も高度で複雑な Windows デスクトップ用アプリまで、またデバイス ドライバーやオペレーティング システムのコンポーネントからモバイル デバイス用のクロスプラットフォーム ゲームまで、さらに最小の IoT デバイスから Azure クラウドにおけるマルチ サーバー ハイ パフォーマンス コンピューティングに至るまで、あらゆるアプリを記述することができます。

Visual Studio 2015、2017、および 2019 は、サイド バイ サイドでインストールできます。 Visual Studio 2019 (コンパイラ ツールセット v142) または Visual Studio 2017 (v141) を使用し、Visual Studio 2017 (v141) と Visual Studio 2015 (v140) のツールセットを使用して、プログラムの編集とビルドを行うことができます。

## <a name="whats-new-and-conformance-history"></a>新機能と準拠の履歴

[Visual Studio での C++ の新機能](what-s-new-for-visual-cpp-in-visual-studio.md)\
Visual Studio の新機能を紹介します。

[Visual Studio 2003 から 2015 の C++ の新機能](../porting/visual-cpp-what-s-new-2003-through-2015.md)\
Visual Studio 2003 から 2015 の各バージョンの、C++ の新機能を紹介します。

[Visual Studio の C++ 準拠の強化](cpp-conformance-improvements.md)\
Visual Studio の C++ 準拠の強化について説明します。

[Microsoft C++ 言語の準拠表](visual-cpp-language-conformance.md)\
MSVC C++ コンパイラの各機能の準拠状態を一覧にしています。

[Microsoft C/C++ 2003 - 2015 の変更履歴](../porting/visual-cpp-change-history-2003-2015.md)\
前のバージョンの互換性に影響する変更点について説明します。

## <a name="install-visual-studio-and-upgrade-from-earlier-versions"></a>Visual Studio をインストールして、以前のバージョンからアップグレードする

[Visual Studio での C++ サポートのインストール](../build/vscpp-step-0-installation.md)\
Visual Studio をダウンロードし、Microsoft C/C++ のツールセットをインストールします。

[Visual C++ 移植およびアップグレード ガイド](../porting/visual-cpp-porting-and-upgrading-guide.md)\
より高度な C++ 標準へのコンパイラの準拠および大幅に向上したコンパイル時間とセキュリティ機能 (Spectre の軽減策など) を活用するために、コードを移植してプロジェクトを Visual Studio 2015 以降にアップグレードするためのガイダンスです。

[さまざまな Visual Studio エディションの C++ ツールと機能](visual-cpp-tools-and-features-in-visual-studio-editions.md)\
さまざまな Visual Studio のエディションに関する情報を提供します。

[サポートされているプラットフォーム](supported-platforms-visual-cpp.md)\
Microsoft C/C++ コンパイラによってサポートされているプラットフォームを確認します。

## <a name="learn-c"></a>C++ について

[C++ へようこそ](../cpp/welcome-back-to-cpp-modern-cpp.md)\
高速で安全なコードを記述し、C スタイルのプログラミングの多くの潜在的な危険を回避するための、C++11 以降に基づく現代的な C++ プログラミング手法に関する情報を提供します。

[標準 C++](https://isocpp.org/)\
C++ について説明しながら、最新の C++ の概要を示すとともに、書籍、記事、講演、イベントなどへのリンクを提供します。

[Visual Studio について学習し、最初の C++ プロジェクトを作成する](../build/vscpp-step-1-create.md)\
Visual Studio で C++ を記述する方法の学習を始めます。

[Visual Studio C++ のサンプル](visual-cpp-samples.md)\
Microsoft から提供されている C++ のコード サンプルに関する情報。

## <a name="c-development-tools"></a>C++ 開発ツール

[Visual Studio での C++ 開発の概要](overview-of-cpp-development.md)\
Visual Studio IDE を使用し、プロジェクトの作成、コードの編集、ライブラリへのリンク、コンパイル、デバッグ、単体テストの作成、静的分析の実行、配置などを行う方法。

[プロジェクトおよびビルド システム](../build/projects-and-build-systems-cpp.md)\
MSVC のコンパイラ オプションとリンカー オプションを使用し、Visual Studio C++ プロジェクト、CMake プロジェクト、その他のプロジェクトを作成し、構成する方法です。

[C++ コードの作成とリファクタリング](../ide/writing-and-refactoring-code-cpp.md)\
C++ エディターの生産性機能を使用し、コードのリファクタリング、理解、記述を行う方法です。

[ネイティブ コードのデバッグ](/visualstudio/debugger/debugging-native-code)\
C++ プロジェクトで Visual Studio デバッガーを使用する。

[C/C++ のコード分析の概要](../code-quality/code-analysis-for-c-cpp-overview.md)\
静的な分析を行うために、SAL 注釈または C++ Core Guidelines チェッカーを使用する。

[Visual Studio で C/C++ 用の単体テストを作成する](/visualstudio/test/writing-unit-tests-for-c-cpp)\
C++ 用の Microsoft 単体テスト フレームワーク、Google Test、Boost.Test または CTest を使用して、単体テストを作成する。

## <a name="write-applications-in-c"></a>C++ でアプリケーションを作成する

[ユニバーサル Windows アプリ (C++)](../cppcx/universal-windows-apps-cpp.md)\
Windows Developer Center 内にあるガイドとリファレンス コンテンツを探します。 UWP アプリの開発の詳細については、「[ユニバーサル Windows プラットフォームの紹介](/windows/uwp/get-started/universal-application-platform-guide)」と、[C++ を使用した最初の UWP アプリの作成](/windows/uwp/get-started/create-a-basic-windows-10-app-in-cpp)に関するページを参照してください。

[デスクトップ アプリケーション (C++)](../windows/desktop-applications-visual-cpp.md)\
Windows 向けの従来のネイティブ C++ デスクトップ アプリケーションの作成方法について説明します。

[C++/CLI による .NET プログラミング](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)\
ネイティブの C++ と、C# や Visual Basic などの言語で記述されている .NET プログラムの間の相互運用を可能にする DLL の作成方法。

[Linux でのプログラミング](../linux/index.yml)\
GCC でコンパイルするためにリモートの Linux マシンにコードを記述し配置するために Visual Studio IDE を使用する方法。

[Visual Studio での C/C++ DLL の作成](../build/dlls-in-visual-cpp.md)\
Win32、ATL、および MFC を使用して Windows のデスクトップ DLL を作成する方法、さらには DLL をコンパイルおよび登録する方法。

[並列プログラミング](../parallel/parallel-programming-in-visual-cpp.md)\
並列パターン ライブラリ、C++ AMP、OpenMP、その他 Windows 上でのマルチスレッド化に関連する機能を使用する方法。

[セキュリティ推奨事項](../security/security-best-practices-for-cpp.md)\
悪意のあるコードや不正使用からアプリケーションを保護する方法を説明します。

[クラウドおよび Web プログラミング](../cloud/cloud-and-web-programming-in-visual-cpp.md)\
C++ では、Web とクラウドに接続するためのいくつかの方法があります。

[データ アクセス](../data/data-access-in-cpp.md)\
ODBC と OLE DB を使用してデータベースに接続します。

[テキストと文字列](../text/text-and-strings-in-visual-cpp.md)\
さまざまなテキスト形式および文字列形式の処理、およびローカルおよび国際対応の開発におけるエンコーディングの処理について説明します。

## <a name="languages-reference"></a>言語リファレンス

[C++ 言語リファレンス](../cpp/cpp-language-reference.md)\
C++ プログラミング言語の Microsoft の実装に関するリファレンス ガイド。

[C/C++ のプリプロセッサ リファレンス](../preprocessor/c-cpp-preprocessor-reference.md)\
C と C++ の共有言語プリプロセッサに関する共通のリファレンス。

[C 言語リファレンス](../c-language/c-language-reference.md)\
C プログラミング言語の Microsoft の実装に関するリファレンス ガイド。

[コンパイラの組み込みとアセンブリ言語](../intrinsics/compiler-intrinsics-and-assembly-language.md)\
各プラットフォームで Microsoft C/C++ コンパイラによってサポートまたは実装されているコンパイラ組み込みに関するガイド。

## <a name="c-libraries-in-visual-studio"></a>Visual Studio での C++ ライブラリ

以下のセクションでは、Visual Studio に含まれるさまざまな C および C++ ライブラリについて説明します。

[C ランタイム ライブラリ リファレンス](../c-runtime-library/c-run-time-library-reference.md)\
セキュリティ上の問題が発生することがわかっている関数に対する、セキュリティを強化された代替品が含まれています。

[C++ 標準ライブラリ](../standard-library/cpp-standard-library-reference.md)\
C++ 標準ライブラリ。

[Active Template Library (ATL)](../atl/atl-com-desktop-components.md)\
COM コンポーネントとアプリのサポート。

[Microsoft Foundation Class (MFC) ライブラリ](../mfc/mfc-desktop-applications.md)\
従来型または Office スタイルのユーザー インターフェイスを持つデスクトップ アプリケーションの作成のサポート。

[並列パターン ライブラリ (PPL)](../parallel/concrt/parallel-patterns-library-ppl.md)\
CPU で実行する非同期および並列アルゴリズム。

[C++ AMP (C++ Accelerated Massive Parallelism)](../parallel/amp/cpp-amp-cpp-accelerated-massive-parallelism.md)\
GPU で実行する膨大な並列アルゴリズム。

[Windows ランタイム C++ テンプレート ライブラリ (WRL)](../cppcx/wrl/windows-runtime-cpp-template-library-wrl.md)\
ユニバーサル Windows プラットフォーム (UWP) アプリとコンポーネント。

[C++/CLI による .NET プログラミング](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)\
共通言語ランタイム (CLR) のプログラミング。

## <a name="third-party-open-source-c-libraries"></a>サード パーティ製オープン ソースの C++ ライブラリ

クロスプラットフォームの **vcpkg** コマンドライン ツールを使用すると、900 を超える C++ オープンソース ライブラリの探索およびインストールを大幅に簡略化することができます。 「[vcpkg: Windows 用の C++ パッケージ マネージャー](../build/vcpkg.md)」を参照してください。

## <a name="feedback-and-community"></a>フィードバックとコミュニティ

[Microsoft Docs Q&A](/answers/topics/c%2B%2B.html)\
Microsoft Docs により、質問と回答のための検索可能なフォーラムがホストされています。 `C++` タグを追加して投稿すると、C++ 関連の問題についてコミュニティが助けてくれます。

[Microsoft C/C++ ツールセットで問題を報告する方法](how-to-report-a-problem-with-the-visual-cpp-toolset.md)\
Microsoft C/C++ ツールセット (コンパイラ、リンカー、その他のツール) に対して効果的なエラー レポートを作成する方法とレポートの提出方法について説明します。

Microsoft [C++ チーム ブログ](https://devblogs.microsoft.com/cppblog/)\
Visual Studio の C++ ツールの開発者による新機能と最新の情報に関する詳細を示します。

[Visual Studio C++ 開発者コミュニティ](https://aka.ms/vsfeedback/browsecpp)\
支援を受けたり、バグを報告したり、Visual Studio での C++ について提案したりします。

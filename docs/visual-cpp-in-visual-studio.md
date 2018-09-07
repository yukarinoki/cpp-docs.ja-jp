---
title: Visual Studio の Visual C++ | Microsoft Docs
ms.custom: ''
ms.date: 08/22/2018
ms.technology:
- cpp-ide
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- unmanaged code, C++
- development environment, Visual C++
- unmanaged code
- Visual C++
- Visual C++, reference
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 6116a1b27595c6400edfcb79daafb362fb7aec5f
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/04/2018
ms.locfileid: "43684492"
---
# <a name="visual-c-in-visual-studio"></a>Visual Studio の Visual C++

> [!NOTE]  
> この開発者向けドキュメントは、Visual Studio 2015 と Visual Studio 2017 に適用されます。 

> プログラムを実行するために Visual C++ 再頒布可能パッケージを探している場合、[Microsoft ダウンロード センター](http://www.microsoft.com/en-us/download/)にアクセスして検索ボックスに「**Visual C++**」と入力してください。  
  

Microsoft Visual C++ (通常は短縮形で Visual C++ または MSVC と表現される) とは、Windows 上で Visual Studio の一部として利用できる C++、C、およびアセンブリ言語の開発ツールおよびライブラリの名前です。 これらのツールとライブラリでは、ユニバーサル Windows プラットフォーム (UWP) アプリ、ネイティブ Windows デスクトップおよびサーバー アプリケーション、Windows、Linux、Android、iOS 上で実行されるクロスプラットフォーム ライブラリおよびアプリに加えて、.NET Framework を使用する管理対象のアプリおよびライブラリを作成できます。 Visual C++ を使用すると、単純なコンソール アプリから最も高度で複雑な Windows デスクトップ用アプリまで、またデバイス ドライバーやオペレーティング システムのコンポーネントからモバイル デバイス用のクロスプラットフォーム ゲームまで、さらに最小の IoT デバイスから Azure クラウドにおけるマルチ サーバー ハイ パフォーマンス コンピューティングに至るまであらゆるアプリを記述することができます。

## <a name="whats-new-and-conformance-history"></a>新機能と準拠の履歴

[Visual Studio 2017 での C++ の新機能](what-s-new-for-visual-cpp-in-visual-studio.md)<br/>
Visual C++ 2017 の新機能を紹介します。

[Visual Studio 2003 から 2015 の C++ の新機能](porting/visual-cpp-what-s-new-2003-through-2015.md)<br/>
Visual Studio 2003 から 2015 の各バージョンの、C++ の新機能を紹介します。

[Visual Studio 2017 の C++ 準拠の強化](cpp-conformance-improvements-2017.md)<br/>
Visual Studio 2017 の C++ 準拠の強化について説明します。

[Visual C++ 言語への準拠](visual-cpp-language-conformance.md)<br/>
MSVC C++ コンパイラの各機能の準拠状態を一覧にしています。

[2003 から 2015 の Visual C++ の履歴の変更](porting/visual-cpp-change-history-2003-2015.md)<br/>
前のバージョンの互換性に影響する変更点について説明します。

## <a name="install-visual-studio-and-upgrade-from-earlier-versions"></a>Visual Studio をインストールして、以前のバージョンからアップグレードする

[Visual Studio での C++ サポートのインストール](build/vscpp-step-0-installation.md)<br/>
Visual Studio 2015 または Visual Studio 2017 をダウンロードして、Visual C++ ツールセットをインストールします。

[Visual C++ 移植とアップグレードのガイド](porting/visual-cpp-porting-and-upgrading-guide.md)<br/>
Windows 10 とユニバーサル Windows プラットフォームに C++ コードを移植するなど、Visual Studio 2015 または Visual Studio 2017 へのコードの移植およびプロジェクトのアップグレードのガイダンス。

[さまざまな Visual Studio エディションの Visual C++ ツールおよび機能](ide/visual-cpp-tools-and-features-in-visual-studio-editions.md)<br/>
さまざまな Visual Studio のエディションに関する情報。

[サポートされているプラットフォーム](supported-platforms-visual-cpp.md)<br/>
サポート対象プラットフォームに関する情報。

## <a name="learn-c"></a>C++ について

[C++ へようこそ](cpp/welcome-back-to-cpp-modern-cpp.md)<br/>
C++11 と C++14 を基盤とする現代的な C++ プログラミング手法にかんする情報。高速で安全なコードを記述し、C スタイルのプログラミングの潜在的な危険を回避できます。

[標準 C++](http://isocpp.org/)<br/>
C++ について学び、最新の C++ の概要を把握し、書籍、記事、講演、イベントなどへのリンクを探します

[Visual C++ に関する詳細情報](build/vscpp-step-1-create.md)<br/>
C++ について学び始める。

[Visual C++ のサンプル](visual-cpp-samples.md)<br/>
サンプルに関する情報。

## <a name="c-development-tools"></a>C++ 開発ツール

[IDE と開発ツール](ide/ide-and-tools-for-visual-cpp-development.md)。
Visual Studio IDE を使用してプロジェクトの作成、ソース コード ファイルの操作、ライブラリへのリンク、コンパイル、デバッグ、単体テストの作成、静的分析の実行、配置などを行う方法。

[コンパイラおよびビルド ツール](build/building-c-cpp-programs.md) Microsoft C++ コンパイラとリンカーのオプション、エラー メッセージ、コマンドラインの例、さまざまなプラットフォームの構成、ビルド リファレンス トピック。 

## <a name="write-applications-in-c"></a>C++ でアプリケーションを作成する

[ユニバーサル Windows アプリ](windows/universal-windows-apps-cpp.md)<br/>
Windows Developer Center 内にあるガイドとリファレンス コンテンツを探します。 UWP アプリの開発の詳細については、「[ユニバーサル Windows プラットフォームの紹介](/windows/uwp/get-started/universal-application-platform-guide)」と、[C++ を使用した最初の UWP アプリの作成](/windows/uwp/get-started/create-a-basic-windows-10-app-in-cpp)に関するページを参照してください。

[デスクトップ アプリケーション (C++)](windows/desktop-applications-visual-cpp.md)<br/>
Windows 向けの従来のネイティブ C++ デスクトップ アプリケーションの作成方法について説明します。

[C++/CLI による .NET プログラミング](dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md) ネイティブの C++ と、C# や Visual Basic などの言語で記述されている .NET プログラムの間の相互運用を可能にする DLL の作成方法について説明します。

[Linux プログラミング](linux/index.md) コーディングと GCC によるコンパイル用のリモート Linux マシンへの配置に Visual Studio IDE を使用します。

[Visual C++ の DLL](build/dlls-in-visual-cpp.md)<br/>
Win32、ATL、および MFC を使用して Windows のデスクトップ DLL を作成する方法、さらには DLL をコンパイルおよび登録する方法。

[並列プログラミング](parallel/parallel-programming-in-visual-cpp.md)<br/>
並列パターン ライブラリ、C++ AMP、OpenMP、その他 Windows 上でのマルチスレッド化に関連する機能を使用する方法。

[セキュリティ推奨事項](security/security-best-practices-for-cpp.md)<br/>
悪意のあるコードや不正使用からアプリケーションを保護する方法。

[クラウドおよび Web プログラミング](cloud/cloud-and-web-programming-in-visual-cpp.md)<br/>
C++ では、Web とクラウドに接続するためのいくつかの方法があります。

[データ アクセス](data/data-access-in-cpp.md)<br/>
ODBC およびその他のデータベース アクセス テクノロジを使用してデータベースに接続します。

[テキストと文字列](text/text-and-strings-in-visual-cpp.md)<br/>
さまざまなテキスト形式および文字列形式の処理、およびローカルおよび国際対応の開発におけるエンコーディングの処理について説明します。

## <a name="c-language-reference"></a>C++ 言語リファレンス

C++ 言語については、「 [C++ Language Reference](cpp/cpp-language-reference.md)」を参照してください。

C++ プリプロセッサの詳細については、「 [C/C++ Preprocessor Reference](preprocessor/c-cpp-preprocessor-reference.md)」を参照してください。

## <a name="c-libraries-in-visual-studio"></a>Visual Studio での C++ ライブラリ

以下のセクションでは、Visual Studio に含まれるさまざまな C および C++ ライブラリについて説明します。

[C ランタイム ライブラリ リファレンス](c-runtime-library/c-run-time-library-reference.md)<br/>
セキュリティ上の問題が発生することがわかっている関数に対する、セキュリティを強化された代替品が含まれています。

[.NET 標準ライブラリ](standard-library/cpp-standard-library-reference.md)<br/>
C++ 標準ライブラリ。

[Active Template Library (ATL)](atl/atl-com-desktop-components.md)<br/>
COM コンポーネントとアプリのサポート。

[Microsoft Foundation Class (MFC) ライブラリ](mfc/mfc-desktop-applications.md)<br/>
従来型または Office スタイルのユーザー インターフェイスを持つデスクトップ アプリケーションの作成のサポート。

[並列パターン ライブラリ (PPL)](parallel/concrt/parallel-patterns-library-ppl.md)<br/>
CPU で実行する非同期および並列アルゴリズム。

[C++ AMP (C++ Accelerated Massive Parallelism)](parallel/amp/cpp-amp-cpp-accelerated-massive-parallelism.md)<br/>
GPU で実行する膨大な並列アルゴリズム。

[Windows ランタイム C++ テンプレート ライブラリ (WRL)](windows/windows-runtime-cpp-template-library-wrl.md)<br/>
ユニバーサル Windows プラットフォーム (UWP) アプリとコンポーネント。

[C++/CLI による .NET プログラミング](dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)<br/>
共通言語ランタイム (CLR) のプログラミング。

## <a name="third-party-open-source-c-libraries"></a>サード パーティ製オープン ソースの C++ ライブラリ

クロスプラットフォームの **vcpkg** コマンドライン ツールを使用すると、900 を超える C++ オープンソース ライブラリの探索およびインストールを大幅に簡略化することができます。 「[vcpkg: Windows 用の C++ パッケージ マネージャー](vcpkg.md)」を参照してください。

## <a name="feedback-and-community"></a>フィードバックとコミュニティ

[Visual C++ ツールセットで問題を報告する方法](how-to-report-a-problem-with-the-visual-cpp-toolset.md)<br/>
Visual C++ ツールセット (コンパイラ、リンカー、その他のツール) に対して効果的なエラー レポートを作成する方法とレポートの提出方法に関す情報。

[Visual C++ チーム ブログ](http://blogs.msdn.com/b/vcblog/)<br/>
[!INCLUDE[vcprvc](build/includes/vcprvc_md.md)]の開発者による新機能と最新の情報に関する詳細。

[Visual Studio 開発者コミュニティ](https://developercommunity.visualstudio.com/)<br/>
Visual Studio のサポート、バグの報告、提案に関する情報。

## <a name="see-also"></a>関連項目

- [C 言語リファレンス](c-language/c-language-reference.md)
- [C ランタイム ライブラリ リファレンス](c-runtime-library/c-run-time-library-reference.md)
- [コンパイラの組み込みとアセンブリ言語](intrinsics/compiler-intrinsics-and-assembly-language.md)

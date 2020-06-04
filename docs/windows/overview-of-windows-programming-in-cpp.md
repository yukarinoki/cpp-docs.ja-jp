---
title: C++ でプログラミングする Windows の概要
ms.date: 09/17/2019
ms.assetid: efc691d7-21f3-47ae-ae56-cab999ccf59d
ms.openlocfilehash: 8ab7fbf7c955b1c828ef583aa639eda7409cf167
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81359941"
---
# <a name="overview-of-windows-programming-in-c"></a>C++ でプログラミングする Windows の概要

C++ で作成できる Windows アプリケーションには、さまざまなカテゴリがあります。 それぞれに独自のプログラミング モデルと Windows 固有のライブラリのセットがありますが、C++ 標準ライブラリとサードパーティの C++ ライブラリは、それらのいずれでも使用できます。

このセクションでは、Visual Studio と MFC/ATL ラッパー ライブラリを使用して Windows プログラムを作成する方法について説明します。 Windows プラットフォーム自体のドキュメントについては[、Windows のドキュメントを参照してください](/windows/index)。

## <a name="command-line-console-applications"></a>コマンド・ライン (コンソール) アプリケーション

C++ コンソール アプリケーションは、コンソール ウィンドウのコマンド ラインから実行され、テキスト出力のみを表示できます。 詳細については[、「C++ コンソール アプリ プロジェクトの作成](../get-started/tutorial-console-cpp.md)」を参照してください。

## <a name="native-desktop-client-applications"></a>ネイティブ デスクトップ クライアント アプリケーション

*ネイティブ デスクトップ クライアント アプリケーション*は、元のネイティブ Windows C API[またはコンポーネント オブジェクト モデル (COM) API を](/windows/win32/apiindex/windows-api-list)使用してオペレーティング システムにアクセスする C または C++ ウィンドウ付きアプリケーションです。 これらの API 自体は主に C で書かれています。ネイティブ デスクトップ アプリを作成する方法は複数あります: オペレーティング システム のイベントを処理する C スタイルのメッセージ ループを使用して、Win32 API を直接使用してプログラムできます。 または、Win32 をラップするオブジェクト指向の C++ ライブラリである*MFC (MFC)* を使用してプログラムを作成することもできます。 どちらのアプローチも、ユニバーサル Windows プラットフォーム (UWP) と比較して「モダン」とは見なされませんが、どちらも完全にサポートされており、現在世界で何百万行ものコードが実行されています。 ウィンドウで実行される Win32 アプリケーションでは、Windows プロシージャ関数内で Windows メッセージを明示的に処理する必要があります。 名前に関わらず、Win32 アプリケーションは 32 ビット (x86) または 64 ビット (x64) のバイナリとしてコンパイルできます。 Visual Studio IDE では、用語 x86 と Win32 は同義語です。

従来の Windows C++ プログラミングを開始するには[、「Win32 および C++ の使用を開始](/windows/win32/LearnWin32/learn-to-program-for-windows)する」を参照してください。 Win32 について理解した後で[、MFC デスクトップ アプリケーション](../mfc/mfc-desktop-applications.md)について学ぶのが簡単になります。 高度なグラフィックスを使用する従来の C++ デスクトップ アプリケーションの例については[、「Hilo: Windows 用 C++ アプリケーションの開発](https://msdn.microsoft.com/library/windows/desktop/ff708696.aspx)」を参照してください。

### <a name="c-or-net"></a>C++ または .NET?

一般に、C# での .NET プログラミングは、複雑性が低く、エラーが発生しにくく、Win32 や MFC よりも最新のオブジェクト指向 API を備えています。 ほとんどの場合、パフォーマンスは十分ではありません。 .NET は、リッチ グラフィックス用の Windows プレゼンテーション ファウンデーション (WPF) を備えており、Win32 と最新の Windows ランタイム API の両方を使用できます。 一般的な規則として、デスクトップ アプリケーションで C++ を使用することをお勧めします。

- メモリ使用量を正確に制御
- 電力消費の最大限の経済
- 一般的なコンピューティングのためのGPUの使用
- DirectX へのアクセス
- 標準 C++ ライブラリの大量使用

C++ の能力と効率を .NET プログラミングと組み合わせることも可能です。 C# でユーザー インターフェイスを作成し、C++/CLI を使用して、アプリケーションがネイティブ C++ ライブラリを使用できるようにします。 詳細については、「 [C++/CLI を使用した .NET プログラミング](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)」を参照してください。

## <a name="com-components"></a>COM コンポーネント

[コンポーネント オブジェクト モデル (COM) は](/windows/win32/com/the-component-object-model)、異なる言語で記述されたプログラムが相互に通信できるようにする仕様です。 多くの Windows コンポーネントは、COM オブジェクトとして実装され、オブジェクトの作成、インターフェイスの検出、およびオブジェクトの破棄に関する標準の COM 規則に従います。  C++ デスクトップ アプリケーションからの COM オブジェクトの使用は比較的簡単ですが、独自の COM オブジェクトの作成がより高度になります。 [アクティブ テンプレート ライブラリ (ATL) には](../atl/atl-com-desktop-components.md)、COM 開発を簡略化するマクロとヘルパー関数が用意されています。 詳細については[、「ATL COM デスクトップ コンポーネント](../atl/atl-com-desktop-components.md)」を参照してください。

## <a name="universal-windows-platform-apps"></a>ユニバーサル Windows プラットフォーム アプリ

ユニバーサル Windows プラットフォーム (UWP) は、最新の Windows API です。 UWP アプリは、任意の Windows 10 デバイスで実行され、ユーザー インターフェイスに XAML を使用し、完全にタッチ対応です。 UWP の詳細については、「[ユニバーサル Windows プラットフォーム (UWP) アプリとは」および「Windows ユニバーサル](/windows/uwp/get-started/whats-a-uwp)[アプリの概要](/windows/uwp/get-started/universal-application-platform-guide)」を参照してください。

UWP の元の C++ サポートは、(1) C++/CX、構文拡張機能を含む C++ の方言、または (2) 標準の C++ と COM に基づく Windows ランタイム ライブラリ (WRL) で構成されていました。 C++/CX と WRL の両方がサポートされています。 新しいプロジェクトの場合は、標準 C++ に基づいており、パフォーマンスが向上する[C++/WinRT](/windows/uwp/cpp-and-winrt-apis/intro-to-using-cpp-with-winrt)をお勧めします。

## <a name="desktop-bridge"></a>デスクトップ ブリッジ

Windows 10 では、既存のデスクトップ アプリケーションまたは COM オブジェクトを UWP アプリとしてパッケージ化し、タッチなどの UWP 機能を追加したり、最新の Windows API セットから API を呼び出したりできます。 また、Uwp アプリを Visual Studio のデスクトップ ソリューションに追加し、1 つのパッケージにパッケージ化し、Windows API を使用してそれらの間で通信を行うこともできます。

Visual Studio 2017 バージョン 15.4 以降では、Windows アプリケーション パッケージ プロジェクトを作成して、既存のデスクトップ アプリケーションのパッケージ化作業を大幅に簡略化できます。 デスクトップ アプリケーションで使用できるレジストリ呼び出しや API には、いくつかの制限が適用されます。 ただし、多くの場合、アプリ パッケージで実行している間に同様の機能を実現する代替コード パスを作成できます。 詳細については、[デスクトップ ブリッジ](/windows/uwp/porting/desktop-to-uwp-root)に関するページをご覧ください。

## <a name="games"></a>ゲーム

DirectX ゲームは PC または Xbox で実行できます。 詳細については、「 [DirectX グラフィックスとゲーム](/windows/win32/directx)」を参照してください。

## <a name="sql-server-database-clients"></a>SQL サーバー データベース クライアント

ネイティブ コードから SQL Server データベースにアクセスするには、ODBC または OLE DB を使用します。 詳細については、「 [SQL Server Native Client](/sql/relational-databases/native-client/odbc/sql-server-native-client-odbc)」を参照してください。

## <a name="windows-device-drivers"></a>Windows デバイス ドライバー

ドライバーは、アプリケーションやその他のオペレーティング システム コンポーネントからハードウェア デバイスからデータをアクセスできるようにする低レベルのコンポーネントです。 詳細については、「 [Windows ドライバー キット (WDK)」](/windows-hardware/drivers/index)を参照してください。

## <a name="windows-services"></a>Windows サービス

Windows*サービス*は、ユーザー操作がほとんどまたはまったくないバックグラウンドで実行できるプログラムです。 これらのプログラムは UNIX システム*上のデーモン*と呼ばれます。 詳細については、「 [サービス](/windows/win32/services/services)」を参照してください。

## <a name="sdks-libraries-and-header-files"></a>SDK、ライブラリ、およびヘッダー ファイル

Visual Studio には、C ランタイム ライブラリ (CRT)、C++ 標準ライブラリ、およびその他のマイクロソフト固有のライブラリが含まれています。 これらのライブラリのヘッダー ファイルを含むインクルード フォルダーのほとんどは、Visual Studio のインストール ディレクトリにある \VC\ フォルダーの下にあります。 Windows および CRT ヘッダー ファイルは、Windows SDK のインストール フォルダーにあります。

[Vcpkg パッケージ マネージャー](../build/vcpkg.md)を使用すると、Windows 用の数百のサードパーティ製のオープン ソース ライブラリを簡単にインストールできます。

マイクロソフトのライブラリには、次のものがあります。

- Microsoft Foundation Classes (MFC): ボタン、リスト ボックス、ツリー ビュー、および他のコントロールを使用した豊富なユーザー インターフェイスを持つ従来の Windows プログラム (特にエンタープライズ アプリケーション) を作成するためのオブジェクト指向フレームワーク。 詳細については、「 [MFC Desktop Applications](../mfc/mfc-desktop-applications.md)」を参照してください。

- Active Template Library (ATL): COM コンポーネントを作成するための強力なヘルパー ライブラリ。 詳細については、「 [ATL COM Desktop Components](../atl/atl-com-desktop-components.md)」を参照してください。

- C++ AMP (C++ Accelerated Massive Parallelism): GPU で一般的な計算作業のパフォーマンス向上を可能にするライブラリ。 詳細については、「 [C++ AMP (C++ Accelerated Massive Parallelism)](../parallel/amp/cpp-amp-cpp-accelerated-massive-parallelism.md)」を参照してください。

- コンカレンシー ランタイム: マルチコア デバイスおよびメニーコア デバイス用の並列プログラミングおよび非同期プログラミング作業を簡略化するために役立つライブラリ。 詳細については、「[コンカレンシー ランタイム](../parallel/concrt/concurrency-runtime.md)」を参照してください。

Windows プログラミングの多くのシナリオでは、Windows SDK も必要になります。これには、Windows オペレーティング システム コンポーネントへのアクセスを可能にするためのヘッダー ファイルが含まれています。 既定では、Visual Studio は、Windows SDK を C++ デスクトップ ワークロードのコンポーネントとしてインストールし、ユニバーサル Windows アプリの開発を可能にします。 UWP アプリを開発するには、Windows 10 バージョンの Windows SDK が必要です。 詳細については[、「Windows 10 SDK」](https://dev.windows.com/downloads/windows-10-sdk)を参照してください。 (以前のバージョンの Windows の Windows SDK の詳細については[、Windows SDK](https://developer.microsoft.com/windows/downloads/sdk-archive)のアーカイブを参照してください)。

**プログラム ファイル (x86)\Windows キット**は、インストールしたすべてのバージョンの Windows SDK の既定の場所です。

Xbox や Azure など、他のプラットフォームには、インストールを要する独自の SDK があります。 詳細については、DirectX デベロッパー センターおよび Azure デベロッパー センターを参照してください。

## <a name="development-tools"></a>開発ツール

Visual Studio には、ネイティブ コード用の強力なデバッガー、スタティック分析ツール、グラフィックス デバッグ ツール、フル装備のコード エディター、単体テストのサポート、その他多数のツールおよびユーティリティが含まれています。 詳細については、「 [Visual Studio を使用した開発の概要](/visualstudio/ide/get-started-developing-with-visual-studio)」および「 [Visual Studio での C++ 開発の概要](../overview/overview-of-cpp-development.md)」を参照してください。

## <a name="in-this-section"></a>このセクションの内容

|タイトル|説明|
|-----------|-----------------|
|[チュートリアル: 標準 C++ プログラムの作成](walkthrough-creating-a-standard-cpp-program-cpp.md)| Windows コンソール アプリケーションを作成します。|
|[チュートリアル: Windows デスクトップ アプリケーション (C++) の作成](walkthrough-creating-windows-desktop-applications-cpp.md)|ネイティブ Windows デスクトップ アプリケーションを作成します。|
|[Windows デスクトップ ウィザード](windows-desktop-wizard.md)|ウィザードを使用して、新しい Windows プロジェクトを作成します。|
|[Active Template Library (ATL)](../atl/atl-com-desktop-components.md)|ATL ライブラリを使用して、C++ で COM コンポーネントを作成します。|
|[Microsoft Foundation Classes (MFC)](../mfc/mfc-desktop-applications.md)|MFC を使用して、ダイアログやコントロールを含む大きな Windows アプリケーションまたは小さな Windows アプリケーションを作成する|
|[ATL および MFC 共有クラス](../atl-mfc-shared/atl-mfc-shared-classes.md)|ATL や MFC で共有される CString などのクラスを使用します。|
|[データ アクセス](../data/data-access-in-cpp.md)| OLE DB および ODBC|
|[テキストと文字列](../text/text-and-strings-in-visual-cpp.md)|Windows 上のさまざまな文字列型。|
|[DirectX を使用してゲームを作成するためのリソース](resources-for-creating-a-game-using-directx.md)
|[方法: Windows デスクトップ アプリケーションでの Windows 10 SDK の使用](how-to-use-the-windows-10-sdk-in-a-windows-desktop-application.md)|Windows SDK|
|[リソース ファイルの操作](working-with-resource-files.md)|デスクトップ アプリケーションにイメージ、アイコン、文字列テーブル、およびその他のリソースを追加する方法。|
|[DirectX を使用するゲームを作成するためのリソース (C++)](resources-for-creating-a-game-using-directx.md)|C++ でゲームを作成するためのコンテンツへのリンク。|
|[方法: Windows デスクトップ アプリケーションでの Windows 10 SDK の使用](how-to-use-the-windows-10-sdk-in-a-windows-desktop-application.md)|Windows 10 SDK を使用してビルドするプロジェクトの設定手順が示されています。|
|[ネイティブ デスクトップ アプリケーションの配置](deploying-native-desktop-applications-visual-cpp.md)|ネイティブ アプリケーションを Windows に展開します。|

## <a name="related-articles"></a>関連記事

|タイトル|説明|
|-----------|-----------------|
|[C++ のビジュアル スタジオ](../overview/visual-cpp-in-visual-studio.md)|Visual C++ 開発者向けコンテンツの親トピックです。|
[C++/CLI を使用した .NET 開発](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)|ネイティブ C++ ライブラリのラッパーを作成して、.NET アプリケーションおよびコンポーネントとの通信を可能にします。|
|[NET および UWP 用のコンポーネント拡張機能](../extensions/component-extensions-for-runtime-platforms.md)|C++/CX および C++/CLI で共有される構文要素のリファレンス。|
|[ユニバーサル Windows アプリ (C++)](../cppcx/universal-windows-apps-cpp.md)|C++/CX または Windows ランタイム テンプレート ライブラリ (WRL) を使用して UWP アプリケーションを作成します。|
|[COM および .NET 用の C++ の属性](attributes/cpp-attributes-com-net.md)|NET または COM を使用した Windows 専用プログラミングの標準以外の属性。|

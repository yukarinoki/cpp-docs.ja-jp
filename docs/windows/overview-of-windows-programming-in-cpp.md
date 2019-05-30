---
title: C++ でプログラミングする Windows の概要
ms.date: 05/06/2019
ms.assetid: efc691d7-21f3-47ae-ae56-cab999ccf59d
ms.openlocfilehash: 585fda614acce85e286e25b807d0fda57d03758b
ms.sourcegitcommit: af580f3a11b19d22288424eac7ceae1bc24ab312
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/29/2019
ms.locfileid: "66355562"
---
# <a name="overview-of-windows-programming-in-c"></a>C++ でプログラミングする Windows の概要

いくつかの C++ を使用して作成する Windows アプリケーションの広範なカテゴリがあります。 独自のプログラミング モデルと Windows 固有のライブラリのセットが、C++標準ライブラリおよびサード パーティ製C++ライブラリは、これらのいずれかで使用できます。

## <a name="command-line-console-applications"></a>コマンドライン (コンソール) アプリケーション

C++ コンソール アプリケーションでは、コンソール ウィンドウでコマンドラインから実行し、テキスト出力のみを表示できます。 詳細については、次を参照してください。[コンソール アプリケーション](console-applications-in-visual-cpp.md)します。

## <a name="native-desktop-client-applications"></a>ネイティブのデスクトップ クライアント アプリケーション

A*ネイティブのデスクトップ クライアント アプリケーション*は C またはC++元ネイティブを使用するウィンドウを持つアプリケーション[Windows C Api またはコンポーネント オブジェクト モデル (COM) Api](/windows/desktop/apiindex/windows-api-list)オペレーティング システムにアクセスします。 これらの Api は c 言語でほとんどの場合ネイティブなデスクトップ アプリを作成するには、複数の方法があります。プログラミングできます Win32 Api を直接を使用してオペレーティング システムのイベントを処理する C スタイルのメッセージ ループを使用します。 またはを使用してプログラミングできます*Microsoft Foundation Classes* (MFC)、軽くオブジェクト指向C++Win32 をラップするライブラリです。 どちらもアプローチが「最新」ユニバーサル Windows プラットフォーム (UWP) への比較と見なさが、両方は引き続き完全にサポートし、何百万もの世界中で現在実行しているコードの行があります。 ウィンドウで実行される Win32 アプリケーションでは、Windows プロシージャ関数内での Windows メッセージを明示的に使用する開発者が必要です。 名前にかかわらず、Win32 アプリケーションは、32 ビット (x86) または 64 ビット (x64) バイナリとしてコンパイルできます。 Visual Studio ide、Win32、x86 の用語は同義です。

従来の Windows C プログラミングを開始するを参照してください。 [Win32 と C++ の概要](/windows/desktop/LearnWin32/learn-to-program-for-windows)します。 Win32 のいくつか理解できるように後の詳細について簡単になります[MFC Desktop Applications](../mfc/mfc-desktop-applications.md)します。 高度なグラフィックスを使用する従来の C++ デスクトップ アプリケーションの例は、次を参照してください[Hilo:。Windows 対応 C++ アプリケーションの開発](https://msdn.microsoft.com/library/windows/desktop/ff708696.aspx)します。

### <a name="c-or-net"></a>C++ または .NET でしょうか。

一般的な .NET プログラミングC#ほど複雑で、低いエラーを起こしやすいの Win32 または MFC より最新オブジェクト指向 API であり。 ほとんどの場合、そのパフォーマンスで十分です。 .NET 機能の豊富なグラフィックスは、Windows Presentation Foundation (WPF) と Win32 と最新の Windows ランタイム API の両方を使用することができます。 一般的な規則として、必要とする場合は、デスクトップ アプリケーションの C++ を使用してお勧めします。

- メモリ使用量を正確に制御
- 電力消費量の最大限の経済性
- 一般的なコンピューティングの GPU の使用状況
- DirectX へのアクセスします。
- 標準 C ライブラリの使用率が高い

電源との効率を結合することもC++.NET プログラミングします。 ユーザー インターフェイスを作成することができますC#C + を使用して/cli CLI ネイティブの C++ ライブラリを使用するアプリケーションを有効にします。 詳細については、次を参照してください。 [C + での .NET プログラミング/cli CLI](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)します。

## <a name="com-components"></a>COM コンポーネント

[コンポーネント オブジェクト モデル (COM)](/windows/desktop/com/the-component-object-model)は、プログラムが相互に通信するさまざまな言語で記述された仕様です。 多くの Windows コンポーネントは、COM オブジェクトとして実装され、オブジェクトの作成、インターフェイスの検出、およびオブジェクトの破棄の標準の COM 規則に従います。  C++ デスクトップ アプリケーションから COM オブジェクトを使用しては比較的簡単ですが、独自の COM オブジェクトの書き込みより高度な。 [Active Template Library (ATL)](../atl/atl-com-desktop-components.md)マクロおよび COM 開発を簡略化するヘルパー関数を提供します。 詳細については、次を参照してください。 [ATL COM デスクトップ コンポーネント](../atl/atl-com-desktop-components.md)します。

## <a name="universal-windows-platform-apps"></a>ユニバーサル Windows プラットフォーム アプリ

ユニバーサル Windows プラットフォーム (UWP) は、最新の Windows API です。 UWP アプリあらゆる Windows 10 デバイスで実行するには、XAML を使用して、ユーザー インターフェイスおよびが完全にタッチ対応します。 UWP の詳細については、次を参照してください。[ユニバーサル Windows プラットフォーム (UWP) アプリとは何ですか?](/windows/uwp/get-started/whats-a-uwp)と[Windows ユニバーサル アプリに関するガイド](/windows/uwp/get-started/universal-application-platform-guide)します。

元のC++UWP を行いました (1) のサポートC++/CX、言語にC++標準に基づくが、構文の拡張機能または (2)、Windows ランタイム ライブラリ (WRL) の場合は、C++および COM 両方C++/CX と WRL はサポートされています。 新しいプロジェクトの場合はお勧めします[ C++/WinRT](/windows/uwp/cpp-and-winrt-apis/intro-to-using-cpp-with-winrt)、これは、標準に基づいて完全C++し高速なパフォーマンスを提供します。

## <a name="desktop-bridge"></a>デスクトップ ブリッジ

Windows 10 で、既存のデスクトップ アプリケーションまたは COM オブジェクトを UWP アプリとしてパッケージ化し、タッチなどの UWP 機能を追加したり、最新の Windows API のセットから Api を呼び出します。 Visual Studio、およびパッケージをパッケージ化し、間の通信に Windows Api を使用して、1 つにまとめることでデスクトップ ソリューションに UWP アプリを追加することもできます。

Visual Studio 2017 バージョン 15.4 以降では、既存のデスクトップ アプリケーションをパッケージ化の作業を大幅に簡略化するには、Windows アプリケーション パッケージ プロジェクトを作成できます。 レジストリの呼び出しまたはデスクトップ アプリケーションで使用して Api にいくつかの制限が適用されます。 ただし、多くの場合は、アプリ パッケージの実行中に同様の機能を実現するために代替のコード パスを作成できます。 詳細については、[デスクトップ ブリッジ](/windows/uwp/porting/desktop-to-uwp-root)に関するページをご覧ください。

## <a name="games"></a>ゲーム

DirectX ゲームは、PC または Xbox で実行できます。 詳細については、次を参照してください。 [DirectX のグラフィックスとゲーム](/windows/desktop/directx)します。

## <a name="sql-server-database-clients"></a>SQL Server データベースのクライアント

ネイティブ コードから SQL Server データベースにアクセスするには、ODBC または OLE DB を使用します。 詳細については、「 [SQL Server Native Client](/sql/relational-databases/native-client/odbc/sql-server-native-client-odbc)」を参照してください。

## <a name="windows-device-drivers"></a>Windows デバイス ドライバー

ドライバーは、ハードウェア デバイスからのデータをアプリケーションにアクセスできるようにする低レベルのコンポーネントとその他のオペレーティング システムのコンポーネントです。 詳細については、次を参照してください。 [Windows Driver Kit (WDK)](/windows-hardware/drivers/index)します。

## <a name="windows-services"></a>Windows サービス

Windows*サービス*はほとんどまたはまったくないユーザーの操作でバック グラウンドで実行できるプログラムです。 これらのプログラムと呼ばれる*デーモン*UNIX システム。 詳細については、次を参照してください。[サービス](/windows/desktop/services/services)します。

## <a name="sdks-libraries-and-header-files"></a>Sdk、ライブラリ、およびヘッダー ファイル

Visual Studio には、C ランタイム ライブラリ (CRT)、C++ 標準ライブラリ、およびその他の Microsoft 固有のライブラリが含まれています。 これらのライブラリのヘッダー ファイルが格納されるインクルード フォルダーのほとんどは、Visual Studio インストール ディレクトリの \VC\ フォルダー下に配置されます。 Windows と CRT のヘッダー ファイルには、Windows SDK のインストール フォルダーが記載されています。

[Vcpkg パッケージ マネージャー](../build/vcpkg.md)に Windows の何百ものサード パーティ製オープン ソース ライブラリをインストールすることができます。

Microsoft ライブラリは次のとおりです。

- Microsoft Foundation Classes (MFC):従来の Windows プログラムを作成するためのオブジェクト指向のフレームワーク、特にエンタープライズ アプリケーション-高度なユーザー インターフェイスは、その機能のボタン、リスト ボックス、ツリー ビュー、およびその他のコントロールがあります。 詳細については、「 [MFC Desktop Applications](../mfc/mfc-desktop-applications.md)」を参照してください。

- Active Template Library (ATL):COM コンポーネントを作成するための強力なヘルパー ライブラリ。 詳細については、「 [ATL COM Desktop Components](../atl/atl-com-desktop-components.md)」を参照してください。

- C++ AMP (C++ Accelerated Massive Parallelism)。GPU 上でパフォーマンスの高い一般的な計算作業をできるようにするライブラリ。 詳細については、「 [C++ AMP (C++ Accelerated Massive Parallelism)](../parallel/amp/cpp-amp-cpp-accelerated-massive-parallelism.md)」を参照してください。

- 同時実行ランタイム:マルチコアおよびメニーコア デバイス用の並列および非同期プログラミングの作業を簡素化するライブラリ。 詳細については、「[コンカレンシー ランタイム](../parallel/concrt/concurrency-runtime.md)」を参照してください。

Windows プログラミングの多くのシナリオでは、Windows SDK も必要になります。これには、Windows オペレーティング システム コンポーネントへのアクセスを可能にするためのヘッダー ファイルが含まれています。 既定では、Visual Studio は、C++ デスクトップ ワークロードでは、ユニバーサル Windows アプリの開発のコンポーネントとして Windows SDK をインストールします。 UWP アプリを開発するには、Windows 10 バージョンの Windows SDK 必要があります。 詳しくは、次を参照してください。 [Windows 10 SDK](https://dev.windows.com/downloads/windows-10-sdk)します。 (Windows の以前のバージョンの Windows Sdk の詳細については、次を参照してください。、 [Windows SDK アーカイブ](https://developer.microsoft.com/windows/downloads/sdk-archive))。

**プログラム ファイル (x86) \Windows キット**はすべてのバージョンをインストールしたらの Windows SDK の既定の場所。

Xbox や Azure など、他のプラットフォームには、インストールを要する独自の SDK があります。 詳細については、DirectX デベロッパー センターおよび Azure デベロッパー センターを参照してください。

## <a name="development-tools"></a>開発ツール

Visual Studio には、ネイティブ コード用の強力なデバッガー、スタティック分析ツール、グラフィックス デバッグ ツール、フル装備のコード エディター、単体テストのサポート、その他多数のツールおよびユーティリティが含まれています。 詳細については、次を参照してください。 [Visual Studio を使用した開発を開始する](/visualstudio/ide/get-started-developing-with-visual-studio)、および[Visual Studio で C++ の概要開発](../overview/overview-of-cpp-development.md)します。

## <a name="in-this-section"></a>このセクションの内容
|Title|説明|
|-----------|-----------------|
|[チュートリアル: 標準 C++ プログラムの作成](walkthrough-creating-a-standard-cpp-program-cpp.md)| Windows コンソール アプリケーションを作成します。|
|[チュートリアル: Windows デスクトップ アプリケーション (C++) の作成](walkthrough-creating-windows-desktop-applications-cpp.md)|ネイティブの Windows デスクトップ アプリケーションを作成します。|
|[Windows デスクトップ ウィザード](windows-desktop-wizard.md)|ウィザードを使用して、新しい Windows プロジェクトを作成します。|
|[Active Template Library (ATL)](../atl/atl-com-desktop-components.md)|C++ での COM コンポーネントを作成するのにには、ATL ライブラリを使用します。|
|[Microsoft Foundation Classes (MFC)](../mfc/mfc-desktop-applications.md)|MFC を使用して、ダイアログ、コントロール、大小の Windows アプリケーションを作成するには|
|[ATL と MFC の共有クラス](../atl-mfc-shared/atl-mfc-shared-classes.md)|ATL と MFC で共有される CString などのクラスを使用します。|
|[データ アクセス](../data/data-access-in-cpp.md)| OLE DB および ODBC|
|[テキストと文字列](../text/text-and-strings-in-visual-cpp.md)|Windows 上のさまざまな文字列型。|
|[DirectX を使用するゲームを作成するためのリソース](resources-for-creating-a-game-using-directx.md)
|[方法: Windows デスクトップ アプリケーションでの Windows 10 SDK の使用](how-to-use-the-windows-10-sdk-in-a-windows-desktop-application.md)|Windows SDK|
|[リソース ファイルの操作](working-with-resource-files.md)|デスクトップ アプリケーションをイメージ、アイコン、文字列テーブル、およびその他のリソースを追加する方法。|
|[DirectX (C++) を使用してゲームを作成するためのリソース](resources-for-creating-a-game-using-directx.md)|C++ でのゲームを作成するためのコンテンツへのリンク。|
|[方法: Windows デスクトップ アプリケーションでの Windows 10 SDK の使用](how-to-use-the-windows-10-sdk-in-a-windows-desktop-application.md)|Windows 10 SDK を使用してビルドするプロジェクトの設定手順が示されています。|
|[ネイティブ デスクトップ アプリケーションの配置](deploying-native-desktop-applications-visual-cpp.md)|Windows のネイティブ アプリケーションをデプロイします。|

## <a name="related-articles"></a>関連トピック

|Title|説明|
|-----------|-----------------|
|[Visual Studio での C++](../overview/visual-cpp-in-visual-studio.md)|Visual C 開発者向けコンテンツの親トピック。|
[C++/CLI による .NET の開発](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)|.NET アプリケーションおよびコンポーネントとの通信を有効にするネイティブの C++ ライブラリのラッパーを作成します。|
|[.NET および UWP でのコンポーネント拡張](../extensions/component-extensions-for-runtime-platforms.md)|リファレンスの構文要素が共有によって C +/cli/CX および C++/cli CLI。|
|[ユニバーサル Windows アプリ (C++)](universal-windows-apps-cpp.md)|C + を使用して、UWP アプリケーションを記述/cli/CX または Windows ランタイム テンプレート ライブラリ (WRL)。|
|[COM および .NET の C++ の属性](attributes/cpp-attributes-com-net.md)|.NET または COM を使用して Windows 専用のプログラミングの非標準の属性|

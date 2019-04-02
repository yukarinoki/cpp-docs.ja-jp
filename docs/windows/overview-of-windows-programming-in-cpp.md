---
title: C++ でプログラミングする Windows の概要
ms.date: 03/28/2019
ms.assetid: efc691d7-21f3-47ae-ae56-cab999ccf59d
ms.openlocfilehash: 35842ae73e59685946afe31e88729a36a6431768
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/01/2019
ms.locfileid: "58772905"
---
# <a name="overview-of-windows-programming-in-c"></a>C++ でプログラミングする Windows の概要

いくつかの C++ を使用して作成する Windows アプリケーションの広範なカテゴリがあります。 独自のプログラミング モデルと Windows 固有のライブラリのセットが、C++ 標準ライブラリとサード パーティ製の C++ ライブラリは、これらのいずれかで使用できます。 

## <a name="command-line-console-applications"></a>コマンドライン (コンソール) アプリケーション

C++ コンソール アプリケーションでは、コンソール ウィンドウでコマンドラインから実行し、テキスト出力のみを表示できます。 詳細については、次を参照してください。[コンソール アプリケーション](console-applications-in-visual-cpp.md)します。
 
## <a name="native-desktop-client-applications"></a>ネイティブのデスクトップ クライアント アプリケーション

用語*ネイティブのデスクトップ クライアント アプリケーション*元ネイティブを使用するための C または C++ ウィンドウを持つアプリケーションを指す[Windows C Api および COM Api](/windows/desktop/apiindex/windows-api-list)オペレーティング システムにアクセスします。 これらの Api は c 言語でほとんどの場合使用してオペレーティング システムのイベントを処理する C スタイルのメッセージ ループに対して直接プログラミングするかを選択する必要があるこの種のアプリケーションを作成するときに*Microsoft Foundation Classes* (MFC) Win32 をラップする C++ ライブラリ方法では、ある程度のオブジェクト指向です。 どちらのアプローチは、「最新」と比較して、ユニバーサル Windows プラットフォーム (下記参照) が、どちらも完全にサポートされているがあり、何百万もの世界中で現在実行しているコードの行があると見なされます。 ウィンドウで実行される Win32 アプリケーションでは、Windows プロシージャ関数内での Windows メッセージを明示的に使用する開発者が必要です。 名前にかかわらず、Win32 アプリケーションは、32 ビット (x86) または 64 ビット (x64) バイナリとしてコンパイルできます。 Visual Studio ide、Win32、x86 の用語は同義です。

従来の Windows C プログラミングを開始するを参照してください。 [Win32 と C++ の概要](/windows/desktop/LearnWin32/learn-to-program-for-windows)します。 Win32 のいくつか理解できるように後の詳細について簡単になります[MFC Desktop Applications](/mfc/mfc-desktop-applications)します。 高度なグラフィックスを使用する従来の C++ デスクトップ アプリケーションの例は、次を参照してください[Hilo:。Windows 対応 C++ アプリケーションの開発](https://msdn.microsoft.com/library/windows/desktop/ff708696.aspx)します。

### <a name="c-or-net"></a>C++ または .NET でしょうか。 

ほとんどのデスクトップ アプリケーション (つまり、いない対象とする UWP) のシナリオでは、使用を検討してC#ユーザー インターフェイスを作成します。 これは、.NET プログラミングがあまり複雑では一般に、低いエラーを起こしやすいよりも Win32 または MFC は最新のオブジェクト指向 API がためです。 ほとんどの場合、そのパフォーマンスで十分です。 .NET 機能の豊富なグラフィックスは、Windows Presentation Foundation (WPF) と、最新の Windows ランタイム API (UWP 以下を参照してください) と Win32 を使用することができます。 一般的な規則として、必要とする場合は、デスクトップ アプリケーションの C++ を使用してお勧めします。

- メモリ使用量を正確に制御
- 電力消費量の最大限の経済性
- 一般的なコンピューティングの GPU の使用状況
- DirectX へのアクセスします。
- 標準 C ライブラリの使用率が高い

ユーザー インターフェイスを作成することができますC#C + を使用して/cli CLI ネイティブの C++ ライブラリを使用するアプリケーションを有効にします。 詳細については、次を参照してください。 [C + での .NET プログラミング/cli CLI](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)します。

## <a name="com-components"></a>COM コンポーネント

[コンポーネント オブジェクト モデル (COM)](/windows/desktop/com/the-component-object-model)は、プログラムが相互に通信するさまざまな言語で記述された仕様です。 多くの Windows コンポーネントが COM オブジェクトとして実装され、オブジェクトの作成の標準の COM 規則に従うには、検出とオブジェクトの破棄がインターフェイスです。  C++ デスクトップ アプリケーションから COM オブジェクトを使用しては比較的簡単ですが、独自の COM オブジェクトの書き込みより高度な。 [Active Template Library (ATL)](../atl/atl-com-desktop-components.md)マクロおよび COM 開発を簡略化するヘルパー関数を提供します。 詳細については、次を参照してください。 [ATL COM デスクトップ コンポーネント](../atl/atl-com-desktop-components.md)します。

## <a name="windows-universal-apps"></a>Windows ユニバーサル アプリ

ユニバーサル Windows プラットフォーム (UWP) は、最新の Windows API です。 UWP アプリあらゆる Windows 10 デバイスで実行するには、XAML を使用して、ユーザー インターフェイスおよびが完全にタッチ対応します。 UWP の詳細については、次を参照してください。[ユニバーサル Windows プラットフォーム (UWP) アプリとは何ですか?](/windows/uwp/get-started/whats-a-uwp)と[Windows ユニバーサル アプリに関するガイド](/windows/uwp/get-started/universal-application-platform-guide)します。

元の C++ UWP のサポートを行いました (1) C + + CX、言語の構文の拡張機能は、C++ または (2)、Windows ランタイム ライブラリ (WRL) 標準の C++ と COM に基づいています 両方 C + + CX および WRL はサポートされています。 新しいプロジェクトの勧め[C +/cli WinRT](/windows/uwp/cpp-and-winrt-apis/intro-to-using-cpp-with-winrt)と C++ の標準に基づいて完全高速なパフォーマンスを提供します。 

## <a name="desktop-bridge"></a>デスクトップ ブリッジ

Windows 10 で、既存のデスクトップ アプリケーションまたは COM オブジェクトを UWP アプリとしてパッケージ化し、タッチなどの UWP 機能を追加したり、最新の Windows API のセットから Api を呼び出します。 Visual Studio、およびパッケージをパッケージ化し、間の通信に Windows Api を使用して、1 つにまとめることでデスクトップ ソリューションに UWP アプリを追加することもできます。

Visual Studio 2017 バージョン 15.4 以降では、既存のデスクトップ アプリケーションをパッケージ化の作業を大幅に簡略化するには、Windows アプリケーション パッケージ プロジェクトを作成することができます。 に関してどのようなレジストリ呼び出しは、いくつかの制限が適用されます。 または、デスクトップ アプリケーションの Api を使用して、、多くの場合、アプリ パッケージの実行中に同様の機能を実現するために代替のコード パスを作成することができます。 詳細については、[デスクトップ ブリッジ](/windows-uwp/porting/desktop-to-uwp-root)に関するページをご覧ください。

## <a name="games"></a>ゲーム

DirectX ゲームは、PC または Xbox で実行できます。 詳細については、次を参照してください。 [DirectX のグラフィックスとゲーム](/windows/desktop/directx)します。

## <a name="sql-server-database-clients"></a>SQL Server データベースのクライアント

ネイティブ コードから SQL Server データベースにアクセスするには、ODBC または OLE DB を使用します。 詳細については、「 [SQL Server Native Client](/sql/relational-databases/native-client/odbc/sql-server-native-client-odbc)」を参照してください。

## <a name="windows-device-drivers"></a>Windows デバイス ドライバー

ドライバーは、ハードウェア デバイスからのデータをアプリケーションにアクセスできるようにする低レベルのコンポーネントとその他のオペレーティング システムのコンポーネントです。 詳細については、次を参照してください。 [Windows Driver Kit (WDK)](/windows-hardware/drivers/index)します。

## <a name="windows-services"></a>Windows サービス

Windows*サービス*はほとんどまたはまったくないユーザーの操作でバック グラウンドで実行できるプログラムです。 呼ばれるこれらの UNIX*デーモン*します。 詳細については、次を参照してください。[サービス](/windows/desktop/services/services)します。

## <a name="sdks-libraries-and-header-files"></a>Sdk、ライブラリ、およびヘッダー ファイル

Visual Studio には、C ランタイム ライブラリ (CRT)、C++ 標準ライブラリ、およびその他の Microsoft 固有のライブラリが含まれています。 これらのライブラリのヘッダー ファイルが含まれているフォルダーの追加、\VC\ フォルダーの下、または Windows SDK のインストール フォルダーで、CRT の場合、Visual Studio のインストール ディレクトリにあります。

使用することができます、 [Vcpkg パッケージ マネージャー](../build/vcpkg.md)に Windows の何百ものサード パーティ製オープン ソース ライブラリをインストールします。

Microsoft ライブラリは次のとおりです。

- Microsoft Foundation Classes (MFC):従来の Windows プログラムを作成するためのオブジェクト指向のフレームワーク、特にエンタープライズ アプリケーション-高度なユーザー インターフェイスは、その機能のボタン、リスト ボックス、ツリー ビュー、およびその他のコントロールがあります。 詳細については、「 [MFC Desktop Applications](../mfc/mfc-desktop-applications.md)」を参照してください。

- Active Template Library (ATL):COM コンポーネントを作成するための強力なヘルパー ライブラリ。 詳細については、「 [ATL COM Desktop Components](../atl/atl-com-desktop-components.md)」を参照してください。

- C++ AMP (C++ Accelerated Massive Parallelism)。GPU 上でパフォーマンスの高い一般的な計算作業をできるようにするライブラリ。 詳細については、「 [C++ AMP (C++ Accelerated Massive Parallelism)](../parallel/amp/cpp-amp-cpp-accelerated-massive-parallelism.md)」を参照してください。

- 同時実行ランタイム:マルチコアおよびメニーコア デバイス用の並列および非同期プログラミングの作業を簡素化するライブラリ。 詳細については、「[コンカレンシー ランタイム](../parallel/concrt/concurrency-runtime.md)」を参照してください。

Windows プログラミングの多くのシナリオでは、Windows SDK も必要になります。これには、Windows オペレーティング システム コンポーネントへのアクセスを可能にするためのヘッダー ファイルが含まれています。 既定では、Visual Studio は、C++ デスクトップ ワークロードでは、ユニバーサル Windows アプリの開発のコンポーネントとして Windows SDK をインストールします。 UWP アプリを開発するには、Windows 10 バージョンの Windows SDK 必要があります。 詳しくは、次を参照してください。 [Windows 10 SDK](https://dev.windows.com/downloads/windows-10-sdk)します。 (Windows の以前のバージョンの Windows Sdk の詳細については、次を参照してください。、 [Windows SDK アーカイブ](https://developer.microsoft.com/windows/downloads/sdk-archive))。

**プログラム ファイル (x86) \Windows キット**がインストールされている Windows SDK のすべてのバージョンの既定の場所。

Xbox や Azure など、他のプラットフォームには、インストールを要する独自の SDK があります。 詳細については、DirectX デベロッパー センターおよび Azure デベロッパー センターを参照してください。

## <a name="development-tools"></a>開発ツール

Visual Studio には、ネイティブ コード用の強力なデバッガー、スタティック分析ツール、グラフィックス デバッグ ツール、フル装備のコード エディター、単体テストのサポート、その他多数のツールおよびユーティリティが含まれています。 詳細については、次を参照してください。 [Visual Studio を使用した開発を開始する](/visualstudio/ide/get-started-developing-with-visual-studio)、および[Visual Studio で C++ の概要開発](../overview/overview-of-cpp-development.md)します。

## <a name="in-this-section"></a>このセクションの内容
|Title|説明|
|-----------|-----------------|
|[チュートリアル: 標準の C++ プログラムを作成します。](walkthrough-creating-a-standard-cpp-program-cpp.md)| Windows コンソール アプリケーションを作成します。|
|[チュートリアル: Windows デスクトップ アプリケーション (C++) の作成](walkthrough-creating-windows-desktop-applications-cpp.md)|シンプルな Windows デスクトップ アプリケーションを作成します。|
|[Windows デスクトップ ウィザード](windows-desktop-wizard.md)|ウィザードを使用して、新しい Windows プロジェクトを作成します。|
|[Active Template Library (ATL)](../atl/TOC.md)|C++ での COM コンポーネントを作成するのにには、ATL ライブラリを使用します。|
|[Microsoft Foundation Classes (MFC)](../mfc/TOC.md)|MFC を使用して、ダイアログ、コントロール、大小の Windows アプリケーションを作成するには|
|[ATL と MFC の共有クラス](../atl-mfc-shared/TOC.md)|ATL と MFC で共有される CString などのクラスを使用します。|
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
|[Visual C++](../overview/visual-cpp-in-visual-studio.md)|Visual C 開発者向けコンテンツの親トピック。|
[C++/CLI による .NET の開発](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)|.NET アプリケーションおよびコンポーネントとの通信を有効にするネイティブの C++ ライブラリのラッパーを作成します。|
|[.NET および UWP でのコンポーネント拡張](../extensions/component-extensions-for-runtime-platforms.md)|リファレンスの構文要素が共有によって C +/cli/CX および C++/cli CLI。|
|[ユニバーサル Windows アプリ (C++)](universal-windows-apps-cpp.md)|C + を使用して、UWP アプリケーションを記述/cli/CX または Windows ランタイム テンプレート ライブラリ (WRL)。|
|[COM および .NET の C++ の属性](attributes/cpp-attributes-com-net.md)|.NET または COM を使用して Windows 専用のプログラミングの非標準の属性|


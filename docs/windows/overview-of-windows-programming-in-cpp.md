---
title: C++ でプログラミングする Windows の概要
ms.date: 11/15/2018
ms.assetid: efc691d7-21f3-47ae-ae56-cab999ccf59d
ms.openlocfilehash: 6338b390b11c58f3ebac2af1bb568ea3c3470cd1
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2019
ms.locfileid: "57810446"
---
# <a name="overview-of-windows-programming-in-c"></a>C++ でプログラミングする Windows の概要

いくつかの C++ を使用して作成する Windows アプリケーションの広範なカテゴリがあります。 独自のプログラミング モデルと Windows 固有のライブラリのセットが、C++ 標準ライブラリとサード パーティ製の C++ ライブラリは、これらのいずれかで使用できます。 

## <a name="command-line-console-applications"></a>コマンドライン (コンソール) アプリケーション

C++ コンソール アプリケーションでは、コンソール ウィンドウでコマンドラインから実行し、テキスト出力のみを表示できます。 詳細については、次を参照してください。[コンソール アプリケーション](console-applications-in-visual-cpp.md)します。
 
## <a name="native-desktop-client-applications"></a>ネイティブのデスクトップ クライアント アプリケーション

用語*ネイティブのデスクトップ クライアント アプリケーション*を元の Windows の Win32 Api を使用して、オペレーティング システムにアクセスするための C または C++ ウィンドウを持つアプリケーションを参照します。 これらの Api は c 言語でほとんどの場合使用してオペレーティング システムのイベントを処理する C スタイルのメッセージ ループに対して直接プログラミングするかを選択する必要があるこの種のアプリケーションを作成するときに*Microsoft Foundation Classes* (MFC) Win32 をラップする C++ ライブラリ方法では、ある程度のオブジェクト指向です。 どちらのアプローチは、「最新」と比較して、ユニバーサル Windows プラットフォーム (下記参照) が、どちらも完全にサポートされているがあり、何百万もの世界中で現在実行しているコードの行があると見なされます。

従来の Windows C プログラミングを開始するを参照してください。 [Win32 と C++ の概要](/windows/desktop/LearnWin32/learn-to-program-for-windows)します。 Win32 のいくつか理解できるように後の詳細について簡単になります[MFC Desktop Applications](/mfc/mfc-desktop-applications)します。 高度なグラフィックスを使用する従来の C++ デスクトップ アプリケーションの例は、次を参照してください[Hilo:。Windows 対応 C++ アプリケーションの開発](https://msdn.microsoft.com/library/windows/desktop/ff708696.aspx)します。

### <a name="c-or-net"></a>C++ または .NET でしょうか。 

ほとんどのデスクトップ アプリケーション (つまり、いない対象とする UWP) のシナリオでは、使用を検討してC#と .NET。 これは、.NET プログラミングがあまり複雑では一般に、低いエラーを起こしやすいよりも Win32 または MFC は最新のオブジェクト指向 API がためです。 ほとんどの場合、そのパフォーマンスで十分です。 .NET 機能の豊富なグラフィックスは、Windows Presentation Foundation (WPF) と、最新の Windows ランタイム API (UWP 以下を参照してください) と Win32 を使用することができます。 一般的な規則として、必要とする場合は、デスクトップ アプリケーションの C++ を使用してお勧めします。

- メモリ使用量を正確に制御
- 電力消費量の最大限の経済性
- 一般的なコンピューティングの GPU の使用状況
- DirectX へのアクセスします。
- 標準 C ライブラリの使用率が高い

## <a name="com-components"></a>COM コンポーネント

Windows オペレーティング システムの多くの部分は、コンポーネントは、あらゆるコンピューター言語で記述されたクライアント アプリケーションから使用できるようにするバイナリの標準を定義するコンポーネント オブジェクト モデル (COM) に基づいています。 C++ では、独自の COM コンポーネントを作成する作業を簡略化するのに、Active Template Library (ATL) を使用できます。 詳細については、次を参照してください。[コンポーネント オブジェクト モデル (COM)](/windows/desktop/com/component-object-model--com--portal)と[ATL COM デスクトップ コンポーネント](../atl/atl-com-desktop-components.md)します。

## <a name="windows-universal-apps"></a>Windows ユニバーサル アプリ

ユニバーサル Windows プラットフォーム (UWP) は、最新の Windows API です。 UWP アプリあらゆる Windows 10 デバイスで実行するには、XAML を使用して、ユーザー インターフェイスおよびが完全にタッチ対応します。 UWP の詳細については、次を参照してください。[ユニバーサル Windows プラットフォーム (UWP) アプリとは何ですか?](/windows/uwp/get-started/whats-a-uwp)と[Windows ユニバーサル アプリに関するガイド](/windows/uwp/get-started/universal-application-platform-guide)します。

元の C++ UWP のサポートを行いました (1) C + + CX、言語の構文の拡張機能は、C++ または (2)、Windows ランタイム ライブラリ (WRL) 標準の C++ と COM に基づいています 両方 C + + CX および WRL はサポートされています。 新しいプロジェクトの勧め[C +/cli WinRT](/windows/uwp/cpp-and-winrt-apis/intro-to-using-cpp-with-winrt)と C++ の標準に基づいて完全高速なパフォーマンスを提供します。 

Windows 10 では既存の C++ のデスクトップ アプリケーションとしてパッケージ化することができます-Microsoft Store から展開されます。 詳細については、次を参照してください。[デスクトップ アプリケーション (デスクトップ ブリッジ) パッケージ](/windows/uwp/porting/desktop-to-uwp-root)します。

## <a name="games"></a>ゲーム

DirectX ゲームは、PC または Xbox で実行できます。 詳細については、次を参照してください。 [DirectX のグラフィックスとゲーム](/windows/desktop/directx)します。

## <a name="net-wrappers-for-c-libraries"></a>C++ ライブラリの .NET ラッパー

C + を使用する/cli CLI でネイティブの C++ ライブラリを使用する .NET コードをできるようにする相互運用機能のレイヤーを作成します。 詳細については、次を参照してください。 [C + での .NET プログラミング/cli CLI](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)します。

## <a name="sql-server-database-clients"></a>SQL Server データベースのクライアント

ネイティブ コードから SQL Server データベースにアクセスするには、ODBC または OLE DB を使用します。 詳細については、「 [SQL Server Native Client](/sql/relational-databases/native-client/odbc/sql-server-native-client-odbc)」を参照してください。

## <a name="windows-device-drivers"></a>Windows デバイス ドライバー

ドライバーは、ハードウェア デバイスからのデータをアプリケーションにアクセスできるようにする低レベルのコンポーネントとその他のオペレーティング システムのコンポーネントです。 詳細については、次を参照してください。 [Windows Driver Kit (WDK)](/windows-hardware/drivers/index)します。

## <a name="windows-services"></a>Windows サービス

Windows*サービス*はほとんどまたはまったくないユーザーの操作でバック グラウンドで実行できるプログラムです。 呼ばれるこれらの UNIX*デーモン*します。 詳細については、次を参照してください。[サービス](/windows/desktop/services/services)します。

## <a name="sdks-libraries-and-header-files"></a>Sdk、ライブラリ、およびヘッダー ファイル

Visual Studio には、C ランタイム ライブラリ (CRT)、C++ 標準ライブラリ、およびその他の Microsoft 固有のライブラリが含まれています。 これらのライブラリのヘッダー ファイルが含まれているフォルダーの追加、\VC\ フォルダーの下、または Windows SDK のインストール フォルダーで、CRT の場合、Visual Studio のインストール ディレクトリにあります。

使用することができます、 [Vcpkg パッケージ マネージャー](../vcpkg.md)に Windows の何百ものサード パーティ製オープン ソース ライブラリをインストールします。

Microsoft ライブラリは次のとおりです。

- Microsoft Foundation Classes (MFC):従来の Windows プログラムを作成するためのオブジェクト指向のフレームワーク、特にエンタープライズ アプリケーション-高度なユーザー インターフェイスは、その機能のボタン、リスト ボックス、ツリー ビュー、およびその他のコントロールがあります。 詳細については、「 [MFC Desktop Applications](../mfc/mfc-desktop-applications.md)」を参照してください。

- Active Template Library (ATL):COM コンポーネントを作成するための強力なヘルパー ライブラリ。 詳細については、「 [ATL COM Desktop Components](../atl/atl-com-desktop-components.md)」を参照してください。

- C++ AMP (C++ Accelerated Massive Parallelism)。GPU 上でパフォーマンスの高い一般的な計算作業をできるようにするライブラリ。 詳細については、「 [C++ AMP (C++ Accelerated Massive Parallelism)](../parallel/amp/cpp-amp-cpp-accelerated-massive-parallelism.md)」を参照してください。

- 同時実行ランタイム:マルチコアおよびメニーコア デバイス用の並列および非同期プログラミングの作業を簡素化するライブラリ。 詳細については、「[コンカレンシー ランタイム](../parallel/concrt/concurrency-runtime.md)」を参照してください。

Windows プログラミングの多くのシナリオでは、Windows SDK も必要になります。これには、Windows オペレーティング システム コンポーネントへのアクセスを可能にするためのヘッダー ファイルが含まれています。 既定では、Visual Studio は、C++ デスクトップ ワークロードでは、ユニバーサル Windows アプリの開発のコンポーネントとして Windows SDK をインストールします。 UWP アプリを開発するには、Windows 10 バージョンの Windows SDK 必要があります。 詳しくは、次を参照してください。 [Windows 10 SDK](https://dev.windows.com/downloads/windows-10-sdk)します。 (Windows の以前のバージョンの Windows Sdk の詳細については、次を参照してください。、 [Windows SDK アーカイブ](https://developer.microsoft.com/windows/downloads/sdk-archive))。

**プログラム ファイル (x86) \Windows キット**がインストールされている Windows SDK のすべてのバージョンの既定の場所。

Xbox や Azure など、他のプラットフォームには、インストールを要する独自の SDK があります。 詳細については、DirectX デベロッパー センターおよび Azure デベロッパー センターを参照してください。

## <a name="development-tools"></a>開発ツール

Visual Studio には、ネイティブ コード用の強力なデバッガー、スタティック分析ツール、グラフィックス デバッグ ツール、フル装備のコード エディター、単体テストのサポート、その他多数のツールおよびユーティリティが含まれています。 詳細については、次を参照してください。 [Visual Studio を使用した開発を開始する](/visualstudio/ide/get-started-developing-with-visual-studio)、および[Visual Studio で C++ の概要開発](../overview-of-cpp-development.md)します。

## <a name="in-this-section"></a>このセクションの内容
|Title|説明|
|-----------|-----------------|
|[C++ による Windows デスクトップ アプリケーション](desktop-applications-visual-cpp.md)| 従来のデスクトップ アプリケーションを作成する方法。|
|[Active Template Library (ATL)](../atl/TOC.md)|C++ での COM コンポーネントを作成するのにには、ATL ライブラリを使用します。|
|[Microsoft Foundation Classes (MFC)](../mfc/TOC.md)|MFC を使用して、ダイアログ、コントロール、大小の Windows アプリケーションを作成するには|
|[ATL と MFC の共有クラス](../atl-mfc-shared/TOC.md)|ATL と MFC で共有される CString などのクラスを使用します。|
|[C++/CLI による .NET の開発](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)|.NET アプリケーションおよびコンポーネントとの通信を有効にするネイティブの C++ ライブラリのラッパーを作成します。|
|[.NET および UWP でのコンポーネント拡張](component-extensions-for-runtime-platforms.md)|リファレンスの構文要素が共有によって C +/cli/CX および C++/cli CLI。|
|[ユニバーサル Windows アプリ (C++)](universal-windows-apps-cpp.md)|C + を使用して、UWP アプリケーションを記述/cli/CX または Windows ランタイム テンプレート ライブラリ (WRL)。|
|[COM および .NET の C++ の属性](attributes/cpp-attributes-com-net.md)|.NET または COM を使用して Windows 専用のプログラミングの非標準の属性|

## <a name="related-articles"></a>関連トピック

|タイトル|説明|
|-----------|-----------------|
|[Visual C++](../visual-cpp-in-visual-studio.md)|Visual C 開発者向けコンテンツの親トピック。|

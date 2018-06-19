---
title: C++ での Windows プログラミングの概要 |Microsoft ドキュメント
ms.custom: ''
ms.date: 04/06/2018
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: efc691d7-21f3-47ae-ae56-cab999ccf59d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 2096c36ec24c1ca7e20c789b8a1eb8c24589ccc1
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
ms.locfileid: "33881664"
---
# <a name="overview-of-windows-programming-in-c"></a>C++ でプログラミングする Windows の概要

Windows server で、クラウド内、または Xbox でさまざまな種類の (x 86、x64 または ARM)、Windows PC で実行されるプログラムを記述するのに Visual C を使用できます。 適切に記述された C++ プログラムは、これらの性質を持っています。
- メモリの要件で効率的です
- 電力消費量経済的です 
- マルチコア デバイスおよびメニーコア デバイスのフル活用すること
- グラフィックス処理装置 (GPU) での一般的なコンピューティング操作を実行できます。   
- 他の最新のハードウェアで活用できます。

Visual C++ で開発できる Windows アプリにはいくつかの大きなカテゴリがあります。 これらのカテゴリがあるさまざまなプログラミング モデル、またはアプリ モデルは、長年にわたってが導入されました。 各モデルは、プラットフォームへのアクセスを提供し、ウィンドウとダイアログ ボックスなどのユーザー インターフェイスを作成する別のライブラリと Api を使用します。 C++ 標準ライブラリに加え、サードパーティ製のライブラリは、UWP のいくつかの制限と、これらのカテゴリのいずれかで使用できます。

- [Windows ユニバーサル アプリ](#BK_WindowsUniversal)。 Windows アプリの 3 番目のカテゴリが Windows 8 で導入され、このカテゴリのアプリは Windows 10 でも引き続きサポートされます。 多くの場合、これらのアプリケーションは単に "Windows アプリ" と呼ばれ、さまざまなデバイスを対象とするデスクトップおよびモバイルのアプリがそれに含まれています。 これらのアプリは、C++/CX (C++ の方言であり、Windows ランタイム開発のサポートを含む) で作成することも、Windows ランタイム ライブラリ (WRL) を使用して 標準 C++ と COM で作成することもできます。 これらのアプリはもともと全画面表示で実行するよう設計されていましたが、Windows 10 のユーザーにはデスクトップ ウィンドウでこれを実行するオプションがあります。 これらのアプリはタッチ指向ですが、ユーザーがマウスを好む場合や、タッチ スクリーンが利用できない場合はマウスを簡単に使用できます。 これらのアプリは、Microsoft ストア、アプリの"Store"が呼び出されることに至ったファクトから配布されます。

UWP アプリは、タブレットや携帯電話など、すべての Windows 10 デバイスおよびデスクトップを実行できます。 デスクトップでは、常に全画面表示で実行しなければならないわけではなく、デスクトップ ウィンドウとして実行することができます。 これらのアプリは Xbox でも動作し、将来のデバイスでも実行できます。  UWP アプリは、ユーザー インターフェイス要素、サービス、および Windows でサポートされているさまざまなハードウェア デバイスへのインターフェイスを提供する Windows ランタイムで実行します。  

C++ UWP アプリを記述することができます + CX、C の言語を使用することができます、 [C + + WinRT ライブラリ](https://moderncpp.com/)一部のシナリオです。 UWP アプリは、ネイティブ コードにコンパイルし、XAML ユーザー インターフェイスでは、または DirectX を使用します。 その他の言語で記述された UWP アプリを使用できるネイティブ コードで記述された Windows ランタイム コンポーネントです。 詳細については、次を参照してください。 [C++ ユニバーサル Windows プラットフォーム アプリを作成](http://go.microsoft.com/fwlink/?LinkID=534976)、[ゲームを初めて作成 UWP DirectX を使用する](http://go.microsoft.com/fwlink/p/?LinkId=244656)、および[C++ で作成する Windows ランタイム コンポーネント](http://go.microsoft.com/fwlink/p/?LinkId=244658)です。

   サーバーおよびクラウド プログラミングのコンテキストにおいて、コア コンポーネントのためや、計算コードのために C++ を使用することも、このカテゴリに含まれます。 場合によっては、サーバーやクラウド アプリケーションのコアとなるパフォーマンス重視のコードを C++ で記述し、パフォーマンスを最適化することもあります。 このようなコードをコンパイルして DLL にし、C# または Visual Basic から使用することができます。

- **.NET Framework アプリケーション**。 .NET Framework アプリケーションのほとんどは C# または Visual Basic で記述されていますが、C++/CLI でも記述できます (Visual C++ の/clr コンパイラ オプション)。 マネージ コードとネイティブ コードを含む大規模なアプリケーションでは、C++/CLI は最小限の相互運用層で使用することをお勧めします。

##  <a name="BK_WindowsUniversal"></a> Windows Universal Apps

Windows 10 では、デスクトップ上だけでなく、タブレットや携帯電話など、すべての Windows 10 デバイスでアプリを実行できます。 デスクトップでは、常に全画面表示で実行しなければならないわけではなく、デスクトップ ウィンドウとして実行することができます。 これらのアプリは Xbox でも動作し、将来のデバイスでも実行できます。  2 種類のアプリのプログラミング モデルは、Win32 デスクトップ アプリケーションとは異なります。 これらの Windows アプリケーションは Windows ランタイム上で動作します。このランタイムは、ユーザー インターフェイス要素、これらのアプリの重要なサービス、およびサポートされている多様なハードウェア デバイスへのインターフェイスを提供します。 これらのアプリはネイティブ コードにコンパイルされ、XAML ユーザー インターフェイスを持つか、DirectX を使用します。 その他の Windows アプリで使用できるネイティブ コードで、Windows ランタイム コンポーネントを記述することも、c#、Visual Basic、または JavaScript で記述されたアプリが含まれます。 詳細については、次を参照してください。 [C++ UWP"Hello world"アプリを作成](/windows/uwp/get-started/create-a-basic-windows-10-app-in-cpp)、 [DirectX で UWP の簡単なゲームを作成する](/windows/uwp/gaming/tutorial--create-your-first-uwp-directx-game)、および[C++ で作成する Windows ランタイム コンポーネント](/windows/uwp/winrt-components/creating-windows-runtime-components-in-cpp)です。

> [!TIP]
> Windows 10 用 Microsoft ストアを介して展開用の既存のデスクトップ アプリケーションをパッケージ化するのに、デスクトップ アプリを実行するコンバーターを使用できます。 詳しくは、「[Using Visual C++ Runtime in Centennial project](https://blogs.msdn.microsoft.com/vcblog/2016/07/07/using-visual-c-runtime-in-centennial-project)」(Centennial プロジェクトでの Visual C++ ランタイムの使用) および「[Bring your desktop app to the Universal Windows Platform (UWP) with the Desktop Bridge](https://msdn.microsoft.com/en-us/windows/uwp/porting/desktop-to-uwp-root)」(Desktop Bridge でデスクトップ アプリをユニバーサル Windows プラットフォーム (UWP) 対応にする) をご覧ください。

ユニバーサル Windows プラットフォームのサンプルの詳細については、「 [GitHub の Windows のユニバーサル サンプル](https://github.com/Microsoft/Windows-universal-samples)」を参照してください。

既存の Windows 8.1 プロジェクトおよび Windows 10 に移植する必要がある場合は、次を参照してください。[ユニバーサル Windows プラットフォームに移植](../porting/porting-to-the-universal-windows-platform-cpp.md)です。 参照してください、UWP アプリに統合する場合、およびコードを既存のクラシック Win32 デスクトップ ライブラリがあります[する方法: ユニバーサル Windows プラットフォーム アプリで既存の C++ コードを使用して](../porting/how-to-use-existing-cpp-code-in-a-universal-windows-platform-app.md)です。

UWP の詳細については一般を参照してください[ユニバーサル Windows プラットフォーム (UWP) アプリとは?](/windows/uwp/get-started/whats-a-uwp)です。

これらすべての概念の詳細については、次を参照してください。 [Windows ユニバーサル アプリ ガイド](http://go.microsoft.com/fwlink/p/?linkid=534605)です。

##  <a name="BK_Native"></a> デスクトップおよびサーバー アプリケーション

デスクトップの Windows クライアント アプリケーションを記述するための基礎を習得するには、「 [Developing Windows Applications in C++](http://msdn.microsoft.com/vstudio//hh304489) 」 (C++ での Windows アプリケーションの開発) および「 [Windows C++ プログラミングの概要](http://msdn.microsoft.com/library/windows/desktop/ff381398\(v=vs.85\).aspx)」を参照してください。

Windows 10 では、Visual C を使用して、さまざまな種類のデスクトップ プログラムを作成することができます。

- コマンド ライン アプリとユーティリティ。 詳細については、次を参照してください。[コンソール アプリケーション](../windows/console-applications-in-visual-cpp.md)です。

- 洗練されたグラフィカル ユーザー インターフェイスを持つコンシューマー向けアプリケーション。 詳細については、「 [Hilo: Windows 7 対応 C++ アプリケーションの開発](http://go.microsoft.com/fwlink/p/?LinkId=256417)」を参照してください。

- Enterprise および基幹業務アプリを .NET Framework で実行します。 C# または Visual Basic では、ほとんどの .NET Framework アプリケーションが書き込まれます。 C + を使用する + CLI ネイティブの C++ ライブラリを使用する .NET コードを有効にする相互運用機能のレイヤーを作成します。 詳細については、次を参照してください。 [C + での .NET プログラミング +/CLI (Visual c)](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)です。

- ネイティブ コードで実行される SQL データベース クライアント。 詳細については、次を参照してください。 [SQL Server Native Client](/sql/relational-databases/native-client/odbc/sql-server-native-client-odbc)です。

- Microsoft Office アプリケーション用アドイン。 詳細については、「 [Outlook 2010 の C++ アドインをビルドする](http://go.microsoft.com/fwlink/p/?LinkId=256420)」を参照してください。

- デバイス ドライバー。 詳細については、「 [Windows Driver Kit (WDK) について](http://go.microsoft.com/fwlink/p/?LinkId=256421)」を参照してください。

- Windows サービス 詳細については、「 [Introduction to Windows Service Applications](/dotnet/framework/windows-services/introduction-to-windows-service-applications)」を参照してください。

Visual C++ を使用すると、高性能なカスタム機能をほぼ種類に関係なく Win32 DLL または COM DLL にパッケージ化できます。これらは、C++ アプリまたは C# や Visual Basic など他の言語で記述されたアプリで使用できます。 WIn32 DLL の詳細については、「 [DLLs in Visual C++](../build/dlls-in-visual-cpp.md)」を参照してください。 COM 開発に関する詳細については、次を参照してください。[コンポーネント オブジェクト モデル (COM)](https://msdn.microsoft.com/library/windows/desktop/ms680573)です。

## <a name="games"></a>ゲーム

DirectX ゲームは、PC または Xbox で実行できます。 詳細については、 [DirectX デベロッパー センター](http://go.microsoft.com/fwlink/p/?LinkId=256418)を参照してください。

## <a name="sdks-libraries-and-header-files"></a>Sdk、ライブラリ、およびヘッダー ファイル

Visual C には、C ランタイム ライブラリ (CRT)、C++ 標準ライブラリでは、およびその他の Microsoft 固有のライブラリが含まれています。 これらのライブラリのヘッダー ファイルが格納されるインクルード フォルダーは、Visual Studio インストール ディレクトリの \VC\ フォルダーの下にある場合は、CRT、Windows SDK のインストール フォルダー内のいずれかであります。   

使用することができます、 [Vcpkg パッケージ マネージャー](../vcpkg.md) Windows 用に何百ものサード パーティ オープン ソース ライブラリをインストールします。

Microsoft ライブラリには、次のとおりです。

- Microsoft Foundation Classes (MFC): ボタン、リスト ボックス、ツリー ビュー、および他のコントロールを使用した豊富なユーザー インターフェイスを持つ従来の Windows プログラム (特にエンタープライズ アプリケーション) を作成するためのオブジェクト指向フレームワーク。 詳細については、「 [MFC Desktop Applications](../mfc/mfc-desktop-applications.md)」を参照してください。

- Active Template Library (ATL): COM コンポーネントを作成するための強力なヘルパー ライブラリ。 詳細については、「 [ATL COM Desktop Components](../atl/atl-com-desktop-components.md)」を参照してください。

- C++ AMP (C++ Accelerated Massive Parallelism): GPU で一般的な計算作業のパフォーマンス向上を可能にするライブラリ。 詳細については、「 [C++ AMP (C++ Accelerated Massive Parallelism)](../parallel/amp/cpp-amp-cpp-accelerated-massive-parallelism.md)」を参照してください。

- 同時実行ランタイム: マルチコア デバイスおよびメニーコア デバイス用の並列プログラミングおよび非同期プログラミング作業を簡略化するために役立つライブラリ。 詳細については、「 [Concurrency Runtime](../parallel/concrt/concurrency-runtime.md)」を参照してください。

Windows プログラミングの多くのシナリオでは、Windows SDK も必要になります。これには、Windows オペレーティング システム コンポーネントへのアクセスを可能にするためのヘッダー ファイルが含まれています。 既定では、Visual Studio は、ユニバーサル Windows アプリの開発できるように C++ デスクトップのワークロードのコンポーネントとして、Windows SDK をインストールします。 UWP アプリを開発するには、Windows 10 バージョンの Windows SDK 必要があります。 詳細については、次を参照してください。 [Windows 10 SDK](https://dev.windows.com/downloads/windows-10-sdk)です。 (Windows の以前のバージョンの Windows Sdk の詳細については、次を参照してください。、 [Windows SDK アーカイブ](https://developer.microsoft.com/windows/downloads/sdk-archive))。 

**プログラム Files (x86) \Windows Kits**がインストールされている Windows SDK のすべてのバージョンの既定の場所。

Xbox や Azure など、他のプラットフォームには、インストールを要する独自の SDK があります。 詳細については、DirectX デベロッパー センターおよび Azure デベロッパー センターを参照してください。

## <a name="development-tools"></a>開発ツール

Visual Studio には、ネイティブ コード用の強力なデバッガー、スタティック分析ツール、グラフィックス デバッグ ツール、フル装備のコード エディター、単体テストのサポート、その他多数のツールおよびユーティリティが含まれています。 詳細については、次を参照してください。 [Visual Studio での開発を開始](/visualstudio/ide/get-started-developing-with-visual-studio)、および[IDE と開発ツール](../ide/ide-and-tools-for-visual-cpp-development.md)です。

## <a name="related-articles"></a>関連トピック

|タイトル|説明|
|-----------|-----------------|
|[Visual C++](../visual-cpp-in-visual-studio.md)|Visual C 開発者向けのコンテンツの親トピック。|

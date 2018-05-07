---
title: 再配布する Dll の決定 |Microsoft ドキュメント
ms.custom: ''
ms.date: 03/13/2018
ms.technology:
- cpp-ide
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- redistributing DLLs
- DLLs [C++], redistributing
- dependencies [C++], application deployment and
- application deployment [C++], DLL redistribution
- deploying applications [C++], DLL redistribution
ms.assetid: f7a2cb42-fb48-42ab-abd2-b35e2fd5601a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b3ca079fc69fe10f15a55812eaa55d4ba2d2ab04
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="determining-which-dlls-to-redistribute"></a>再配布する DLL の決定

Visual Studio によって提供されるライブラリ Dll を使用するアプリケーションをビルドすると、アプリケーションのユーザーでは、アプリケーションを実行するコンピューターには、それらの Dll 必要があります。 多くのユーザーは Visual Studio をインストールしていないと考えられるので、それらの DLL をユーザーに提供する必要があります。 Visual Studio では、これらの Dll として利用可能な*再頒布可能ファイル*アプリケーションのインストーラーに含めることができます。

インストーラーによる再頒布可能 Dll を含めるに容易にできるように、利用することはスタンドアロンとして*再頒布可能パッケージ*です。 これらは、アーキテクチャ固有の実行可能ファイル、ユーザーのコンピューターに再頒布可能ファイルをインストールするための集中配置を使用します。 たとえば、vcredist\_x86.exe ライブラリをインストール、32 ビット x86 用コンピューター、vcredist\_x64.exe ライブラリをインストール、32 ビットおよび 64 ビット x64 用コンピューター、および vcredist\_ARM.exe ARM 用のライブラリのインストールコンピューターです。 一元的な展開は、Microsoft は、Windows Update サービスを使用して、これらのライブラリの更新を個別にためお勧めします。 だけでなく、コピー、Visual Studio のインストールでは、現在の再頒布可能パッケージがでダウンロード可能な[VisualStudio.com/Downloads](https://www.visualstudio.com/downloads/)その他のツール、フレームワークのセクションでします。

展開する再頒布可能パッケージのメジャー バージョン番号は、アプリケーションを作成するために使用した Visual Studio ツールセットのバージョンと一致する必要があります。 Visual Studio 2017 と Visual Studio 2015、Visual Studio 2017 年 1 再頒布可能ファイルは、2015年ツールセットを使用してビルドされたアプリで使用することを意味の互換性のあるツールセットのバージョン番号があります。 これらは、互換性のある可能性がありますが、2017年ツールセットを使用してビルドされたアプリで 2015 再頒布可能ファイルを使用はサポートされません。 再頒布可能パッケージが同じか、ツールセットのバージョンよりも新しいバージョンを使用することのみサポートします。 以前のツールセットのサポートされている最新再頒布可能パッケージへのリンクを参照してください。[最新の Visual c のダウンロードをサポートする](https://support.microsoft.com/en-us/help/2977003/the-latest-supported-visual-c-downloads)です。 再頒布可能パッケージの特定の以前のバージョンが検索された、 [Microsoft ダウンロード センター](http://go.microsoft.com/fwlink/p/?LinkId=158431) 「Visual C 再頒布可能パッケージで」にします。

含める再頒布可能 Dll のインストーラーを使用する別の方法を使用して*マージ モジュール*です。 これらの Microsoft インストーラー モジュールに含まれ、アプリケーションのインストーラーによってインストールされています。 Dll の再頒布可能マージ モジュールが、Visual Studio インストール ディレクトリの下で見つかった\\VC\\Redist\MSVC\\*バージョン*\\MergeModules\\. Visual Studio の以前のバージョンでこれらのファイル内にある、 \\Program Files または\\一般的なファイルで、Program Files (x86) ディレクトリ\\マージ モジュールのサブディレクトリ。 これらのファイルの使用に関する詳細については、次を参照してください。[マージ モジュールを使用した再配布コンポーネント](../ide/redistributing-components-by-using-merge-modules.md)です。

個々 の再頒布可能 Dll は、Visual Studio のインストールにも含まれます。 Visual Studio インストール ディレクトリに既定では、インストールは、 \\VC\\Redist\\MSVC\\*バージョン*フォルダーです。 *バージョン*番号は再頒布可能ファイルの 1 つの共通セットの別のマイナー ビルド番号を表すことがあります。 ライブラリの DLL ファイル、再頒布可能パッケージは、これらのディレクトリで見つかったマージ モジュールの最新バージョンを使用します。 アプリケーションと同じディレクトリにインストールすることで、ローカル配置にこれらのライブラリを使用できます。 ローカル配置を可能になったため、更新プログラムを展開したアプリケーションに配信を担当するお勧めしません。 再頒布可能パッケージを使用した集中配置をお勧めします。

アプリケーションと共に再配布する必要がある DLL を判断するには、アプリケーションが依存する DLL の完全な一覧を収集します。 これらは、インポート ライブラリの入力をリンカーに通常一覧表示されます。 既定では、vcruntime とユニバーサル C ランタイム ライブラリ (UCRT) などの特定のライブラリが含まれています。 アプリまたはその依存関係の 1 つは、LoadLibrary を使用して動的に DLL を読み込む、その DLL 可能性があります、リンカーへの入力に表示されません。 動的に読み込まれた Dll のリストを収集する方法の 1 つが、Dependency Walker (depends.exe) をアプリの実行」の説明に従って[Visual C アプリケーションの依存関係を理解する](../ide/understanding-the-dependencies-of-a-visual-cpp-application.md)です。 残念ながら、このツールは、期限が切れ、特定の Dll が見つからないことを報告することがあります。

依存関係の一覧がある場合は、比較、Microsoft Visual Studio インストール ディレクトリの下、見つかった Redist.txt ファイルにあるリンク先の一覧に、または"再頒布可能パッケージの一覧に"再頒布可能 Dll「再頒布可能コード ファイル」のセクションで参照されているVisual Studio のコピーのマイクロソフト ソフトウェア ライセンス条項。 Visual Studio 2017 年 1、次を参照してください。 [Microsoft Visual Studio 2017 (ユーティリティを含む、拡張性、および BuildServer ファイル) の再頒布可能コード](http://go.microsoft.com/fwlink/p/?linkid=823098)です。 Visual Studio 2015 では、次を参照してください。 [Microsoft Visual Studio 2015 および Microsoft Visual Studio 2015 SDK 用 (が含まれていますユーティリティおよび BuildServer ファイル) 再頒布可能コード](http://go.microsoft.com/fwlink/p/?linkid=799794)です。 Visual Studio 2013 で、一覧は利用可能なオンライン[Microsoft Visual Studio 2013 および Microsoft Visual Studio 2013 SDK 用頒布可能コード](http://go.microsoft.com/fwlink/p/?LinkId=313603)です。

Visual Studio 2015 以前のバージョンを Visual Studio での C ランタイム ライブラリ (CRT) が msvc に、再頒布可能 DLL として含まれている*バージョン*.dll です。 CRT の関数は vcruntime と UCRT にリファクタリングが Visual Studio 2015 以降。 UCRT は Windows Update によって管理されている Windows 10 で、システム コンポーネントになりました。 すべての Windows 10 オペレーティング システムで使用可能になります。 アプリケーションを以前のオペレーティング システムを展開するには、同様に、UCRT を再配布する必要があります。 UCRT の以前のバージョンは、UCRT のバージョンが既にインストールされていない場合はのみにインストールされているオペレーティング システム Windows 10 より前、Visual Studio 再頒布可能ファイルに含まれているとのみです。 Microsoft システムの更新パッケージとしては、ダウンレベル システム用の UCRT のインストール可能なバージョンを参照してください。 [Windows 10 の Universal C Runtime](https://www.microsoft.com/en-us/download/details.aspx?id=48234) 、Microsoft ダウンロード センターにします。

Visual Studio に含まれているすべてのファイルを再配布することはできません。再配布を許可されているのは、Redist.txt またはオンラインの "REDIST list" で指定されているファイルだけです。 アプリケーションのデバッグ バージョンと、各種の Visual C++ デバッグ DLL は、再配布できません。 詳細については、次を参照してください。[配置方法の選択](../ide/choosing-a-deployment-method.md)です。

次の表に、アプリケーションが依存する可能性がある一部の Visual C++ DLL を示します。

|Visual C++ ライブラリ|説明|対象|
|--------------------------|-----------------|----------------|
|vcruntime*バージョン*.dll|ネイティブ コード用のランタイム ライブラリ。|標準 C および C++ 言語の起動と終了サービスを使用するアプリケーション。|
|vccorlib*version*.dll|マネージ コード用のランタイム ライブラリ。|C++ 言語サービスを使用するアプリケーションはマネージ コードです。|
|msvcp*バージョン*.dll および msvcp*バージョン*_*dotnumber*.dll|ネイティブ コードの C++ 標準ライブラリです。|使用するアプリケーション、 [C++ 標準ライブラリ](../standard-library/cpp-standard-library-reference.md)です。|
|concrt*バージョン*.dll|ネイティブ コードの同時実行ランタイム ライブラリです。|使用するアプリケーション、[同時実行ランタイム](../parallel/concrt/concurrency-runtime.md)です。|
|mfc*version*.dll|MFC (Microsoft Foundation Class) ライブラリ|使用するアプリケーション、 [MFC ライブラリ](../mfc/mfc-desktop-applications.md)です。|
|mfc*バージョン**言語*.dll|Microsoft Foundation はクラス (MFC) ライブラリ リソースです。|特定の言語リソースを MFC を使用するアプリケーション。|
|mfc*version*u.dll|Unicode をサポートする MFC ライブラリ|使用するアプリケーション、 [MFC ライブラリ](../mfc/mfc-desktop-applications.md)Unicode のサポートを必要とします。|
|mfcmifc80.dll|MFC マネージ インターフェイス ライブラリ|使用するアプリケーション、 [MFC ライブラリ](../mfc/mfc-desktop-applications.md)で[Windows フォーム コントロール](/dotnet/framework/winforms/controls/index)です。|
|mfcm*version*.dll|MFC マネージ ライブラリ|使用するアプリケーション、 [MFC ライブラリ](../mfc/mfc-desktop-applications.md)で[Windows フォーム コントロール](/dotnet/framework/winforms/controls/index)です。|
|mfcm*version*u.dll|Unicode をサポートする MFC マネージ ライブラリ|使用するアプリケーション、 [MFC ライブラリ](../mfc/mfc-desktop-applications.md)で[Windows フォーム コントロール](/dotnet/framework/winforms/controls/index)Unicode のサポートを必要とします。|
|vcamp*version*.dll|ネイティブ コードの AMP ライブラリです。|使用するアプリケーション、 [C++ AMP ライブラリ](../parallel/amp/cpp-amp-cpp-accelerated-massive-parallelism.md)コード。|
|vcomp*version*.dll|ネイティブ コードの OpenMP ライブラリです。|使用するアプリケーション、 [C++ OpenMP ライブラリ](../parallel/openmp/openmp-in-visual-cpp.md)コード。|

> [!NOTE]
> Active Template Library を別の DLL として再配布する必要がなくなりました。 その機能はヘッダーとスタティック ライブラリに移動されました。

アプリケーションを使用してこれらの Dll を再配布する方法の詳細については、次を参照してください。 [Visual c ファイルの再配布](../ide/redistributing-visual-cpp-files.md)です。 例については、次を参照してください。[配置例については](../ide/deployment-examples.md)します。

システム Dll はオペレーティング システムの一部であるため、通常は再配布する必要はありません。 ただし、Microsoft オペレーティング システムの複数のバージョンでアプリケーションを実行する場合など、これが該当しない可能性もあります。 この場合、使用許諾契約書を必ずお読みください。 また、Windows Update や Service Pack を通じて、または Microsoft が提供する再頒布可能パッケージを使用して、システム DLL のアップグレードを試みてください。

## <a name="see-also"></a>関連項目

[配置方法の選択](../ide/choosing-a-deployment-method.md)

[デスクトップ アプリケーションの配置](../ide/deploying-native-desktop-applications-visual-cpp.md)

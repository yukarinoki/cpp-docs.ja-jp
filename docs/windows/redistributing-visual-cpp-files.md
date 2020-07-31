---
title: Visual C++ ファイルの再配布
description: Visual Studio には、アプリケーションと共にデプロイできる再頒布可能ライブラリとコンポーネントが含まれています。
ms.date: 07/16/2020
helpviewer_keywords:
- application deployment [C++], file redistributing
- redistributing applications [C++]
- deploying applications [C++], file redistributing
- file redistribution [C++]
- redistributing applications [C++], about redistributing applications
ms.assetid: d201b2ce-36f1-44e5-a96c-0db81a1ba652
ms.openlocfilehash: 7a639f7ad7deb76cade47b0162012dcb70cb0d69
ms.sourcegitcommit: e15b46ea7888dbdd7e0bb47da76aeed680c3c1f3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/17/2020
ms.locfileid: "86446754"
---
# <a name="redistributing-visual-c-files"></a>Visual C++ ファイルの再配布

> [!NOTE]
> ここでは、Visual C++ ランタイムファイルの1つをダウンロードしているので、 [Microsoft の web サイト](https://www.microsoft.com/)にアクセスして、検索ボックスに**Visual C++ 再頒布可能パッケージ**を入力します。 次に、お使いのコンピューターのアーキテクチャ用の再頒布可能パッケージ (たとえば、64 ビット Windows を実行している場合は x64) と、必要な Visual C++ のバージョン (たとえば、2015) をダウンロードしてインストールします。

## <a name="redistributable-files-and-licensing"></a>再頒布可能ファイルとライセンス

アプリケーションを配置する場合は、アプリケーションをサポートするために必要なすべてのファイルも配置する必要があります。 これらのファイルのいずれかが Microsoft によって提供されている場合は、再配布が許可されているかどうかを確認します。 IDE で Visual Studio のライセンス条項へのリンクが表示されます。 [バージョン Microsoft Visual Studio 情報] ダイアログボックスの [ライセンス条項] リンクを使用します。 または、Visual Studio[ライセンスディレクトリ](https://visualstudio.microsoft.com/license-terms/)から関連する eula とライセンスをダウンロードしてください。

::: moniker range="vs-2019"

Visual Studio 2019 マイクロソフトソフトウェアライセンス条項の「再頒布可能コード」セクションで言及されている "再頒布リスト" を表示するには、 [Microsoft Visual Studio 2019 の](/visualstudio/releases/2019/redistribution#-distributable-code-files-for-visual-studio-2019)再頒布可能コードファイルを参照してください。

::: moniker-end

::: moniker range="vs-2017"

Visual Studio 2017 マイクロソフトソフトウェアライセンス条項の「再頒布可能コード」セクションで言及されている "再頒布リスト" を表示するには、 [Microsoft Visual Studio 2017 の](/visualstudio/productinfo/2017-redistribution-vs#-distributable-code-files-for-visual-studio-2017)再頒布可能コードファイルを参照してください。

::: moniker-end

::: moniker range="vs-2015"

Visual Studio 2015 マイクロソフトソフトウェアライセンス条項の「再頒布可能コード」セクションで言及されている "再頒布リスト" を表示するには、 [Microsoft Visual Studio 2015 の](/visualstudio/productinfo/2015-redistribution-vs#-distributable-code-files-for-visual-studio-2015)再頒布可能コードファイルを参照してください。

::: moniker-end

再頒布可能ファイルの詳細については、「再[配布する dll の決定](determining-which-dlls-to-redistribute.md)」と「[デプロイの例](deployment-examples.md)」を参照してください。

## <a name="locate-the-redistributable-files"></a>再頒布可能ファイルの検索

再頒布可能ファイルを配置するには、Visual Studio によってインストールされた再頒布可能パッケージを使用できます。 2017以降のバージョンの Visual Studio では、これらのファイルには、、およびという名前が付けられ *`vc_redist.arm64.exe`* *`vc_redist.x64.exe`* て *`vc_redist.x86.exe`* います。 Visual Studio 2015、Visual Studio 2017、および Visual Studio 2019 では、、、 *`vcredist_x86.exe`* *`vcredist_x64.exe`* および (2015 のみ) の名前でも使用でき *`vcredist_arm.exe`* ます。

再頒布可能ファイルを検索する最も簡単な方法は、開発者コマンドプロンプトで設定された環境変数を使用することです。 最新バージョンの Visual Studio 2019 では、再頒布可能ファイルは *`%VCINSTALLDIR%Redist\MSVC\v142`* フォルダーにあります。 Visual Studio 2017 と Visual Studio 2019 の両方で、にもあり *`%VCToolsRedistDir%`* ます。 Visual Studio 2015 では、これらのファイルはにあり *`%VCINSTALLDIR%redist\<locale>`* *`<locale>`* ます。は再頒布可能パッケージのロケールです。

もう1つの配置オプションは、再頒布可能マージモジュール (ファイル) を使用することです *`.msm`* 。 Visual Studio 2019 では、これらのファイルは、Visual Studio インストーラーの**C++ 2019 再頒布可能パッケージ**というオプションのインストール可能なコンポーネントの一部です。 マージモジュールは、Visual Studio 2017 および Visual Studio 2015 の C++ インストールの一部として既定でインストールされます。 最新バージョンの Visual Studio 2019 にインストールされている場合は、に再頒布可能なマージモジュールが *`%VCINSTALLDIR%Redist\MSVC\v142\MergeModules`* あります。 Visual Studio 2019 と Visual Studio 2017 の両方で、にもあり *`%VCToolsRedistDir%MergeModules`* ます。 Visual Studio 2015 では、にあり *`Program Files [(x86)]\Common Files\Merge Modules`* ます。

## <a name="install-the-redistributable-packages"></a>再頒布可能パッケージをインストールする

Visual C++ 再頒布可能パッケージでは、すべての Visual C++ ライブラリがインストールされ、登録されます。 1つを使用する場合は、アプリケーションをインストールする前に、ターゲットシステムで前提条件として実行します。 配置ではこのパッケージを使用することをお勧めします。これにより、Visual C++ ライブラリの自動更新が有効になるためです。 これらのパッケージの使用方法の例については、「[チュートリアル: Visual C++ 再頒布可能パッケージを使用した Visual C++ アプリケーションの配置](deploying-visual-cpp-application-by-using-the-vcpp-redistributable-package.md)」を参照してください。

各 Visual C++ 再頒布可能パッケージは、より新しいバージョンがコンピューター上に存在するかどうかを確認します。 より新しいバージョンが見つかった場合、パッケージはインストールされません。 Visual Studio 2015 以降では、再頒布可能パッケージのセットアップが失敗したことを示すエラー メッセージが表示されます。 フラグを使用してパッケージを実行すると **`/quiet`** 、エラーメッセージは表示されません。 いずれの場合も、Microsoft インストーラーによってエラーがログ記録され、エラー結果が呼び出し元に返されます。 Visual Studio 2015 パッケージ以降では、レジストリを確認して、より新しいバージョンがインストールされているかどうかを調べると、このエラーを回避できます。 現在インストールされているバージョン番号は、キーに格納され `HKEY_LOCAL_MACHINE\SOFTWARE[\Wow6432Node]\Microsoft\VisualStudio\14.0\VC\Runtimes\{x86|x64|ARM}` ます。 最新の再頒布可能パッケージは、2015バージョンとのバイナリ互換性があるため、バージョン番号は Visual Studio 2015、Visual Studio 2017、および Visual Studio 2019 の場合は14.0 です。 キーは `ARM` 、 `x86` `x64` プラットフォームにインストールされている vcredist のバージョンに応じて、、、またはです。 ( `Wow6432Node` サブキーは、インストールされている x86 パッケージのバージョンを x64 プラットフォームで表示するために Regedit を使用している場合にのみ、確認する必要があります)。バージョン番号は、REG_SZ 文字列値 **`Version`** と、、、、の各値のセットに格納され **`Major`** **`Minor`** **`Bld`** **`Rbld`** `REG_DWORD` ます。 インストール時のエラーを回避するため、現在インストールされているバージョンの方が新しい場合は、再頒布可能パッケージのインストールをスキップする必要があります。

## <a name="install-the-redistributable-merge-modules"></a>再頒布可能マージモジュールをインストールする

再頒布可能なマージモジュールは、アプリケーションの配置に使用する Windows インストーラーパッケージ (または同様のインストールパッケージ) に含める必要があります。 詳細については、「[マージ モジュールを使用した再配布](redistributing-components-by-using-merge-modules.md)」を参照してください。 例については、「[チュートリアル: セットアッププロジェクトを使用した Visual C++ アプリケーションの配置](walkthrough-deploying-a-visual-cpp-application-by-using-a-setup-project.md)」を参照してください。

## <a name="install-individual-redistributable-files"></a>個々の再頒布可能ファイルをインストールする

*アプリケーションのローカルフォルダー*に再頒布可能 dll を直接インストールすることもできます。 これは、実行可能アプリケーションファイルを含むフォルダーです。 サービス上の理由から、このインストール場所は使用しないことをお勧めします。

## <a name="potential-run-time-errors"></a>実行時エラーの可能性

アプリケーションで必要な再頒布可能ライブラリ Dll が見つからない場合は、次のようなメッセージが表示されることがあります。 "このアプリケーションは、*ライブラリ*.dll が見つからなかったため、起動できませんでした。 アプリケーションを再インストールすると、この問題が解決する可能性があります。 "

この種のエラーを解決するには、アプリケーションインストーラーが正しくビルドされていることを確認します。 再頒布可能ライブラリがターゲットシステムに正しく配置されていることを確認します。 詳細については、「[Visual C++ アプリケーションの依存関係の理解](understanding-the-dependencies-of-a-visual-cpp-application.md)」を参照してください。

## <a name="related-articles"></a>関連記事

[マージモジュールを使用した再配布](redistributing-components-by-using-merge-modules.md)\
Visual C++ 再頒布可能マージモジュールを使用して、Visual C++ ランタイムライブラリを共有 Dll としてフォルダーにインストールする方法について説明し *`%windir%\system32\`* ます。

[Visual C++ ActiveX コントロールの再配布](redistributing-visual-cpp-activex-controls.md)\
ActiveX コントロールを使用するアプリケーションを再配布する方法について説明します。

[MFC ライブラリの再配布](redistributing-the-mfc-library.md)\
MFC を使用するアプリケーションを再配布する方法について説明します。

[ATL アプリケーションの再配布](redistributing-an-atl-application.md)\
ATL を使用するアプリケーションを再頒布する方法について説明します。 Visual Studio 2012 以降では、ATL 用の再頒布可能ライブラリは必要ありません。

[デプロイの例](deployment-examples.md)\
Visual C++ アプリケーションを配置する方法の例にリンクします。

[デスクトップアプリケーションの展開](deploying-native-desktop-applications-visual-cpp.md)\
Visual C++ の配置の概念とテクノロジの概要です。

---
title: Visual C ファイルの再頒布 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- application deployment [C++], file redistributing
- redistributing applications [C++]
- deploying applications [C++], file redistributing
- file redistribution [C++]
- redistributing applications [C++], about redistributing applications
ms.assetid: d201b2ce-36f1-44e5-a96c-0db81a1ba652
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e67ad87f1dce47f3d02dcbe907285cf0513a8ce9
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="redistributing-visual-c-files"></a>Visual C++ ファイルの再配布

> [!NOTE]
> ここで、いずれかの Visual C ランタイム ファイルのダウンロードを探しているためですか。 移動して、 [Microsoft](http://www.microsoft.com/) web サイトを入力および**Visual C Redistributable**検索ボックスにします。 ダウンロードして、コンピューター (たとえば、x64 64 ビット Windows を実行している場合) のアーキテクチャと、Visual C のバージョン (たとえば、2015) に必要な再頒布可能パッケージをインストールします。

アプリケーションを配置する場合は、アプリケーションをサポートするために必要なすべてのファイルも配置する必要があります。 必要なファイルに Microsoft から提供されるファイルが含まれる場合、それを再配布する権限を持っているかどうか確認します。 Visual Studio のライセンス条項を確認するは Microsoft Visual Studio ダイアログ ボックス、IDE でのライセンス条項リンクをご覧くださいまたはダウンロード、[マイクロソフト ソフトウェア ライセンス条項](http://go.microsoft.com/fwlink/p/?LinkId=831114)ファイル。 特定のエディションの Visual Studio の Microsoft ソフトウェア ライセンス条項の「頒布可能コード」セクションで参照されている"REDIST list"を表示する次を参照してください。 [Microsoft Visual Studio 2017 および Microsoft Visual Studio 2017 用頒布可能コード(が含まれていますユーティリティおよび BuildServer ファイル) の SDK](http://go.microsoft.com/fwlink/p/?LinkId=823098)、Visual Studio 2015 では、次を参照してください。 または[Microsoft Visual Studio 2015 および Microsoft Visual Studio 2015 SDK 用頒布可能コード](http://go.microsoft.com/fwlink/p/?LinkId=523763)です。 再頒布可能ファイルの詳細については、次を参照してください。[再配布する Dll の決定](../ide/determining-which-dlls-to-redistribute.md)と[配置例については](../ide/deployment-examples.md)します。

Visual C の再頒布可能ファイルを展開するには、Visual C 再頒布可能パッケージを使用することができます (VCRedist\_x86.exe、VCRedist\_x64.exe、または VCRedist\_arm.exe) Visual Studio に含まれています。 Visual Studio 2017 でこれらのファイルは含まれて Program Files [(x86)]\\Microsoft Visual Studio\\2017\\_エディション_\\VC\\Redist\\MSVC\\_lib バージョン_フォルダー場所_エディション_がインストールされている場合、Visual Studio のエディションと_lib バージョン_のバージョンは、再配布するライブラリ。 Visual Studio 2015 では、これらのファイル、Visual Studio インストール ディレクトリの下で見つかります Program Files [(x86)] \Microsoft Visual Studio*バージョン*\VC\redist\\*ロケール*\\. 別のオプションは、Visual Studio 2017 に Program Files [(x86)] で公開されている再頒布可能マージ モジュール (.msm ファイル) を使用する\\Microsoft Visual Studio\\2017\\_エディション_\\VC\\Redist\\MSVC\\_lib バージョン_\\MergeModules\\フォルダーです。 Visual Studio 2015 でこれらは含まれて Program Files [(x86)] \common モジュール\\です。 再頒布可能な Visual C Dll を直接インストールすることも、*アプリケーション ローカル フォルダー*、これは、アプリケーションの実行可能ファイルが含まれているフォルダーです。 サービス上の理由から、このインストール場所を使用することはお勧めしません。

Visual C++ 再頒布可能パッケージでは、すべての Visual C++ ライブラリがインストールされ、登録されます。 その 1 つを使用する場合は、アプリケーション インストールの必要条件として、インストール先のシステムでそれが実行されるように設定する必要があります。 配置ではこのパッケージを使用することをお勧めします。これにより、Visual C++ ライブラリの自動更新が有効になるためです。 これらのパッケージを使用する方法の例は、次を参照してください。[チュートリアル: Visual c 再頒布可能パッケージを、ビジュアル C++ を使ったアプリケーションを展開](../ide/deploying-visual-cpp-application-by-using-the-vcpp-redistributable-package.md)です。

各 Visual C++ 再頒布可能パッケージは、より新しいバージョンがコンピューター上に存在するかどうかを確認します。 より新しいバージョンが見つかった場合、パッケージはインストールされません。 Visual Studio 2015 以降では、再頒布可能パッケージのセットアップが失敗したことを示すエラー メッセージが表示されます。 使用してパッケージを実行した場合、 **/quiet**フラグは、エラー メッセージが表示されます。 いずれの場合も、Microsoft インストーラーによってエラーがログ記録され、エラー結果が呼び出し元に返されます。 Visual Studio 2015 パッケージ以降より新しいバージョンがインストールされているかどうかを調べるには、レジストリをチェックして、このエラーを回避できます。 現在インストールされているバージョンは hkey_local_machine \software [\Wow6432Node] \Microsoft\VisualStudio\\_vs バージョン_\VC\Runtimes\\{x86 | x64 |ARM} キー、 _vs バージョン_for Visual Studio のバージョン番号は、(Visual Studio 2015 と Visual Studio 2017、14.0 再頒布可能パッケージの更新された 2017 が 2015年のバージョンとバイナリ互換性のため)、キーであるとARM、x86、または x64 プラットフォームにインストールされている vcredist バージョンによって異なります。 (RegEdit を使用してインストールされた x86 のバージョンを表示する場合を除き、Wow6432Node サブキーの下で確認する必要はありませんパッケージを x64 プラットフォームです)。REG_SZ 文字列値にバージョン番号が格納されている**バージョン**のセットにも**メジャー**、**マイナー**、 **Bld**、および**Rbld** REG_DWORD の値。 インストール時に、エラーを回避するには、現在インストールされているバージョンより新しい場合、再頒布可能パッケージのインストールをスキップする必要があります。

Visual C++ DLL を含むマージ モジュールを使用する場合は、アプリケーションを配置するために使用する Windows インストーラー パッケージ (または同様のインストール パッケージ) にそのモジュール含める必要があります。 詳細については、次を参照してください。[の再配布してモジュールを使用してマージ](../ide/redistributing-components-by-using-merge-modules.md)です。 例については、次を参照してください。[チュートリアル: プロジェクトを配置する、Visual C++ を使ったアプリケーション セットアップ](../ide/walkthrough-deploying-a-visual-cpp-application-by-using-a-setup-project.md)、InstallShield Limited Edition を使用して、インストール パッケージを作成する方法も示しています。

## <a name="potential-run-time-errors"></a>発生する可能性のある実行時エラー

次のようなメッセージが表示されますが見つからない場合、再頒布可能ライブラリ、アプリケーションの必要な Dll のいずれか、:"このアプリケーションがあるためにの開始に失敗しました*ライブラリ*.dll が見つかりませんでした。 アプリケーションの再インストールがこの問題を解決します。"

この種のエラーを解決するには、アプリケーションのインストーラーが正しくビルドされると、再頒布可能ライブラリがターゲット システムに正しく配置されているを確認します。 詳細については、次を参照してください。 [Visual c アプリケーションの依存関係を理解する](../ide/understanding-the-dependencies-of-a-visual-cpp-application.md)です。

## <a name="related-topics"></a>関連トピック

|タイトル|説明|
|-----------|-----------------|
|[マージ モジュールを使用した再配布](../ide/redistributing-components-by-using-merge-modules.md)|Visual C 再頒布可能マージ モジュールを使用して %windir%\system32\ フォルダーに共有 Dll として、Visual C ランタイム ライブラリをインストールする方法について説明します。|
|[Visual C++ ActiveX コントロールの再頒布](../ide/redistributing-visual-cpp-activex-controls.md)|ActiveX コントロールを使用するアプリケーションを再配布する方法について説明します。|
|[データベース サポート ファイルの再頒布](../ide/redistributing-database-support-files.md)|データ アクセス オブジェクト (DAO: Data Access Object) 用のサポート ファイルの再配布、および Microsoft Data Access SDK のデータベース テクノロジのサポート ファイルの再配布について説明します。|
|[MFC ライブラリの再頒布](../ide/redistributing-the-mfc-library.md)|MFC を使用するアプリケーションを再配布する方法について説明します。|
|[ATL アプリケーションの再頒布](../ide/redistributing-an-atl-application.md)|ATL を使用するアプリケーションを再頒布する方法について説明します。 Visual Studio 2012 以降では、ATL 用の再頒布可能ライブラリは必要ありません。|
|[配置例](../ide/deployment-examples.md)|Visual C++ アプリケーションを配置する方法の例にリンクします。|
|[デスクトップ アプリケーションの配置](../ide/deploying-native-desktop-applications-visual-cpp.md)|Visual C++ の配置の概念とテクノロジの概要です。|
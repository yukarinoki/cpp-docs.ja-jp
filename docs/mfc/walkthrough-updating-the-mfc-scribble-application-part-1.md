---
title: 'チュートリアル: MFC Scribble アプリケーションの更新 (パート 1)'
ms.date: 09/09/2019
helpviewer_keywords:
- examples [MFC], update existing application
- ribbon UI, porting to
- Office Fluent UI, porting to
- samples [MFC], update existing application
- MFC Feature Pack, update existing application
- walkthroughs [MFC], update existing application
ms.assetid: aa6330d3-6cfc-4c79-8fcb-0282263025f7
ms.openlocfilehash: 9fc2903180a055c18c6f3779b1da55ee347d2535
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87230429"
---
# <a name="walkthrough-updating-the-mfc-scribble-application-part-1"></a>チュートリアル: MFC Scribble アプリケーションの更新 (パート 1)

このチュートリアルでは、リボン ユーザー インターフェイスを使用するために MFC アプリケーションを修正する方法を説明します。 Visual Studio は、Office 2007 リボンと Windows 7 Scenic リボンの両方をサポートしています。 リボンユーザーインターフェイスの詳細については、「[リボン](/windows/win32/uxguide/cmd-ribbons)」を参照してください。

このチュートリアルでは、マウスを使用して線画を描く、従来の Scribble 1.0 MFC サンプルを変更します。 ここでは、リボン バーを表示するよう Scribble サンプルを変更します。 [パート 2](../mfc/walkthrough-updating-the-mfc-scribble-application-part-2.md)では、リボンバーにボタンを追加します。

## <a name="prerequisites"></a>前提条件

[Scribble 1.0 MFC サンプル](https://download.microsoft.com/download/4/0/9/40946FEC-EE5C-48C2-8750-B0F8DA1C99A8/MFC/general/Scribble.zip.exe)。 Visual Studio 2017 以降への変換については、「[移植ガイド: MFC Scribble](../porting/porting-guide-mfc-scribble.md)」を参照してください。

## <a name="sections"></a><a name="top"></a>各項

このパートは、次のセクションで構成されています。

- [基底クラスの置き換え](#replaceclass)

- [プロジェクトへのビットマップの追加](#addbitmap)

- [プロジェクトへのリボン リソースの追加](#addribbon)

- [リボン バーのインスタンスの作成](#createinstance)

- [リボン カテゴリの追加](#addcategory)

- [アプリケーションの外観の設定](#setlook)

## <a name="replacing-the-base-classes"></a><a name="replaceclass"></a>基底クラスの置換

メニュー ベースのアプリケーションをリボン ベースのアプリケーションに変換するには、アプリケーション、フレーム ウィンドウ、ツール バーの各クラスを、更新された基底クラスから派生させる必要があります  (元の Scribble サンプルは変更しないことをお勧めします。 代わりに、Scribble プロジェクトを消去し、別のディレクトリにコピーして、コピーを変更します。)

### <a name="to-replace-the-base-classes-in-the-scribble-application"></a>Scribble アプリケーションの基底クラスを置き換えるには

1. Scribble で、に `CScribbleApp::InitInstance` [AfxOleInit](../mfc/reference/ole-initialization.md#afxoleinit)の呼び出しが含まれていることを確認します。

1. 次のコードを *.pch*ファイル (Visual Studio 2017 以前の*stdafx.h* ) に追加します。

    ```cpp
    #include <afxcontrolbars.h>
    ```

1. Scribble. h で、クラスの定義を変更して、 `CScribbleApp` [CWinAppEx クラス](../mfc/reference/cwinappex-class.md)から派生するようにします。

    ```cpp
    class CScribbleApp: public CWinAppEx
    ```

1. Scribble 1.0 は、Windows アプリケーションが初期化 (.ini) ファイルを使用してユーザー設定のデータを保存したときに書き込まれています。 初期化ファイルは変更せず、Scribble を変更してユーザー設定をレジストリに格納します。 レジストリ キーとベースを設定するには、次のコードを、`CScribbleApp::InitInstance` ステートメントの後ろの `LoadStdProfileSettings()` に含めます。

    ```cpp
    SetRegistryKey(_T("MFCNext\\Samples\\Scribble2"));
    SetRegistryBase(_T("Settings"));
    ```

1. マルチ ドキュメント インターフェイス (MDI) アプリケーション用のメイン フレームはもう `CMDIFrameWnd` クラスから派生しません。 代わりに、 [CMDIFrameWndEx](../mfc/reference/cmdiframewndex-class.md)クラスから派生します。

    mainfrm.h ファイルと mainfrm.cpp ファイルで、`CMDIFrameWnd` への参照をすべて、`CMDIFrameWndEx` への参照に置き換えます。

1. childfrm.h ファイルと childfrm.cpp ファイルで、`CMDIChildWnd` を `CMDIChildWndEx` に置き換えます。

    Childfrm にあります。 h ファイル。を `CSplitterWnd` に置き換え `CSplitterWndEx` ます。

1. ツール バーとステータス バーを変更して、新しい MFC クラスを使用します。

    mainfrm.h ファイルでは、次の手順に従います。

    1. `CToolBar` を `CMFCToolBar` で置き換え

    1. `CStatusBar` を `CMFCStatusBar` で置き換え

1. mainfrm.cpp ファイルでは、次の手順に従います。

    1. `m_wndToolBar.SetBarStyle` を `m_wndToolBar.SetPaneStyle` に置き換えます。

    1. `m_wndToolBar.GetBarStyle` を `m_wndToolBar.GetPaneStyle` に置き換えます。

    1. `DockControlBar(&m_wndToolBar)` を `DockPane(&m_wndToolBar)` に置き換えます。

1. ipframe.cpp ファイルでは、コードの次の 3 行をコメント アウトします。

    ```cpp
    m_wndToolBar.EnableDocking(CBRS_ALIGN_ANY);
    pWndFrame->EnableDocking(CBRS_ALIGN_ANY);
    pWndFrame->DockPane(&m_wndToolBar);
    ```

1. 変更を保存し、アプリケーションをビルドして実行します。

## <a name="adding-bitmaps-to-the-project"></a><a name="addbitmap"></a>プロジェクトへのビットマップの追加

このチュートリアルの次の 4 つの手順には、ビットマップ リソースが必要です。 適切なビットマップは、さまざまな方法で取得できます。

- 独自のビットマップを作成するには、[リソースエディター](../windows/resource-editors.md)を使用します。 または、リソースエディターを使用して、Visual Studio に含まれているポータブルネットワークグラフィックス (.png) イメージからビットマップをアセンブルし、 [Visual studio イメージライブラリ](https://docs.microsoft.com/visualstudio/designers/the-visual-studio-image-library)からダウンロードすることができます。

    ただし、**リボン**のユーザーインターフェイスでは、特定のビットマップで透明なイメージがサポートされている必要があります。 透明なビットマップでは32ビットピクセルが使用されます。ここで、24ビットは色の赤、緑、および青のコンポーネントを指定し、8ビットは色の透明度を指定する*アルファチャネル*を定義します。 現在のリソース エディターでは、32 ビット ピクセルのビットマップを表示できますが、変更できません。 そのため、透明なビットマップを作成する場合は、リソース エディターではなく、外部のイメージ エディターを使用します。

- 適切なリソース ファイルを別のアプリケーションからプロジェクトにコピーし、そのファイルからビットマップをインポートします。

このチュートリアルでは、 [「チュートリアル: MFC を使用したリボンアプリケーションの作成](../mfc/walkthrough-creating-a-ribbon-application-by-using-mfc.md)」で作成した例からリソースファイルをコピーします。

### <a name="to-add-bitmaps-to-the-project"></a>ビットマップをプロジェクトに追加するには

1. ファイルエクスプローラーを使用して、リボンの例の resources ディレクトリ ( `res` ) から Scribble プロジェクトのリソースディレクトリ () に次の .bmp ファイルをコピーし `res` ます。

   1. main.bmp を Scribble プロジェクトにコピーします。

   1. filesmall.bmp と filelarge.bmp を Scribble プロジェクトにコピーします。

   1. filelarge.bmp と filesmall.bmp ファイルの新しいコピーを作成しますが、リボンの例にコピーを保存します。 homesmall.bmp と homelarge.bmp のコピーの名前を変更し、それらを Scribble プロジェクトに移動します。

   1. toolbar.bmp ファイルのコピーを作成しますが、リボンの例にコピーを保存します。 panelicons.bmp のコピーの名前を変更し、それを Scribble プロジェクトに移動します。

1. MFC アプリケーション用のビットマップをインポートします。 **リソースビュー**で、[ **scribble** ] ノードをダブルクリックし、[ **Bitmap** ] ノードをダブルクリックして、[**リソースの追加**] をクリックします。 表示されるダイアログボックスで、[**インポート**] をクリックします。 ディレクトリを参照して `res` main.bmp ファイルを選択し、[**開く**] をクリックします。

   main.bmp ビットマップには、26 × 26 イメージが含まれています。 ビットマップの ID をに変更 `IDB_RIBBON_MAIN` します。

1. [**アプリケーション**] ボタンに関連付けられている [ファイル] メニューのビットマップをインポートします。

   1. 11 16x16 (16x176) のイメージを含む filesmall.bmp ファイルをインポートします。 ビットマップの ID をに変更 `IDB_RIBBON_FILESMALL` します。

   > [!NOTE]
   > 最初の 8 16x16 イメージ (16x128) のみが必要であるため、必要に応じて、このビットマップの右端の幅を176から128にトリミングすることができます。

   1. 9つの 32x32 (32x288) イメージを含む filelarge.bmp をインポートします。 ビットマップの ID をに変更 `IDB_RIBBON_FILELARGE` します。

1. リボンのカテゴリとパネル用のビットマップをインポートします。 リボン バーの各タブはカテゴリであり、テキスト ラベルと省略可能なイメージで構成されます。

   1. homesmall.bmp ビットマップをインポートします。このビットマップには、小さいボタンのビットマップ用に 11 16x16 の画像が含まれています。 ビットマップの ID をに変更 `IDB_RIBBON_HOMESMALL` します。

   1. homelarge.bmp ビットマップをインポートします。このビットマップには、大きいボタンのビットマップ用に9つの32x32 のイメージが含まれています。 ビットマップの ID をに変更 `IDB_RIBBON_HOMELARGE` します。

1. サイズが変更されたリボン パネル用のビットマップをインポートします。 このビットマップ、つまりパネル アイコンは、リボンが小さすぎてパネル全体を表示できない場合に、サイズ変更操作後に使用されます。

   1. panelicons.bmp をインポートします。このファイルには 16 × 16 イメージが 8 個含まれています。 **ビットマップエディター**の [**プロパティ**] ウィンドウで、ビットマップの幅を 64 (16x64) に調整します。 ビットマップの ID をに変更 `IDB_PANEL_ICONS` します。

   > [!NOTE]
   > 最初の4つの16x16 イメージ (16x64) のみが必要であるため、必要に応じて、このビットマップの右端の幅を128から64にトリミングすることができます。

## <a name="adding-a-ribbon-resource-to-the-project"></a><a name="addribbon"></a>プロジェクトへのリボンリソースの追加

メニューを使用するアプリケーションを、リボンを使用するアプリケーションに変換する場合、既存のメニューを削除したり無効にしたりする必要はありません。 リボンリソースを作成し、リボンボタンを追加して、新しいボタンを既存のメニュー項目に関連付けるだけです。 メニューは表示されなくなりましたが、リボンバーからのメッセージはメニューを通じてルーティングされ、メニューのショートカットは引き続き機能します。

リボンは、リボンの左上にある大きいボタンである [**アプリケーション**] ボタンと、1つまたは複数の [カテゴリ] タブで構成されています。 各カテゴリ タブは、1 つまたは複数のパネルで構成されます。パネルは、リボンのボタンやコントロールのコンテナーの役割を果たします。 次の手順は、リボンリソースを作成し、**アプリケーション**ボタンをカスタマイズする方法を示しています。

### <a name="to-add-a-ribbon-resource-to-the-project"></a>リボン リソースをプロジェクトに追加するには

1. **ソリューションエクスプローラー**で Scribble プロジェクトを選択した状態で、[**プロジェクト**] メニューの [**リソースの追加**] をクリックします。

1. [**リソースの追加**] ダイアログボックスで [**リボン**] を選択し、[**新規作成**] をクリックします。

   Visual Studio でリボン リソースが作成され、デザイン ビューで開かれます。 リボンリソース ID はで `IDR_RIBBON1` 、**リソースビュー**に表示されます。 リボンには、1 つのカテゴリと 1 つのパネルがあります。

1. アプリケーションのプロパティを変更することで、**アプリケーション**ボタンをカスタマイズできます。 このコードで使用されているメッセージ ID は、Scribble 1.0 用のメニューで定義済みです。

1. [デザイン] ビューで、[**アプリケーション**] ボタンをクリックしてプロパティを表示します。 プロパティの値を次のように変更します。 [**画像** `IDB_RIBBON_MAIN` ]、[**プロンプト** `File` ]、[**キー** ] `f` 、[**大きい画像**]、 `IDB_RIBBON_FILELARGE` および [**小さい画像**] を指定し `IDB_RIBBON_FILESMALL` ます。

1. 次の変更により、ユーザーが**アプリケーション**ボタンをクリックしたときに表示されるメニューが作成されます。 [**メイン項目**] の横にある省略記号 (**...**) をクリックして、**項目エディター**を開きます。

   1. [**項目**の種類 **] ボタン**を選択した状態で、[**追加**] をクリックしてボタンを追加します。 [**キャプション**] をに変更し、[ `&New` **ID** ] を、[ `ID_FILE_NEW` **イメージ**] を [ `0` **大きいイメージ**] に変更 `0` します。

   1. [**追加**] をクリックしてボタンを追加します。 [**キャプション**] をに、[ID] を、[イメージ] を [イメージ] をに変更し `&Save` **ID** `ID_FILE_SAVE` **Image** `2` **Image Large** `2` ます。

   1. [**追加**] をクリックしてボタンを追加します。 [**キャプション**] をに、[ID] を、[イメージ] を [イメージ] をに変更し `Save &As` **ID** `ID_FILE_SAVE_AS` **Image** `3` **Image Large** `3` ます。

   1. [**追加**] をクリックしてボタンを追加します。 [**キャプション**] をに、[ID] を、[イメージ] を [イメージ] をに変更し `&Print` **ID** `ID_FILE_PRINT` **Image** `4` **Image Large** `4` ます。

   1. **項目**の種類を [**区切り記号**] に変更し、[**追加**] をクリックします。

   1. **項目**の種類を **[ボタン]** に変更します。 5番目のボタンを追加するには、[**追加**] をクリックします。 [**キャプション**] をに、[ID] を、[イメージ] を [イメージ] をに変更し `&Close` **ID** `ID_FILE_CLOSE` **Image** `5` **Image Large** `5` ます。

1. 次の変更を行うと、前の手順で作成した [**印刷**] ボタンの下にサブメニューが作成されます。

   1. [**印刷**] ボタンをクリックし、**項目**の種類を [**ラベル**] に変更して、[**挿入**] をクリックします。 **キャプション**をに変更 `Preview and print the document` します。

   1. [**印刷**] ボタンをクリックし、**項目**の種類を [**ボタン]** に変更して、[**挿入**] をクリックします。 [**キャプション**] をに、[ID] を、[イメージ] を [イメージ] をに変更し `&Print` **ID** `ID_FILE_PRINT` **Image** `4` **Image Large** `4` ます。

   1. [**印刷**] ボタンをクリックし、[**挿入**] をクリックしてボタンを追加します。 [**キャプション**] をに、[ID] を、[イメージ] を [イメージ] をに変更し `&Quick Print` **ID** `ID_FILE_PRINT_DIRECT` **Image** `7` **Image Large** `7` ます。

   1. [**印刷**] ボタンをクリックし、[**挿入**] をクリックして別のボタンを追加します。 [**キャプション**] をに、[ID] を、[イメージ] を [イメージ] をに変更し `Print Pre&view` **ID** `ID_FILE_PRINT_PREVIEW` **Image** `6` **Image Large** `6` ます。

   1. これで、**メイン項目**が変更されました。 [**閉じる**] をクリックして、**項目エディター**を終了します。

1. 次の変更を行うと、**アプリケーション**のボタンメニューの下部に表示される [終了] ボタンが作成されます。

   1. **ソリューションエクスプローラー**の [**リソースビュー** ] タブを選択します。
   1. [**プロパティ**] ウィンドウで、**ボタン**の横にある省略記号 (**..**.) をクリックして、**項目エディター**を開きます。

   1. [**項目**の種類 **] ボタン**を選択した状態で、[**追加**] をクリックしてボタンを追加します。 [**キャプション**] をに `E&xit` 、[ **ID** ] を、 `ID_APP_EXIT` [**イメージ**] をに変更 `8` します。

   1. **ボタン**が変更されました。 [**閉じる**] をクリックして、**項目エディター**を終了します。

## <a name="creating-an-instance-of-the-ribbon-bar"></a><a name="createinstance"></a>リボンバーのインスタンスの作成

次の手順では、アプリケーションの起動時にリボン バーのインスタンスを作成する方法を説明します。 リボン バーをアプリケーションに追加するには、mainfrm.h ファイルでリボン バーを宣言します。 次に、mainfrm.cpp ファイルで、リボン リソースを読み込むコードを作成します。

### <a name="to-create-an-instance-of-the-ribbon-bar"></a>リボン バーのインスタンスを作成するには

1. mainfrm.h ファイルで、メイン フレームのクラス定義 `CMainFrame` の保護されたセクションにデータ メンバーを追加します。 このメンバーは、リボンバー用です。

    ```cpp
    // Ribbon bar for the application
    CMFCRibbonBar m_wndRibbonBar;
    ```

2. Mainfrm.cpp ファイルで、 **`return`** 関数の最後にある最後のステートメントの前に次のコードを追加します `CMainFrame::OnCreate` 。 リボンバーのインスタンスを作成します。

    ```cpp
    // Create the ribbon bar
    if (!m_wndRibbonBar.Create(this))
    {
        return -1;   //Failed to create ribbon bar
    }
    m_wndRibbonBar.LoadFromResource(IDR_RIBBON1);
    ```

## <a name="customizing-the-ribbon-resource"></a><a name="addcategory"></a>リボンリソースのカスタマイズ

**アプリケーション**ボタンを作成したので、リボンに要素を追加できます。

> [!NOTE]
> このチュートリアルでは、すべてのパネルで同じパネル アイコンを使用します。 ただし、他のイメージ リスト インデックスを使用して、他のアイコンを表示してもかまいません。

### <a name="to-add-a-home-category-and-edit-panel"></a>[Home] カテゴリと [Edit] パネルを追加するには

1. この Scribble プログラムに必要なカテゴリは 1 つだけです。 [デザイン] ビューの [**ツールボックス**] で、[**カテゴリ**] をダブルクリックして追加し、そのプロパティを表示します。 プロパティ値を次のように変更します。**キャプション**の場合は、 `&Home` **大きい画像** `IDB_RIBBON_HOMELARGE` の場合は、**小さい画像**の場合は `IDB_RIBBON_HOMESMALL` です。

1. 各リボン カテゴリは名前付きパネルに整理されます。 各パネルには、関連する操作を完了するコントロールのセットが含まれています。 このカテゴリには 1 つのパネルがあります。 [**パネル**] をクリックし、[**キャプション**] を「」に変更し `Edit` ます。

1. [**編集**] パネルに、ドキュメントの内容をクリアするボタンを追加します。 このボタンのメッセージ ID は、メニューリソースで既に定義されてい `IDR_SCRIBBTYPE` ます。 ボタンのテキストとしてを指定し、 `Clear All` ボタンを装飾するビットマップのインデックスを指定します。 [**ツールボックス**] を開き、**ボタン**を [**編集**] パネルにドラッグします。 ボタンをクリックし、[**キャプション**] を [ID] に変更し、[イメージのインデックス] を [大きいイメージのインデックス] に変更し `Clear All` **ID** `ID_EDIT_CLEAR_ALL` **Image Index** `0` **Large Image Index** `0` ます。

1. 変更内容を保存し、アプリケーションをビルドして実行します。 Scribble アプリケーションが起動されますが、ウィンドウ最上部にはメニュー バーではなく、リボンが表示されます。 リボンバーには1つのカテゴリ、[**ホーム**]、[**ホーム**] に1つのパネルがあり、[**編集**] が表示されている必要があります。 追加したリボンのボタンは既存のイベントハンドラーに関連付けられ、[**開く**]、[**閉じる**]、[**保存**]、[**印刷**]、および [**すべてクリア**] の各ボタンは想定どおりに動作します。

## <a name="setting-the-look-of-the-application"></a><a name="setlook"></a>アプリケーションの外観の設定

*ビジュアルマネージャー*は、アプリケーションのすべての描画を制御するグローバルオブジェクトです。 元の Scribble アプリケーションは Office 2000 のユーザー インターフェイス (UI) スタイルを使用しているため、このアプリケーションの外観は古めかしく感じられるかもしれません。 このアプリケーションは、Office 2007 のビジュアル マネージャーを使用するようにリセットして、Office 2007 のような外観にすることができます。

### <a name="to-set-the-look-of-the-application"></a>アプリケーションの外観を設定するには

1. 関数で、 `CMainFrame::OnCreate` ステートメントの前に次のコードを入力して、 `return 0;` 既定のビジュアルマネージャーとスタイルを変更します。

    ```cpp
    // Set the default manager to Office 2007
    CMFCVisualManager::SetDefaultManager(RUNTIME_CLASS(CMFCVisualManagerOffice2007));
    CMFCVisualManagerOffice2007::SetStyle(CMFCVisualManagerOffice2007::Office2007_LunaBlue);
    ```

1. 変更内容を保存し、アプリケーションをビルドして実行します。 アプリケーションの UI が Office 2007 と類似した UI になります。

## <a name="next-steps"></a>次のステップ

**リボンデザイナー**を使用するように、従来の SCRIBBLE 1.0 MFC サンプルを変更しました。 次に、[パート 2](../mfc/walkthrough-updating-the-mfc-scribble-application-part-2.md)に進んでください。

## <a name="see-also"></a>関連項目

[チュートリアル](../mfc/walkthroughs-mfc.md)<br/>
[チュートリアル: MFC Scribble アプリケーションの更新 (パート 2)](../mfc/walkthrough-updating-the-mfc-scribble-application-part-2.md)

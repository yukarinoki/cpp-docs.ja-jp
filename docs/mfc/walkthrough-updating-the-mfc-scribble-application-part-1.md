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
ms.openlocfilehash: 18803d2222c80b80ac2b1fde75b442ea1e9a89bb
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81360260"
---
# <a name="walkthrough-updating-the-mfc-scribble-application-part-1"></a>チュートリアル: MFC Scribble アプリケーションの更新 (パート 1)

このチュートリアルでは、リボン ユーザー インターフェイスを使用するために MFC アプリケーションを修正する方法を説明します。 Visual Studio は、Office 2007 リボンと Windows 7 Scenic リボンの両方をサポートしています。 リボン のユーザー インターフェイスの詳細については、「[リボン](/windows/win32/uxguide/cmd-ribbons)」を参照してください。

このチュートリアルでは、マウスを使用して線画を描く、従来の Scribble 1.0 MFC サンプルを変更します。 ここでは、リボン バーを表示するよう Scribble サンプルを変更します。 [パート 2](../mfc/walkthrough-updating-the-mfc-scribble-application-part-2.md)では、リボン バーにさらにボタンを追加します。

## <a name="prerequisites"></a>前提条件

[Scribble 1.0 MFC サンプル](https://download.microsoft.com/download/4/0/9/40946FEC-EE5C-48C2-8750-B0F8DA1C99A8/MFC/general/Scribble.zip.exe). Visual Studio 2017 以降への変換のヘルプについては、「[移植ガイド: MFC Scribble](../porting/porting-guide-mfc-scribble.md)」を参照してください。

## <a name="sections"></a><a name="top"></a>セクション

このパートは、次のセクションで構成されています。

- [基底クラスの置き換え](#replaceclass)

- [プロジェクトへのビットマップの追加](#addbitmap)

- [プロジェクトへのリボン リソースの追加](#addribbon)

- [リボン バーのインスタンスの作成](#createinstance)

- [リボン カテゴリの追加](#addcategory)

- [アプリケーションの外観の設定](#setlook)

## <a name="replacing-the-base-classes"></a><a name="replaceclass"></a>基本クラスの置換

メニュー ベースのアプリケーションをリボン ベースのアプリケーションに変換するには、アプリケーション、フレーム ウィンドウ、ツール バーの各クラスを、更新された基底クラスから派生させる必要があります  (元の Scribble サンプルは変更しないことをお勧めします。 代わりに、Scribble プロジェクトをクリーンアップし、別のディレクトリにコピーしてから、コピーを変更します)。

### <a name="to-replace-the-base-classes-in-the-scribble-application"></a>Scribble アプリケーションの基底クラスを置き換えるには

1. Scribble.cpp で`CScribbleApp::InitInstance`[、AfxOleInit](../mfc/reference/ole-initialization.md#afxoleinit)への呼び出しが含まれていることを確認します。

1. 次のコードを*pch.h*ファイル (Visual Studio 2017 以前のバージョンの*stdafx.h)* に追加します。

    ```cpp
    #include <afxcontrolbars.h>
    ```

1. Scribble.h では、クラスの定義を`CScribbleApp`変更して[、CWinAppEx クラス](../mfc/reference/cwinappex-class.md)から派生するようにします。

    ```cpp
    class CScribbleApp: public CWinAppEx
    ```

1. Scribble 1.0 は、Windows アプリケーションが初期化 (.ini) ファイルを使用してユーザー設定のデータを保存したときに書き込まれています。 初期化ファイルは変更せず、Scribble を変更してユーザー設定をレジストリに格納します。 レジストリ キーとベースを設定するには、次のコードを、`CScribbleApp::InitInstance` ステートメントの後ろの `LoadStdProfileSettings()` に含めます。

    ```cpp
    SetRegistryKey(_T("MFCNext\\Samples\\Scribble2"));
    SetRegistryBase(_T("Settings"));
    ```

1. マルチ ドキュメント インターフェイス (MDI) アプリケーション用のメイン フレームはもう `CMDIFrameWnd` クラスから派生しません。 代わりに、クラスから派生[します](../mfc/reference/cmdiframewndex-class.md)。

    mainfrm.h ファイルと mainfrm.cpp ファイルで、`CMDIFrameWnd` への参照をすべて、`CMDIFrameWndEx` への参照に置き換えます。

1. childfrm.h ファイルと childfrm.cpp ファイルで、`CMDIChildWnd` を `CMDIChildWndEx` に置き換えます。

    子供のfrmで。 h ファイル、 `CSplitterWnd` `CSplitterWndEx`で置き換えます。

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

- リソース[エディタを](../windows/resource-editors.md)使用して、独自のビットマップを作成します。 または、リソース エディターを使用して、Visual Studio に含まれ[、Visual](https://docs.microsoft.com/visualstudio/designers/the-visual-studio-image-library)Studio イメージ ライブラリからダウンロードできるポータブル ネットワーク グラフィックス (.png) イメージからビットマップをアセンブルします。

    ただし、**リボン**のユーザー インターフェイスでは、特定のビットマップが透明なイメージをサポートする必要があります。 透明なビットマップでは 32 ビットピクセルが使用され、24 ビットがカラーの赤、緑、青の各要素を指定し、8 ビットが色の透明度を指定する*アルファ チャンネル*を定義します。 現在のリソース エディターでは、32 ビット ピクセルのビットマップを表示できますが、変更できません。 そのため、透明なビットマップを作成する場合は、リソース エディターではなく、外部のイメージ エディターを使用します。

- 適切なリソース ファイルを別のアプリケーションからプロジェクトにコピーし、そのファイルからビットマップをインポートします。

このチュートリアルでは、「チュートリアル : MFC を[使用したリボン アプリケーションの作成](../mfc/walkthrough-creating-a-ribbon-application-by-using-mfc.md)」で作成した例のリソース ファイルをコピーします。

### <a name="to-add-bitmaps-to-the-project"></a>ビットマップをプロジェクトに追加するには

1. ファイル エクスプローラを使用して、リボンの例のリソース ディレクトリ (`res`) から Scribble プロジェクト`res`のリソース ディレクトリ ( ) に次の .bmp ファイルをコピーします。

   1. main.bmp を Scribble プロジェクトにコピーします。

   1. filesmall.bmp と filelarge.bmp を Scribble プロジェクトにコピーします。

   1. filelarge.bmp ファイルと filesmall.bmp ファイルの新しいコピーを作成しますが、リボンの例ではコピーを保存します。 homesmall.bmp と homelarge.bmp のコピーの名前を変更し、それらを Scribble プロジェクトに移動します。

   1. toolbar.bmp ファイルのコピーを作成しますが、リボンの例では保存します。 panelicons.bmp のコピーの名前を変更し、それを Scribble プロジェクトに移動します。

1. MFC アプリケーション用のビットマップをインポートします。 **リソース ビュー**で **、scribble.rc**ノードをダブルクリックし、**ビットマップ**ノードをダブルクリックして、[リソースの**追加**] をクリックします。 表示されるダイアログ ボックスで、[**インポート**] をクリックします。 ディレクトリを`res`参照し、main.bmp ファイルを選択して、[**開く**] をクリックします。

   main.bmp ビットマップには、26 × 26 イメージが含まれています。 ビットマップの ID を`IDB_RIBBON_MAIN`に変更します。

1. **アプリケーション**ボタンにアタッチされているファイル メニューのビットマップをインポートします。

   1. 16x16 (16x176) の 11 個のイメージを含むファイル小さな.bmp ファイルをインポートします。 ビットマップの ID を`IDB_RIBBON_FILESMALL`に変更します。

   > [!NOTE]
   > 最初の 8 つの 16x16 イメージ (16x128) のみが必要なため、必要に応じてこのビットマップの右側の幅を 176 ~ 128 にトリミングできます。

   1. 9 つの 32x32 (32x288) イメージを含むファイル large.bmp をインポートします。 ビットマップの ID を`IDB_RIBBON_FILELARGE`に変更します。

1. リボンのカテゴリとパネル用のビットマップをインポートします。 リボン バーの各タブはカテゴリであり、テキスト ラベルと省略可能なイメージで構成されます。

   1. 小さいボタンビットマップ用の 16 x 16 イメージを 11 個含む homesmall.bmp ビットマップをインポートします。 ビットマップの ID を`IDB_RIBBON_HOMESMALL`に変更します。

   1. 大きいボタン ビットマップ用の 32 x 32 イメージを 9 つ含む homelarge.bmp ビットマップをインポートします。 ビットマップの ID を`IDB_RIBBON_HOMELARGE`に変更します。

1. サイズが変更されたリボン パネル用のビットマップをインポートします。 このビットマップ、つまりパネル アイコンは、リボンが小さすぎてパネル全体を表示できない場合に、サイズ変更操作後に使用されます。

   1. panelicons.bmp をインポートします。このファイルには 16 × 16 イメージが 8 個含まれています。 **ビットマップ エディタ**の **[プロパティ]** ウィンドウで、ビットマップの幅を 64 (16x64) に調整します。 ビットマップの ID を`IDB_PANEL_ICONS`に変更します。

   > [!NOTE]
   > 最初の 4 つの 16 x 16 イメージ (16x64) のみが必要なので、必要に応じてこのビットマップの右側の幅を 128 から 64 にトリミングできます。

## <a name="adding-a-ribbon-resource-to-the-project"></a><a name="addribbon"></a>プロジェクトへのリボン リソースの追加

メニューを使用するアプリケーションをリボンを使用するアプリケーションに変換する場合、既存のメニューを削除したり無効にしたりする必要はありません。 リボン リソースを作成し、リボン ボタンを追加し、新しいボタンを既存のメニュー項目に関連付けるだけです。 メニューは表示されなくなりますが、リボン バーからのメッセージはメニューを通じてルーティングされ、メニュー ショートカットは引き続き機能します。

リボンは、リボンの左上にある大きなボタンである **[アプリケーション**] ボタンと、1 つ以上のカテゴリ タブで構成されます。 各カテゴリ タブは、1 つまたは複数のパネルで構成されます。パネルは、リボンのボタンやコントロールのコンテナーの役割を果たします。 次の手順は、リボン リソースを作成し、[**アプリケーション**] ボタンをカスタマイズする方法を示しています。

### <a name="to-add-a-ribbon-resource-to-the-project"></a>リボン リソースをプロジェクトに追加するには

1. **ソリューション エクスプローラ**で Scribble プロジェクトを選択し、[プロジェクト] メニューの [**リソース**の**追加**] をクリックします。

1. [**リソースの追加**] ダイアログ ボックスで、[**リボン**] を選択し、[**新規作成**] をクリックします。

   Visual Studio でリボン リソースが作成され、デザイン ビューで開かれます。 リボン リソース ID`IDR_RIBBON1`は、 リソース**ビュー**に表示されます。 リボンには、1 つのカテゴリと 1 つのパネルがあります。

1. **[アプリケーション]** ボタンのプロパティを変更してカスタマイズできます。 このコードで使用されているメッセージ ID は、Scribble 1.0 用のメニューで定義済みです。

1. デザイン ビューで、[**アプリケーション**] ボタンをクリックしてプロパティを表示します。 プロパティ値を次のように変更します**Image**:`IDB_RIBBON_MAIN`イメージ 、`File`プロンプト 、**キー**の`IDB_RIBBON_FILELARGE`**Keys**入力`f`、**大きなイメージ**のサイズ 、 小**さいイメージ**の値 。 `IDB_RIBBON_FILESMALL`

1. 次の変更により、ユーザーが **[アプリケーション**] ボタンをクリックしたときに表示されるメニューが作成されます。 [**メインアイテム**] の横にある省略記号 (**..**) をクリックして、**アイテム エディタ**を開きます。

   1. **[項目タイプ]** **ボタンを**選択した状態で、[**追加**] をクリックしてボタンを追加します。 **キャプション**を`&New`に変更`ID_FILE_NEW`し **、ID**を 、`0`**画像**から`0`、**イメージを 大きい**に変更します。

   1. [**追加**] をクリックしてボタンを追加します。 **キャプション**`&Save`を に変更`ID_FILE_SAVE`し **、ID**を に変更`2`し、**画像**から 、`2`に**大きいイメージ**を に変更します。

   1. [**追加**] をクリックしてボタンを追加します。 **キャプション**`Save &As`を に変更`ID_FILE_SAVE_AS`し **、ID**を に変更`3`し、**画像**から 、`3`に**大きいイメージ**を に変更します。

   1. [**追加**] をクリックしてボタンを追加します。 **キャプション**`&Print`を に変更`ID_FILE_PRINT`し **、ID**を に変更`4`し、**画像**から 、`4`に**大きいイメージ**を に変更します。

   1. **[項目**の種類] を **[区切り記号]** に変更し、[**追加**] をクリックします。

   1. **項目**の種類を **[ ボタン ]** に変更します。 5 番目のボタンを追加するには、[**追加**] をクリックします。 **キャプション**`&Close`を に変更`ID_FILE_CLOSE`し **、ID**を に変更`5`し、**画像**から 、`5`に**大きいイメージ**を に変更します。

1. 次の変更を行うと、前の手順で作成した **[印刷**] ボタンの下にサブメニューが作成されます。

   1. [**印刷**] ボタンをクリックし、[**アイテム**の種類] を **[ラベル**] に変更**します。** **キャプションを**`Preview and print the document`に変更します。

   1. [**印刷**] ボタンをクリックし、[アイテムの種類 **] を** **[ボタン]** に変更して、[**挿入**] をクリックします。 **キャプション**`&Print`を に変更`ID_FILE_PRINT`し **、ID**を に変更`4`し、**画像**から 、`4`に**大きいイメージ**を に変更します。

   1. [**印刷**] ボタンをクリックし、[**挿入**] をクリックしてボタンを追加します。 **キャプション**`&Quick Print`を に変更`ID_FILE_PRINT_DIRECT`し **、ID**を に変更`7`し、**画像**から 、`7`に**大きいイメージ**を に変更します。

   1. [**印刷**] ボタンをクリックし、[**挿入**] をクリックして別のボタンを追加します。 **キャプション**`Print Pre&view`を に変更`ID_FILE_PRINT_PREVIEW`し **、ID**を に変更`6`し、**画像**から 、`6`に**大きいイメージ**を に変更します。

   1. これで、**メイン項目**が変更されました。 [**閉じる**] をクリックして**アイテム エディタ**を終了します。

1. 次の変更により、**アプリケーション**ボタン メニューの下部に表示される終了ボタンが作成されます。

   1. **ソリューション エクスプローラ**の [**リソース ビュー** ] タブを選択します。
   1. [**プロパティ]** ウィンドウで、[**ボタン**] の横にある省略記号 **(.)** をクリックして**アイテム エディタ**を開きます。

   1. **[項目タイプ]** **ボタンを**選択した状態で、[**追加**] をクリックしてボタンを追加します。 **キャプション**を`E&xit`に変更し`ID_APP_EXIT`**、ID**を に変更し、**イメージ**を に変更します`8`。

   1. **ボタン**を変更しました。 [**閉じる**] をクリックして**アイテム エディタ**を終了します。

## <a name="creating-an-instance-of-the-ribbon-bar"></a><a name="createinstance"></a>リボン バーのインスタンスの作成

次の手順では、アプリケーションの起動時にリボン バーのインスタンスを作成する方法を説明します。 リボン バーをアプリケーションに追加するには、mainfrm.h ファイルでリボン バーを宣言します。 次に、mainfrm.cpp ファイルで、リボン リソースを読み込むコードを作成します。

### <a name="to-create-an-instance-of-the-ribbon-bar"></a>リボン バーのインスタンスを作成するには

1. mainfrm.h ファイルで、メイン フレームのクラス定義 `CMainFrame` の保護されたセクションにデータ メンバーを追加します。 このメンバーはリボン バー用です。

    ```cpp
    // Ribbon bar for the application
    CMFCRibbonBar m_wndRibbonBar;
    ```

2. mainfrm.cpp ファイルで、`return` 関数の末尾にある最後の `CMainFrame::OnCreate` ステートメントの前に、次のコードを追加します。 リボン バーのインスタンスを作成します。

    ```cpp
    // Create the ribbon bar
    if (!m_wndRibbonBar.Create(this))
    {
        return -1;   //Failed to create ribbon bar
    }
    m_wndRibbonBar.LoadFromResource(IDR_RIBBON1);
    ```

## <a name="customizing-the-ribbon-resource"></a><a name="addcategory"></a>リボン リソースのカスタマイズ

**アプリケーション**ボタンを作成したので、リボンに要素を追加できます。

> [!NOTE]
> このチュートリアルでは、すべてのパネルで同じパネル アイコンを使用します。 ただし、他のイメージ リスト インデックスを使用して、他のアイコンを表示してもかまいません。

### <a name="to-add-a-home-category-and-edit-panel"></a>[Home] カテゴリと [Edit] パネルを追加するには

1. この Scribble プログラムに必要なカテゴリは 1 つだけです。 デザイン ビューの **[ツールボックス**] で、[**カテゴリ**] をダブルクリックしてカテゴリを追加し、プロパティを表示します。 プロパティ値を次のように変更します**Caption**:`&Home`キャプションを 、 `IDB_RIBBON_HOMELARGE`**大きなイメージ**に 、**小さいイメージ**に`IDB_RIBBON_HOMESMALL`.

1. 各リボン カテゴリは名前付きパネルに整理されます。 各パネルには、関連する操作を完了する一連のコントロールが含まれています。 このカテゴリには 1 つのパネルがあります。 [**パネル**] をクリックし、[`Edit`**キャプション] を**に変更します。

1. **編集**パネルに、ドキュメントの内容をクリアするボタンを追加します。 このボタンのメッセージ ID は、メニュー リソース`IDR_SCRIBBTYPE`で既に定義されています。 ボタン`Clear All`テキストとボタンを装飾するビットマップのインデックスとして指定します。 **ツールボックス**を開き、**ボタン**を**編集**パネルにドラッグします。 ボタンをクリックし、[**キャプション**]`Clear All`を [、ID]`0`を`ID_EDIT_CLEAR_ALL`[**画像インデックス**] を 、[**大きなイメージ インデックス**] に変更します`0`。 **ID**

1. 変更内容を保存し、アプリケーションをビルドして実行します。 Scribble アプリケーションが起動されますが、ウィンドウ最上部にはメニュー バーではなく、リボンが表示されます。 リボン バーには 、[**ホーム]** というカテゴリが 1 つ、**および [ホーム**] パネルが 1 つ必要**です。** 追加したリボン ボタンは既存のイベント ハンドラに関連付けられており、[**開く**]、[**閉じる**]、[**保存**]、[**印刷**]、[**すべてクリア**] の各ボタンが正しく動作します。

## <a name="setting-the-look-of-the-application"></a><a name="setlook"></a>アプリケーションの外観の設定

*ビジュアル マネージャー*は、アプリケーションのすべての描画を制御するグローバル オブジェクトです。 元の Scribble アプリケーションは Office 2000 のユーザー インターフェイス (UI) スタイルを使用しているため、このアプリケーションの外観は古めかしく感じられるかもしれません。 このアプリケーションは、Office 2007 のビジュアル マネージャーを使用するようにリセットして、Office 2007 のような外観にすることができます。

### <a name="to-set-the-look-of-the-application"></a>アプリケーションの外観を設定するには

1. 関数で`CMainFrame::OnCreate`、ステートメントの前に次のコード`return 0;`を入力して、既定のビジュアル マネージャーとスタイルを変更します。

    ```cpp
    // Set the default manager to Office 2007
    CMFCVisualManager::SetDefaultManager(RUNTIME_CLASS(CMFCVisualManagerOffice2007));
    CMFCVisualManagerOffice2007::SetStyle(CMFCVisualManagerOffice2007::Office2007_LunaBlue);
    ```

1. 変更内容を保存し、アプリケーションをビルドして実行します。 アプリケーションの UI が Office 2007 と類似した UI になります。

## <a name="next-steps"></a>次の手順

従来の Scribble 1.0 MFC サンプルを変更して **、リボン デザイナー**を使用しました。 次に[、パート 2](../mfc/walkthrough-updating-the-mfc-scribble-application-part-2.md)に進む。

## <a name="see-also"></a>関連項目

[チュートリアル](../mfc/walkthroughs-mfc.md)<br/>
[チュートリアル: MFC Scribble アプリケーションの更新 (パート 2)](../mfc/walkthrough-updating-the-mfc-scribble-application-part-2.md)

---
title: 'チュートリアル: MFC Scribble アプリケーション (パート 1) の更新 |Microsoft Docs'
ms.custom: ''
ms.date: 09/20/2018
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- examples [MFC], update existing application
- ribbon UI, porting to
- Office Fluent UI, porting to
- samples [MFC], update existing application
- MFC Feature Pack, update existing application
- walkthroughs [MFC], update existing application
ms.assetid: aa6330d3-6cfc-4c79-8fcb-0282263025f7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3daa42008bd385b2d45d05106162c99fb9ca0b12
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/25/2018
ms.locfileid: "50082880"
---
# <a name="walkthrough-updating-the-mfc-scribble-application-part-1"></a>チュートリアル: MFC Scribble アプリケーション (パート 1) の更新

このチュートリアルでは、リボン ユーザー インターフェイスを使用するために MFC アプリケーションを修正する方法を説明します。 Visual Studio は、Office 2007 リボンと Windows 7 Scenic リボンの両方をサポートしています。 リボンのユーザー インターフェイスの詳細については、次を参照してください。[リボン](/windows/desktop/uxguide/cmd-ribbons)します。

このチュートリアルでは、マウスを使用して線画を描く、従来の Scribble 1.0 MFC サンプルを変更します。 ここでは、リボン バーを表示するよう Scribble サンプルを変更します。 [第 2 部](../mfc/walkthrough-updating-the-mfc-scribble-application-part-2.md)リボン バーにボタンを追加します。

## <a name="prerequisites"></a>必須コンポーネント

[Scribble 1.0 MFC サンプル](http://download.microsoft.com/download/4/0/9/40946FEC-EE5C-48C2-8750-B0F8DA1C99A8/MFC/general/Scribble.zip.exe)します。 Visual Studio 2017 に変換する方法については、次を参照してください。[移植のガイド: MFC Scribble](../porting/porting-guide-mfc-scribble.md)します。

##  <a name="top"></a> セクション

このパートは、次のセクションで構成されています。

- [基底クラスの置き換え](#replaceclass)

- [ビットマップをプロジェクトに追加します。](#addbitmap)

- [プロジェクトにリボン リソースを追加します。](#addribbon)

- [リボン バーのインスタンスを作成します。](#createinstance)

- [リボン カテゴリを追加します。](#addcategory)

- [アプリケーションの外観の設定](#setlook)

##  <a name="replaceclass"></a> 基底クラスの置き換え

メニュー ベースのアプリケーションをリボン ベースのアプリケーションに変換するには、アプリケーション、フレーム ウィンドウ、ツール バーの各クラスを、更新された基底クラスから派生させる必要があります  (元の Scribble サンプルを変更しないことが推奨されます。 代わりに、Scribble プロジェクトをクリーンアップ、別のディレクトリにコピーし、変更、コピー。)

### <a name="to-replace-the-base-classes-in-the-scribble-application"></a>Scribble アプリケーションの基底クラスを置き換えるには

1. Scribble.cpp で、ことを確認します`CScribbleApp::InitInstance`への呼び出しが含まれています[AfxOleInit](../mfc/reference/ole-initialization.md#afxoleinit)します。

1. stdafx.h ファイルに次のコードを追加します。

    ```cpp
    #include <afxcontrolbars.h>
    ```

1. Scribble.h での定義を変更、`CScribbleApp`クラスから派生されるように[CWinAppEx クラス](../mfc/reference/cwinappex-class.md)します。

    ```cpp
    class CScribbleApp: public CWinAppEx
    ```

1. Scribble 1.0 は、Windows アプリケーションが初期化 (.ini) ファイルを使用してユーザー設定のデータを保存したときに書き込まれています。 初期化ファイルは変更せず、Scribble を変更してユーザー設定をレジストリに格納します。 レジストリ キーとベースを設定するには、次のコードを、`CScribbleApp::InitInstance` ステートメントの後ろの `LoadStdProfileSettings()` に含めます。

    ```cpp
    SetRegistryKey(_T("MFCNext\\Samples\\Scribble2"));
    SetRegistryBase(_T("Settings"));
    ```

1. マルチ ドキュメント インターフェイス (MDI) アプリケーション用のメイン フレームはもう `CMDIFrameWnd` クラスから派生しません。 派生される代わりに、 [CMDIFrameWndEx](../mfc/reference/cmdiframewndex-class.md)クラス。

    mainfrm.h ファイルと mainfrm.cpp ファイルで、`CMDIFrameWnd` への参照をすべて、`CMDIFrameWndEx` への参照に置き換えます。

1. childfrm.h ファイルと childfrm.cpp ファイルで、`CMDIChildWnd` を `CMDIChildWndEx` に置き換えます。

    で childfrm です。 h ファイルは、置き換える`CSplitterWnd`で`CSplitterWndEx`します。

1. ツール バーとステータス バーを変更して、新しい MFC クラスを使用します。

    mainfrm.h ファイルでは、次の手順に従います。

    1. `CToolBar` を `CMFCToolBar`に置き換えます。

    1. `CStatusBar` を `CMFCStatusBar`に置き換えます。

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

##  <a name="addbitmap"></a> ビットマップをプロジェクトに追加します。

このチュートリアルの次の 4 つの手順には、ビットマップ リソースが必要です。 さまざまな方法では、適切なビットマップを取得できます。

- 使用して、[リソース エディター](../windows/resource-editors.md)独自のビットマップを作成します。 リソース エディターを使用して、Visual Studio に含まれておりからダウンロードできるポータブル ネットワーク グラフィックス (.png) イメージからビットマップを作成するか、 [Visual Studio image library](https://docs.microsoft.com/visualstudio/designers/the-visual-studio-image-library)します。

    ただし、**リボン**ユーザー インターフェイスでは、特定のビットマップが透明なイメージをサポートする必要があります。 透明なビットマップを使用して、32 ビット (ピクセル単位)、24 ビット カラーの赤、緑、および青のコンポーネントを指定して、残りの 8 ビット、*アルファ チャネル*色の透明度を指定します。 現在のリソース エディターでは、32 ビット ピクセルのビットマップを表示できますが、変更できません。 そのため、透明なビットマップを作成する場合は、リソース エディターではなく、外部のイメージ エディターを使用します。

- 適切なリソース ファイルを別のアプリケーションからプロジェクトにコピーし、そのファイルからビットマップをインポートします。

このチュートリアルでは、リソース ファイルをコピーで作成された例から[チュートリアル: リボン アプリケーションで使用して MFC を作成する](../mfc/walkthrough-creating-a-ribbon-application-by-using-mfc.md)します。

### <a name="to-add-bitmaps-to-the-project"></a>ビットマップをプロジェクトに追加するには

1. ファイル エクスプ ローラーを使用して、リソースのディレクトリから次の .bmp ファイルをコピーする (`res`) のリソース ディレクトリにリボン例では、(`res`) の Scribble プロジェクト。

   1. main.bmp を Scribble プロジェクトにコピーします。

   1. filesmall.bmp と filelarge.bmp を Scribble プロジェクトにコピーします。

   1. Filelarge.bmp ファイルと filesmall.bmp ファイルの新しいコピーを作成しますが、リボンの例では、コピーを保存します。 homesmall.bmp と homelarge.bmp のコピーの名前を変更し、それらを Scribble プロジェクトに移動します。

   1. Toolbar.bmp ファイルのコピーを作成しますが、リボンの例では、コピーを保存します。 panelicons.bmp のコピーの名前を変更し、それを Scribble プロジェクトに移動します。

1. MFC アプリケーション用のビットマップをインポートします。 **リソース ビュー**をダブルクリック、 **[scribble.rc]** ノードをダブルクリック、**ビットマップ**ノードをクリック**リソースを追加**。 ダイアログ ボックスが表示されますが、をクリックして**インポート**します。 参照、`res`ディレクトリ、main.bmp ファイルを選択およびクリックして**オープン**します。

   main.bmp ビットマップには、26 × 26 イメージが含まれています。 ビットマップの ID を変更`IDB_RIBBON_MAIN`します。

1. 関連付けられているファイル メニューのビットマップをインポート、**アプリケーション**ボタンをクリックします。

   1. 11 個の 16 x 16 (16 x 176) を含む filesmall.bmp ファイルをインポートするイメージ。 ビットマップの ID を変更`IDB_RIBBON_FILESMALL`します。

   > [!NOTE]
   > 最初の 8 つの 16 x 16 イメージ (16 × 128) のみ、必要なため、必要に応じて 128 176 からは、このビットマップの右側の幅をトリミングすることがあります。

   1. 9 つの 32 x 32 (32 x 288) を含む、filelarge.bmp をインポートするイメージ。 ビットマップの ID を変更`IDB_RIBBON_FILELARGE`します。

1. リボンのカテゴリとパネル用のビットマップをインポートします。 リボン バーの各タブはカテゴリであり、テキスト ラベルと省略可能なイメージで構成されます。

   1. 11 個の 16 × 16 イメージ小さいボタン用含まれて homesmall.bmp ビットマップをインポートします。 ビットマップの ID を変更`IDB_RIBBON_HOMESMALL`します。

   1. 9 つの 32 倍大きいボタン用の 32 のイメージを含む homelarge.bmp ビットマップをインポートします。 ビットマップの ID を変更`IDB_RIBBON_HOMELARGE`します。

1. サイズが変更されたリボン パネル用のビットマップをインポートします。 このビットマップ、つまりパネル アイコンは、リボンが小さすぎてパネル全体を表示できない場合に、サイズ変更操作後に使用されます。

   1. panelicons.bmp をインポートします。このファイルには 16 × 16 イメージが 8 個含まれています。 **プロパティ**のウィンドウ、**ビットマップ エディター**64 (16 × 64) にビットマップの幅を調整します。 ビットマップの ID を変更`IDB_PANEL_ICONS`します。

   > [!NOTE]
   > 最初の 4 つの 16 x 16 イメージ (16 × 64) のみ、必要なため、必要に応じて、右側にあるビットマップの幅この 128 から 64 をトリミングすることがあります。

##  <a name="addribbon"></a> プロジェクトにリボン リソースを追加します。

リボンを使用するアプリケーションにメニューを使用するアプリケーションを変換するときに、削除または既存のメニューを無効にする必要はありません。 リボン リソースを作成し、リボン ボタンを追加し、新しいボタンを既存のメニュー項目に関連付けます。 メニューは表示されませんが、メニューから、リボン バーからのメッセージのルーティングし、 メニューのショートカットは引き続き機能します。

リボンから成る、**アプリケーション**リボンの左上隅にある大きいボタンには、ボタンと 1 つまたは複数のカテゴリ タブ。 各カテゴリ タブは、1 つまたは複数のパネルで構成されます。パネルは、リボンのボタンやコントロールのコンテナーの役割を果たします。 次の手順は、リボン リソースを作成し、カスタマイズする方法を示しています、**アプリケーション**ボタンをクリックします。

### <a name="to-add-a-ribbon-resource-to-the-project"></a>リボン リソースをプロジェクトに追加するには

1. 選択された Scribble プロジェクト**ソリューション エクスプ ローラー**の**プロジェクト** メニューのをクリックして**リソースの追加**します。

1. **リソースの追加**ダイアログ ボックスで、**リボン** をクリックし、**新規**します。

   Visual Studio でリボン リソースが作成され、デザイン ビューで開かれます。 リボン リソース ID は`IDR_RIBBON1`に表示される**リソース ビュー**します。 リボンには、1 つのカテゴリと 1 つのパネルがあります。

1. カスタマイズすることができます、**アプリケーション**そのプロパティを変更してボタンをクリックします。 このコードで使用されているメッセージ ID は、Scribble 1.0 用のメニューで定義済みです。

1. デザイン ビューでクリックして、**アプリケーション**プロパティを表示するボタンをクリックします。 プロパティ値を次のように変更:**イメージ**に`IDB_RIBBON_MAIN`、**プロンプト**に`File`、**キー**に`f`、 **Large Images**に`IDB_RIBBON_FILELARGE`、および**Small Images**に`IDB_RIBBON_FILESMALL`します。

1. 次の変更は、ユーザーがクリックしたときに表示されるメニューを作成、**アプリケーション**ボタンをクリックします。 省略記号をクリックします (**.**) 横に**Main Items**を開く、**項目エディター**します。

   1. **項目**型**ボタン**選択されていること、**追加**ボタンを追加します。 変更**キャプション**に`&New`、 **ID**に`ID_FILE_NEW`、**イメージ**に`0`、**大きいイメージ**に`0`.

   1. クリックして**追加**ボタンを追加します。 変更**キャプション**に`&Save`、 **ID**に`ID_FILE_SAVE`、**イメージ**に`2`、および**大きいイメージ**に`2`.

   1. クリックして**追加**ボタンを追加します。 変更**キャプション**に`Save &As`、 **ID**に`ID_FILE_SAVE_AS`、**イメージ**に`3`、および**大きいイメージ**に`3`.

   1. クリックして**追加**ボタンを追加します。 変更**キャプション**に`&Print`、 **ID**に`ID_FILE_PRINT`、**イメージ**に`4`、および**大きいイメージ**に`4`.

   1. 変更、**項目**型**区切り**順にクリックします**追加**します。

   1. 変更、**項目**型**ボタン**します。 クリックして**追加**5 番目のボタンを追加します。 変更**キャプション**に`&Close`、 **ID**に`ID_FILE_CLOSE`、**イメージ**に`5`、および**大きいイメージ**に`5`.

1. 次の変更は、下のサブメニューを作成、**印刷**前の手順で作成したボタンをクリックします。

   1. をクリックして、**印刷** ボタンを変更、**項目**型**ラベル**、順にクリックします**挿入**。 変更**キャプション**に`Preview and print the document`します。

   1. をクリックして、**印刷** ボタンを変更、**項目**型**ボタン**、 をクリック**挿入**。 変更**キャプション**に`&Print`、 **ID**に`ID_FILE_PRINT`、**イメージ**に`4`、および**大きいイメージ**に`4`.

   1. をクリックして、**印刷**ボタンをクリックし、をクリックし、**挿入**ボタンを追加します。 変更**キャプション**に`&Quick Print`、 **ID**に`ID_FILE_PRINT_DIRECT`、**イメージ**に`7`、および**大きいイメージ**に`7`.

   1. をクリックして、**印刷**ボタンをクリックし、をクリックし、**挿入**もう 1 つのボタンを追加します。 変更**キャプション**に`Print Pre&view`、 **ID**に`ID_FILE_PRINT_PREVIEW`、**イメージ**に`6`、および**大きいイメージ**に`6`.

   1. 変更したようになりました、 **Main Items**します。 クリックして**閉じる**を終了する、**項目エディター**します。

1. 次の変更の下部に表示される終了ボタンを作成し、**アプリケーション** ボタン メニュー。

   1. **プロパティ**ウィンドウで、省略記号をクリックします (**.**) 横に**ボタン**を開く、**項目エディター**します。

   1. **項目**型**ボタン**選択されていること、**追加**ボタンを追加します。 変更**キャプション**に`E&xit`、 **ID**に`ID_APP_EXIT`、**イメージ**に`8`します。

   1. 変更した、**ボタン**します。 クリックして**閉じる**を終了する、**項目エディター**します。

##  <a name="createinstance"></a> リボン バーのインスタンスを作成します。

次の手順では、アプリケーションの起動時にリボン バーのインスタンスを作成する方法を説明します。 リボン バーをアプリケーションに追加するには、mainfrm.h ファイルでリボン バーを宣言します。 次に、mainfrm.cpp ファイルで、リボン リソースを読み込むコードを作成します。

### <a name="to-create-an-instance-of-the-ribbon-bar"></a>リボン バーのインスタンスを作成するには

1. mainfrm.h ファイルで、メイン フレームのクラス定義 `CMainFrame` の保護されたセクションにデータ メンバーを追加します。 このメンバーは、リボン バーのです。

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

##  <a name="addcategory"></a> リボン リソースのカスタマイズ

作成したので、**アプリケーション** ボタンをリボンに要素を追加することができます。

> [!NOTE]
> このチュートリアルでは、すべてのパネルで同じパネル アイコンを使用します。 ただし、他のイメージ リスト インデックスを使用して、他のアイコンを表示してもかまいません。

### <a name="to-add-a-home-category-and-edit-panel"></a>[Home] カテゴリと [Edit] パネルを追加するには

1. この Scribble プログラムに必要なカテゴリは 1 つだけです。 デザイン ビューでの**ツールボックス**、 をダブルクリックします**カテゴリ**を 1 つ追加してそのプロパティを表示します。 プロパティ値を次のように変更:**キャプション**に`&Home`、 **Large Images**に`IDB_RIBBON_HOMELARGE`、 **Small Images**に`IDB_RIBBON_HOMESMALL`します。

1. 各リボン カテゴリは名前付きパネルに整理されます。 各パネルには、関連する操作完了するには一連コントロールにはが含まれています。 このカテゴリには 1 つのパネルがあります。 クリックして**パネル**、し、変更**キャプション**に`Edit`します。

1. **編集**パネルで、[追加] ボタン、ドキュメントの内容を消去する責任を負います。 このボタンは、メッセージ ID は既に定義されて、`IDR_SCRIBBTYPE`メニュー リソース。 指定`Clear All`ボタンのテキストとボタンを装飾するビットマップのインデックス。 開く、**ツールボックス**、し、ドラッグ、**ボタン**を**編集**パネル。 ボタンをクリックし、変更**キャプション**に`Clear All`、 **ID**に`ID_EDIT_CLEAR_ALL`、**イメージ インデックス**に`0`、 **Large Image Index**に`0`します。

1. 変更内容を保存し、アプリケーションをビルドして実行します。 Scribble アプリケーションが起動されますが、ウィンドウ最上部にはメニュー バーではなく、リボンが表示されます。 リボン バーは、1 つのカテゴリにあります**ホーム**、および**ホーム**1 つのパネルがあります。**編集**します。 追加したリボンのボタンは、既存のイベント ハンドラーを関連付ける必要があります、**オープン**、**閉じる**、**保存**、**印刷**、**すべてクリア**のボタンは期待どおりに機能する必要があります。

##  <a name="setlook"></a> アプリケーションの外観の設定

A*ビジュアル マネージャー*はアプリケーションのすべての描画を制御するグローバル オブジェクトです。 元の Scribble アプリケーションは Office 2000 のユーザー インターフェイス (UI) スタイルを使用しているため、このアプリケーションの外観は古めかしく感じられるかもしれません。 このアプリケーションは、Office 2007 のビジュアル マネージャーを使用するようにリセットして、Office 2007 のような外観にすることができます。

### <a name="to-set-the-look-of-the-application"></a>アプリケーションの外観を設定するには

1. `CMainFrame::OnCreate`関数を入力する前に、次のコード、`return 0;`既定のビジュアル マネージャーとスタイルを変更するステートメント。

    ```cpp
    // Set the default manager to Office 2007
    CMFCVisualManager::SetDefaultManager(RUNTIME_CLASS(CMFCVisualManagerOffice2007));
    CMFCVisualManagerOffice2007::SetStyle(CMFCVisualManagerOffice2007::Office2007_LunaBlue);
    ```

1. 変更内容を保存し、アプリケーションをビルドして実行します。 アプリケーションの UI が Office 2007 と類似した UI になります。

## <a name="next-steps"></a>次の手順

使用する従来の Scribble 1.0 MFC サンプルを変更した、**リボン デザイナー**します。 次に「[第 2 部](../mfc/walkthrough-updating-the-mfc-scribble-application-part-2.md)します。

## <a name="see-also"></a>関連項目

[チュートリアル](../mfc/walkthroughs-mfc.md)<br/>
[チュートリアル: MFC Scribble アプリケーションの更新 (パート 2)](../mfc/walkthrough-updating-the-mfc-scribble-application-part-2.md)

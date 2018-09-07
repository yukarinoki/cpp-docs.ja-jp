---
title: 'チュートリアル: MFC Scribble アプリケーション (パート 1) の更新 |Microsoft Docs'
ms.custom: ''
ms.date: 06/28/2018
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
ms.openlocfilehash: ce50d2c70107b4c88f223e32fdd8cc083df38840
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/04/2018
ms.locfileid: "43685546"
---
# <a name="walkthrough-updating-the-mfc-scribble-application-part-1"></a>チュートリアル: MFC Scribble アプリケーション (パート 1) の更新

このチュートリアルでは、リボン ユーザー インターフェイスを使用するために MFC アプリケーションを修正する方法を説明します。 Visual Studio は、Office 2007 リボンと Windows 7 Scenic リボンの両方をサポートしています。 リボンのユーザー インターフェイスの詳細については、次を参照してください。[リボン](/windows/desktop/uxguide/cmd-ribbons)します。

このチュートリアルでは、マウスを使用して線画を描く、従来の Scribble 1.0 MFC サンプルを変更します。 ここでは、リボン バーを表示するよう Scribble サンプルを変更します。 [第 2 部](../mfc/walkthrough-updating-the-mfc-scribble-application-part-2.md)リボン バーにボタンを追加します。

## <a name="prerequisites"></a>必須コンポーネント

[Visual C++ のサンプル](../visual-cpp-samples.md)

[Visual C++ のサンプル](../visual-cpp-samples.md)

##  <a name="top"></a> セクション

このパートは、次のセクションで構成されています。

- [基底クラスの置き換え](#replaceclass)

- [ビットマップをプロジェクトに追加します。](#addbitmap)

- [プロジェクトにリボン リソースを追加します。](#addribbon)

- [リボン バーのインスタンスを作成します。](#createinstance)

- [リボン カテゴリを追加します。](#addcategory)

- [アプリケーションの外観の設定](#setlook)

##  <a name="replaceclass"></a> 基底クラスの置き換え

メニュー ベースのアプリケーションをリボン ベースのアプリケーションに変換するには、アプリケーション、フレーム ウィンドウ、ツール バーの各クラスを、更新された基底クラスから派生させる必要があります  (元の Scribble サンプルは変更せず、Scribble プロジェクトをクリーンアップし、別のディレクトリにコピーして、そのコピーを変更することをお勧めします)。

### <a name="to-replace-the-base-classes-in-the-scribble-application"></a>Scribble アプリケーションの基底クラスを置き換えるには

1. Scribble.cpp で、ことを確認します`CScribbleApp::InitInstance`への呼び出しが含まれています[AfxOleInit](../mfc/reference/ole-initialization.md#afxoleinit)します。

2. stdafx.h ファイルに次のコードを追加します。

    ```cpp
    #include <afxcontrolbars.h>
    ```

3. Scribble.h での定義を変更、`CScribbleApp`クラスから派生されるように[CWinAppEx クラス](../mfc/reference/cwinappex-class.md)します。

    ```cpp
    class CScribbleApp: public CWinAppEx
    ```

4. Scribble 1.0 は、Windows アプリケーションが初期化 (.ini) ファイルを使用してユーザー設定のデータを保存したときに書き込まれています。 初期化ファイルは変更せず、Scribble を変更してユーザー設定をレジストリに格納します。 レジストリ キーとベースを設定するには、次のコードを、`CScribbleApp::InitInstance` ステートメントの後ろの `LoadStdProfileSettings()` に含めます。

    ```cpp
    SetRegistryKey(_T("MFCNext\\Samples\\Scribble2"));
    SetRegistryBase(_T("Settings"));
    ```

5. マルチ ドキュメント インターフェイス (MDI) アプリケーション用のメイン フレームはもう `CMDIFrameWnd` クラスから派生しません。 派生される代わりに、 [CMDIFrameWndEx](../mfc/reference/cmdiframewndex-class.md)クラス。

     mainfrm.h ファイルと mainfrm.cpp ファイルで、`CMDIFrameWnd` への参照をすべて、`CMDIFrameWndEx` への参照に置き換えます。

6. childfrm.h ファイルと childfrm.cpp ファイルで、`CMDIChildWnd` を `CMDIChildWndEx` に置き換えます。

     で childfrm です。 h ファイルは、置き換える`CSplitterWnd`で`CSplitterWndEx`します。

7. ツール バーとステータス バーを変更して、新しい MFC クラスを使用します。

     mainfrm.h ファイルでは、次の手順に従います。

    1. `CToolBar` を `CMFCToolBar` に置き換えます。

    2. `CStatusBar` を `CMFCStatusBar` に置き換えます。

8. mainfrm.cpp ファイルでは、次の手順に従います。

    1. `m_wndToolBar.SetBarStyle` を `m_wndToolBar.SetPaneStyle` に置き換えます。

    2. `m_wndToolBar.GetBarStyle` を `m_wndToolBar.GetPaneStyle` に置き換えます。

    3. `DockControlBar(&m_wndToolBar)` を `DockPane(&m_wndToolBar)` に置き換えます。

9. ipframe.cpp ファイルでは、コードの次の 3 行をコメント アウトします。

    ```cpp
    m_wndToolBar.EnableDocking(CBRS_ALIGN_ANY);
    pWndFrame->EnableDocking(CBRS_ALIGN_ANY);
    pWndFrame->DockPane(&m_wndToolBar);
    ```

10. アプリケーションを静的にリンクする場合は、プロジェクトのリソース (.rc) ファイルの先頭に次のコードを追加します。

    ```cpp
    #include "afxribbon.rc"
    ```

     afxribbon.rc ファイルには、実行時に必要とされるリソースが含まれています。 [MFC アプリケーション ウィザード](../mfc/reference/mfc-application-wizard.md)アプリケーションを作成するときに、このファイルを自動的に含まれます。

11. 変更を保存し、アプリケーションをビルドして実行します。

[[セクション](#top)]

##  <a name="addbitmap"></a> ビットマップをプロジェクトに追加します。

このチュートリアルの次の 4 つの手順には、ビットマップ リソースが必要です。 適切なビットマップをさまざまな方法で取得できます。

- 使用して、[リソース エディター](../windows/resource-editors.md)独自のビットマップを作成します。 または、Visual Studio に含まれているポータブル ネットワーク グラフィックス (.png) イメージからビットマップを作成するリソース エディターを使用します。 これらのイメージはでは、`VS2008ImageLibrary`ディレクトリ。

     ただし、リボン ユーザー インターフェイスでは、特定のビットマップが透明なイメージをサポートしている必要があります。 透明なビットマップを使用して、32 ビット (ピクセル単位)、24 ビット カラーの赤、緑、および青のコンポーネントを指定して、残りの 8 ビット、*アルファ チャネル*色の透明度を指定します。 現在のリソース エディターでは、32 ビット ピクセルのビットマップを表示できますが、変更できません。 そのため、透明なビットマップを作成する場合は、リソース エディターではなく、外部のイメージ エディターを使用します。

- 適切なリソース ファイルを別のアプリケーションからプロジェクトにコピーし、そのファイルからビットマップをインポートします。

このチュートリアルでは、Samples ディレクトリにあるアプリケーションからリソース ファイルをコピーします。

### <a name="to-add-bitmaps-to-the-project"></a>ビットマップをプロジェクトに追加するには

1. ファイル エクスプローラーを使用して、RibbonGadgets サンプルのリソース ディレクトリ (`res`) から次の .bmp ファイルをコピーします。

   1. main.bmp を Scribble プロジェクトにコピーします。

   2. filesmall.bmp と filelarge.bmp を Scribble プロジェクトにコピーします。

   3. filelarge.bmp ファイルと filesmall.bmp ファイルの新しいコピーを作成します。このとき、コピーは RibbonGadgets サンプルに保存します。 homesmall.bmp と homelarge.bmp のコピーの名前を変更し、それらを Scribble プロジェクトに移動します。

   4. toolbar.bmp ファイルのコピーを作成します。このとき、コピーを RibbonGadgets サンプルに保存します。 panelicons.bmp のコピーの名前を変更し、それを Scribble プロジェクトに移動します。

2. MFC アプリケーション用のビットマップをインポートします。 **リソース ビュー**をダブルクリック、 **[scribble.rc]** ノードをダブルクリック、**ビットマップ**ノードをクリック**リソースを追加**。 ダイアログ ボックスが表示されますが、をクリックして**インポート**します。 参照、`res`ディレクトリ、main.bmp ファイルを選択およびクリックして**オープン**します。

   main.bmp ビットマップには、26 × 26 イメージが含まれています。 ビットマップの ID を IDB_RIBBON_MAIN に変更します。

3. アプリケーション ボタンにアタッチされるファイル メニュー用のビットマップをインポートします。

   1. filesmall.bmp ファイルをインポートします。このファイルには 16 × 16 イメージが 10 個 (16 × 160) 含まれています。 8 個の 16 x 16 イメージ (16 × 128)、必要なために、使用、**リソース ビュー**ビットマップの幅を 160 から 128 に変更します。 ビットマップの ID を IDB_RIBBON_FILESMALL に変更します。

   2. filelarge.bmp をインポートします。このファイルには 32 × 32 イメージが 8 個 (32 × 256) 含まれています。 ビットマップの ID を IDB_RIBBON_FILELARGE に変更します。

4. リボンのカテゴリとパネル用のビットマップをインポートします。 リボン バーの各タブはカテゴリであり、テキスト ラベルと省略可能なイメージで構成されます。

   1. homesmall.bmp ビットマップをインポートします。このファイルには、小さいボタン用の 16 × 16 イメージが 8 個含まれています。 ビットマップの ID を IDB_RIBBON_HOMESMALL に変更します。

   2. homelarge.bmp ビットマップをインポートします。このファイルには、大きいボタン用の 32 × 32 イメージが 8 個含まれています。 ビットマップの ID を IDB_RIBBON_HOMELARGE に変更します。

5. サイズが変更されたリボン パネル用のビットマップをインポートします。 このビットマップ、つまりパネル アイコンは、リボンが小さすぎてパネル全体を表示できない場合に、サイズ変更操作後に使用されます。

   1. panelicons.bmp をインポートします。このファイルには 16 × 16 イメージが 8 個含まれています。 **プロパティ**のウィンドウ、**ビットマップ エディター**64 (16 × 64) にビットマップの幅を調整します。 ビットマップの ID を IDB_PANEL_ICONS に変更します。

[[セクション](#top)]

##  <a name="addribbon"></a> プロジェクトにリボン リソースを追加します。

メニューを使用するアプリケーションを、リボンを使用するアプリケーションに変更する場合は、既存のメニューを削除する必要も、無効にする必要もありません。 代わりに、リボン リソースを作成し、リボン ボタンを追加し、新しいボタンをメニュー項目と関連付けます。 メニューは表示されなくなりますが、リボン バーからのメッセージはメニュー経由で送られます。 また、メニューのショートカットは引き続き機能します。

リボンはアプリケーション ボタンと 1 つ以上のカテゴリ タブで構成されます。アプリケーション ボタンは、リボンの左上にある大きいボタンです。 各カテゴリ タブは、1 つまたは複数のパネルで構成されます。パネルは、リボンのボタンやコントロールのコンテナーの役割を果たします。 次の手順では、リボン リソースを作成して、アプリケーション ボタンをカスタマイズする方法を説明します。

### <a name="to-add-a-ribbon-resource-to-the-project"></a>リボン リソースをプロジェクトに追加するには

1. **プロジェクト** メニューのをクリックして**リソースの追加**します。

2. **リソースの追加**ダイアログ ボックスで、**リボン** をクリックし、**新規**します。

   Visual Studio でリボン リソースが作成され、デザイン ビューで開かれます。 リボン リソース ID に表示される IDR_RIBBON1**リソース ビュー**します。 リボンには、1 つのカテゴリと 1 つのパネルがあります。

3. アプリケーション ボタンのカスタマイズは、そのプロパティを修正して行います。 このコードで使用されているメッセージ ID は、Scribble 1.0 用のメニューで定義済みです。

4. デザイン ビューでアプリケーション ボタンをクリックして、そのプロパティを表示します。 プロパティ値を次のように変更:**イメージ**に`IDB_RIBBON_MAIN`、**プロンプト**に`File`、**キー**に`f`、 **Large Images**に`IDB_RIBBON_FILELARGE`、および**Small Images**に`IDB_RIBBON_FILESMALL`します。

5. 次の修正を行い、ユーザーがアプリケーション ボタンをクリックしたときに表示されるメニューを作成します。 省略記号をクリックします (**.**) 横に**Main Items**を開く、**項目エディター**します。

   1. クリックして**追加**ボタンを追加します。 変更**キャプション**に`&New`、 **ID**に`ID_FILE_NEW`、**イメージ**に`0`、**大きいイメージ**に`0`.

   2. クリックして**追加**2 番目のボタンを追加します。 変更**キャプション**に`&Save`、 **ID**に`ID_FILE_SAVE`、**イメージ**に`2`、および**大きいイメージ**に`2`.

   3. クリックして**追加**3 番目のボタンを追加します。 変更**キャプション**に`Save &As`、 **ID**に`ID_FILE_SAVE_AS`、**イメージ**に`3`、および**大きいイメージ**に`3`.

   4. クリックして**追加**4 番目のボタンを追加します。 変更**キャプション**に`&Print`、 **ID**に`ID_FILE_PRINT`、**イメージ**に`4`、および**大きいイメージ**に`4`.

   5. 変更、**項目**型**区切り**順にクリックします**追加**します。

   6. 変更、**項目**型**ボタン**します。 クリックして**追加**5 番目のボタンを追加します。 変更**キャプション**に`&Close`、 **ID**に`ID_FILE_CLOSE`、**イメージ**に`5`、および**大きいイメージ**に`5`.

6. 次の修正を行い、前の手順で作成した [印刷] ボタンにサブメニューを作成します。

   1. をクリックして、**印刷** ボタンを変更、**項目**型**ラベル**、順にクリックします**挿入**。 変更**キャプション**に`Preview and print the document`します。

   2. をクリックして、**印刷** ボタンを変更、**項目**型**ボタン**、 をクリック**挿入**。 変更**キャプション**に`&Print`、 **ID**に`ID_FILE_PRINT`、**イメージ**に`4`、および**大きいイメージ**に`4`.

   3. をクリックして、**印刷**ボタンをクリックし、をクリックし、**挿入**ボタンを追加します。 変更**キャプション**に`&Quick Print`、 **ID**に`ID_FILE_PRINT_DIRECT`、**イメージ**に`7`、および**大きいイメージ**に`7`.

   4. をクリックして、**印刷**ボタンをクリックし、をクリックし、**挿入**もう 1 つのボタンを追加します。 変更**キャプション**に`Print Pre&view`、 **ID**に`ID_FILE_PRINT_PREVIEW`、**イメージ**に`6`、および**大きいイメージ**に`6`.

   5. 修正できました、 **Main Items**します。 クリックして**閉じる**を終了する、**項目エディター**します。

7. 次の修正を行い、アプリケーション ボタン メニューの下部に表示される終了ボタンを作成します。

   1. **プロパティ**ウィンドウで、省略記号をクリックします (**.**) 横に**ボタン**を開く、**項目エディター**します。

   2. クリックして**追加**ボタンを追加します。 変更**キャプション**に`E&xit`、 **ID**に`ID_APP_EXIT`、**イメージ**に`8`します。

[[セクション](#top)]

##  <a name="createinstance"></a> リボン バーのインスタンスを作成します。

次の手順では、アプリケーションの起動時にリボン バーのインスタンスを作成する方法を説明します。 リボン バーをアプリケーションに追加するには、mainfrm.h ファイルでリボン バーを宣言します。 次に、mainfrm.cpp ファイルで、リボン リソースを読み込むコードを作成します。

### <a name="to-create-an-instance-of-the-ribbon-bar"></a>リボン バーのインスタンスを作成するには

1. mainfrm.h ファイルで、メイン フレームのクラス定義 `CMainFrame` の保護されたセクションにデータ メンバーを追加します。 このメンバーはリボン バーを表します。

    ```cpp
    // Ribbon bar for the application
    CMFCRibbonBar m_wndRibbonBar;
    ```

2. mainfrm.cpp ファイルで、`return` 関数の末尾にある最後の `CMainFrame::OnCreate` ステートメントの前に、次のコードを追加します。 このコードは、リボン バーのインスタンスを作成します。

    ```cpp
    // Create the ribbon bar
    if (!m_wndRibbonBar.Create(this))
    {
        return -1;   //Failed to create ribbon bar
    }
    m_wndRibbonBar.LoadFromResource(IDR_RIBBON1);
    ```

[[セクション](#top)]

##  <a name="addcategory"></a> リボン リソースのカスタマイズ

アプリケーション ボタンを作成したので、要素をリボンに追加できます。

> [!NOTE]
> このチュートリアルでは、すべてのパネルで同じパネル アイコンを使用します。 ただし、他のイメージ リスト インデックスを使用して、他のアイコンを表示してもかまいません。

### <a name="to-add-a-home-category-and-edit-panel"></a>[Home] カテゴリと [Edit] パネルを追加するには

1. この Scribble プログラムに必要なカテゴリは 1 つだけです。 デザイン ビューで次のようにクリックします。**カテゴリ**そのプロパティを表示します。 プロパティ値を次のように変更:**キャプション**に`&Home`、 **Large Images**に`IDB_RIBBON_HOMELARGE`、 **Small Images**に`IDB_RIBBON_HOMESMALL`します。

2. 各リボン カテゴリは名前付きパネルに整理されます。 各パネルには、関連操作を実行するコントロールのセットが含まれています。 このカテゴリには 1 つのパネルがあります。 をクリックして**パネル**、し、変更**キャプション**に`Edit`と**イメージ インデックス**に`0`します。

3. **編集** パネルで、ドキュメントの内容を消去するボタンを追加します。 このボタンのメッセージ ID は、IDR_SCRIBBTYPE メニュー リソースに定義済みです。 指定`Clear All`ボタンのテキストとボタンを装飾するビットマップのインデックス。 開く、**ツールボックス**、し、ドラッグ、**ボタン**を**編集**パネル。 ボタンをクリックし、変更**キャプション**に`Clear All`、 **ID**に`ID_EDIT_CLEAR_ALL`、**イメージ インデックス**に`0`、 **Large Image Index**に`0`します。

4. 変更内容を保存し、アプリケーションをビルドして実行します。 Scribble アプリケーションが起動されますが、ウィンドウ最上部にはメニュー バーではなく、リボンが表示されます。 リボン バーは、1 つのカテゴリにあります**ホーム**、および**ホーム**1 つのパネルがあります。**編集**します。 追加したリボンのボタンは、既存のイベント ハンドラーを関連付ける必要があります、**オープン**、**閉じる**、**保存**、**印刷**、**すべてクリア**のボタンは期待どおりに機能する必要があります。

[[セクション](#top)]

##  <a name="setlook"></a> アプリケーションの外観の設定

A*ビジュアル マネージャー*はアプリケーションのすべての描画を制御するグローバル オブジェクトです。 元の Scribble アプリケーションは Office 2000 のユーザー インターフェイス (UI) スタイルを使用しているため、このアプリケーションの外観は古めかしく感じられるかもしれません。 このアプリケーションは、Office 2007 のビジュアル マネージャーを使用するようにリセットして、Office 2007 のような外観にすることができます。

### <a name="to-set-the-look-of-the-application"></a>アプリケーションの外観を設定するには

1. `CMainFrame::OnCreate` 関数に次のコードを入力して、既定のビジュアル マネージャーとスタイルを変更します。

    ```cpp
    // Set the default manager to Office 2007
    CMFCVisualManager::SetDefaultManager(RUNTIME_CLASS(CMFCVisualManagerOffice2007));
    CMFCVisualManagerOffice2007::SetStyle(CMFCVisualManagerOffice2007::Office2007_LunaBlue);
    ```

2. 変更内容を保存し、アプリケーションをビルドして実行します。 アプリケーションの UI が Office 2007 と類似した UI になります。

[[セクション](#top)]

## <a name="next-steps"></a>次の手順

これで、従来の Scribble 1.0 MFC サンプルを、リボン デザイナーを使用するように修正しました。 次に「[第 2 部](../mfc/walkthrough-updating-the-mfc-scribble-application-part-2.md)します。

## <a name="see-also"></a>関連項目

[チュートリアル](../mfc/walkthroughs-mfc.md)  
[チュートリアル: MFC Scribble アプリケーション (第 2 部) の更新] (../mfc/walkthrough-updating-the-mfc-scribble-application-part-2.md)  

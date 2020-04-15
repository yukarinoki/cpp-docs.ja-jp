---
title: 'チュートリアル: MFC Scribble アプリケーションの更新 (パート 2)'
ms.date: 04/25/2019
helpviewer_keywords:
- walkthroughs [MFC]
ms.assetid: 602df5c2-17d4-4cd9-8cf6-dff652c4cae5
ms.openlocfilehash: bc204a152168accf3731eede8ca9ef960ab121d2
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81360229"
---
# <a name="walkthrough-updating-the-mfc-scribble-application-part-2"></a>チュートリアル: MFC Scribble アプリケーションの更新 (パート 2)

このチュートリアルの[第 1 部](../mfc/walkthrough-updating-the-mfc-scribble-application-part-1.md)では、従来の Scribble アプリケーションに Office Fluent リボンを追加する方法を示しました。 このパートでは、メニューやコマンドの代わりにユーザーが使用できるリボン パネルとコントロールを追加する方法を示します。

## <a name="prerequisites"></a>前提条件

[Visual C++ のサンプル](../overview/visual-cpp-samples.md)

## <a name="sections"></a><a name="top"></a>セクション

このパートは、次のセクションで構成されています。

- [リボンへの新しいパネルの追加](#addnewpanel)

- [リボンへのヘルプ パネルの追加](#addhelppanel)

- [リボンへのペン パネルの追加](#addpenpanel)

- [リボンへのカラー ボタンの追加](#addcolorbutton)

- [ドキュメント クラスへのカラー メンバの追加](#addcolormember)

- [ペンの初期化と環境設定の保存](#initpensave)

## <a name="adding-new-panels-to-the-ribbon"></a><a name="addnewpanel"></a>リボンへの新しいパネルの追加

ここでは、ツールバーとステータス バーの表示を制御する 2 つのチェック ボックスを含む **[ビュー** ] パネルを追加する方法と、マルチドキュメント インターフェイス (MDI) ウィンドウの作成と配置を制御する垂直方向の分割ボタンを含む**ウィンドウ**パネルを追加する方法を示します。

### <a name="to-add-a-view-panel-and-window-panel-to-the-ribbon-bar"></a>リボン バーに [ビュー] パネルと [ウィンドウ] パネルを追加するには

1. という名前`View`のパネルを作成し、ステータス バーとツールバーを切り替える 2 つのチェック ボックスを備えています。

   1. [**ツールボックス**] から [ホーム]**カテゴリに** **[パネル]** をドラッグします。 次に、2 つの**チェックボックス**をパネルにドラッグします。

   1. パネルをクリックして、そのプロパティを変更します。 **キャプションを**`View`に変更します。

   1. 最初のチェック ボックスをクリックして、プロパティを変更します。 **ID**を`ID_VIEW_TOOLBAR`に変更`Toolbar`し **、キャプション を**に変更します。

   1. 2 番目のチェック ボックスをクリックして、プロパティを変更します。 **ID**を`ID_VIEW_STATUS_BAR`に変更`Status Bar`し **、キャプション を**に変更します。

1. 分割ボタンのあるパネル`Window`を作成します。 ユーザーが分割ボタンをクリックすると、Scribble アプリケーションで既に定義されている 3 つのコマンドがショートカット メニューに表示されます。

   1. [**ツールボックス**] から [ホーム]**カテゴリに** **[パネル]** をドラッグします。 次に **、ボタン**をパネルにドラッグします。

   1. パネルをクリックして、そのプロパティを変更します。 **キャプションを**`Window`に変更します。

   1. このボタンをクリックします。 **キャプション**を`Windows`に変更`w`し、**キー**を`1`に変更し、**大きいイメージ インデックス**を に、**分割モード**を に変更します`False`。 次に、[**メニュー項目**] の横にある省略記号 **(.)** をクリックして、[**アイテム エディター** ] ダイアログ ボックスを開きます。

   1. 3 つのボタンを追加するには、[**追加**] を 3 回クリックします。

   1. 最初のボタンをクリックし、[キャプション]`New Window`を に`ID_WINDOW_NEW`変更し **、[ID]** を に変更します。 **ID**

   1. 2 番目のボタンをクリックし、[`Cascade`**キャプション]** を`ID_WINDOW_CASCADE`に変更し **、[ID]** を に変更します。

   1. 3 番目のボタンをクリックし、[`Tile`**キャプション]** を`ID_WINDOW_TILE_HORZ`に変更し **、[ID]** を に変更します。

1. 変更内容を保存し、アプリケーションをビルドして実行します。 **[表示]** パネルと **[ウィンドウ]** パネルが表示されます。 ボタンをクリックして、正しく機能することを確認します。

## <a name="adding-a-help-panel-to-the-ribbon"></a><a name="addhelppanel"></a>リボンへのヘルプ パネルの追加

これで、Scribble アプリケーションで定義されている 2 つのメニュー項目を **、ヘルプ トピック**と**Scribble について**という名前のリボン ボタンに割り当てることができます。 ボタンは **、Help**という名前の新しいパネルに追加されます。

### <a name="to-add-a-help-panel"></a>ヘルプ パネルを追加するには

1. [**ツールボックス**] から [ホーム]**カテゴリに** **[パネル]** をドラッグします。 次に、2 つの**ボタン**をパネルにドラッグします。

1. パネルをクリックして、そのプロパティを変更します。 **キャプションを**`Help`に変更します。

1. 最初のボタンをクリックします。 **[キャプション] を**[ ] に`Help Topics`変更し **、ID**を に変更します`ID_HELP_FINDER`。

1. 2 番目のボタンをクリックします。 **[キャプション] を**[ ] に`About Scribble...`変更し **、ID**を に変更します`ID_APP_ABOUT`。

1. 変更内容を保存し、アプリケーションをビルドして実行します。 2 つのリボン ボタンを含む**ヘルプ**パネルが表示されます。

   > [!IMPORTANT]
   > **[トピックのヘルプ**] ボタンをクリックすると、Scribble アプリケーションは 、.chm という名前の圧縮された HTML (.chm) ヘルプ ファイル*your_project_name*開きます。 したがって、プロジェクト名が Scribble でない場合は、ヘルプ ファイルの名前をプロジェクト名に変更する必要があります。

## <a name="adding-a-pen-panel-to-the-ribbon"></a><a name="addpenpanel"></a>リボンへのペン パネルの追加

次に、ペンの太さと色を制御するボタンを表示するパネルを追加します。 このパネルには、太いペンと細いペンを切り替えるチェック ボックスが含まれています。 その機能は、Scribble アプリケーションの**太線**メニュー項目に似ています。

元の Scribble アプリケーションでは、ユーザーがメニューの [ペンの幅] をクリックしたときに表示されるダイアログ ボックスから**ペンの幅**を選択できます。 リボン バーには新しいコントロールを使用する十分な領域があるため、リボン上の 2 つのコンボ ボックスを使用してダイアログ ボックスを置き換えることができます。 1 つのコンボ ボックスは、薄いペンの幅を調整し、もう一方のコンボ ボックスは太いペンの幅を調整します。

#### <a name="to-add-a-pen-panel-and-combo-boxes-to-the-ribbon"></a>ペン パネルとコンボ ボックスをリボンに追加するには

1. [**ツールボックス**] から [ホーム]**カテゴリに** **[パネル]** をドラッグします。 次に **、チェックボックス**と2つの**コンボボックス**をパネルにドラッグします。

1. パネルをクリックして、そのプロパティを変更します。 **キャプションを**`Pen`に変更します。

1. チェック ボックスをオンにします。 **[キャプション] を**[ ] に`Use Thick`変更し **、ID**を に変更します`ID_PEN_THICK_OR_THIN`。

1. 最初のコンボ ボックスをクリックします。 **[キャプション**`Thin Pen`] を`ID_PEN_THIN_WIDTH`に変更し`Drop List`**、ID**を に変更し、[**入力]** を [入力`1;2;3;4;5;6;7;8;9;`] を [**入力**] を [に設定] を 、[**に変換**] を [テキスト] に変更します`2`。

1. 2 番目のコンボ ボックスをクリックします。 **[キャプション**`Thick Pen`] を`ID_PEN_THICK_WIDTH`に変更し`Drop List`**、ID**を に変更し、[**入力]** を [入力`5;6;7;8;9;10;11;12;13;14;15;16;17;18;19;20;`] を [**入力**] を [に設定] を 、[**に変換**] を [テキスト] に変更します`5`。

1. 新しいコンボ ボックスは、既存のメニュー項目に対応していません。

   1. [**リソース ビュー]** ウィンドウで **、[IDR_SCRIBBTYPE]** メニュー リソースを開きます。

   1. [**ペン**] をクリックして、ペン メニューを開きます。 次に、[**ここに入力**して`Thi&n Pen`入力] をクリックします。

   1. 入力したテキストを右クリックして **[プロパティ]** ウィンドウを開き、ID プロパティを`ID_PEN_THIN_WIDTH`に変更します。

   1. すべてのペン メニュー項目に対してイベント ハンドラーを作成します。 作成した**Thi&n Pen**メニュー項目を右クリックし、[ イベント ハンドラの**追加**] をクリックします。 **イベント ハンドラー ウィザード**が表示されます。

   1. ウィザードの [クラス]**リスト**ボックスで **[CScribbleDoc]** を選択し、[**追加と編集**] をクリックします。 このコマンドは、 という名前`CScribbleDoc::OnPenThinWidth`のイベント ハンドラーを作成します。

   1. `CScribbleDoc::OnPenThinWidth` に次のコードを追加します。

        ```cpp
        // Get a pointer to the ribbon bar
        CMFCRibbonBar* pRibbon = ((CMDIFrameWndEx*) AfxGetMainWnd())->GetRibbonBar();
        ASSERT_VALID(pRibbon);

        // Get a pointer to the Thin Width combo box
        CMFCRibbonComboBox* pThinComboBox = DYNAMIC_DOWNCAST(
        CMFCRibbonComboBox, pRibbon->FindByID(ID_PEN_THIN_WIDTH));

        //Get the selected value
        int nCurSel = pThinComboBox->GetCurSel();
        if (nCurSel>= 0)
        {
            m_nThinWidth = atoi(CStringA(pThinComboBox->GetItem(nCurSel)));
        }

        // Create a new pen using the selected width
        ReplacePen();
        ```

1. 次に、太いペンのメニュー項目とイベント ハンドラーを作成します。

   1. [**リソース ビュー]** ウィンドウで **、[IDR_SCRIBBTYPE]** メニュー リソースを開きます。

   1. [**ペン**] をクリックして、ペン メニューを開きます。 次に、[**ここに入力**して`Thic&k Pen`入力] をクリックします。

   1. 入力したテキストを右クリックして **、[プロパティ]** ウィンドウを表示します。 ID プロパティを`ID_PEN_THICK_WIDTH`に変更します。

   1. 作成した **[太いペン**] メニュー項目を右クリックし、[**イベント ハンドラの追加**] をクリックします。 **イベント ハンドラー ウィザード**が表示されます。

   1. ウィザードの [クラス]**リスト**ボックスで **[CScribbleDoc]** を選択し、[**追加と編集**] をクリックします。 このコマンドは、 という名前`CScribbleDoc::OnPenThickWidth`のイベント ハンドラーを作成します。

   1. `CScribbleDoc::OnPenThickWidth` に次のコードを追加します。

        ```cpp
        // Get a pointer to the ribbon bar
        CMFCRibbonBar* pRibbon = ((CMDIFrameWndEx *) AfxGetMainWnd())->GetRibbonBar();
        ASSERT_VALID(pRibbon);

        CMFCRibbonComboBox* pThickComboBox = DYNAMIC_DOWNCAST(
            CMFCRibbonComboBox, pRibbon->FindByID(ID_PEN_THICK_WIDTH));
        // Get the selected value
        int nCurSel = pThickComboBox->GetCurSel();
        if (nCurSel>= 0)
        {
            m_nThickWidth = atoi(CStringA(pThickComboBox->GetItem(nCurSel)));
        }

        // Create a new pen using the selected width
        ReplacePen();
        ```

1. 変更内容を保存し、アプリケーションをビルドして実行します。 新しいボタンとコンボ ボックスが表示されます。 落書きに異なるペン幅を使用してみてください。

## <a name="adding-a-color-button-to-the-pen-panel"></a><a name="addcolorbutton"></a>ペンパネルへのカラーボタンの追加

次に、ユーザーが色で落書きをできるようにする[CMFCRibbonColorButton](../mfc/reference/cmfcribboncolorbutton-class.md)オブジェクトを追加します。

### <a name="to-add-a-color-button-to-the-pen-panel"></a>ペンパネルにカラーボタンを追加するには

1. カラー ボタンを追加する前に、そのメニュー項目を作成します。 [**リソース ビュー]** ウィンドウで **、[IDR_SCRIBBTYPE]** メニュー リソースを開きます。 **ペン**メニュー項目をクリックして、ペンメニューを開きます。 次に、[**ここに入力**して`&Color`入力] をクリックします。 入力したテキストを右クリックして **、[プロパティ]** ウィンドウを表示します。 ID を `ID_PEN_COLOR`に変更します。

1. カラーボタンを追加します。 **[ツールボックス**] から[**カラーボタン**]を**ペン**パネルにドラッグします。

1. カラーボタンをクリックします。 **キャプション**`Color`を に変更`ID_PEN_COLOR`し **、ID** `True`を、**簡易検索**を 、**大きなイメージ インデックス**を`1`に、**分割モード**に変更します`False`。

1. 変更内容を保存し、アプリケーションをビルドして実行します。 新しいカラーボタンが**ペン**パネルに表示されます。 ただし、まだイベント ハンドラーがないため、この値は使用できません。 次の手順では、色のボタンのイベント ハンドラーを追加する方法を示します。

## <a name="adding-a-color-member-to-the-document-class"></a><a name="addcolormember"></a>ドキュメント クラスへのカラー メンバの追加

元の Scribble アプリケーションにはカラー ペンがないため、実装を記述する必要があります。 ドキュメントのペンの色を保存するには、ドキュメント クラス`CscribbleDoc`に新しいメンバーを追加します。

### <a name="to-add-a-color-member-to-the-document-class"></a>ドキュメント クラスに色のメンバーを追加するには

1. scribdoc.h の`CScribbleDoc`クラスで、セクションを`// Attributes`見つけます。 データ メンバーの定義の後に、次の`m_nThickWidth`コード行を追加します。

   ```cpp
   // Current pen color
   COLORREF m_penColor;
   ```

1. すべてのドキュメントには、ユーザーが既に描画したストークスのリストが含まれています。 すべてのストロークは`CStroke`オブジェクトによって定義されます。 `CStroke`このクラスにはペンの色に関する情報が含まれていないため、クラスを変更する必要があります。 scribdoc.h の`CStroke`クラスで、データ メンバーの定義の後に次のコード行`m_nPenWidth`を追加します。

   ```cpp
   // Pen color for the stroke
   COLORREF m_penColor;
   ```

1. scribdoc.h で、パラメーターに`CStroke`幅と色を指定する新しいコンストラクターを追加します。 ステートメントの後に次のコード行`CStroke(UINT nPenWidth);`を追加します。

   ```cpp
   CStroke(UINT nPenWidth, COLORREF penColor);
   ```

1. scribdoc.cpp で、新しい`CStroke`コンストラクターの実装を追加します。 コンストラクターの実装後に次のコードを`CStroke::CStroke(UINT nPenWidth)`追加します。

   ```cpp
   // Constructor that uses the document's current width and color
   CStroke::CStroke(UINT nPenWidth, COLORREF penColor)
   {
       m_nPenWidth = nPenWidth;
       m_penColor = penColor;
       m_rectBounding.SetRectEmpty();
   }
   ```

1. メソッドの 2 行`CStroke::DrawStroke`目を次のように変更します。

   ```cpp
   if (!penStroke.CreatePen(PS_SOLID, m_nPenWidth, m_penColor))
   ```

1. ドキュメント クラスの既定のペンの色を設定します。 scribdoc.cpp で、ステートメントの後に`CScribbleDoc::InitDocument`次の行`m_nThickWidth = 5;`を追加します。

   ```cpp
   // default pen color is black
   m_penColor = RGB(0, 0, 0);
   ```

1. scribdoc.cpp で、メソッドの最初の行`CScribbleDoc::NewStroke`を次のように変更します。

   ```cpp
   CStroke* pStrokeItem = new CStroke(m_nPenWidth, m_penColor);
   ```

1. メソッドの最後の行を`CScribbleDoc::ReplacePen`次のように変更します。

   ```cpp
   m_penCur.CreatePen(PS_SOLID, m_nPenWidth, m_penColor);
   ```

1. 前の手順`m_penColor`でメンバーを追加しました。 次に、メンバーを設定するカラー ボタンのイベント ハンドラーを作成します。

   1. [**リソース ビュー]** ウィンドウで、IDR_SCRIBBTYPE メニュー リソースを開きます。

   1. [**色**] メニュー項目を右クリックし、[**イベント ハンドラの追加**] をクリックします。 **イベント ハンドラ ウィザード**が表示されます。

   1. ウィザードの **[クラス**] リスト ボックスで **[CScribbleDoc]** を選択し、[**追加と編集**] ボタンをクリックします。 このコマンドは、`CScribbleDoc::OnPenColor`イベント ハンドラー スタブを作成します。

1. イベント ハンドラーのスタブ`CScribbleDoc::OnPenColor`を次のコードに置き換えます。

   ```cpp
   void CScribbleDoc::OnPenColor()
   {
       // Change pen color to reflect color button's current selection
       CMFCRibbonBar* pRibbon = ((CMDIFrameWndEx*) AfxGetMainWnd())->GetRibbonBar();
       ASSERT_VALID(pRibbon);

       CMFCRibbonColorButton* pColorBtn = DYNAMIC_DOWNCAST(
           CMFCRibbonColorButton, pRibbon->FindByID(ID_PEN_COLOR));

       m_penColor = pColorBtn->GetColor();
       // Create new pen using the selected color
       ReplacePen();
   }
   ```

1. 変更を保存し、アプリケーションをビルドして実行します。 カラーボタンを押してペンの色を変更できるようになりました。

## <a name="initializing-pens-and-saving-preferences"></a><a name="initpensave"></a>ペンの初期化と環境設定の保存

次に、ペンの色と幅を初期化します。 最後に、ファイルからカラー図面を保存してロードします。

### <a name="to-initialize-controls-on-the-ribbon-bar"></a>リボン バーのコントロールを初期化するには

1. リボン バーのペンを初期化します。

   ステートメントの後に、メソッドの scribdoc.cpp`CScribbleDoc::InitDocument`に次の`m_sizeDoc = CSize(200,200)`コードを追加します。

   ```cpp
   // Reset the ribbon UI to its initial values
   CMFCRibbonBar* pRibbon =
       ((CMDIFrameWndEx*) AfxGetMainWnd())->GetRibbonBar();
   ASSERT_VALID(pRibbon);

   CMFCRibbonColorButton* pColorBtn = DYNAMIC_DOWNCAST(
       CMFCRibbonColorButton,
       pRibbon->FindByID(ID_PEN_COLOR));

   // Set ColorButton to black
   pColorBtn->SetColor(RGB(0, 0, 0));

   CMFCRibbonComboBox* pThinComboBox = DYNAMIC_DOWNCAST(
       CMFCRibbonComboBox,
       pRibbon->FindByID(ID_PEN_THIN_WIDTH));

   // Set Thin pen combobox to 2
   pThinComboBox->SelectItem(1);

   CMFCRibbonComboBox* pThickComboBox = DYNAMIC_DOWNCAST(
       CMFCRibbonComboBox,
       pRibbon->FindByID(ID_PEN_THICK_WIDTH));

   // Set Thick pen combobox to 5
   pThickComboBox->SelectItem(0);
   ```

1. カラー図面をファイルに保存します。 `CStroke::Serialize`次のステートメントをメソッドの scribdoc.cpp に追加`ar << (WORD)m_nPenWidth;`します。

   ```cpp
   ar << (COLORREF)m_penColor;
   ```

1. 最後に、ファイルからカラー図面をロードします。 ステートメントの後に、メソッド内の次`CStroke::Serialize`のコード行を`m_nPenWidth = w;`追加します。

   ```cpp
   ar >> m_penColor;
   ```

1. 今すぐ色で落書きし、ファイルに図面を保存します。

## <a name="conclusion"></a>まとめ

MFC の落書きアプリケーションを更新しました。 既存のアプリケーションを変更する場合は、このチュートリアルをガイドとして使用します。

## <a name="see-also"></a>関連項目

[チュートリアル](../mfc/walkthroughs-mfc.md)<br/>
[チュートリアル: MFC Scribble アプリケーションの更新 (パート 1)](../mfc/walkthrough-updating-the-mfc-scribble-application-part-1.md)

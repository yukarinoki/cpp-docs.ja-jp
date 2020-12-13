---
description: '詳細については、「チュートリアル: MFC Scribble アプリケーションの更新 (パート 2)」を参照してください。'
title: 'チュートリアル: MFC Scribble アプリケーションの更新 (パート 2)'
ms.date: 04/25/2019
helpviewer_keywords:
- walkthroughs [MFC]
ms.assetid: 602df5c2-17d4-4cd9-8cf6-dff652c4cae5
ms.openlocfilehash: 2520ac8fc1c66a2fc388738d22f4851547b6d03b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97142962"
---
# <a name="walkthrough-updating-the-mfc-scribble-application-part-2"></a>チュートリアル: MFC Scribble アプリケーションの更新 (パート 2)

このチュートリアルの[パート 1](../mfc/walkthrough-updating-the-mfc-scribble-application-part-1.md)では、従来の Scribble アプリケーションに Office Fluent リボンを追加する方法を説明しました。 このパートでは、ユーザーがメニューやコマンドの代わりに使用できるリボンパネルとコントロールを追加する方法を示します。

## <a name="prerequisites"></a>前提条件

[Visual C++ のサンプル](../overview/visual-cpp-samples.md)

## <a name="sections"></a><a name="top"></a> 各項

このパートは、次のセクションで構成されています。

- [リボンへの新しいパネルの追加](#addnewpanel)

- [リボンへのヘルプパネルの追加](#addhelppanel)

- [リボンへのペンパネルの追加](#addpenpanel)

- [リボンへのカラーボタンの追加](#addcolorbutton)

- [Color メンバーを Document クラスに追加する](#addcolormember)

- [ペンの初期化と基本設定の保存](#initpensave)

## <a name="adding-new-panels-to-the-ribbon"></a><a name="addnewpanel"></a> リボンへの新しいパネルの追加

次の手順では、ツールバーとステータスバーの表示を制御する2つのチェックボックスと、マルチドキュメントインターフェイス (MDI) ウィンドウの作成と配置を制御する垂直方向の分割ボタンを含む **ウィンドウ****パネルを追加** する方法を示します。

### <a name="to-add-a-view-panel-and-window-panel-to-the-ribbon-bar"></a>リボンバーにビューパネルとウィンドウパネルを追加するには

1. という名前のパネルを作成します。このパネルには `View` 、ステータスバーとツールバーを切り替える2つのチェックボックスがあります。

   1. [**ツールボックス**] から [**ホーム**] カテゴリに **パネル** をドラッグします。 次に、2つの **チェックボックス** をパネルにドラッグします。

   1. パネルをクリックしてプロパティを変更します。 **キャプション** をに変更 `View` します。

   1. プロパティを変更するには、最初のチェックボックスをオンにします。 **ID** をに変更 `ID_VIEW_TOOLBAR` し、**キャプション** をに変更 `Toolbar` します。

   1. 2番目のチェックボックスをクリックして、プロパティを変更します。 **ID** をに変更 `ID_VIEW_STATUS_BAR` し、**キャプション** をに変更 `Status Bar` します。

1. 分割ボタンを持つという名前のパネルを作成 `Window` します。 ユーザーが分割ボタンをクリックすると、Scribble アプリケーションで既に定義されている3つのコマンドがショートカットメニューに表示されます。

   1. [**ツールボックス**] から [**ホーム**] カテゴリに **パネル** をドラッグします。 次に、 **ボタン** をパネルにドラッグします。

   1. パネルをクリックしてプロパティを変更します。 **キャプション** をに変更 `Window` します。

   1. ボタンをクリックします。 **キャプション** をに変更し、 `Windows` **キー** をに `w` 、**大きいイメージのインデックス** をに変更 `1` し、モードをに **分割** し `False` ます。 次に、[**メニュー項目]** の横にある省略記号 ([.**..**]) をクリックして、[**項目エディター** ] ダイアログボックスを開きます。

   1. 3つのボタンを追加するには、[ **追加** ] を3回クリックします。

   1. 最初のボタンをクリックし、[ **キャプション** ] をに `New Window` 、[ **ID** ] をに変更し `ID_WINDOW_NEW` ます。

   1. 2番目のボタンをクリックし、[ **キャプション** ] をに `Cascade` 、[ **ID** ] をに変更し `ID_WINDOW_CASCADE` ます。

   1. 3番目のボタンをクリックし、[ **キャプション** ] をに `Tile` 、[ **ID** ] をに変更し `ID_WINDOW_TILE_HORZ` ます。

1. 変更内容を保存し、アプリケーションをビルドして実行します。 **ビュー** と **ウィンドウ** パネルが表示されます。 ボタンをクリックして、正しく機能していることを確認します。

## <a name="adding-a-help-panel-to-the-ribbon"></a><a name="addhelppanel"></a> リボンへのヘルプパネルの追加

これで、Scribble アプリケーションで定義されている2つのメニュー項目を、 **ヘルプトピック** および **scribble** の名前付きのリボンボタンに割り当てることができます。 ボタンが [ **ヘルプ**] という名前の新しいパネルに追加されます。

### <a name="to-add-a-help-panel"></a>ヘルプパネルを追加するには

1. [**ツールボックス**] から [**ホーム**] カテゴリに **パネル** をドラッグします。 次に、2つの **ボタン** をパネルにドラッグします。

1. パネルをクリックしてプロパティを変更します。 **キャプション** をに変更 `Help` します。

1. 最初のボタンをクリックします。 [ **キャプション** ] をに `Help Topics` 、[ **ID** ] をに変更 `ID_HELP_FINDER` します。

1. 2番目のボタンをクリックします。 [ **キャプション** ] をに `About Scribble...` 、[ **ID** ] をに変更 `ID_APP_ABOUT` します。

1. 変更内容を保存し、アプリケーションをビルドして実行します。 2つのリボンボタンを含む **ヘルプ** パネルが表示されます。

   > [!IMPORTANT]
   > [ **ヘルプトピック** ] ボタンをクリックすると、Scribble アプリケーションによって、 *your_project_name* という名前の圧縮された HTML (.chm) ヘルプファイルが開きます。 そのため、プロジェクトに Scribble という名前が付けられていない場合は、ヘルプファイルの名前をプロジェクト名に変更する必要があります。

## <a name="adding-a-pen-panel-to-the-ribbon"></a><a name="addpenpanel"></a> リボンへのペンパネルの追加

ここで、ペンの太さと色を制御するボタンを表示するパネルを追加します。 このパネルには、太いペンと細いペンを切り替えるチェックボックスがあります。 この機能は、Scribble アプリケーションの **太線** メニュー項目の機能に似ています。

元の Scribble アプリケーションを使用すると、ユーザーがメニューの [ **ペンの幅** ] をクリックしたときに表示されるダイアログボックスからペンの幅を選択できます。 リボンバーには新しいコントロール用の十分なスペースがあるため、リボンの2つのコンボボックスを使用してダイアログボックスを置き換えることができます。 1つのコンボボックスで細いペンの幅を調整し、もう一方のコンボボックスは太いペンの幅を調整します。

#### <a name="to-add-a-pen-panel-and-combo-boxes-to-the-ribbon"></a>リボンにペンパネルとコンボボックスを追加するには

1. [**ツールボックス**] から [**ホーム**] カテゴリに **パネル** をドラッグします。 次に、 **チェックボックス** と2つの **コンボボックス** をパネルにドラッグします。

1. パネルをクリックしてプロパティを変更します。 **キャプション** をに変更 `Pen` します。

1. チェック ボックスをオンにします。 [ **キャプション** ] をに `Use Thick` 、[ **ID** ] をに変更 `ID_PEN_THICK_OR_THIN` します。

1. 最初のコンボボックスをクリックします。 [ **Caption** ] をに変更し、[ID] を、[ `Thin Pen`  `ID_PEN_THIN_WIDTH` **型** `Drop List` ] に、[**データ**] を [ `1;2;3;4;5;6;7;8;9;` **テキスト**] に変更し `2` ます。

1. 2番目のコンボボックスをクリックします。 [ **Caption** ] をに変更し、[ID] を、[ `Thick Pen`  `ID_PEN_THICK_WIDTH` **型** `Drop List` ] に、[**データ**] を [ `5;6;7;8;9;10;11;12;13;14;15;16;17;18;19;20;` **テキスト**] に変更し `5` ます。

1. 新しいコンボボックスは、既存のメニュー項目に対応していないため、すべてのペンオプションのメニュー項目を作成する必要があります。

   1. [ **リソースビュー** ] ウィンドウで、[ **IDR_SCRIBBTYPE** ] メニューリソースを開きます。

   1. [ **ペン** ] をクリックして、[ペン] メニューを開きます。 [ **ここに入力** ] をクリックし、「」と入力し `Thi&n Pen` ます。

   1. 入力したテキストを右クリックして [ **プロパティ** ] ウィンドウを開き、ID プロパティをに変更し `ID_PEN_THIN_WIDTH` ます。

   1. すべてのペンメニュー項目のイベントハンドラーを作成します。 作成した **Thi&n ペン** メニュー項目を右クリックし、[ **イベントハンドラーの追加**] をクリックします。 **イベントハンドラーウィザード** が表示されます。

   1. ウィザードの [ **クラス]** ボックスの一覧で [ **CScribbleDoc** ] を選択し、[ **追加と編集**] をクリックします。 コマンドは、という名前のイベントハンドラーを作成し `CScribbleDoc::OnPenThinWidth` ます。

   1. 次のコードを `CScribbleDoc::OnPenThinWidth` に追加します。

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

1. 次に、太いペン用のメニュー項目とイベントハンドラーを作成します。

   1. [ **リソースビュー** ] ウィンドウで、[ **IDR_SCRIBBTYPE** ] メニューリソースを開きます。

   1. [ **ペン** ] をクリックして、[ペン] メニューを開きます。 [ **ここに入力** ] をクリックし、「」と入力し `Thic&k Pen` ます。

   1. 入力したテキストを右クリックして、[ **プロパティ** ] ウィンドウを表示します。 ID プロパティをに変更 `ID_PEN_THICK_WIDTH` します。

   1. 作成した **シックペン** メニュー項目を右クリックし、[ **イベントハンドラーの追加**] をクリックします。 **イベントハンドラーウィザード** が表示されます。

   1. ウィザードの [ **クラス]** ボックスの一覧で [ **CScribbleDoc** ] を選択し、[ **追加と編集**] をクリックします。 コマンドは、という名前のイベントハンドラーを作成し `CScribbleDoc::OnPenThickWidth` ます。

   1. 次のコードを `CScribbleDoc::OnPenThickWidth` に追加します。

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

1. 変更内容を保存し、アプリケーションをビルドして実行します。 新しいボタンとコンボボックスが表示されます。 別のペンの幅を使って scribble を試してください。

## <a name="adding-a-color-button-to-the-pen-panel"></a><a name="addcolorbutton"></a> ペンパネルへのカラーボタンの追加

次に、ユーザーが scribble を色付けできるようにする [CMFCRibbonColorButton](../mfc/reference/cmfcribboncolorbutton-class.md) オブジェクトを追加します。

### <a name="to-add-a-color-button-to-the-pen-panel"></a>色のボタンをペンパネルに追加するには

1. 色のボタンを追加する前に、そのメニュー項目を作成します。 [ **リソースビュー** ] ウィンドウで、[ **IDR_SCRIBBTYPE** ] メニューリソースを開きます。 [ **ペン** ] メニュー項目をクリックして、[ペン] メニューを開きます。 [ **ここに入力** ] をクリックし、「」と入力し `&Color` ます。 入力したテキストを右クリックして、[ **プロパティ** ] ウィンドウを表示します。 ID を `ID_PEN_COLOR`に変更します。

1. 次に、[色] ボタンを追加します。 [ **ツールボックス**] から、[ **色] ボタン** を [ **ペン** ] パネルにドラッグします。

1. [色] ボタンをクリックします。 [ **キャプション** ] をに `Color` 、[ **ID** ] を、[ `ID_PEN_COLOR` **単純な検索** ] `True` 、[ **大きいイメージのインデックス** ] に、 `1` [ **モード** ] をに変更し `False` ます。

1. 変更内容を保存し、アプリケーションをビルドして実行します。 [新しい色] ボタンが **ペン** パネルに表示されます。 ただし、イベントハンドラーがまだないため、使用できません。 次の手順では、[色] ボタンのイベントハンドラーを追加する方法について説明します。

## <a name="adding-a-color-member-to-the-document-class"></a><a name="addcolormember"></a> Color メンバーを Document クラスに追加する

元の Scribble アプリケーションにはカラーペンがないため、実装を記述する必要があります。 ドキュメントのペンの色を格納するには、ドキュメントクラスに新しいメンバーを追加し `CscribbleDoc` ます。

### <a name="to-add-a-color-member-to-the-document-class"></a>色のメンバーをドキュメントクラスに追加するには

1. Scribdoc のクラスで、セクションを `CScribbleDoc` 見つけ `// Attributes` ます。 データメンバーの定義の後に、次のコード行を追加 `m_nThickWidth` します。

   ```cpp
   // Current pen color
   COLORREF m_penColor;
   ```

1. すべてのドキュメントには、ユーザーが既に描画した stokes の一覧が含まれています。 すべてのストロークは、オブジェクトによって定義され `CStroke` ます。 クラスには、 `CStroke` ペンの色に関する情報が含まれていないため、クラスを変更する必要があります。 Scribdoc のクラスで、 `CStroke` データメンバーの定義の後に次のコード行を追加します `m_nPenWidth` 。

   ```cpp
   // Pen color for the stroke
   COLORREF m_penColor;
   ```

1. Scribdoc で、 `CStroke` 幅と色を指定するパラメーターを持つ新しいコンストラクターを追加します。 ステートメントの後に次のコード行を追加し `CStroke(UINT nPenWidth);` ます。

   ```cpp
   CStroke(UINT nPenWidth, COLORREF penColor);
   ```

1. Scribdoc で、新しいコンストラクターの実装を追加します `CStroke` 。 コンストラクターの実装の後に、次のコードを追加し `CStroke::CStroke(UINT nPenWidth)` ます。

   ```cpp
   // Constructor that uses the document's current width and color
   CStroke::CStroke(UINT nPenWidth, COLORREF penColor)
   {
       m_nPenWidth = nPenWidth;
       m_penColor = penColor;
       m_rectBounding.SetRectEmpty();
   }
   ```

1. メソッドの2行目を次のように変更し `CStroke::DrawStroke` ます。

   ```cpp
   if (!penStroke.CreatePen(PS_SOLID, m_nPenWidth, m_penColor))
   ```

1. ドキュメントクラスの既定のペンの色を設定します。 Scribdoc で、 `CScribbleDoc::InitDocument` ステートメントの後に次の行を追加します。 `m_nThickWidth = 5;`

   ```cpp
   // default pen color is black
   m_penColor = RGB(0, 0, 0);
   ```

1. Scribdoc で、メソッドの最初の行 `CScribbleDoc::NewStroke` を次のように変更します。

   ```cpp
   CStroke* pStrokeItem = new CStroke(m_nPenWidth, m_penColor);
   ```

1. メソッドの最後の行 `CScribbleDoc::ReplacePen` を次のように変更します。

   ```cpp
   m_penCur.CreatePen(PS_SOLID, m_nPenWidth, m_penColor);
   ```

1. 前の手順でメンバーを追加しました `m_penColor` 。 ここで、メンバーを設定するカラーボタンのイベントハンドラーを作成します。

   1. [ **リソースビュー** ] ウィンドウで、[IDR_SCRIBBTYPE] メニューリソースを開きます。

   1. **カラー** メニュー項目を右クリックし、[**イベントハンドラーの追加**] をクリックします。 **イベントハンドラーウィザード** が表示されます。

   1. ウィザードの [ **クラス]** ボックスの一覧で [ **CScribbleDoc** ] を選択し、[ **追加と編集** ] ボタンをクリックします。 コマンドは、 `CScribbleDoc::OnPenColor` イベントハンドラースタブを作成します。

1. イベントハンドラーのスタブを `CScribbleDoc::OnPenColor` 次のコードに置き換えます。

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

1. 変更を保存し、アプリケーションをビルドして実行します。 色のボタンを押して、ペンの色を変更できるようになりました。

## <a name="initializing-pens-and-saving-preferences"></a><a name="initpensave"></a> ペンの初期化と基本設定の保存

次に、ペンの色と幅を初期化します。 最後に、ファイルからカラー描画を保存して読み込みます。

### <a name="to-initialize-controls-on-the-ribbon-bar"></a>リボンバーのコントロールを初期化するには

1. リボンバーのペンを初期化します。

   次のコードを、メソッドの scribdoc のステートメントの後に追加します `CScribbleDoc::InitDocument` `m_sizeDoc = CSize(200,200)` 。

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

1. カラー描画をファイルに保存します。 ステートメントの後に、メソッド内の scribdoc に次のステートメントを追加し `CStroke::Serialize` `ar << (WORD)m_nPenWidth;` ます。

   ```cpp
   ar << (COLORREF)m_penColor;
   ```

1. 最後に、ファイルからカラー描画を読み込みます。 メソッド内のステートメントの後に、次のコード行を追加し `CStroke::Serialize` `m_nPenWidth = w;` ます。

   ```cpp
   ar >> m_penColor;
   ```

1. 次に、色を落書きし、図面をファイルに保存します。

## <a name="conclusion"></a>結論

MFC Scribble アプリケーションが更新されました。 既存のアプリケーションを変更する場合は、このチュートリアルをガイドとして使用してください。

## <a name="see-also"></a>関連項目

[チュートリアル](../mfc/walkthroughs-mfc.md)<br/>
[チュートリアル: MFC Scribble アプリケーションの更新 (パート 1)](../mfc/walkthrough-updating-the-mfc-scribble-application-part-1.md)

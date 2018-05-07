---
title: 'チュートリアル: MFC Scribble アプリケーション (パート 2) の更新 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- walkthroughs [MFC]
ms.assetid: 602df5c2-17d4-4cd9-8cf6-dff652c4cae5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: eae1dd3c1662aafb6b52d2ecb821e073adc0bfd5
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="walkthrough-updating-the-mfc-scribble-application-part-2"></a>チュートリアル: MFC Scribble アプリケーションの更新 (パート 2)
[第 1 部](../mfc/walkthrough-updating-the-mfc-scribble-application-part-1.md)このチュートリアルでは、クラシックに Office Fluent リボンを追加する方法を示しましたの Scribble アプリケーションです。 この部分では、リボン パネルやユーザーがメニューやコマンドの代わりに使用できるコントロールを追加する方法を示します。  
  
## <a name="prerequisites"></a>必須コンポーネント  
 [Visual C++ のサンプル](../visual-cpp-samples.md)  
  
##  <a name="top"></a> セクション  
 このパートは、次のセクションで構成されています。  
  
- [新しいパネルをリボンに追加します。](#addnewpanel)  
  
- [ヘルプ パネルをリボンに追加します。](#addhelppanel)  
  
- [ペン パネルをリボンに追加します。](#addpenpanel)  
  
- [リボンのカラー ボタンの追加](#addcolorbutton)  
  
- [ドキュメント クラスへの色のメンバーの追加](#addcolormember)  
  
- [初期化と環境設定の保存](#initpensave)  
  
##  <a name="addnewpanel"></a> 新しいパネルをリボンに追加します。  
 次の手順を追加する方法を説明する、**ビュー**ツールバーとステータス バーの可視性を制御する 2 つのチェック ボックスを含むパネルとも、**ウィンドウ**を垂直方向の分割を含むパネル作成とマルチ ドキュメント インターフェイス (MDI) ウィンドウの配置を制御するボタンをクリックします。  
  
#### <a name="to-add-a-view-panel-and-window-panel-to-the-ribbon-bar"></a>リボン バーにビュー パネルとウィンドウのパネルを追加するには  
  
1.  名前付きパネルを作成`View`、ステータス バーとツールバーを切り替える 2 つのチェック ボックスを持ちます。  
  
    1.  **ツールボックス**、ドラッグ、**パネル**を**ホーム**カテゴリ。 2 つをドラッグ**チェック ボックス**パネルにします。  
  
    2.  そのプロパティを変更するパネルをクリックします。 変更**キャプション**に`View`です。  
  
    3.  そのプロパティを変更する最初のチェック ボックスをクリックします。 変更**ID**に`ID_VIEW_TOOLBAR`と**キャプション**に`Toolbar`です。  
  
    4.  そのプロパティを変更する 2 番目のチェック ボックスをクリックします。 変更**ID**に`ID_VIEW_STATUS_BAR`と**キャプション**に`Status Bar`です。  
  
2.  名前付きパネルを作成`Window`分割ボタンを持ちます。 ユーザーには、分割ボタンがクリックすると、ショートカット メニューには、Scribble アプリケーションで既に定義されている 3 つのコマンドが表示されます。  
  
    1.  **ツールボックス**、ドラッグ、**パネル**を**ホーム**カテゴリ。 ドラッグし、**ボタン**パネルにします。  
  
    2.  そのプロパティを変更するパネルをクリックします。 変更**キャプション**に`Window`です。  
  
    3.  ボタンをクリックします。 変更**キャプション**に`Windows`、**キー**に`w`、**大きいイメージ インデックス**に`1`、および**分割モード**`False`です。 省略記号ボタンをクリックし、(**.**) の横に**メニュー項目**を開くには、**項目エディター**  ダイアログ ボックス。  
  
    4.  をクリックして**追加**3 つのボタンの追加を 3 回です。  
  
    5.  最初のボタンをクリックし、変更**キャプション**に`New Window`、および**ID**に`ID_WINDOW_NEW`です。  
  
    6.  2 番目のボタンをクリックし、変更**キャプション**に`Cascade`、および**ID**に`ID_WINDOW_CASCADE`です。  
  
    7.  3 番目のボタンをクリックし、変更**キャプション**に`Tile`、および**ID**に`ID_WINDOW_TILE_HORZ`です。  
  
3.  変更内容を保存し、アプリケーションをビルドして実行します。 **ビュー**と**ウィンドウ**パネルを表示する必要があります。 正しく機能することを確認するためのボタンをクリックします。  
  
 [[セクション](#top)]  
  
##  <a name="addhelppanel"></a> ヘルプ パネルをリボンに追加します。  
 ここで、名前が付けられるリボン ボタンに Scribble アプリケーションで定義されている 2 つのメニュー項目を割り当てることができます**ヘルプ トピック**と**について Scribble**です。 ボタンがという名前の新しいパネルに追加されます**ヘルプ**です。  
  
#### <a name="to-add-a-help-panel"></a>ヘルプ パネルを追加するには  
  
1.  **ツールボックス**、ドラッグ、**パネル**を**ホーム**カテゴリ。 2 つをドラッグ**ボタン**パネルにします。  
  
2.  そのプロパティを変更するパネルをクリックします。 変更**キャプション**に`Help`です。  
  
3.  最初のボタンをクリックします。 変更**キャプション**に`Help Topics`、および**ID**に`ID_HELP_FINDER`です。  
  
4.  2 番目のボタンをクリックします。 変更**キャプション**に`About Scribble...`、および**ID**に`ID_APP_ABOUT`です。  
  
5.  変更内容を保存し、アプリケーションをビルドして実行します。 A**ヘルプ**を 2 つのリボン ボタンを含むパネルを表示する必要があります。  
  
    > [!IMPORTANT]
    >  クリックすると、**ヘルプ トピック**ボタン、Scribble アプリケーションは、という名前の圧縮 (.chm) の HTML ヘルプ ファイルを開きます*your_project_name*chm.。 そのため、プロジェクトが Scribble に名前がない場合、プロジェクトの名前をヘルプ ファイルの名前を変更する必要があります。  
  
 [[セクション](#top)]  
  
##  <a name="addpenpanel"></a> ペン パネルをリボンに追加します。  
 ここで、太さ、ペンの色を制御するボタンを表示するパネルを追加します。 このパネルには、シック (thick) およびシン ペン間を切り替える チェック ボックスが含まれています。 その機能に似ています、**太い線**Scribble アプリケーションのメニュー項目。  
  
 元の Scribble アプリケーションでは、ユーザーは、ユーザーがクリックしたときに表示されるダイアログ ボックスをペンの幅を選択**ペンの幅**メニュー。 リボン バーには、新しいコントロールの十分な余裕があるために、リボンを次の 2 つのコンボ ボックスを使用して、ダイアログ ボックスを置き換えることができます。 細いペンの幅を調整します。 1 つのコンボ ボックスと、その他のコンボ ボックスがシック (thick) のペンの幅を調整します。  
  
#### <a name="to-add-a-pen-panel-and-combo-boxes-to-the-ribbon"></a>ペン パネルとコンボ ボックスをリボンに追加するには  
  
1.  **ツールボックス**、ドラッグ、**パネル**を**ホーム**カテゴリ。 ドラッグし、 ** チェック ボックスを**と 2 つ**コンボ ボックス**パネルにします。  
  
2.  そのプロパティを変更するパネルをクリックします。 変更**キャプション**に`Pen`です。  
  
3.  チェック ボックスをクリックします。 変更**キャプション**に`Use Thick`、および**ID**に`ID_PEN_THICK_OR_THIN`です。  
  
4.  最初のコンボ ボックスをクリックします。 変更**キャプション**に`Thin Pen`、 **ID**に`ID_PEN_THIN_WIDTH`、**テキスト**に`2`、**型**に`Drop List`、および**データ**に`1;2;3;4;5;6;7;8;9;`です。  
  
5.  2 番目のコンボ ボックスをクリックします。 変更**キャプション**に`Thick Pen`、 **ID**に`ID_PEN_THICK_WIDTH`、**テキスト**に`5`、**型**に`Drop List`、および**データ**に`5;6;7;8;9;10;11;12;13;14;15;16;17;18;19;20;`です。  
  
6.  新しいコンボ ボックスは、既存のメニュー項目に対応していません。 そのため、すべてペンのオプションのメニュー項目を作成する必要があります。  
  
    1.  **リソース ビュー**  ウィンドウで、IDR_SCRIBBTYPE メニュー リソースを開きます。  
  
    2.  をクリックして**ペン**を開くには、p**en**メニュー。 をクリックして**ここへ入力**および種類`Thi&n Pen`です。  
  
    3.  開くには入力したテキストを右クリックし、**プロパティ**ウィンドウ、およびし、変更、ID プロパティを`ID_PEN_THIN_WIDTH`です。  
  
    4.  また、ペンのすべてのメニュー項目のイベント ハンドラーを作成する必要があります。 右クリックし、 **Thi と n のペン**だけを作成し、をクリックするメニュー項目**イベント ハンドラーの追加**です。 **イベント ハンドラー ウィザード**が表示されます。  
  
    5.  **クラス リスト**ウィザードで、選択ボックス**CScribbleDoc**  をクリックし、**の追加し、編集**です。 名前付きイベント ハンドラーを作成これ`CScribbleDoc::OnPenThinWidth`です。  
  
    6.  `CScribbleDoc::OnPenThinWidth` に次のコードを追加します。  
  
 ``` *リボンへのポインターを取得バー CMFCRibbonBar* pRibbon = ((CMDIFrameWndEx*) AfxGetMainWnd()) GetRibbonBar();]-> [ASSERT_VALID(pRibbon) です。*/シン幅コンボ ボックス CMFCRibbonComboBox へのポインターを取得/* pThinComboBox = DYNAMIC_DOWNCAST (CMFCRibbonComboBox、pRibbon]-> [FindByID(ID_PEN_THIN_WIDTH)); *//Get、選択した値  
    int nCurSel = pThinComboBox GetCurSel();]-> [場合 (nCurSel > = 0)  
{  
m_nThinWidth = atoi (pThinComboBox]-> [GetItem(nCurSel)) です。

 } */選択の幅を使用して新しいペンを作成します。  
    ReplacePen() です。

 ```  
  
7.  Next, create a menu item and event handlers for the thick pen.  
  
    1.  In the **Resource View** window, open the IDR_SCRIBBTYPE menu resource.  
  
    2.  Click **Pen** to open the pen menu. Then click **Type Here** and type `Thic&k Pen`.  
  
    3.  Right-click the text that you just typed to display the **Properties** window. Change the ID property to `ID_PEN_THICK_WIDTH`.  
  
    4.  Right-click the **Thick Pen** menu item that you just created and then click **Add Event Handler**. The **Event Handler Wizard** is displayed.  
  
    5.  In the **Class list** box of the wizard, select **CScribbleDoc** and then click **Add and Edit**. This creates an event handler named `CScribbleDoc::OnPenThickWidth`.  
  
    6.  Add the following code to `CScribbleDoc::OnPenThickWidth`.  
  
 ``` *// Get a pointer to the ribbon bar  
    CMFCRibbonBar* pRibbon = ((CMDIFrameWndEx *) AfxGetMainWnd())->GetRibbonBar();
ASSERT_VALID(pRibbon);

 CMFCRibbonComboBox* pThickComboBox = DYNAMIC_DOWNCAST(
    CMFCRibbonComboBox, pRibbon->FindByID(ID_PEN_THICK_WIDTH));
*// Get the selected value  
    int nCurSel = pThickComboBox->GetCurSel();
if (nCurSel>= 0)  
 {  
    m_nThickWidth = atoi(pThickComboBox->GetItem(nCurSel));

 } *// Create a new pen using the selected width  
    ReplacePen();

 ```  
  
8.  変更内容を保存し、アプリケーションをビルドして実行します。 新しいボタンやコンボ ボックスが表示されます。 Scribble を別のペンの幅を使用してください。  
  
 [[セクション](#top)]  
  
##  <a name="addcolorbutton"></a> ペン パネルにカラー ボタンを追加します。  
 次に、追加、 [CMFCRibbonColorButton](../mfc/reference/cmfcribboncolorbutton-class.md)により、ユーザー オブジェクトの色で scribble です。  
  
#### <a name="to-add-a-color-button-to-the-pen-panel"></a>カラー ボタン、[ペン] パネルを追加するには  
  
1.  色のボタンを追加する前に、そのメニュー項目を作成します。 **リソース ビュー**  ウィンドウで、IDR_SCRIBBTYPE メニュー リソースを開きます。 クリックして、**ペン**を開くには、[ペン] メニューのメニュー項目。 をクリックして**ここへ入力**および種類`&Color`です。 表示を入力するテキストを右クリックし、**プロパティ**ウィンドウです。 ID を変更する`ID_PEN_COLOR`です。  
  
2.  色のボタンを追加します。 **ツールボックス**、ドラッグ、**のカラー ボタンは**を**ペン**パネルです。  
  
3.  色のボタンをクリックします。 変更**キャプション**に`Color`、 **ID**に`ID_PEN_COLOR`、 **SimpleLook**に`True`、**大きいイメージ インデックス**に`1`、および**分割モード**に`False`です。  
  
4.  変更内容を保存し、アプリケーションをビルドして実行します。 新しい色のボタンを表示するか、**ペン**パネルです。 ただし、イベント ハンドラーがまだがないために、このことを使用できません。 次の手順では、色のボタンのイベント ハンドラーを追加する方法を示します。  
  
 [[セクション](#top)]  
  
##  <a name="addcolormember"></a> ドキュメント クラスへの色のメンバーの追加  
 元の Scribble アプリケーションがある色のペン、それらの実装を記述する必要があります。 ドキュメントのペンの色を保存するには、ドキュメント クラスに新しいメンバーを追加します。 `CscribbleDoc.`  
  
#### <a name="to-add-a-color-member-to-the-document-class"></a>ドキュメント クラスに色のメンバーを追加するには  
  
1.  Scribdoc.h、内で、`CScribbleDoc`クラス、検索、`// Attributes`セクションです。 定義の後に、次のコード行を追加、`m_nThickWidth`データ メンバーです。  
  
 '' *//現在のペンの色  
    COLORREF m_penColor です。  
 ```  
  
2.  Every document contains a list of stokes that the user has already drawn. Every stroke is defined by a `CStroke` object. The `CStroke` class does not include information about pen color. Therefore, you must modify the class. In scribdoc.h, in the `CStroke` class, add the following lines of code after the definition of the `m_nPenWidth` data member.  
  
 ``` *// Pen color for the stroke  
    COLORREF m_penColor;  
 ```  
  
3.  Scribdoc.h で追加、新しい`CStroke`コンス トラクターのパラメーターを持つ幅と色を指定します。 次の後のコード行を追加、`CStroke(UINT nPenWidth);`ステートメントです。  
  
 ```  
    CStroke(UINT nPenWidth, COLORREF penColor);

 ```  
  
4.  Scribdoc.cpp での新しい実装を追加`CStroke`コンス トラクターです。 実装後に、次のコードを追加、`CStroke::CStroke(UINT nPenWidth)`コンス トラクターです。  
  
 '' *//のドキュメントを使用するコンス トラクターの現在の幅と色  
    CStroke::CStroke (UINT nPenWidth、COLORREF penColor)  
 {  
    m_nPenWidth nPenWidth; を =  
    m_penColor penColor; を =  
    m_rectBounding.SetRectEmpty() です。

 }  
 ```  
  
5.  Change the second line of the `CStroke::DrawStroke` method as follows.  
  
 ```  
    場合 (! penStroke.CreatePen (きは、m_nPenWidth、m_penColor))  
 ```  
  
6.  Set the default pen color for the document class. In scribdoc.cpp, add the following lines to `CScribbleDoc::InitDocument`, after the `m_nThickWidth = 5;` statement.  
  
 ``` *// default pen color is black  
    m_penColor = RGB(0,
    0,
    0);

 ```  
  
7.  Scribdoc.cpp での最初の行を変更、`CScribbleDoc::NewStroke`には、次のメソッドです。  
  
 ```  
    CStroke* pStrokeItem = new CStroke(m_nPenWidth, m_penColor);

 ```  
  
8.  最後の行の変更、`CScribbleDoc::ReplacePen`には、次のメソッドです。  
  
 ```  
    m_penCur.CreatePen(PS_SOLID,
    m_nPenWidth,
    m_penColor);

 ```  
  
9. 追加する、`m_penColor`前の手順でのメンバーです。 ここで、メンバーを設定する色のボタンのイベント ハンドラーを作成します。  
  
    1.  **リソース ビュー**  ウィンドウで、IDR_SCRIBBTYPE メニュー リソースを開きます。  
  
    2.  右クリックし、**色**メニュー項目をクリック**イベント ハンドラーの追加**です。 **イベント ハンドラー ウィザード**が表示されます。  
  
    3.  **クラス リスト**ウィザードで、選択ボックス**CScribbleDoc**をクリックし、**の追加し、編集**ボタンをクリックします。 これを作成、`CScribbleDoc::OnPenColor`イベント ハンドラーのスタブ。  
  
10. スタブを置換、`CScribbleDoc::OnPenColor`イベント ハンドラーを次のコード。  
  
 ```  
    void CScribbleDoc::OnPenColor()  
 { *// Change pen color to reflect color button's current selection  
    CMFCRibbonBar* pRibbon = ((CMDIFrameWndEx*) AfxGetMainWnd())->GetRibbonBar();
ASSERT_VALID(pRibbon);

 CMFCRibbonColorButton* pColorBtn = DYNAMIC_DOWNCAST(
    CMFCRibbonColorButton, pRibbon->FindByID(ID_PEN_COLOR));

    m_penColor = pColorBtn->GetColor();
*// Create new pen using the selected color  
    ReplacePen();

 }  
 ```  
  
11. 変更を保存し、アプリケーションをビルドして実行します。 色のボタンを押し、ペンの色を変更することができます。  
  
 [[セクション](#top)]  
  
##  <a name="initpensave"></a> 初期化と環境設定の保存  
 次に、ペンの幅と色を初期化します。 最後に、保存し、カラー ファイルから描画を読み込みます。  
  
#### <a name="to-initialize-controls-on-the-ribbon-bar"></a>リボン バーのコントロールを初期化するには  
  
1.  リボン バーのペンを初期化します。  
  
     Scribdoc.cpp に次のコードを追加、`CScribbleDoc::InitDocument`メソッドの後に、`m_sizeDoc = CSize(200,200)`ステートメントです。  
  
 ``` *リボン UI をその初期値 CMFCRibbonBar にリセット*pRibbon = ((CMDIFrameWndEx*) AfxGetMainWnd()) GetRibbonBar();]-> [ASSERT_VALID(pRibbon) です。

 CMFCRibbonColorButton * pColorBtn = DYNAMIC_DOWNCAST (CMFCRibbonColorButton、pRibbon]-> [FindByID(ID_PEN_COLOR)) です。*//Set を黒に ColorButton  
    pColorBtn SetColor RGB (0, 0, 0);]-> [します。

 CMFCRibbonComboBox * pThinComboBox = DYNAMIC_DOWNCAST (CMFCRibbonComboBox、pRibbon]-> [FindByID(ID_PEN_THIN_WIDTH)) です。*/設定/2 のシン ペン コンボ ボックス  
    pThinComboBox SelectItem(1);]-> [します。

 CMFCRibbonComboBox * pThickComboBox = DYNAMIC_DOWNCAST (CMFCRibbonComboBox、pRibbon]-> [FindByID(ID_PEN_THICK_WIDTH)) です。*/設定/5 シック (thick) のペンのコンボ ボックス  
    pThickComboBox SelectItem(0);]-> [します。

 ```  
  
2.  Save a color drawing to a file. Add the following statement to scribdoc.cpp, in the `CStroke::Serialize` method, after the `ar << (WORD)m_nPenWidth;` statement.  
  
 ```  
    ar << (COLORREF) m_penColor です。  
 ```  
  
3.  Finally, load a color drawing from a file. Add the following line of code, in the `CStroke::Serialize` method, after the `m_nPenWidth = w;` statement.  
  
 ```  
    ar >> m_penColor です。  
 ```  
  
4.  Now scribble in color and save your drawing to a file.  
  
 [[Sections](#top)]  
  
## Conclusion  
 You have updated the MFC Scribble application. Use this walkthrough as a guide when you modify your existing applications.  
  
## See Also  
 [Walkthroughs](../mfc/walkthroughs-mfc.md)   
 [Walkthrough: Updating the MFC Scribble Application (Part 1)](../mfc/walkthrough-updating-the-mfc-scribble-application-part-1.md)


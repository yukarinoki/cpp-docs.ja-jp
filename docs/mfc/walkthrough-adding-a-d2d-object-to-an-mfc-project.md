---
title: 'チュートリアル: MFC プロジェクトへの D2D オブジェクトの追加 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- MFC, D2D
- D2D [MFC]
ms.assetid: dda36c33-c231-4da6-a62f-72d69a12b6dd
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7985b36c0eeaa7adf5441a7a6fbb3314bac8353f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="walkthrough-adding-a-d2d-object-to-an-mfc-project"></a>チュートリアル: MFC プロジェクトへの D2D オブジェクトの追加
このチュートリアルで基本 Direct2D を追加する方法について説明 (D2D) が Visual C、Microsoft Foundation Class ライブラリ (MFC) プロジェクトにオブジェクトを出力するアプリケーションに、プロジェクトをビルド「こんにちは, world」グラデーションの背景にします。  
  
 このチュートリアルでは、これらのタスクを実行する方法を示します。  
  
-   MFC アプリケーションを作成します。  
  
-   純色のブラシと線形グラデーション ブラシを作成します。  
  
-   グラデーション ブラシを変更して、変更は適切には、ウィンドウのサイズを変更するとき。  
  
-   D2D 描画ハンドラーを実装します。  
  
-   結果を確認します。  
  
 [!INCLUDE[note_settings_general](../mfc/includes/note_settings_general_md.md)]  
  
## <a name="prerequisites"></a>必須コンポーネント  
 このチュートリアルを完了するには、Visual Studio が必要です。  
  
### <a name="to-create-an-mfc-application"></a>MFC アプリケーションを作成するには  
  
1.  **[ファイル]** メニューの **[新規作成]** をポイントし、 **[プロジェクト]** をクリックします。  
  
2.  **新しいプロジェクト**ダイアログ ボックスの下の左ペインで**インストールされたテンプレート**、展開**Visual C**し、 **MFC**です。 中央のペインで選択**MFC アプリケーション**です。 **[名前]** ボックスに「`MFCD2DWalkthrough`」と入力します。 **[OK]** をクリックします。  
  
3.  **MFC アプリケーション ウィザード**をクリックして**完了**設定を変更せずします。  
  
### <a name="to-create-a-solid-color-brush-and-a-linear-gradient-brush"></a>純色のブラシと線形グラデーション ブラシを作成するには  
  
1.  **ソリューション エクスプ ローラー**で、 **MFCD2DWalkthrough**プロジェクトで、**ヘッダー ファイル**フォルダー、開いている MFCD2DWalkthroughView.h です。 次のコードを追加、 `CMFCD2DWalkthroughView` 3 つのデータ変数を作成するクラス。  
  
 ```  
    CD2DTextFormat* m_pTextFormat;  
    CD2DSolidColorBrush* m_pBlackBrush;  
    CD2DLinearGradientBrush* m_pLinearGradientBrush;  
 ```  
  
     ファイルを保存して閉じます。  
  
2.  **ソースファイル**フォルダー、開いている MFCD2DWalkthroughView.cpp です。 コンス トラクターで、`CMFCD2DWalkthroughView`クラスで、次のコードを追加します。  
  
 '' *//ウィンドウの D2D のサポートを有効にします。  
    EnableD2DSupport() です。

 *//D2D リソースを初期化します。  
    m_pBlackBrush = 新しい CD2DSolidColorBrush(GetRenderTarget()、D2D1::ColorF(D2D1::ColorF::Black)) です。

 
    m_pTextFormat = 新しい CD2DTextFormat(GetRenderTarget()、_T("Verdana")、50) です。

    m_pTextFormat Get()]-> [SetTextAlignment(DWRITE_TEXT_ALIGNMENT_CENTER); ->

 m_pTextFormat Get()]-> [SetParagraphAlignment(DWRITE_PARAGRAPH_ALIGNMENT_CENTER); ->

 
    D2D1_GRADIENT_STOP gradientStops [2]。  
 
    [0] gradientStops .color D2D1::ColorF(D2D1::ColorF::White); を =

    [0] gradientStops .position 0.f; を =  
    [1] gradientStops .color D2D1::ColorF(D2D1::ColorF::Indigo); を =

    [1] gradientStops .position 1.f; を =  
 
    m_pLinearGradientBrush 新しい CD2DLinearGradientBrush(GetRenderTarget()、=   
    gradientStops、ARRAYSIZE(gradientStops)、  
    D2D1::LinearGradientBrushProperties (D2D1::Point2F (0, 0), (0, 0) D2D1::Point2F)) です。

 ```  
  
     Save the file and close it.  
  
### To modify the gradient brush so that it will change appropriately when the window is resized  
  
1.  On the **Project** menu, click **Class Wizard**.  
  
2.  In the **MFC Class Wizard**, under **Class name**, select `CMFCD2DWalkthroughView`.  
  
3.  On the **Messages** tab, in the **Messages** box, select `WM_SIZE` and then click **Add Handler**. This action adds the `OnSize` message handler to the `CMFCD2DWalkthroughView` class.  
  
4.  In the **Existing handlers** box, select `OnSize`. Click **Edit Code** to display the `CMFCD2DWalkthroughView::OnSize` method. At the end of the method, add the following code.  
  
 ```  
    m_pLinearGradientBrush SetEndPoint (CPoint (cx、cy);]-> [します。

 ```  
  
     Save the file and close it.  
  
### To implement a D2D drawing handler  
  
1.  On the **Project** menu, click **Class Wizard**.  
  
2.  In the **MFC Class Wizard**, under **Class name**, select `CMFCD2DWalkthroughView`.  
  
3.  On the **Messages** tab, click **Add Custom Message**.  
  
4.  In the **Add Custom Message** dialog box, in the **Custom Windows Message** box, type `AFX_WM_DRAW2D`. In the **Message handler name** box, type `OnDraw2D`. Select the **Registered Message** option and then click **OK**. This action adds a message handler for the `AFX_WM_DRAW2D` message to the `CMFCD2DWalkthroughView` class.  
  
5.  In the **Existing handlers** box, select `OnDraw2D`. Click **Edit Code** to display the `CMFCD2DWalkthroughView::OnDraw2D` method. Use the following code for the `CMFCD2DWalkthroughView::OnDrawD2D` method.  
  
 ```  
    afx_msg LRESULT CMFCD2DWalkthroughView::OnDraw2D(WPARAM wParam, LPARAM lParam)  
    {  
 CHwndRenderTarget * pRenderTarget (CHwndRenderTarget *) lParam; を =  
    ASSERT_VALID(pRenderTarget) です。

 
    CRect rect です。  
    GetClientRect(rect) です。

 
    pRenderTarget FillRectangle (rect、m_pLinearGradientBrush);]-> [します。

    pRenderTarget DrawText (_T (「こんにちは, World!」)、rect、m_pBlackBrush、m_pTextFormat)]-> [します。

 
    TRUE を返す  
 }  
 ```  
  
     Save the file and close it.  
  
### To verify the results  
  
1.  Build and run the application. It should have a gradient rectangle that changes when you resize the window. “Hello World!” should be displayed in the center of the rectangle.  
  
## See Also  
 [Walkthroughs](../mfc/walkthroughs-mfc.md)


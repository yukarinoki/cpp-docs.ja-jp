---
description: '詳細については、「チュートリアル: MFC プロジェクトへのアニメーションの追加」を参照してください。'
title: 'チュートリアル: MFC プロジェクトへのアニメーションの追加'
ms.date: 04/25/2019
helpviewer_keywords:
- animation [MFC]
- MFC, animation
ms.assetid: 004f832c-9fd5-4f88-9ca9-ae65dececdc2
ms.openlocfilehash: ef6d6fc8e17c8e6dc4c6f0f4e8d7407f2690927f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97143118"
---
# <a name="walkthrough-adding-animation-to-an-mfc-project"></a>チュートリアル: MFC プロジェクトへのアニメーションの追加

このチュートリアルでは、基本的なアニメーションオブジェクトを Visual C++、Microsoft Foundation Class ライブラリ (MFC) プロジェクトに追加する方法について説明します。

このチュートリアルでは、次のタスクを実行する方法について説明します。

- MFC アプリケーションを作成します。

- メニューを追加し、アニメーションを開始および停止するコマンドを追加します。

- Start および stop コマンドのハンドラーを作成します。

- アニメーション化されたオブジェクトをプロジェクトに追加します。

- アニメーション化されたオブジェクトをウィンドウの中央に配置します。

- 結果を確認しましょう。

[!INCLUDE[note_settings_general](../mfc/includes/note_settings_general_md.md)]

## <a name="prerequisites"></a>前提条件

このチュートリアルを完了するには、Visual Studio が必要です。

### <a name="to-create-an-mfc-application"></a>MFC アプリケーションを作成するには

1. Mfc **アプリケーションウィザード** を使用して、mfc アプリケーションを作成します。 お使いのバージョンの Visual Studio のウィザードを開く方法については [、「チュートリアル: 新しい MFC シェルコントロールの使用](walkthrough-using-the-new-mfc-shell-controls.md) 」を参照してください。

1. [ **名前** ] ボックスに「 *Mfcanimationwalkthrough*」と入力します。 **[OK]** をクリックします。

1. [ **MFC アプリケーションウィザード** ] ダイアログボックスで、[ **アプリケーションの種類** ] が [ **複数のドキュメント**]、[ **プロジェクトスタイル** ] が [ **Visual Studio**]、[ **ドキュメント/ビューアーキテクチャのサポート** ] オプションが選択されていることを確認します。 **[完了]** をクリックします。

### <a name="to-add-a-menu-and-then-add-commands-to-start-and-stop-an-animation"></a>メニューを追加し、アニメーションを開始および停止するコマンドを追加するには

1. [ **表示** ] メニューの [ **その他のウィンドウ** ] をポイントし、[ **リソースビュー**] をクリックします。

1. **リソースビュー** で、**メニュー** フォルダーに移動して開きます。 **IDR_MFCAnimationWalkthroughTYPE** リソースをダブルクリックして開き、変更します。

1. メニューバーの [ **ここに入力** ] ボックスに、 *&nimation* を入力して、[アニメーション] メニューを作成します。

1. [ **アニメーション**] の [ **ここに入力** ] ボックスに「 *start &forward* 」と入力して、[開始] コマンドを作成します。

1. [ **開始**] の [ **ここに入力** ] ボックスに「 *start &後方*」と入力します。

1. [ **前に戻る**] の [ **ここに入力** ] ボックスで、「 *S&top* 」と入力して停止コマンドを作成します。

1. MFCAnimationWalkthrough を保存して閉じます。

1. **ソリューションエクスプローラー** で、mainfrm.cpp をダブルクリックして開き、変更します。 メソッドで、の `CMainFrame::OnCreate` 複数の呼び出しを含むセクションを見つけ `lstBasicCommands.AddTail` ます。 そのセクションの直後に、次のコードを追加します。

    ```cpp
    lstBasicCommands.AddTail(ID_ANIMATION_STARTFORWARD);
    lstBasicCommands.AddTail(ID_ANIMATION_STARTBACKWARD);
    lstBasicCommands.AddTail(ID_ANIMATION_STOP);
    ```

1. ファイルを保存して閉じます。

### <a name="to-create-handlers-for-the-start-and-stop-commands"></a>Start および stop コマンドのハンドラーを作成するには

1. [ **プロジェクト** ] メニューの [ **クラスウィザード**] をクリックします。

1. **MFC クラスウィザード** の [**クラス名**] で、[ **CMFCAnimationWalkthroughView**] を選択します。

1. [ **コマンド** ] タブの [ **オブジェクト id** ] ボックスで、[ **ID_ANIMATION_STARTFORWARD**] を選択し、[ **メッセージ** ] ボックスで [ **コマンド**] を選択します。 [ **ハンドラーの追加**] をクリックします。

1. [ **メンバー関数の追加** ] ダイアログボックスで、[ **OK]** をクリックします。

1. [ **オブジェクト id** ] ボックスで [ **ID_ANIMATION_STARTBACKWARD**] を選択し、[ **メッセージ** ] ボックスで [ **コマンド**] を選択します。 [ **ハンドラーの追加**] をクリックします。

1. [ **メンバー関数の追加** ] ダイアログボックスで、[ **OK]** をクリックします。

1. [ **オブジェクト id** ] ボックスで [ **ID_ANIMATION_STOP**] を選択し、[ **メッセージ** ] ボックスで [ **コマンド**] を選択します。 [ **ハンドラーの追加** ] をクリックし、[ **OK**] をクリックします。

1. [ **メンバー関数の追加** ] ダイアログボックスで、[ **OK]** をクリックします。

1. **MFC クラスウィザード** で、[ **OK]** をクリックします。

1. エディターで開かれているが、閉じないで、Mfcanimationのビューを保存します。

### <a name="to-add-an-animated-object-to-the-project"></a>アニメーション化されたオブジェクトをプロジェクトに追加するには

1. **ソリューションエクスプローラー** で、[Mfcanimationウォーク] をダブルクリックして開き、変更します。 クラスの定義の直前に `CMFCAnimationWalkthroughView` 、次のコードを追加して、アニメーションオブジェクトとのスケジュールの競合を処理するカスタムアニメーションコントローラーを作成します。

    ```cpp
    class CCustomAnimationController : public CAnimationController
    {
    public:
        CCustomAnimationController()
        {
        }

        virtual BOOL OnHasPriorityTrim(CAnimationGroup* pGroupScheduled,
            CAnimationGroup* pGroupNew,
            UI_ANIMATION_PRIORITY_EFFECT priorityEffect)
        {
            return TRUE;
        }
    };
    ```

1. クラスの末尾に `CMFCAnimationWalkthroughView` 、次のコードを追加します。

    ```cpp
    CCustomAnimationController m_animationController;
    CAnimationColor m_animationColor;
    CAnimationRect m_animationRect;
    ```

1. 行の後 `DECLARE_MESSAGE_MAP()` に、次のコードを追加します。

    ```cpp
    void Animate(BOOL bDirection);
    ```

1. ファイルを保存して閉じます。

1. ファイルの先頭で、ステートメントの後、クラスメソッドの前に、次のコードを追加して、Mfcanimationウォークを実行します。 `#include`

    ```cpp
    static int nAnimationGroup = 0;
    static int nInfoAreaHeight = 40;
    ```

1. のコンストラクターの末尾に `CMFCAnimationWalkthroughView` 、次のコードを追加します。

    ```cpp
    m_animationController.EnableAnimationTimerEventHandler();
    m_animationController.EnablePriorityComparisonHandler(UI_ANIMATION_PHT_TRIM);
    m_animationColor = RGB(255, 255, 255);
    m_animationRect = CRect(0, 0, 0, 0);
    m_animationColor.SetID(-1, nAnimationGroup);
    m_animationRect.SetID(-1, nAnimationGroup);
    m_animationController.AddAnimationObject(&m_animationColor);
    m_animationController.AddAnimationObject(&m_animationRect);
    ```

1. メソッドを見つけ `CAnimationWalthroughView::PreCreateWindow` て、次のコードに置き換えます。

    ```cpp
    BOOL CMFCAnimationWalkthroughView::PreCreateWindow(CREATESTRUCT& cs)
    {
        // TODO: Modify the Window class or styles here by modifying
        //       the CREATESTRUCT cs
        m_animationController.SetRelatedWnd(this);

        return CView::PreCreateWindow(cs);
    }
    ```

1. メソッドを見つけ `CAnimationWalkthroughView::OnDraw` て、次のコードに置き換えます。

    ```cpp
    void CMFCAnimationWalkthroughView::OnDraw(CDC* pDC)
    {
        CMFCAnimationWalkthroughDoc* pDoc = GetDocument();
        ASSERT_VALID(pDoc);
        if (!pDoc)
            return;

        // TODO: add draw code for native data here
        CMemDC dcMem(*pDC, this);
        CDC& dc = dcMem.GetDC();
        CRect rect;
        GetClientRect(rect);

        dc.FillSolidRect(rect, GetSysColor(COLOR_WINDOW));

        CString strRGB;
        strRGB.Format(_T("Fill Color is: %d; %d; %d"),
            GetRValue(m_animationColor),
            GetGValue(m_animationColor),
            GetBValue(m_animationColor));

        dc.DrawText(strRGB, rect, DT_CENTER);
        rect.top += nInfoAreaHeight;

        CBrush br;
        br.CreateSolidBrush(m_animationColor);
        CBrush* pBrushOld = dc.SelectObject(&br);

        dc.Rectangle((CRect)m_animationRect);

        dc.SelectObject(pBrushOld);
    }
    ```

1. ファイルの末尾に、次のコードを追加します。

    ```cpp
    void CMFCAnimationWalkthroughView::Animate(BOOL bDirection)
    {
        static UI_ANIMATION_SECONDS duration = 3;
        static DOUBLE dblSpeed = 35.;
        static BYTE nStartColor = 50;
        static BYTE nEndColor = 255;

        BYTE nRedColorFinal = bDirection ? nStartColor : nEndColor;
        BYTE nGreenColorFinal = bDirection ? nStartColor : nEndColor;
        BYTE nBlueColorFinal = bDirection ? nStartColor : nEndColor;

        CLinearTransition* pRedTransition =
            new CLinearTransition(duration, (DOUBLE)nRedColorFinal);

        CSmoothStopTransition* pGreenTransition =
            new CSmoothStopTransition(duration, (DOUBLE)nGreenColorFinal);

        CLinearTransitionFromSpeed* pBlueTransition =
            new CLinearTransitionFromSpeed(dblSpeed, (DOUBLE)nBlueColorFinal);

        m_animationColor.AddTransition(pRedTransition,
            pGreenTransition,
            pBlueTransition);

        CRect rectClient;
        GetClientRect(rectClient);

        rectClient.top += nInfoAreaHeight;

        int nLeftFinal = bDirection ? rectClient.left : rectClient.CenterPoint().x;
        int nTopFinal = bDirection ? rectClient.top : rectClient.CenterPoint().y;
        int nRightFinal = bDirection ? rectClient.right : rectClient.CenterPoint().x;
        int nBottomFinal = bDirection ? rectClient.bottom : rectClient.CenterPoint().y;

        CLinearTransition* pLeftTransition =
            new CLinearTransition(duration, nLeftFinal);

        CLinearTransition* pTopTransition =
            new CLinearTransition(duration, nTopFinal);

        CLinearTransition* pRightTransition =
            new CLinearTransition(duration, nRightFinal);

        CLinearTransition* pBottomTransition =
            new CLinearTransition(duration, nBottomFinal);

        m_animationRect.AddTransition(pLeftTransition,
            pTopTransition,
            pRightTransition,
            pBottomTransition);

        CBaseKeyFrame* pKeyframeStart =
            CAnimationController::GetKeyframeStoryboardStart();
        CKeyFrame* pKeyFrameEnd =
            m_animationController.CreateKeyframe(nAnimationGroup,
                pBlueTransition);

        pLeftTransition->SetKeyframes(pKeyframeStart, pKeyFrameEnd);
        pTopTransition->SetKeyframes(pKeyframeStart, pKeyFrameEnd);
        pRightTransition->SetKeyframes(pKeyframeStart, pKeyFrameEnd);
        pBottomTransition->SetKeyframes(pKeyframeStart, pKeyFrameEnd);

        m_animationController.AnimateGroup(nAnimationGroup);
    }
    ```

1. [ **プロジェクト** ] メニューの [ **クラスウィザード**] をクリックします。

1. **MFC クラスウィザード** の [**クラス名**] で、[ **CMFCAnimationWalkthroughView**] を選択します。

1. [ **メッセージ** ] タブの [ **メッセージ** ] ボックスで [ **WM_ERASEBKGND**] を選択し、[ **ハンドラーの追加**] をクリックして、[ **OK**] をクリックします。

1. 次のように、の実装を次のコードに置き換えて、アニメーション化されたオブジェクトが再描画され `OnEraseBkgnd` たときのちらつきを減らします。

    ```cpp
    BOOL CMFCAnimationWalkthroughView::OnEraseBkgnd(CDC* /*pDC*/)
    {
        return TRUE;
    }
    ```

1. `CMFCAnimationWalkthroughView::OnAnimationStartforward`、、およびの実装を `CMFCAnimationWalkthroughView::OnAnimationStartbackward` 次の `CMFCAnimationWalkthroughView::OnAnimationStop` コードに置き換えます。

    ```cpp
    void CMFCAnimationWalkthroughView::OnAnimationStartforward()
    {
        Animate(TRUE);
    }

    void CMFCAnimationWalkthroughView::OnAnimationStartbackward()
    {
        Animate(FALSE);
    }

    void CMFCAnimationWalkthroughView::OnAnimationStop()
    {
        IUIAnimationManager* pManager = m_animationController.GetUIAnimationManager();
        if (pManager != NULL)
        {
            pManager->AbandonAllStoryboards();

        }
    }
    ```

1. ファイルを保存して閉じます。

### <a name="to-center-the-animated-object-in-the-window"></a>アニメーション化されたオブジェクトをウィンドウの中央に配置するには

1. **ソリューションエクスプローラー** で、[Mfcanimationウォーク] をダブルクリックして開き、変更します。 クラスの末尾に、 `CMFCAnimationWalkthroughView` の定義の直後に `m_animationRect` 、次のコードを追加します。

    ```cpp
    BOOL m_bCurrentDirection;
    ```

1. ファイルを保存して閉じます。

1. [ **プロジェクト** ] メニューの [ **クラスウィザード**] をクリックします。

1. **MFC クラスウィザード** の [**クラス名**] で、[ **CMFCAnimationWalkthroughView**] を選択します。

1. [ **メッセージ** ] タブの [ **メッセージ** ] ボックスで [ **WM_SIZE**] を選択し、[ **ハンドラーの追加**] をクリックして、[ **OK**] をクリックします。

1. 次のコードを使用して、のコードを次のコードに置き換えます。 `CMFCAnimationWalkthroughView::OnSize`

    ```cpp
    void CMFCAnimationWalkthroughView::OnSize(UINT nType, int cx, int cy)
    {
        CView::OnSize(nType, cx, cy);
        CRect rect;
        GetClientRect(rect);

        rect.top += nInfoAreaHeight;

        CRect rectAnim = m_animationRect;
        m_animationRect = CRect(CPoint(rect.CenterPoint().x - rectAnim.Width() / 2,
        rect.CenterPoint().y - rectAnim.Height() / 2),
        rectAnim.Size());

        if (m_animationController.IsAnimationInProgress())
        {
            Animate(m_bCurrentDirection);
        }
    }
    ```

1. のコンストラクターの先頭に `CMFCAnimationWalkthroughView` 、次のコードを追加します。

    ```cpp
    m_bCurrentDirection = TRUE;
    ```

1. メソッドの先頭に `CMFCAnimationWalkthroughView::Animate` 、次のコードを追加します。

    ```cpp
    m_bCurrentDirection = bDirection;
    ```

1. ファイルを保存して閉じます。

### <a name="to-verify-the-results"></a>結果を確認するには

1. アプリケーションをビルドして実行します。 [ **アニメーション** ] メニューの [ **前面へ** 移動] をクリックします。 四角形が表示され、中央の領域が塗りつぶされます。 [ **戻る**] をクリックすると、アニメーションが反転され、[ **停止**] をクリックすると停止します。 アニメーションの進行に合わせて四角形の塗りつぶしの色が変化し、現在の色がアニメーションウィンドウの上部に表示されます。

## <a name="see-also"></a>関連項目

[チュートリアル](../mfc/walkthroughs-mfc.md)

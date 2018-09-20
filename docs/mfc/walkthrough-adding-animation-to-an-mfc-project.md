---
title: 'チュートリアル: MFC プロジェクトへのアニメーションの追加 |Microsoft Docs'
ms.custom: ''
ms.date: 06/28/2018
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- animation [MFC]
- MFC, animation
ms.assetid: 004f832c-9fd5-4f88-9ca9-ae65dececdc2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: dfcab237070b401d78c3fc52fc765930272832da
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46439277"
---
# <a name="walkthrough-adding-animation-to-an-mfc-project"></a>チュートリアル: MFC プロジェクトへのアニメーションの追加

このチュートリアルでは、Visual C、Microsoft Foundation Class ライブラリ (MFC) プロジェクトを基本的なアニメーション化されたオブジェクトを追加する方法について説明します。

このチュートリアルでは、これらのタスクを実行する方法を示します。

- MFC アプリケーションを作成します。

- メニューを追加し、コマンドを開始およびアニメーションを停止します。

- Start および stop コマンドのハンドラーを作成します。

- アニメーション化するオブジェクトをプロジェクトに追加します。

- センター ウィンドウでアニメーション化するオブジェクト。

- 結果を確認します。

[!INCLUDE[note_settings_general](../mfc/includes/note_settings_general_md.md)]

## <a name="prerequisites"></a>必須コンポーネント

このチュートリアルを完了するには、Visual Studio が必要です。

### <a name="to-create-an-mfc-application"></a>MFC アプリケーションを作成するには

1. **[ファイル]** メニューの **[新規作成]** をポイントし、 **[プロジェクト]** をクリックします。

2. **新しいプロジェクト** ダイアログ ボックスで、下の左ペインで**インストールされたテンプレート**、展開**Visual C**選び**MFC**。 中央のペインで選択**MFC アプリケーション**します。 **名前**ボックスに「 *MFCAnimationWalkthrough*します。 **[OK]** をクリックします。

3. **MFC アプリケーション ウィザード** ダイアログ ボックスで、いることを確認**アプリケーションの種類**は**複数のドキュメント**、**プロジェクト スタイル**は、**Visual Studio**、および**ドキュメント/ビュー アーキテクチャ サポート**オプションを選択します。 **[完了]** をクリックします。

### <a name="to-add-a-menu-and-then-add-commands-to-start-and-stop-an-animation"></a>メニューを追加し、開始およびアニメーションを停止するコマンドを追加するには

1. **ビュー**メニューで、**その他の Windows**  をクリックし、**リソース ビュー**します。

2. **リソース ビュー**に移動し、**メニュー**フォルダーを開きます。 ダブルクリックして、`IDR_MFCAnimationWalTYPE`リソース変更用に開きます。

3. メニュー バーで、**ここへ入力**ボックスに「 *& nimation*アニメーション メニューを作成します。

4. **アニメーション**の**ここへ入力**ボックスに「*開始 (&) 転送*フォワード開始コマンドを作成します。

5. **フォワード開始**の**ここへ入力**ボックスに「*の開始日と下位*します。

6. **旧バージョンと開始**の**ここへ入力**ボックスに「 *S (& t)* を停止するコマンドを作成しますします。

7. MFCAnimationWalkthrough.rc を保存して閉じます。

8. **ソリューション エクスプ ローラー**変更用に開きます MainFrm.cpp をダブルクリックします。 `CMainFrame::OnCreate`メソッドへのいくつかの呼び出しがあるセクションを見つけます`lstBasicCommands.AddTail`します。 このセクションでは、直後後には、次のコードを追加します。

    ```cpp
    lstBasicCommands.AddTail(ID_ANIMATION_STARTFORWARD);
    lstBasicCommands.AddTail(ID_ANIMATION_STARTBACKWARD);
    lstBasicCommands.AddTail(ID_ANIMATION_STOP);
    ```

9. ファイルを保存して閉じます。

### <a name="to-create-handlers-for-the-start-and-stop-commands"></a>最初のハンドラーを作成し、コマンドを停止するには

1. **プロジェクト** メニューのをクリックして**クラス ウィザード**します。

2. **MFC クラス ウィザード****クラス名**、 `CMFCAnimationWalkthroughView`。

3. **コマンド** タブで、**オブジェクト Id**ボックスで、 `ID_ANIMATION_STARTFORWARD`、し、**メッセージ**ボックスで、`COMMAND`します。 クリックして**ハンドラーを追加**します。

4. **メンバー関数を追加**ダイアログ ボックスで、をクリックして**OK**。

5. **オブジェクト Id**ボックスで、 `ID_ANIMATION_STARTBACKWARD`、し、**メッセージ**ボックスで、`COMMAND`します。 クリックして**ハンドラーを追加**します。

6. **メンバー関数を追加**ダイアログ ボックスで、をクリックして**OK**。

7. **オブジェクト Id**ボックスで、 `ID_ANIMATION_STOP`、し、**メッセージ**ボックスで、`COMMAND`します。 クリックして**ハンドラーの追加**順にクリックします**OK**します。

8. **メンバー関数を追加**ダイアログ ボックスで、をクリックして**OK**。

9. **MFC クラス ウィザード**、 をクリックして**OK**します。

10. MFCAnimationWalkthroughView.cpp、これは、エディターで開く、保存しますが、終了しません。

### <a name="to-add-an-animated-object-to-the-project"></a>アニメーション化するオブジェクトをプロジェクトに追加するには

1. ソリューション エクスプ ローラーで、変更用に開きます MFCAnimationWalkthroughView.h をダブルクリックします。 定義の直前に、`CMFCAnimationWalkthroughView`クラスでのアニメーション オブジェクトとスケジュールの競合を処理するカスタム アニメーション コント ローラーを作成するには、次のコードを追加します。

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

2. 最後に、`CMFCAnimationWalkthroughView`クラスで、次のコードを追加します。

    ```cpp
    CCustomAnimationController m_animationController;
    CAnimationColor m_animationColor;
    CAnimationRect m_animationRect;
    ```

3. 後に、`DECLARE_MESSAGE_MAP()`行に、次のコードを追加します。

    ```cpp
    void Animate(BOOL bDirection);
    ```

4. ファイルを保存して閉じます。

5. 後のファイルの上部にある、MFCAnimationWalkthroughView.cpp で、`#include`ステートメントがいずれかのクラスのメソッドでは、前に、次のコードを追加します。

    ```cpp
    static int nAnimationGroup = 0;
    static int nInfoAreaHeight = 40;
    ```

6. コンス トラクターの末尾に`CMFCAnimationWalkthroughView`、次のコードを追加します。

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

7. 検索、`CAnimationWalthroughView::PreCreateWindow`メソッドと、次のコードに置き換えます。

    ```cpp
    BOOL CMFCAnimationWalkthroughView::PreCreateWindow(CREATESTRUCT& cs)
    {
        // TODO: Modify the Window class or styles here by modifying
        //       the CREATESTRUCT cs
        m_animationController.SetRelatedWnd(this);

        return CView::PreCreateWindow(cs);
    }
    ```

8. 検索、`CAnimationWalkthroughView::OnDraw`メソッドと、次のコードに置き換えます。

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

9. ファイルの末尾には、次のコードを追加します。

    ```cpp
    void CMFCAnimationWalkthroughView::Animate(BOOL bDirection)
    {
        static UI_ANIMATION_SECONDS duration = 3;
        static DOUBLE dblSpeed = 35.;
        static BYTE nStartColor = 50;
        static BYTE nEndColor = 255;

        BYTE nRedColorFinal = bDirection  nStartColor : nEndColor;
        BYTE nGreenColorFinal = bDirection  nStartColor : nEndColor;
        BYTE nBlueColorFinal = bDirection  nStartColor : nEndColor;

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

10. **プロジェクト** メニューのをクリックして**クラス ウィザード**します。

11. **MFC クラス ウィザード****クラス名**、 `CMFCAnimationWalkthroughView`。

12. **メッセージ** タブで、**メッセージ**ボックスで、 `WM_ERASEBKGND`、 をクリックして**ハンドラーの追加**、順にクリックします**OK**。

13. MFCAnimationWalkthroughView.cpp での実装を置き換える`OnEraseBkgnd`を次のコードが再描画されるときにアニメーション化されたオブジェクトのちらつきを軽減します。

    ```cpp
    BOOL CMFCAnimationWalkthroughView::OnEraseBkgnd(CDC* /*pDC*/)
    {
        return TRUE;
    }
    ```

14. 実装を置き換える`CMFCAnimationWalkthroughView::OnAnimationStartforward`、 `CMFCAnimationWalkthroughView::OnAnimationStartbackward`、および`CMFCAnimationWalkthroughView::OnAnimationStop`を次のコード。

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

15. ファイルを保存して閉じます。

### <a name="to-center-the-animated-object-in-the-window"></a>ウィンドウのアニメーション化されたオブジェクトを中央に

1. **ソリューション エクスプ ローラー**変更用に開きます MFCAnimationWalkthroughView.h をダブルクリックします。 最後に、`CMFCAnimationWalkthroughView`クラスの定義の直後後`m_animationRect`、次のコードを追加します。

    ```cpp
    BOOL m_bCurrentDirection;
    ```

2. ファイルを保存して閉じます。

3. **プロジェクト** メニューのをクリックして**クラス ウィザード**します。

4. **MFC クラス ウィザード****クラス名**、 `CMFCAnimationWalkthroughView`。

5. **メッセージ** タブで、**メッセージ**ボックスで、 `WM_SIZE`、 をクリックして**ハンドラーの追加**、順にクリックします**OK**。

6. MFCAnimationWalkthroughView.cpp でのコードに書き換えます`CMFCAnimationWalkthroughView::OnSize`を次のコード。

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

7. コンス トラクターの先頭に`CMFCAnimationWalkthroughView`、次のコードを追加します。

    ```cpp
    m_bCurrentDirection = TRUE;
    ```

8. 先頭に、`CMFCAnimationWalkthroughView::Animate`メソッドでは、次のコードを追加します。

    ```cpp
    m_bCurrentDirection = bDirection;
    ```

9. ファイルを保存して閉じます。

### <a name="to-verify-the-results"></a>結果を確認するには

1. アプリケーションをビルドして実行します。 **アニメーション** メニューのをクリックして**フォワード開始**します。 四角形が表示され、中央の領域を入力する必要があります。 クリックすると**開始旧バージョンと**、アニメーションが反転する必要があります、およびクリックすると**停止**、それを停止する必要があります。 四角形の塗りつぶしの色をアニメーションの進行に合わせて変更する必要があり、アニメーションをウィンドウの上部にある現在の色を表示する必要があります。

## <a name="see-also"></a>関連項目

[チュートリアル](../mfc/walkthroughs-mfc.md)

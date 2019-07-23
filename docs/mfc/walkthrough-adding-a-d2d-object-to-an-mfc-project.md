---
title: 'チュートリアル: MFC プロジェクトへの D2D オブジェクトの追加'
ms.date: 04/25/2019
helpviewer_keywords:
- MFC, D2D
- D2D [MFC]
ms.assetid: dda36c33-c231-4da6-a62f-72d69a12b6dd
ms.openlocfilehash: 5710add59c0e5d27b2969ae22087533cae901ca9
ms.sourcegitcommit: 283cb64fd7958a6b7fbf0cd8534de99ac8d408eb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64558174"
---
# <a name="walkthrough-adding-a-d2d-object-to-an-mfc-project"></a>チュートリアル: MFC プロジェクトへの D2D オブジェクトの追加

このチュートリアルは、基本的な Direct2D を追加する方法を説明します (D2D) Visual c、Microsoft Foundation Class ライブラリ (MFC) プロジェクトでは、オブジェクトし、を出力するアプリケーションにプロジェクトをビルドし、"Hello, World!"のグラデーションの背景。

このチュートリアルでは、これらのタスクを実行する方法を示します。

- MFC アプリケーションを作成します。

- 単色のブラシと線形グラデーション ブラシを作成します。

- これが変化するように適切には、ウィンドウのサイズを変更するときに、グラデーション ブラシを変更します。

- D2D 描画ハンドラーを実装します。

- 結果を確認します。

[!INCLUDE[note_settings_general](../mfc/includes/note_settings_general_md.md)]

## <a name="prerequisites"></a>必須コンポーネント

このチュートリアルを完了するには Visual Studio をインストールが必要、 **C++ によるデスクトップ開発**ワークロードと省略可能な**x86 および x64 用 Visual C MFC**コンポーネント。

## <a name="to-create-an-mfc-application"></a>MFC アプリケーションを作成するには

1. 使用して、 **MFC アプリケーション ウィザード**MFC アプリケーションを作成します。 「[チュートリアル:新しい MFC シェル コントロールを使用して](walkthrough-using-the-new-mfc-shell-controls.md)Visual Studio のバージョンのウィザードを開く方法の詳細について。

1. **名前**ボックスに「 *MFCD2DWalkthrough*します。 **[OK]** をクリックします。

1. **MFC アプリケーション ウィザード**、選択**完了**すべての設定を変更することがなく。

## <a name="to-create-a-solid-color-brush-and-a-linear-gradient-brush"></a>単色のブラシと線形グラデーション ブラシを作成するには

1. **ソリューション エクスプ ローラー**の**MFCD2DWalkthrough**プロジェクトの**ヘッダー ファイル**フォルダー、開いている MFCD2DWalkthroughView.h します。 このコードを追加、`CMFCD2DWalkthroughView`データの 3 つの変数を作成するクラス。

   ```cpp
   CD2DTextFormat* m_pTextFormat;
   CD2DSolidColorBrush* m_pBlackBrush;
   CD2DLinearGradientBrush* m_pLinearGradientBrush;
   ```

   ファイルを保存して閉じます。

1. **ソースファイル**フォルダー、開いている MFCD2DWalkthroughView.cpp します。 コンス トラクターで、`CMFCD2DWalkthroughView`クラスでこのコードを追加します。

   ```cpp
   // Enable D2D support for this window:
   EnableD2DSupport();

   // Initialize D2D resources:
   m_pBlackBrush = new CD2DSolidColorBrush(
       GetRenderTarget(),
       D2D1::ColorF(D2D1::ColorF::Black));

   m_pTextFormat = new CD2DTextFormat(
       GetRenderTarget(),
       _T("Verdana"),
       50);

   m_pTextFormat->Get()->SetTextAlignment(
       DWRITE_TEXT_ALIGNMENT_CENTER);

   m_pTextFormat->Get()->SetParagraphAlignment(
       DWRITE_PARAGRAPH_ALIGNMENT_CENTER);

   D2D1_GRADIENT_STOP gradientStops[2];

   gradientStops[0].color =
       D2D1::ColorF(D2D1::ColorF::White);

   gradientStops[0].position = 0.f;
   gradientStops[1].color =
       D2D1::ColorF(D2D1::ColorF::Indigo);

   gradientStops[1].position = 1.f;

   m_pLinearGradientBrush = new CD2DLinearGradientBrush(
       GetRenderTarget(),
       gradientStops,
       ARRAYSIZE(gradientStops),
       D2D1::LinearGradientBrushProperties(
           D2D1::Point2F(0,0),
           D2D1::Point2F(0,0)));
   ```

   ファイルを保存して閉じます。

## <a name="to-modify-the-gradient-brush-so-that-it-will-change-appropriately-when-the-window-is-resized"></a>これが変化するように適切にウィンドウのサイズを変更すると、グラデーション ブラシを変更するには

1. **プロジェクト**] メニューの [選択**クラス ウィザード**します。

1. **MFC クラス ウィザード****クラス名**、 `CMFCD2DWalkthroughView`。

1. **メッセージ** タブで、**メッセージ**ボックスで、`WM_SIZE`選び、**ハンドラーの追加**します。 このアクションを追加、`OnSize`メッセージ ハンドラーを`CMFCD2DWalkthroughView`クラス。

1. **既存のハンドラー**ボックスで、`OnSize`します。 選択**コードの編集**を表示する、`CMFCD2DWalkthroughView::OnSize`メソッド。 メソッドの末尾には、次のコードを追加します。

   ```cpp
   m_pLinearGradientBrush->SetEndPoint(CPoint(cx, cy));
   ```

   ファイルを保存して閉じます。

## <a name="to-implement-a-d2d-drawing-handler"></a>D2D 描画ハンドラーを実装するには

1. **プロジェクト**] メニューの [選択**クラス ウィザード**します。

1. **MFC クラス ウィザード****クラス名**、 `CMFCD2DWalkthroughView`。

1. **メッセージ** タブで、選択**カスタム メッセージの追加**します。

1. **カスタム メッセージの追加** ダイアログ ボックスで、**カスタム Windows メッセージ**ボックスに「 *AFX_WM_DRAW2D*します。 **メッセージ ハンドラー名**ボックスに「 *OnDraw2D*します。 選択、**登録メッセージ**オプションを選び、 **OK**。 この操作に AFX_WM_DRAW2D メッセージのメッセージ ハンドラーの追加、`CMFCD2DWalkthroughView`クラス。

1. **既存のハンドラー**ボックスで、`OnDraw2D`します。 選択**コードの編集**を表示する、`CMFCD2DWalkthroughView::OnDraw2D`メソッド。 このコードを使用して、`CMFCD2DWalkthroughView::OnDrawD2D`メソッド。

   ```cpp
   afx_msg LRESULT CMFCD2DWalkthroughView::OnDraw2D(
       WPARAM wParam,
       LPARAM lParam)
   {
       CHwndRenderTarget* pRenderTarget = (CHwndRenderTarget*)lParam;
       ASSERT_VALID(pRenderTarget);

       CRect rect;
       GetClientRect(rect);

       pRenderTarget->FillRectangle(rect, m_pLinearGradientBrush);

       pRenderTarget->DrawText(
           _T("Hello, World!"),
           rect,
           m_pBlackBrush,
           m_pTextFormat);

       return TRUE;
   }
   ```

   ファイルを保存して閉じます。

## <a name="to-verify-the-results"></a>結果を確認するには

アプリケーションをビルドして実行します。 ウィンドウのサイズを変更するときに変化するグラデーションの四角形が必要です。 "Hello World!" 四角形の中央に表示されます。

## <a name="see-also"></a>関連項目

[チュートリアル](../mfc/walkthroughs-mfc.md)

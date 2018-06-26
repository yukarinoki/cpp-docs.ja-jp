---
title: 'チュートリアル: MFC プロジェクトへの D2D オブジェクトの追加 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/19/2018
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
ms.openlocfilehash: 68a6d5a0cda8c4d7fd06cf7bb6b9c1b60e50374b
ms.sourcegitcommit: 301bb19056e5bae84ff50f7d1df1e546efe225ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/21/2018
ms.locfileid: "36306009"
---
# <a name="walkthrough-adding-a-d2d-object-to-an-mfc-project"></a>チュートリアル: MFC プロジェクトへの D2D オブジェクトの追加

このチュートリアルで基本 Direct2D を追加する方法について説明 (D2D) が Visual C、Microsoft Foundation Class ライブラリ (MFC) プロジェクトにオブジェクトを出力するアプリケーションに、プロジェクトをビルド「こんにちは, world」グラデーションの背景にします。

このチュートリアルでは、これらのタスクを実行する方法を示します。

- MFC アプリケーションを作成します。

- 純色のブラシと線形グラデーション ブラシを作成します。

- グラデーション ブラシを変更して、変更は適切には、ウィンドウのサイズを変更するとき。

- D2D 描画ハンドラーを実装します。

- 結果を確認します。

[!INCLUDE[note_settings_general](../mfc/includes/note_settings_general_md.md)]

## <a name="prerequisites"></a>必須コンポーネント

このチュートリアルを完了するには Visual Studio のインストールが必要、 **C++ を使用したデスクトップ開発**ワークロードと省略可能な**x86 と x64 用の Visual C MFC**コンポーネントです。

## <a name="to-create-an-mfc-application"></a>MFC アプリケーションを作成するには

1. **ファイル** メニューのをポイント**新規**を選択し**プロジェクト**です。

2. **新しいプロジェクト**ダイアログ ボックスの下の左ペインで**インストールされたテンプレート**、展開**Visual C**し、 **MFC**です。 中央のペインで選択**MFC アプリケーション**です。 **[名前]** ボックスに「`MFCD2DWalkthrough`」と入力します。 **[OK]** をクリックします。

3. **MFC アプリケーション ウィザード**、選択**完了**設定を変更せずします。

## <a name="to-create-a-solid-color-brush-and-a-linear-gradient-brush"></a>純色のブラシと線形グラデーション ブラシを作成するには

1. **ソリューション エクスプ ローラー**で、 **MFCD2DWalkthrough**プロジェクトで、**ヘッダー ファイル**フォルダー、開いている MFCD2DWalkthroughView.h です。 このコードを追加、 `CMFCD2DWalkthroughView` 3 つのデータ変数を作成するクラス。

   ```cpp
   CD2DTextFormat* m_pTextFormat;
   CD2DSolidColorBrush* m_pBlackBrush;
   CD2DLinearGradientBrush* m_pLinearGradientBrush;
   ```

   ファイルを保存して閉じます。

2. **ソースファイル**フォルダー、開いている MFCD2DWalkthroughView.cpp です。 コンス トラクターで、`CMFCD2DWalkthroughView`クラスで、このコードを追加します。

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

## <a name="to-modify-the-gradient-brush-so-that-it-will-change-appropriately-when-the-window-is-resized"></a>変更は適切には、ウィンドウのサイズを変更するときになるようにグラデーション ブラシを変更するには

1. **プロジェクト**] メニューの [選択**クラス ウィザード**です。

2. **MFC クラス ウィザード****クラス名**`CMFCD2DWalkthroughView`です。

3. **メッセージ** タブで、**メッセージ**ボックスで、`WM_SIZE`を選択し**ハンドラーの追加**です。 この操作は追加、`OnSize`メッセージ ハンドラーを`CMFCD2DWalkthroughView`クラスです。

4. **既存ハンドラー**ボックスで、`OnSize`です。 選択**コードの編集**を表示する、`CMFCD2DWalkthroughView::OnSize`メソッドです。 メソッドの最後に、次のコードを追加します。

   ```cpp
   m_pLinearGradientBrush->SetEndPoint(CPoint(cx, cy));
   ```

   ファイルを保存して閉じます。

## <a name="to-implement-a-d2d-drawing-handler"></a>D2D 描画ハンドラーを実装するには

1. **プロジェクト**] メニューの [選択**クラス ウィザード**です。

2. **MFC クラス ウィザード****クラス名**`CMFCD2DWalkthroughView`です。

3. **メッセージ** タブで、選択**カスタム メッセージの追加**です。

4. **カスタム メッセージの追加** ダイアログ ボックスで、**カスタム Windows メッセージ**ボックスに、入力`AFX_WM_DRAW2D`です。 **メッセージ ハンドラー名**ボックスに、入力`OnDraw2D`です。 選択、**登録メッセージ**を選択し**OK**です。 この操作用のメッセージ ハンドラーの追加、`AFX_WM_DRAW2D`メッセージごとに、`CMFCD2DWalkthroughView`クラスです。

5. **既存ハンドラー**ボックスで、`OnDraw2D`です。 選択**コードの編集**を表示する、`CMFCD2DWalkthroughView::OnDraw2D`メソッドです。 このコードを使用して、`CMFCD2DWalkthroughView::OnDrawD2D`メソッド。

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

- アプリケーションをビルドして実行します。 ウィンドウのサイズを変更するときに変化するグラデーションの四角形が必要です。 "Hello World!" 四角形の中央に表示されます。

## <a name="see-also"></a>関連項目

- [チュートリアル](../mfc/walkthroughs-mfc.md)

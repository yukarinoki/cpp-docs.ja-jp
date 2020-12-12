---
description: '詳細については、「方法: Windows フォームコントロールのプロパティとメソッドを呼び出す」を参照してください。'
title: '方法: Windows フォーム コントロールのプロパティとメソッドを呼び出す'
ms.custom: get-started-article
ms.date: 11/04/2016
helpviewer_keywords:
- method calls, Windows Forms
- calling methods, Windows Forms control
- calling properties, Windows Forms control
- Windows Forms controls [C++], methods
- calling properties
- Windows Forms controls [C++], properties
ms.assetid: 6e647d8a-fdaa-4aa1-b3fe-04f15cff8eb3
ms.openlocfilehash: a797084a28eefec27699814a09c8521da7460bc7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97268406"
---
# <a name="how-to-call-properties-and-methods-of-the-windows-forms-control"></a>方法: Windows フォーム コントロールのプロパティとメソッドを呼び出す

[CWinFormsView:: GetControl](../mfc/reference/cwinformsview-class.md#getcontrol)はへのポインターを返すため、へ <xref:System.Windows.Forms.Control?displayProperty=fullName> のポインターではなく、 `WindowsControlLibrary1::UserControl1` ユーザーコントロール型のメンバーを追加して、 [IView:: OnInitialUpdate](../mfc/reference/iview-interface.md#oninitialupdate)で初期化することをお勧めします。 を使用してメソッドとプロパティを呼び出すことができるようになりました `m_ViewControl` 。

このトピックでは、「 [方法: ダイアログボックスにユーザーコントロールとホストを作成](../dotnet/how-to-create-the-user-control-and-host-in-a-dialog-box.md) する」および「 [方法: ユーザーコントロールを作成して MDI ビューをホスト](../dotnet/how-to-create-the-user-control-and-host-mdi-view.md)する」を既に完了していることを前提としています。

### <a name="to-create-the-mfc-host-application"></a>MFC ホスト アプリケーションを作成するには

1. [「方法: ユーザーコントロールを作成し、MDI ビューをホスト](../dotnet/how-to-create-the-user-control-and-host-mdi-view.md)する」で作成した MFC アプリケーションを開きます。

1. MFC02View のクラス宣言のパブリックオーバーライドセクションに、次の行を追加 `CMFC02View` します。

   `gcroot<WindowsFormsControlLibrary1::UserControl1 ^> m_ViewControl;`

1. OnInitialupdate の上書きを追加します。

   [ **プロパティ** ] ウィンドウ (F4) を表示します。 **クラスビュー** (CTRL + SHIFT + C) で、[CMFC02View クラス] を選択します。 [ **プロパティ** ] ウィンドウで、[上書き] のアイコンを選択します。 OnInitialUpdate に一覧を表示します。 ドロップダウンリストをクリックし、を選択し \<Add> ます。 MFC02View にあります。 OnInitialUpdate 関数の本体が次のようになっていることを確認します。

    ```
    CWinFormsView::OnInitialUpdate();
    m_ViewControl = safe_cast<WindowsFormsControlLibrary1::UserControl1 ^>(this->GetControl());
    m_ViewControl->textBox1->Text = gcnew System::String("hi");
    ```

1. プロジェクトをビルドして実行します。

   **[ビルド]** メニューの **[ソリューションのビルド]** をクリックします。

   [ **デバッグ** ] メニューの [ **デバッグなしで開始**] をクリックします。

   テキストボックスが初期化されていることに注意してください。

## <a name="see-also"></a>関連項目

[MFC ビューとしての Windows フォーム ユーザー コントロールのホスト](../dotnet/hosting-a-windows-forms-user-control-as-an-mfc-view.md)

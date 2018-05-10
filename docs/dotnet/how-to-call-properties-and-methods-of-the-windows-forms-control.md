---
title: '方法: Windows フォームの呼び出しのプロパティとメソッドが制御 |Microsoft ドキュメント'
ms.custom: get-started-article
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- method calls, Windows Forms
- calling methods, Windows Forms control
- calling properties, Windows Forms control
- Windows Forms controls [C++], methods
- calling properties
- Windows Forms controls [C++], properties
ms.assetid: 6e647d8a-fdaa-4aa1-b3fe-04f15cff8eb3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 206c7bc89ce2bbc48beb1d95f3929ea4694fce20
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-call-properties-and-methods-of-the-windows-forms-control"></a>方法: Windows フォーム コントロールのプロパティとメソッドを呼び出す
[CWinFormsView::GetControl](../mfc/reference/cwinformsview-class.md#getcontrol)へのポインターを返します<xref:System.Windows.Forms.Control?displayProperty=fullName>、およびへのポインターではなく`WindowsControlLibrary1::UserControl1`、ユーザー コントロールの種類のメンバーを追加しで初期化することをお勧め[IView::OnInitialUpdate](../mfc/reference/iview-interface.md#oninitialupdate). メソッドとプロパティを使用してを呼び出すことができますので`m_ViewControl`です。  
  
 このトピックでは、終了したと仮定[する方法: ダイアログ ボックスで、ユーザー コントロールとホストを作成](../dotnet/how-to-create-the-user-control-and-host-in-a-dialog-box.md)と[する方法: ユーザー コントロールとホスト MDI ビューを作成](../dotnet/how-to-create-the-user-control-and-host-mdi-view.md)です。  
  
### <a name="to-create-the-mfc-host-application"></a>MFC ホスト アプリケーションを作成するには  
  
1.  作成した MFC アプリケーションを開く[する方法: ユーザー コントロールとホスト MDI ビューの作成](../dotnet/how-to-create-the-user-control-and-host-mdi-view.md)です。  
  
2.  パブリック オーバーライド セクションに次の行を追加、`CMFC02View`クラス MFC02View.h で宣言します。  
  
     `gcroot<WindowsFormsControlLibrary1::UserControl1 ^> m_ViewControl;`  
  
3.  フィルターと並べ替え順序の上書きを追加します。  
  
     表示、**プロパティ**ウィンドウ (F4)。 **クラス ビュー** (CTRL + SHIFT + C)、CMFC02View クラスを選択します。 **プロパティ**ウィンドウで、上書きのアイコンを選択します。 Scoll フィルターと並べ替え順序を一覧に表示します。 ドロップダウン リストと選択 をクリックして\<追加 >。 MFC02View.cpp で。 次のように関連付けてから関数の本体を確認します。  
  
    ```  
    CWinFormsView::OnInitialUpdate();  
    m_ViewControl = safe_cast<WindowsFormsControlLibrary1::UserControl1 ^>(this->GetControl());  
    m_ViewControl->textBox1->Text = gcnew System::String("hi");  
    ```  
  
4.  プロジェクトをビルドして実行します。  
  
     **[ビルド]** メニューの **[ソリューションのビルド]** をクリックします。  
  
     **デバッグ** メニューのをクリックして**デバッグなしで開始**です。  
  
     テキスト ボックスが初期化されるようになりましたことに注意してください。  
  
## <a name="see-also"></a>関連項目  
 [MFC ビューとしての Windows フォーム ユーザー コントロールのホスト](../dotnet/hosting-a-windows-forms-user-control-as-an-mfc-view.md)
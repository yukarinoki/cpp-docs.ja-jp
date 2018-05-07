---
title: '方法: ネイティブの C++ のクラスから Windows フォーム イベントをシンク |Microsoft ドキュメント'
ms.custom: get-started-article
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- event handling, managed/native interop
- event handling, sinking .NET in C++
- event handling, .NET/native interop
- event handling, Windows Forms in C++
ms.assetid: 6e30ddee-d058-4c8d-9956-2a43d86f19d5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 0fec32bf179424b5ec0164e4511f74eae44f7320
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-sink-windows-forms-events-from-native-c-classes"></a>方法: ネイティブ C++ クラスから Windows フォーム イベントをシンクする
Windows フォーム コントロールまたは MFC マクロ マップ形式の他のフォームから発生した管理対象のイベントからのコールバックを受信するネイティブの C++ クラスを有効にすることができます。 ビューとダイアログでイベントをシンクは、コントロールに対して同じタスクの実行に似ています。  
  
 これを行うには、する必要があります。  
  
-   アタッチ、`OnClick`イベント ハンドラーを使用してコントロールを[MAKE_DELEGATE](../mfc/reference/delegate-and-interface-maps.md#make_delegate)です。  
  
-   使用してデリゲート マップ作成[BEGIN_DELEGATE_MAP](../mfc/reference/delegate-and-interface-maps.md#begin_delegate_map)、 [END_DELEGATE_MAP](../mfc/reference/delegate-and-interface-maps.md#end_delegate_map)、および[EVENT_DELEGATE_ENTRY](../mfc/reference/delegate-and-interface-maps.md#event_delegate_entry)です。  
  
 このサンプルで行った作業を続行する[する方法: Windows フォームで DDX/DDV データ バインドを行う](../dotnet/how-to-do-ddx-ddv-data-binding-with-windows-forms.md)です。  
  
 ここで、MFC コントロールが関連付けるされます (`m_MyControl`) と呼ばれる管理対象のイベント ハンドラー デリゲートで`OnClick`マネージ<xref:System.Windows.Forms.Control.Click>イベント。  
  
### <a name="to-attach-the-onclick-event-handler"></a>OnClick イベント ハンドラーをアタッチします。  
  
1.  BOOL CMFC01Dlg::OnInitDialog の実装には、次のコードを追加します。  
  
    ```  
    m_MyControl.GetControl()->button1->Click += MAKE_DELEGATE( System::EventHandler, OnClick );  
    ```  
  
2.  CMFC01Dlg クラスの宣言でのパブリック セクションに次のコードを追加します。 パブリック CDialog です。  
  
    ```  
    // delegate map  
    BEGIN_DELEGATE_MAP( CMFC01Dlg )  
    EVENT_DELEGATE_ENTRY( OnClick, System::Object^, System::EventArgs^ )  
    END_DELEGATE_MAP()  
  
    void OnClick( System::Object^ sender, System::EventArgs^ e );  
    ```  
  
3.  実装を最後に、追加`OnClick`CMFC01Dlg.cpp に。  
  
    ```  
    void CMFC01Dlg::OnClick(System::Object^ sender, System::EventArgs^ e)  
    {  
        AfxMessageBox(_T("Button clicked"));  
    }  
    ```  
  
## <a name="see-also"></a>関連項目  
 [MAKE_DELEGATE](../mfc/reference/delegate-and-interface-maps.md#make_delegate)   
 [BEGIN_DELEGATE_MAP](../mfc/reference/delegate-and-interface-maps.md#begin_delegate_map)   
 [END_DELEGATE_MAP](../mfc/reference/delegate-and-interface-maps.md#end_delegate_map)   
 [EVENT_DELEGATE_ENTRY](../mfc/reference/delegate-and-interface-maps.md#event_delegate_entry)
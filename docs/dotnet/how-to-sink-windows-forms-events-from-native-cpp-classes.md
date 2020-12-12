---
description: '詳細については、「方法: ネイティブ C++ クラスからイベントを Windows フォームシンクする」を参照してください。'
title: '方法: ネイティブ C++ クラスから Windows フォーム イベントをシンクする'
ms.custom: get-started-article
ms.date: 11/04/2016
helpviewer_keywords:
- event handling, managed/native interop
- event handling, sinking .NET in C++
- event handling, .NET/native interop
- event handling, Windows Forms in C++
ms.assetid: 6e30ddee-d058-4c8d-9956-2a43d86f19d5
ms.openlocfilehash: 223590849f114bfe02b030a0639f160b8fc1c321
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97286359"
---
# <a name="how-to-sink-windows-forms-events-from-native-c-classes"></a>方法: ネイティブ C++ クラスから Windows フォーム イベントをシンクする

ネイティブ C++ クラスを有効にすると、Windows フォームコントロールまたはその他の形式で発生したマネージイベントから、MFC マクロマップ形式を使用してコールバックを受け取ることができます。 ビューおよびダイアログでのシンクイベントは、コントロールに対して同じタスクを実行することと似ています。

そのためには、次の手順を実行する必要があります。

- `OnClick` [MAKE_DELEGATE](../mfc/reference/delegate-and-interface-maps.md#make_delegate)を使用して、コントロールにイベントハンドラーをアタッチします。

- [BEGIN_DELEGATE_MAP](../mfc/reference/delegate-and-interface-maps.md#begin_delegate_map)、 [END_DELEGATE_MAP](../mfc/reference/delegate-and-interface-maps.md#end_delegate_map)、および[EVENT_DELEGATE_ENTRY](../mfc/reference/delegate-and-interface-maps.md#event_delegate_entry)を使用して、デリゲートマップを作成します。

このサンプルでは、 [「方法: Windows フォームで DDX/DDV データバインディングを実行](../dotnet/how-to-do-ddx-ddv-data-binding-with-windows-forms.md)する」で行った作業を続行します。

次に、MFC コントロール ( `m_MyControl` ) と、 `OnClick` マネージイベントに対して呼び出されるマネージイベントハンドラーデリゲートを関連付けます <xref:System.Windows.Forms.Control.Click> 。

### <a name="to-attach-the-onclick-event-handler"></a>OnClick イベントハンドラーをアタッチするには、次のようにします。

1. BOOL CMFC01Dlg:: OnInitDialog の実装に次のコードを追加します。

    ```
    m_MyControl.GetControl()->button1->Click += MAKE_DELEGATE( System::EventHandler, OnClick );
    ```

1. CMFC01Dlg: public CDialog クラスの宣言のパブリックセクションに、次のコードを追加します。

    ```
    // delegate map
    BEGIN_DELEGATE_MAP( CMFC01Dlg )
    EVENT_DELEGATE_ENTRY( OnClick, System::Object^, System::EventArgs^ )
    END_DELEGATE_MAP()

    void OnClick( System::Object^ sender, System::EventArgs^ e );
    ```

1. 最後に、の実装を CMFC01Dlg に追加します。 `OnClick`

    ```
    void CMFC01Dlg::OnClick(System::Object^ sender, System::EventArgs^ e)
    {
        AfxMessageBox(_T("Button clicked"));
    }
    ```

## <a name="see-also"></a>関連項目

[MAKE_DELEGATE](../mfc/reference/delegate-and-interface-maps.md#make_delegate)<br/>
[BEGIN_DELEGATE_MAP](../mfc/reference/delegate-and-interface-maps.md#begin_delegate_map)<br/>
[END_DELEGATE_MAP](../mfc/reference/delegate-and-interface-maps.md#end_delegate_map)<br/>
[EVENT_DELEGATE_ENTRY](../mfc/reference/delegate-and-interface-maps.md#event_delegate_entry)

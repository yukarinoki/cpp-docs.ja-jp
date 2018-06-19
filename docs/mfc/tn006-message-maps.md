---
title: 'TN006: メッセージ マップ |Microsoft ドキュメント'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- vc.messages.maps
dev_langs:
- C++
helpviewer_keywords:
- ON_UPDATE_COMMAND_UI macro [MFC]
- ON_NOTIFY_RANGE macro [MFC]
- ON_COMMAND macro [MFC]
- ON_CONTROL_RANGE macro [MFC]
- ON_REGISTERED_MESSAGE macro [MFC]
- ON_NOTIFY message [MFC]
- ON_COMMAND_RANGE_EX macro [MFC]
- ON_MESSAGE macro [MFC]
- Windows messages [MFC], message maps
- ON_COMMAND_RANGE macro [MFC]
- TN006
- ON_CONTROL macro [MFC]
- ON_COMMAND_EX macro [MFC]
- message maps [MFC], Windows messaging
ms.assetid: af4b6794-4b40-4f1e-ad41-603c3b7409bb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 160b88a7069ac9a5851c0f472f756d694e59874e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33384698"
---
# <a name="tn006-message-maps"></a>テクニカル ノート 6: メッセージ マップ
ここでは、MFC メッセージ マップ機能について説明します。  
  
## <a name="the-problem"></a>問題を  
 Microsoft Windows では、そのメッセージング機能を使用するウィンドウ クラスの仮想関数を実装します。 関連するメッセージの数が多いため Windows メッセージごとに個別の仮想関数を提供する、非常に大規模な vtable を作成します。  
  
 システム定義の Windows メッセージの数が時間の経過と共に変化し、メッセージがマップするため、アプリケーションは、独自の Windows メッセージを定義することができます、ためをインターフェイスの変更が既存のコードを中断するを妨げる間接参照のレベルを提供します。  
  
## <a name="overview"></a>概要  
 MFC には、代わりに、ウィンドウに送信されたメッセージを処理する従来の Windows ベースのプログラムで使用された switch ステートメントが用意されています。 ウィンドウによってメッセージが受信されると、適切なメソッドが自動的にできるように、メッセージからメソッドへのマッピングを定義できます。 このメッセージ マップ機能は仮想関数に似ていますが C++ の仮想関数では実現できないその他の利点です。  
  
## <a name="defining-a-message-map"></a>メッセージ マップを定義します。  
 [DECLARE_MESSAGE_MAP](reference/message-map-macros-mfc.md#declare_message_map)マクロは、クラスの 3 つのメンバーを宣言します。  
  
-   プライベート配列`AFX_MSGMAP_ENTRY`と呼ばれるエントリ`_messageEntries`です。  
  
-   プロテクト`AFX_MSGMAP`と呼ばれる構造`messageMap`を指す、`_messageEntries`配列。  
  
-   Protected で呼び出される仮想関数`GetMessageMap`のアドレスを返す`messageMap`です。  
  
 メッセージ マップを使用して任意のクラスの宣言では、このマクロを含める必要があります。 慣例により、クラス宣言の最後になります。 例えば:  
  
```  
class CMyWnd : public CMyParentWndClass  
{ *// my stuff...  
 
protected: *//{{AFX_MSG(CMyWnd)  
    afx_msg void OnPaint();
*//}}AFX_MSG  
 
    DECLARE_MESSAGE_MAP() 
};  
```  
  
 これは、新しいクラスを作成するときに、AppWizard と ClassWizard で生成された形式です。 //{{と//}} ClassWizard の角かっこが必要です。  
  
 メッセージ マップのテーブルは、一連のメッセージ マップ エントリに展開されるマクロを使用して定義されます。 テーブルが始まり、 [BEGIN_MESSAGE_MAP](reference/message-map-macros-mfc.md#begin_message_map)マクロの呼び出しは、このメッセージ マップで処理されるクラスと未処理のメッセージが渡され、親クラスを定義します。 テーブル、 [END_MESSAGE_MAP](reference/message-map-macros-mfc.md#end_message_map)マクロの呼び出しです。  
  
 これらの 2 つのマクロ呼び出しの間、このメッセージ マップで処理するには、各メッセージのエントリです。 各標準の Windows メッセージには、フォーム ON_WM_ のマクロ*MESSAGE_NAME*そのメッセージのエントリを生成します。  
  
 標準的な関数のシグネチャが定義されて Windows メッセージごとのパラメーターをアンパックし、タイプ セーフを提供します。 Afxwin.h、宣言内のファイルで見つかる可能性があるこれらの署名の[CWnd](../mfc/reference/cwnd-class.md)です。 それぞれが、キーワードでマークされた`afx_msg`を識別しやすくします。  
  
> [!NOTE]
>  ClassWizard では、使用することが必要です、`afx_msg`メッセージ マップ ハンドラーの宣言でキーワード。  
  
 これらの関数シグネチャは、単純な規則を使用して取得しました。 関数の名前は、常にで始まる`"On`"です。 これは後に、"WM _ で Windows メッセージの名前と大文字で入力の各単語の最初の文字。 パラメーターの順序は`wParam`続く`LOWORD`(`lParam`) し、 `HIWORD`(`lParam`)。 使用されていないパラメーターは渡されません。 MFC クラスによってラップされているすべてのハンドルは、適切な MFC オブジェクトへのポインターに変換されます。 次の例は、処理する方法を示しています。、`WM_PAINT`メッセージになり、`CMyWnd::OnPaint`に呼び出される関数。  
  
```  
BEGIN_MESSAGE_MAP(CMyWnd, CMyParentWndClass) *//{{AFX_MSG_MAP(CMyWnd)  
    ON_WM_PAINT() *//}}AFX_MSG_MAP  
END_MESSAGE_MAP()  
```  
  
 任意の関数またはクラス定義のスコープ外メッセージ マップ テーブルを定義する必要があります。 Extern"C"ブロックに配置する必要があります。  
  
> [!NOTE]
>  ClassWizard の間に発生するメッセージ マップ エントリを変更、//{{と//}} コメントの角かっこです。  
  
## <a name="user-defined-windows-messages"></a>ユーザー定義の Windows メッセージ  
 使用して、ユーザー定義メッセージをメッセージ マップに含めることは、 [ON_MESSAGE](reference/message-map-macros-mfc.md#on_message)マクロです。 このマクロは、メッセージの数とフォームのメソッドを受け取ります。  
  
'' *//クラス宣言内  
    afx_msg LRESULT OnMyMessage(WPARAM wParam, LPARAM lParam) です。

 
 #<a name="define-wmmymessage-wmuser--100"></a>WM_MYMESSAGE の定義 (WM_USER 100 +)  
 
BEGIN_MESSAGE_MAP (CMyWnd、CMyParentWndClass)  
    ON_MESSAGE (WM_MYMESSAGE、OnMyMessage)  
END_MESSAGE_MAP()  
```  
  
 In this example, we establish a handler for a custom message that has a Windows message ID derived from the standard `WM_USER` base for user-defined messages. The following example shows how to call this handler:  
  
```  
CWnd * pWnd =... です。  
pWnd SendMessage(WM_MYMESSAGE);]-> [します。
```  
  
 The range of user-defined messages that use this approach must be in the range `WM_USER` to 0x7fff.  
  
> [!NOTE]
>  ClassWizard does not support entering `ON_MESSAGE` handler routines from the ClassWizard user interface. You must manually enter them from the Visual C++ editor. ClassWizard will parse these entries and let you browse them just like any other message-map entries.  
  
## Registered Windows Messages  
 The [RegisterWindowMessage](http://msdn.microsoft.com/library/windows/desktop/ms644947) function is used to define a new window message that is guaranteed to be unique throughout the system. The macro `ON_REGISTERED_MESSAGE` is used to handle these messages. This macro accepts a name of a `UINT NEAR` variable that contains the registered windows message ID. For example  
  
```  
クラスの CMyWnd: パブリック CMyParentWndClass  
{  
public:  
    CMyWnd() です。

 *//{{AFX_MSG(CMyWnd)  
    afx_msg LRESULT OnFind(WPARAM wParam, LPARAM lParam) です。*//}}AFX_MSG  
 
    DECLARE_MESSAGE_MAP() 
};  
 
静的 UINT 近く WM_FIND RegisterWindowMessage("COMMDLG_FIND"); を =

 
BEGIN_MESSAGE_MAP (CMyWnd、CMyParentWndClass) *//{{AFX_MSG_MAP(CMyWnd)  
    ON_REGISTERED_MESSAGE (WM_FIND、OnFind) *//}}AFX_MSG_MAP  
END_MESSAGE_MAP()  
```  
  
 The registered Windows message ID variable (WM_FIND in this example) must be a `NEAR` variable because of the way `ON_REGISTERED_MESSAGE` is implemented.  
  
 The range of user-defined messages that use this approach will be in the range 0xC000 to 0xFFFF.  
  
> [!NOTE]
>  ClassWizard does not support entering `ON_REGISTERED_MESSAGE` handler routines from the ClassWizard user interface. You must manually enter them from the text editor. ClassWizard will parse these entries and let you browse them just like any other message-map entries.  
  
## Command Messages  
 Command messages from menus and accelerators are handled in message maps with the `ON_COMMAND` macro. This macro accepts a command ID and a method. Only the specific `WM_COMMAND` message that has a `wParam` equal to the specified command ID is handled by the method specified in the message-map entry. Command handler member functions take no parameters and return `void`. The macro has the following form:  
  
```  
ON_COMMAND (id、memberFxn)  
```  
  
 Command update messages are routed through the same mechanism, but use the `ON_UPDATE_COMMAND_UI` macro instead. Command update handler member functions take a single parameter, a pointer to a [CCmdUI](../mfc/reference/ccmdui-class.md) object, and return `void`. The macro has the form  
  
```  
ON_UPDATE_COMMAND_UI (id、memberFxn)  
```  
  
 Advanced users can use the `ON_COMMAND_EX` macro, which is an extended form of command message handlers. The macro provides a superset of the `ON_COMMAND` functionality. Extended command-handler member functions take a single parameter, a `UINT` that contains the command ID, and return a `BOOL`. The return value should be `TRUE` to indicate that the command has been handled. Otherwise routing will continue to other command target objects.  
  
 Examples of these forms:  
  
-   Inside Resource.h (usually generated by Visual C++)  
  
 ```  
 #<a name="define----idmycmd------100"></a>ID_MYCMD 100 を定義します。  
 #<a name="define----idcomplex----101"></a>ID_COMPLEX 101 を定義します。  
 ```  
  
-   Inside the class declaration  
  
 ```  
    afx_msg void OnMyCommand();
afx_msg void OnUpdateMyCommand (CCmdUI * 対応付けられた) です。

    afx_msg BOOL OnComplexCommand(UINT nID);

 ```  
  
-   Inside the message map definition  
  
 ```  
    ON_COMMAND(ID_MYCMD,
    OnMyCommand)  
    ON_UPDATE_COMMAND_UI(ID_MYCMD,
    OnUpdateMyCommand)  
    ON_COMMAND_EX(ID_MYCMD,
    OnComplexCommand)  
 ```  
  
-   In the implementation file  
  
 ```  
    void CMyClass::OnMyCommand()  
 {*//コマンドの処理  
 }  
 
    void CMyClass::OnUpdateMyCommand(CCmdUI* pCmdUI)  
 {*//対応付けられたと UI の状態を設定  
 }  
 
    BOOL CMyClass::OnComplexCommand(UINT nID)  
 {*//コマンドの処理  
    TRUE を返す  
 }  
 ```  
  
 Advanced users can handle a range of commands by using a single command handler: [ON_COMMAND_RANGE](reference/message-map-macros-mfc.md#on_command_range) or `ON_COMMAND_RANGE_EX`. See the product documentation for more information about these macros.  
  
> [!NOTE]
>  ClassWizard supports creating `ON_COMMAND` and `ON_UPDATE_COMMAND_UI` handlers, but it does not support creating `ON_COMMAND_EX` or `ON_COMMAND_RANGE` handlers. However, Class Wizard will parse and let you browse all four command handler variants.  
  
## Control Notification Messages  
 Messages that are sent from child controls to a window have an extra bit of information in their message map entry: the control's ID. The message handler specified in a message map entry is called only if the following conditions are true:  
  
-   The control notification code (high word of `lParam`), such as BN_CLICKED, matches the notification code specified in the message-map entry.  
  
-   The control ID (`wParam`) matches the control ID specified in the message-map entry.  
  
 Custom control notification messages may use the [ON_CONTROL](reference/message-map-macros-mfc.md#on_control) macro to define a message map entry with a custom notification code. This macro has the form  
  
```  
ON_CONTROL (wNotificationCode、id、memberFxn)  
```  
  
 For advanced usage [ON_CONTROL_RANGE](reference/message-map-macros-mfc.md#on_control_range) can be used to handle a specific control notification from a range of controls with the same handler.  
  
> [!NOTE]
>  ClassWizard does not support creating an `ON_CONTROL` or `ON_CONTROL_RANGE` handler in the user interface. You must manually enter them with the text editor. ClassWizard will parse these entries and let you browse them just like any other message map entries.  
  
 The Windows Common Controls use the more powerful [WM_NOTIFY](http://msdn.microsoft.com/library/windows/desktop/bb775583) for complex control notifications. This version of MFC has direct support for this new message by using the `ON_NOTIFY` and `ON_NOTIFY_RANGE` macros. See the product documentation for more information about these macros.  
  
## See Also  
 [Technical Notes by Number](../mfc/technical-notes-by-number.md)   
 [Technical Notes by Category](../mfc/technical-notes-by-category.md)


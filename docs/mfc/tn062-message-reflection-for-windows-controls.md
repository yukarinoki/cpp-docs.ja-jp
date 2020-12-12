---
description: '詳細については、「テクニカルノート 62: Message リフレクション for Windows Controls」を参照してください。'
title: 'テクニカル ノート 62: Windows コントロールへのメッセージ リフレクション (メッセージ返送)'
ms.date: 06/28/2018
f1_keywords:
- vc.controls.messages
helpviewer_keywords:
- ON_WM_VKEYTOITEM_REFLECT macro [MFC]
- ON_WM_DRAWITEM_REFLECT macro [MFC]
- ON_WM_VSCROLL_REFLECT macro [MFC]
- ON_NOTIFY_REFLECT message [MFC]
- ON_CONTROL_REFLECT_EX macro [MFC]
- ON_UPDATE_COMMAND_UI_REFLECT macro [MFC]
- ON_NOTIFY_REFLECT_EX message [MFC]
- ON_WM_HSCROLL_REFLECT macro [MFC]
- message reflection [MFC]
- ON_WM_COMPAREITEM_REFLECT macro [MFC]
- ON_WM_MEASUREITEM_REFLECT macro [MFC]
- ON_NOTIFY message [MFC]
- WM_COMMAND [MFC]
- WM_CTLCOLOR message [MFC]
- TN062 [MFC]
- ON_WM_CHARTOITEM_REFLECT macro [MFC]
- ON_WM_CTLCOLOR_REFLECT macro [MFC]
- ON_WM_DELETEITEM_REFLECT macro [MFC]
- notification messages [MFC]
- ON_WM_PARENTNOTIFY_REFLECT macro [MFC]
- WM_NOTIFY message [MFC]
- ON_CONTROL_REFLECT macro
ms.assetid: 53efb0ba-fcda-4fa0-a3c7-14e0b78fb494
ms.openlocfilehash: 9dc106c1513032e654acfc2c4b86b8eb3b939578
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97214729"
---
# <a name="tn062-message-reflection-for-windows-controls"></a>テクニカル ノート 62: Windows コントロールへのメッセージ リフレクション (メッセージ返送)

> [!NOTE]
> 次のテクニカル ノートは、最初にオンライン ドキュメントの一部とされてから更新されていません。 結果として、一部のプロシージャおよびトピックが最新でないか、不正になります。 最新の情報について、オンライン ドキュメントのキーワードで関係のあるトピックを検索することをお勧めします。

このテクニカルノートでは、MFC 4.0 の新機能であるメッセージリフレクションについて説明します。 また、メッセージリフレクションを使用する単純な再利用可能なコントロールを作成するための指示も含まれています。

このテクニカルノートでは、ActiveX コントロール (旧称 OLE コントロール) に適用されるメッセージリフレクションについては説明しません。 「 [ActiveX コントロール: Windows コントロールのサブクラス](../mfc/mfc-activex-controls-subclassing-a-windows-control.md)化」を参照してください。

**メッセージのリフレクションとは**

Windows コントロールは、多くの場合、通知メッセージを親ウィンドウに送信します。 たとえば、多くのコントロールでは、コントロールの色の通知メッセージ (WM_CTLCOLOR またはそのバリアントの1つ) が親に送信され、親はコントロールの背景を描画するためのブラシを提供できます。

バージョン4.0 より前の Windows および MFC では、親ウィンドウ (多くの場合、ダイアログボックス) がこれらのメッセージの処理を担当します。 これは、メッセージを処理するコードが親ウィンドウのクラスに存在し、そのメッセージを処理する必要があるすべてのクラスで重複している必要があることを意味します。 上の例では、カスタムの背景を持つコントロールが必要なすべてのダイアログボックスで、コントロールの色の通知メッセージを処理する必要があります。 独自の背景色を処理するコントロールクラスを記述できる場合は、コードを再利用する方がはるかに簡単です。

MFC 4.0 では、以前のメカニズムは引き続き機能します。親ウィンドウでは、通知メッセージを処理できます。 また、MFC 4.0 では、これらの通知メッセージを子コントロールウィンドウ、親ウィンドウ、またはその両方で処理できる "メッセージリフレクション" と呼ばれる機能を提供することで、再利用が容易になります。 コントロールの背景色の例では、親に依存せずに、リフレクションされた WM_CTLCOLOR メッセージを処理することによって、独自の背景色を設定するコントロールクラスを記述できるようになりました。 (メッセージリフレクションは Windows ではなく MFC によって実装されるため、 `CWnd` メッセージリフレクションを機能させるには、親ウィンドウクラスがから派生している必要があることに注意してください)。

以前のバージョンの MFC では、オーナー描画のリストボックス (WM_DRAWITEM など) のためのメッセージなど、いくつかのメッセージに対して仮想関数を提供することによって、メッセージのリフレクションと同様の処理を行いました。 新しいメッセージのリフレクションメカニズムは一般化され、一貫性があります。

メッセージリフレクションは、4.0 より前のバージョンの MFC 用に記述されたコードとの下位互換性があります。

親ウィンドウのクラスで特定のメッセージまたは範囲のメッセージのハンドラーを指定した場合は、独自のハンドラーで基底クラスのハンドラー関数を呼び出さないと、同じメッセージに対して、リフレクションされたメッセージハンドラーがオーバーライドされます。 たとえば、ダイアログボックスクラスで WM_CTLCOLOR を処理する場合、処理は、反映されたメッセージハンドラーをオーバーライドします。

親ウィンドウクラスで、特定の WM_NOTIFY メッセージまたは WM_NOTIFY メッセージの範囲のハンドラーを指定した場合、そのメッセージを送信する子コントロールにからのリフレクションメッセージハンドラーがない場合にのみ、ハンドラーが呼び出され `ON_NOTIFY_REFLECT()` ます。 メッセージマップでを使用する場合は、メッセージ `ON_NOTIFY_REFLECT_EX()` ハンドラーが親ウィンドウでメッセージを処理できるかどうかによって異なることがあります。 ハンドラーが **FALSE** を返す場合、メッセージは親によっても処理されますが、 **TRUE** を返す呼び出しでは親がそれを処理できません。 反映されたメッセージは、通知メッセージの前に処理されることに注意してください。

WM_NOTIFY メッセージが送信されると、コントロールは最初に処理する機会に提供されます。 他のリフレクションメッセージが送信された場合、親ウィンドウは最初にそれを処理する機会があり、コントロールはリフレクションされたメッセージを受信します。 これを行うには、ハンドラー関数と、コントロールのクラスメッセージマップ内の適切なエントリが必要です。

リフレクションされたメッセージのメッセージマップマクロは、通常の通知とは少し異なります。通常の名前に追加 *_REFLECT* れます。 たとえば、親の WM_NOTIFY メッセージを処理するには、親のメッセージマップで ON_NOTIFY マクロを使用します。 子コントロールでリフレクションされたメッセージを処理するには、子コントロールのメッセージマップで ON_NOTIFY_REFLECT マクロを使用します。 場合によっては、パラメーターも異なっています。 ClassWizard は通常、メッセージマップのエントリを追加し、正しいパラメーターを使用してスケルトン関数の実装を提供することに注意してください。

新しい WM_NOTIFY メッセージの情報については、「 [テクニカルノート 61: ON_NOTIFY」および「WM_NOTIFY メッセージ](../mfc/tn061-on-notify-and-wm-notify-messages.md) 」を参照してください。

**メッセージマップのエントリと、反映されたメッセージのハンドラー関数のプロトタイプ**

リフレクションされたコントロールの通知メッセージを処理するには、次の表に示すメッセージマップマクロと関数プロトタイプを使用します。

通常、ClassWizard では、これらのメッセージマップエントリを追加し、スケルトン関数の実装を提供できます。 リフレクションされたメッセージのハンドラーを定義する方法の詳細については、「リフレクションされ [たメッセージのメッセージハンドラーの定義](../mfc/reference/defining-a-message-handler-for-a-reflected-message.md) 」を参照してください。

メッセージ名をリフレクションされたマクロ名に変換するには、 *ON_* を付加し、 *_REFLECT* を追加します。 たとえば、WM_CTLCOLOR が ON_WM_CTLCOLOR_REFLECT になります。 (どのメッセージを反映できるかを確認するには、次の表のマクロエントリで逆の変換を行います)。

上記のルールの3つの例外は次のとおりです。

- WM_COMMAND 通知のマクロは ON_CONTROL_REFLECT。

- WM_NOTIFY の反射のマクロは ON_NOTIFY_REFLECT です。

- ON_UPDATE_COMMAND_UI の反射のマクロは ON_UPDATE_COMMAND_UI_REFLECT です。

上記の各特殊なケースでは、ハンドラーメンバー関数の名前を指定する必要があります。 それ以外の場合は、ハンドラー関数の標準名を使用する必要があります。

関数のパラメーターと戻り値の意味については、の前にとを含む関数名または関数名の下 *に* 記載されています。 たとえば、 `CtlColor` は「」に記載されてい `OnCtlColor` ます。 いくつかのリフレクションされたメッセージハンドラーには、親ウィンドウの同様のハンドラーよりも多くのパラメーターが必要です。 次の表の名前は、ドキュメント内の仮パラメーターの名前と一致するだけです。

|マップエントリ|関数プロトタイプ|
|---------------|------------------------|
|**ON_CONTROL_REFLECT (** `wNotifyCode` **、** `memberFxn` **)**|**void afx_msg** `memberFxn`**( );**|
|**ON_NOTIFY_REFLECT (** `wNotifyCode` **、** `memberFxn` **)**|**void afx_msg** `memberFxn`**(NMHDR** <strong>\*</strong> `pNotifyStruct`**、LRESULT** <strong>\*</strong>*結果* **);**|
|**ON_UPDATE_COMMAND_UI_REFLECT (** `memberFxn` **)**|**void afx_msg** `memberFxn`**(CCmdUI** <strong>\*</strong> `pCmdUI`**);**|
|**ON_WM_CTLCOLOR_REFLECT ()**|**afx_msg HBRUSH CtlColor (CDC)** <strong>\*</strong> `pDC`**, UINT** `nCtlColor`**);**|
|**ON_WM_DRAWITEM_REFLECT ()**|**afx_msg Void DrawItem (LPDRAWITEMSTRUCT** `lpDrawItemStruct` **);**|
|**ON_WM_MEASUREITEM_REFLECT ()**|**afx_msg Void MeasureItem (LPMEASUREITEMSTRUCT** `lpMeasureItemStruct` **);**|
|**ON_WM_DELETEITEM_REFLECT ()**|**afx_msg Void DeleteItem (LPDELETEITEMSTRUCT** `lpDeleteItemStruct` **);**|
|**ON_WM_COMPAREITEM_REFLECT ()**|**afx_msg Int CompareItem (LPCOMPAREITEMSTRUCT** `lpCompareItemStruct` **);**|
|**ON_WM_CHARTOITEM_REFLECT ()**|**afx_msg int chartoitem (uint** `nKey` **, uint** `nIndex` **);**|
|**ON_WM_VKEYTOITEM_REFLECT ()**|**afx_msg int vkeytoitem (uint** `nKey` **, uint** `nIndex` **);**|
|**ON_WM_HSCROLL_REFLECT ()**|**afx_msg void HScroll (uint** `nSBCode` **, uint** `nPos` **);**|
|**ON_WM_VSCROLL_REFLECT ()**|**void vscroll (uint** `nSBCode` **, uint) を afx_msg し** `nPos` **ます。**|
|**ON_WM_PARENTNOTIFY_REFLECT ()**|**afx_msg void ParentNotify (UINT** `message` **, LPARAM** `lParam` **);**|

ON_NOTIFY_REFLECT マクロと ON_CONTROL_REFLECT マクロには、特定のメッセージを処理するために複数のオブジェクト (コントロールやその親など) を許可するバリエーションがあります。

|マップエントリ|関数プロトタイプ|
|---------------|------------------------|
|**ON_NOTIFY_REFLECT_EX (** `wNotifyCode` **、** `memberFxn` **)**|**AFX_MSG ブール** `memberFxn` 値 **(NMHDR** <strong>\*</strong> `pNotifyStruct`**、LRESULT** <strong>\*</strong>*結果* **);**|
|**ON_CONTROL_REFLECT_EX (** `wNotifyCode` **、** `memberFxn` **)**|**AFX_MSG ブール** `memberFxn` 値 **( );**|

## <a name="handling-reflected-messages-an-example-of-a-reusable-control"></a>リフレクションされたメッセージの処理: 再利用可能なコントロールの例

この簡単な例では、という再利用可能なコントロールを作成し `CYellowEdit` ます。 コントロールは通常の編集コントロールと同じように動作しますが、黒いテキストが黄色の背景に表示される点が異なります。 コントロールに異なる色を表示させるメンバー関数を簡単に追加でき `CYellowEdit` ます。

### <a name="to-try-the-example-that-creates-a-reusable-control"></a>再利用可能なコントロールを作成する例を試すには

1. 既存のアプリケーションに新しいダイアログボックスを作成します。 詳細については、「 [ダイアログエディター](../windows/dialog-editor.md) 」を参照してください。

   再利用可能なコントロールを開発するアプリケーションが必要です。 使用する既存のアプリケーションがない場合は、AppWizard を使用してダイアログベースのアプリケーションを作成します。

2. プロジェクトが Visual C++ に読み込まれた状態で、ClassWizard を使用して、に基づいてという新しいクラスを作成し `CYellowEdit` `CEdit` ます。

3. クラスに3つのメンバー変数を追加 `CYellowEdit` します。 最初の2つは、テキストの色と背景色を保持するために、 *COLORREF* 変数になります。 3番目のは、 `CBrush` 背景を描画するためのブラシを保持するオブジェクトです。 オブジェクトを使用すると、 `CBrush` ブラシを1回だけ作成し、その後で単にそれを参照するだけで、 `CYellowEdit` コントロールが破棄されたときにブラシを自動的に破棄することができます。

4. 次のようにコンストラクターを記述して、メンバー変数を初期化します。

    ```cpp
    CYellowEdit::CYellowEdit()
    {
        m_clrText = RGB(0, 0, 0);
        m_clrBkgnd = RGB(255, 255, 0);
        m_brBkgnd.CreateSolidBrush(m_clrBkgnd);
    }
    ```

5. ClassWizard を使用して、リフレクションされた WM_CTLCOLOR メッセージのハンドラーをクラスに追加し `CYellowEdit` ます。 処理可能なメッセージの一覧のメッセージ名の前に等号があると、メッセージが反映されていることに注意してください。 これについては、「リフレクションされ [たメッセージのメッセージハンドラーの定義](../mfc/reference/defining-a-message-handler-for-a-reflected-message.md)」を参照してください。

   ClassWizard では、次のメッセージマップマクロとスケルトン関数が追加されます。

    ```cpp
    ON_WM_CTLCOLOR_REFLECT()
    // Note: other code will be in between....

    HBRUSH CYellowEdit::CtlColor(CDC* pDC, UINT nCtlColor)
    {
        // TODO: Change any attributes of the DC here
        // TODO: Return a non-NULL brush if the
        //       parent's handler should not be called
        return NULL;
    }
    ```

6. 関数の本体を次のコードに置き換えます。 このコードでは、コントロールの残りの部分のテキストの色、テキストの背景色、および背景色を指定します。

    ```cpp
    pDC->SetTextColor(m_clrText);   // text
    pDC->SetBkColor(m_clrBkgnd);    // text bkgnd
    return m_brBkgnd;               // ctl bkgnd
    ```

7. ダイアログボックスに編集コントロールを作成し、コントロールキーを押しながら編集コントロールをダブルクリックしてメンバー変数にアタッチします。 [メンバー変数の追加] ダイアログボックスで、変数名を入力し、カテゴリの [コントロール] を選択します。次に、変数の型として "CYellowEdit" を選択します。 ダイアログボックスのタブオーダーは忘れずに設定してください。 また、 `CYellowEdit` ダイアログボックスのヘッダーファイルにコントロールのヘッダーファイルを含めるようにしてください。

8. アプリケーションをビルドして実行します。 エディットコントロールには黄色の背景が表示されます。

## <a name="see-also"></a>関連項目

[番号別テクニカルノート](../mfc/technical-notes-by-number.md)<br/>
[カテゴリ別テクニカルノート](../mfc/technical-notes-by-category.md)

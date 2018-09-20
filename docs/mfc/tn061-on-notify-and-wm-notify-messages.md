---
title: 'TN061: ON_NOTIFY メッセージと WM_NOTIFY メッセージ |Microsoft Docs'
ms.custom: ''
ms.date: 06/28/2018
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- ON_NOTIFY
- WM_NOTIFY
dev_langs:
- C++
helpviewer_keywords:
- ON_NOTIFY_EX message [MFC]
- TN061
- ON_NOTIFY message [MFC]
- ON_NOTIFY_EX_RANGE message [MFC]
- ON_NOTIFY_RANGE message [MFC]
- notification messages
- WM_NOTIFY message
ms.assetid: 04a96dde-7049-41df-9954-ad7bb5587caf
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2395cb7b1f3d719fd64494ee9b9c7c64ba222bac
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46381830"
---
# <a name="tn061-onnotify-and-wmnotify-messages"></a>テクニカル ノート 61: ON_NOTIFY メッセージと WM_NOTIFY メッセージ

> [!NOTE]
> 次のテクニカル ノートは、最初にオンライン ドキュメントの一部とされてから更新されていません。 結果として、一部のプロシージャおよびトピックが最新でないか、不正になります。 最新の情報について、オンライン ドキュメントのキーワードで関係のあるトピックを検索することをお勧めします。

このテクニカル ノートでは、新しい WM_NOTIFY メッセージの背景情報を提供し、MFC アプリケーションで WM_NOTIFY メッセージの処理の推奨される (および最も一般的な) 方法について説明します。

**Windows での通知メッセージ 3.x**

Windows で 3.x は親にメッセージを送信することによって変更コンテンツおよび選択した場合、コントロールの背景の描画にコントロールがマウスのクリックなどのイベントの親に通知します。 単純な通知は通知のコード (BN_CLICKED) などの特殊な WM_COMMAND メッセージとして送信されにパックされている ID を制御*wParam*とコントロールのハンドルで*lParam*します。 以降注意*wParam*と*lParam*は完全では、その他のデータを渡す方法はありません — これらのメッセージは、単純な通知のみを指定できます。 たとえば、BN_CLICKED の通知方法はありません、ボタンがクリックされたときにマウス カーソルの場所に関する情報を送信します。

WM_CTLCOLOR、WM_VSCROLL、兄弟、WM_DRAWITEM、ため、WM_COMPAREITEM、WM_DELETEITEM、wm _ で始まるなどの特殊なメッセージのさまざまな Windows 3.x をする必要があります内のコントロールは、追加のデータを含む通知メッセージを送信、時に使用します。CHARTOITEM、WM_VKEYTOITEM、しにします。 これらのメッセージを送信してコントロールに反映できます。 詳細については、次を参照してください。 [TN062: Windows コントロールへのメッセージ リフレクション](../mfc/tn062-message-reflection-for-windows-controls.md)します。

**Win32 での通知メッセージ**

Win32 API、Windows 3.1 に存在しているコントロールの Windows で使用されていた通知メッセージのほとんどを使用して 3.x です。 ただし、Win32 もに、加算、高度な複合コントロールの Windows でサポートされている 3.x です。 多くの場合、これらのコントロールは、通知メッセージと共に追加のデータを送信する必要があります。 新しい追加することがなく**wm _ で始まる**<strong>\*</strong> WM_NOTIFY で、いずれかを渡すことができます、1 つのメッセージを追加することを選択、Win32 API の設計者、追加のデータが必要な新しい通知は、メッセージ標準化された方法で追加のデータの量。

WM_NOTIFY メッセージ メッセージを送信するコントロールの ID を含めることが*wParam*内の構造体へのポインター *lParam*します。 この構造は、いずれか、 **NMHDR**構造体またはいくつかの大規模な構造を持つ、 **NMHDR**その最初のメンバーとして構造体。 以降を**NMHDR**メンバーが最初は、この構造体へのポインターへのポインターとして使用できます、 **NMHDR**またはとしてキャストする方法に応じてより大きな構造体へのポインター。

ほとんどの場合、ポインターはより大きな構造体とを使用する場合は、それをキャストする必要があります。 一般的な通知などのいくつか通知 (で始まる名前**NM_**)、ツール ヒント コントロールの TTN_SHOW と TTN_POP 通知やが、 **NMHDR**構造が実際に使用します。

**NMHDR**構造または最初のメンバーに、ハンドルと、メッセージと (ttn_show) 通知コードを送信するコントロールの ID が含まれています。 形式、 **NMHDR**構造を次に示します。

```cpp
typedef struct tagNMHDR {
    HWND hwndFrom;
    UINT idFrom;
    UINT code;
} NMHDR;
```

TTN_SHOW メッセージの場合、**コード**メンバーは TTN_SHOW に設定されます。

ほとんどの通知を含むより大きな構造体へのポインターを渡す、 **NMHDR**その最初のメンバーとして構造体。 たとえば、リスト ビュー コントロールで、キーが押されたときに送信されるリスト ビュー コントロールの LVN_KEYDOWN 通知メッセージによって使用される構造を検討してください。 ポインターが指す、 **LV_KEYDOWN**構造体は、次に示すように定義されます。

```cpp
typedef struct tagLV_KEYDOWN {
    NMHDR hdr;
    WORD wVKey;
    UINT flags;
} LV_KEYDOWN;
```

以降を**NMHDR**メンバーがこの構造体の先頭に、通知メッセージに渡されるポインターへのポインターにキャストできる、 **NMHDR**またはへのポインター、 **LV_KEYDOWN**.

**すべての新しい Windows コントロールに共通の通知**

一部の通知は、すべての新しい Windows コントロールに共通です。 これらの通知へのポインターを渡す、 **NMHDR**構造体。

|通知コード|の送信|
|-----------------------|------------------|
|NM_CLICK|ユーザーがコントロールでマウスの左ボタンをクリックしました。|
|NM_DBLCLK|ユーザーがコントロールの左ボタンをダブルクリックしました。|
|NM_RCLICK|ユーザーがコントロールでマウスの右ボタンをクリックしました。|
|NM_RDBLCLK|ユーザーがコントロールで右ボタンをダブルクリック|
|NM_RETURN|コントロールに入力フォーカスがあるときに、ユーザーが ENTER キーを押しました|
|NM_SETFOCUS|コントロールに入力フォーカスが指定されています|
|NM_KILLFOCUS|コントロールが入力フォーカスを失った|
|NM_OUTOFMEMORY|十分なメモリがないために、コントロールは、操作を完了できませんでした。|

##  <a name="_mfcnotes_on_notify.3a_.handling_wm_notify_messages_in_mfc_applications"></a> ON_NOTIFY: MFC アプリケーションで WM_NOTIFY メッセージの処理

関数は、`CWnd::OnNotify`通知メッセージを処理します。 既定の実装は、通知ハンドラーを呼び出し、メッセージ マップを確認します。 オーバーライドしない一般に、`OnNotify`します。 代わりに、ハンドラー関数を提供し、そのハンドラーのメッセージ マップ エントリをオーナー ウィンドウのクラスのメッセージ マップに追加します。

ClassWizard プロパティ シートを使用して、ClassWizard ON_NOTIFY メッセージ マップ エントリを作成し、スケルトン ハンドラー関数を提供できます。 ClassWizard を使用して、簡単に確認する詳細については、次を参照してください。[関数へのメッセージの割り当て](../mfc/reference/mapping-messages-to-functions.md)します。

ON_NOTIFY メッセージ マップ マクロでは、次の構文があります。

```cpp
ON_NOTIFY(wNotifyCode, id, memberFxn)
```

パラメーターは次のとおりです。

*wNotifyCode*<br/>
通知メッセージが、LVN_KEYDOWN などを処理するまでのコードです。

*ID*<br/>
通知の送信対象のコントロールの子の識別子。

*memberFxn*<br/>
この通知は送信時に呼び出されるメンバー関数。

メンバー関数は、次のプロトタイプで宣言する必要があります。

```cpp
afx_msg void memberFxn(NMHDR* pNotifyStruct, LRESULT* result);
```

パラメーターは次のとおりです。

*pNotifyStruct*<br/>
上記のセクションで説明した通知構造体へのポインター。

*結果*<br/>
結果コードへのポインターを返す前に設定します。

## <a name="example"></a>例

メンバー関数は、ことを指定する`OnKeydownList1`から LVN_KEYDOWN メッセージを処理する、 `CListCtrl` ID が持つ`IDC_LIST1`、ClassWizard 使用して、次のメッセージ マップを追加します。

```cpp
ON_NOTIFY(LVN_KEYDOWN, IDC_LIST1, OnKeydownList1)
```

上記の例では、ClassWizard で指定された関数。

```cpp
void CMessageReflectionDlg::OnKeydownList1(NMHDR* pNMHDR, LRESULT* pResult)
{
    LV_KEYDOWN* pLVKeyDow = (LV_KEYDOWN*)pNMHDR;

    // TODO: Add your control notification handler
    //       code here

    *pResult = 0;
}
```

ClassWizard が自動的に適切な型のポインターを提供することに注意してください。 通知の構造体をいずれかでアクセスできる*pNMHDR*または*pLVKeyDow*します。

##  <a name="_mfcnotes_on_notify_range"></a> ON_NOTIFY_RANGE

コントロールのセットの同じ WM_NOTIFY メッセージを処理する必要がある場合は、ON_NOTIFY ではなく ON_NOTIFY_RANGE を使用することができます。 たとえば、特定の通知メッセージの同じ操作を実行するボタンのセットがあります。

ON_NOTIFY_RANGE を使用する場合は、連続した範囲の先頭を指定して、範囲の子の識別子を終了して通知メッセージを処理する対象の子の識別子を指定します。

ClassWizard ON_NOTIFY_RANGE; を処理しませんこれを使用するには、自分でメッセージ マップを編集する必要があります。

メッセージ マップ エントリおよび ON_NOTIFY_RANGE の関数プロトタイプは次のとおりです。

```cpp
ON_NOTIFY_RANGE(wNotifyCode, id, idLast, memberFxn)
```

パラメーターは次のとおりです。

*wNotifyCode*<br/>
通知メッセージが、LVN_KEYDOWN などを処理するまでのコードです。

*ID*<br/>
連続した範囲の識別子の最初の識別子。

*idLast*<br/>
識別子の連続する範囲の最後の識別子。

*memberFxn*<br/>
この通知は送信時に呼び出されるメンバー関数。

メンバー関数は、次のプロトタイプで宣言する必要があります。

```cpp
afx_msg void memberFxn(UINT id, NMHDR* pNotifyStruct, LRESULT* result);
```

パラメーターは次のとおりです。

*ID*<br/>
通知を送信したコントロールの子の識別子。

*pNotifyStruct*<br/>
前述のように、通知構造へのポインター。

*結果*<br/>
結果コードへのポインターを返す前に設定します。

##  <a name="_mfcnotes_tn061_on_notify_ex.2c_.on_notify_ex_range"></a> ON_NOTIFY_EX、ON_NOTIFY_EX_RANGE

メッセージを処理するルーティング通知では、1 つ以上のオブジェクトを実行する場合に、ON_NOTIFY (または ON_NOTIFY_RANGE) ではなく ON_NOTIFY_EX (または ON_NOTIFY_EX_RANGE) を使用することができます。 唯一の違い、 **EX**バージョンと、標準バージョンのメンバー関数を呼び出すことは、 **EX**バージョンを返します、 **BOOL**を示すかどうかメッセージの処理を続行する必要があります。 返す**FALSE**この関数から使用すると、1 つ以上のオブジェクトで同じメッセージを処理します。

ON_NOTIFY_EX または ON_NOTIFY_EX_RANGE; ClassWizard を処理しませんこれらのいずれかを使用する場合は、自分でメッセージ マップを編集する必要があります。

メッセージ マップ エントリおよび ON_NOTIFY_EX と ON_NOTIFY_EX_RANGE 関数プロトタイプは次のとおりです。 パラメーターの意味は、以外の場合と同じ**EX**バージョン。

```cpp
ON_NOTIFY_EX(nCode, id, memberFxn)
ON_NOTIFY_EX_RANGE(wNotifyCode, id, idLast, memberFxn)
```

上記の両方のプロトタイプは、同じです。

```cpp
afx_msg BOOL memberFxn(UINT id, NMHDR* pNotifyStruct, LRESULT* result);
```

どちらの場合も、 *id*通知を送信したコントロールの子の識別子を保持します。

関数が返す必要があります**TRUE**通知メッセージが完全に処理された場合または**FALSE**コマンド ルーティングの他のオブジェクトがメッセージを処理する機会がかどうか。

## <a name="see-also"></a>関連項目

[番号順テクニカル ノート](../mfc/technical-notes-by-number.md)<br/>
[カテゴリ別テクニカル ノート](../mfc/technical-notes-by-category.md)

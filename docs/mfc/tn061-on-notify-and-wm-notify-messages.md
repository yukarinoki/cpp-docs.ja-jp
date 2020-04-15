---
title: 'テクニカル ノート 61: ON_NOTIFY メッセージと WM_NOTIFY メッセージ'
ms.date: 06/28/2018
helpviewer_keywords:
- ON_NOTIFY_EX message [MFC]
- TN061
- ON_NOTIFY message [MFC]
- ON_NOTIFY_EX_RANGE message [MFC]
- ON_NOTIFY_RANGE message [MFC]
- notification messages
- WM_NOTIFY message
ms.assetid: 04a96dde-7049-41df-9954-ad7bb5587caf
ms.openlocfilehash: 845558dad6b9f6e820c759cb83fce2c6cbceaa0c
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81366596"
---
# <a name="tn061-on_notify-and-wm_notify-messages"></a>テクニカル ノート 61: ON_NOTIFY メッセージと WM_NOTIFY メッセージ

> [!NOTE]
> 次のテクニカル ノートは、最初にオンライン ドキュメントの一部とされてから更新されていません。 結果として、一部のプロシージャおよびトピックが最新でないか、不正になります。 最新の情報について、オンライン ドキュメントのキーワードで関係のあるトピックを検索することをお勧めします。

このテクニカル ノートでは、新しいWM_NOTIFY メッセージの背景情報を提供し、MFC アプリケーションでWM_NOTIFY メッセージを処理する推奨される (および最も一般的な) 方法について説明します。

**Windows 3.x の通知メッセージ**

Windows 3.x では、コントロールは、マウス クリック、コンテンツと選択の変更、および親にメッセージを送信することによってバックグラウンド描画を制御するなどのイベントを親に通知します。 単純な通知は、通知コード (BN_CLICKED など) とコントロール ID が*wParam*にパックされ、コントロールのハンドルが*lParam*に含まれる、特別なWM_COMMAND メッセージとして送信されます。 *wParam*と*lParam*がいっぱいなので、追加のデータを渡す方法はありません。 たとえば、BN_CLICKED通知では、ボタンがクリックされたときにマウス カーソルの位置に関する情報を送信する方法はありません。

Windows 3.x のコントロールは、追加のデータを含む通知メッセージを送信する必要がある場合、WM_CTLCOLOR、WM_VSCROLL、WM_HSCROLL、WM_DRAWITEM、WM_MEASUREITEM、WM_COMPAREITEM、WM_DELETEITEM、WM_CHARTOITEM、WM_VKEYTOITEMなど、さまざまな特別な目的のメッセージを使用します。 これらのメッセージは、送信したコントロールに反映できます。 詳細については、「 [TN062: Windows コントロールのメッセージ リフレクション](../mfc/tn062-message-reflection-for-windows-controls.md)」を参照してください。

**Win32 の通知メッセージ**

Windows 3.1 に存在するコントロールの場合、Win32 API は Windows 3.x で使用されていた通知メッセージのほとんどを使用します。 ただし、Win32 では、Windows 3.x でサポートされている高度で複雑なコントロールも追加されています。 多くの場合、これらのコントロールは、通知メッセージとともに追加のデータを送信する必要があります。 追加のデータを必要とする新しい通知ごとに新しい**WM_**<strong>\*</strong>メッセージを追加するのではなく、Win32 API の設計者は、標準化された方法で任意の量の追加データを渡すことができる 1 つのメッセージWM_NOTIFY追加することを選択しました。

WM_NOTIFYメッセージには、メッセージを*wParam*で送信するコントロールの ID と *、lParam*の構造体へのポインタが含まれています。 この構造は **、NMHDR**構造または最初のメンバーとして**NMHDR**構造を有する大きな構造のいずれかである。 **NMHDR**メンバーが最初に使用されるので、この構造体へのポインターは **、NMHDR**へのポインターとして、またはキャスト方法に応じて、より大きな構造体へのポインターとして使用できます。

ほとんどの場合、ポインタはより大きな構造体を指し示し、使用するときにキャストする必要があります。 一般的な通知 (名前が**NM_** で始まる) やツール ヒント コントロールのTTN_SHOWとTTN_POP通知など、ほんの数個の通知では、実際に使用される**NMHDR**構造です。

**NMHDR**構造体または初期メンバーには、メッセージを送信するコントロールのハンドルと ID と通知コード (TTN_SHOWなど) が含まれています。 **NMHDR**構造体の形式は、以下のとおりです。

```cpp
typedef struct tagNMHDR {
    HWND hwndFrom;
    UINT idFrom;
    UINT code;
} NMHDR;
```

TTN_SHOW メッセージの場合、**コード**メンバーはTTN_SHOWに設定されます。

ほとんどの通知は、最初のメンバーとして**NMHDR**構造体を含む大きな構造体へのポインターを渡します。 たとえば、リスト ビュー コントロールでキーが押されたときに送信される、リスト ビュー コントロールのLVN_KEYDOWN通知メッセージによって使用される構造を考えてみます。 ポインターは、次のように定義されている**LV_KEYDOWN**構造体を指します。

```cpp
typedef struct tagLV_KEYDOWN {
    NMHDR hdr;
    WORD wVKey;
    UINT flags;
} LV_KEYDOWN;
```

**NMHDR**メンバーはこの構造体の最初にあるので、通知メッセージで渡されるポインターは **、NMHDR**へのポインターまたは**LV_KEYDOWN**へのポインターのいずれかにキャストできます。

**すべての新しい Windows コントロールに共通の通知**

一部の通知は、すべての新しい Windows コントロールに共通です。 これらの通知は **、NMHDR**構造体へのポインタを渡します。

|通知コード|送信されたのは|
|-----------------------|------------------|
|NM_CLICK|ユーザーがコントロール内でマウスの左ボタンをクリックした|
|NM_DBLCLK|ユーザーがコントロール内でマウスの左ボタンをダブルクリックした場合|
|NM_RCLICK|ユーザーがコントロール内でマウスの右ボタンをクリックした|
|NM_RDBLCLK|ユーザーがコントロール内で右クリックしたボタン|
|NM_RETURN|コントロールが入力フォーカスを持っている間にユーザーが Enter キーを押した|
|NM_SETFOCUS|コントロールに入力フォーカスが与えられている|
|NM_KILLFOCUS|コントロールが入力フォーカスを失いました|
|NM_OUTOFMEMORY|メモリが不足しているため、コントロールは操作を完了できませんでした|

## <a name="on_notify-handling-wm_notify-messages-in-mfc-applications"></a><a name="_mfcnotes_on_notify.3a_.handling_wm_notify_messages_in_mfc_applications"></a>ON_NOTIFY: MFC アプリケーションでのWM_NOTIFY メッセージの処理

この関数`CWnd::OnNotify`は通知メッセージを処理します。 既定の実装では、メッセージ マップをチェックして、呼び出す通知ハンドラーを探します。 一般に、 はオーバーライド`OnNotify`しません。 代わりに、ハンドラー関数を提供し、そのハンドラーのメッセージ マップ エントリを所有者ウィンドウのクラスのメッセージ マップに追加します。

ClassWizard プロパティ シートを使用して、ON_NOTIFY メッセージ マップ エントリを作成し、スケルトン ハンドラー関数を提供できます。 ClassWizard を使用してこれを簡単にする方法の詳細については、「[関数へのメッセージのマッピング](../mfc/reference/mapping-messages-to-functions.md)」を参照してください。

ON_NOTIFYメッセージ マップ マクロの構文は次のとおりです。

```cpp
ON_NOTIFY(wNotifyCode, id, memberFxn)
```

パラメーターは次のとおりです。

*コードを通知します。*<br/>
LVN_KEYDOWNなどの、処理する通知メッセージのコード。

*id*<br/>
通知を送信するコントロールの子識別子。

*メンバーFxn*<br/>
この通知が送信されたときに呼び出されるメンバー関数。

メンバー関数は、次のプロトタイプで宣言する必要があります。

```cpp
afx_msg void memberFxn(NMHDR* pNotifyStruct, LRESULT* result);
```

パラメーターは次のとおりです。

*をクリックします。*<br/>
上のセクションで説明したように、通知構造体へのポインター。

*result*<br/>
戻る前に設定する結果コードへのポインター。

## <a name="example"></a>例

メンバー関数`OnKeydownList1`が、 ID`CListCtrl``IDC_LIST1`からのメッセージLVN_KEYDOWN処理するように指定するには、ClassWizard を使用して、メッセージ マップに次のメッセージを追加します。

```cpp
ON_NOTIFY(LVN_KEYDOWN, IDC_LIST1, OnKeydownList1)
```

上の例では、ClassWizard によって提供される関数は次のとおりです。

```cpp
void CMessageReflectionDlg::OnKeydownList1(NMHDR* pNMHDR, LRESULT* pResult)
{
    LV_KEYDOWN* pLVKeyDow = (LV_KEYDOWN*)pNMHDR;

    // TODO: Add your control notification handler
    //       code here

    *pResult = 0;
}
```

ClassWizard は適切な型のポインタを自動的に提供します。 通知構造には *、pNMHDR*または*pLVKeyDow*を使用してアクセスできます。

## <a name="on_notify_range"></a><a name="_mfcnotes_on_notify_range"></a>ON_NOTIFY_RANGE

一連のコントロールに対して同じWM_NOTIFY メッセージを処理する必要がある場合は、ON_NOTIFYではなくON_NOTIFY_RANGEを使用できます。 たとえば、特定の通知メッセージに対して同じアクションを実行するボタンのセットがあるとします。

ON_NOTIFY_RANGE使用する場合は、範囲の開始と終了の子 ID を指定して、通知メッセージを処理する連続した範囲の子 ID を指定します。

クラス ウィザードはON_NOTIFY_RANGEを処理しません。これを使用するには、自分でメッセージ マップを編集する必要があります。

ON_NOTIFY_RANGEのメッセージ・マップ項目および関数プロトタイプは、以下のとおりです。

```cpp
ON_NOTIFY_RANGE(wNotifyCode, id, idLast, memberFxn)
```

パラメーターは次のとおりです。

*コードを通知します。*<br/>
LVN_KEYDOWNなどの、処理する通知メッセージのコード。

*id*<br/>
連続する識別子の範囲内の最初の識別子。

*idLast*<br/>
連続する識別子の範囲内の最後の識別子。

*メンバーFxn*<br/>
この通知が送信されたときに呼び出されるメンバー関数。

メンバー関数は、次のプロトタイプで宣言する必要があります。

```cpp
afx_msg void memberFxn(UINT id, NMHDR* pNotifyStruct, LRESULT* result);
```

パラメーターは次のとおりです。

*id*<br/>
通知を送信したコントロールの子識別子。

*をクリックします。*<br/>
上で説明した通知構造体へのポインター。

*result*<br/>
戻る前に設定する結果コードへのポインター。

## <a name="on_notify_ex-on_notify_ex_range"></a><a name="_mfcnotes_tn061_on_notify_ex.2c_.on_notify_ex_range"></a>ON_NOTIFY_EX、ON_NOTIFY_EX_RANGE

通知ルーティング内の複数のオブジェクトでメッセージを処理する場合は、ON_NOTIFY (またはON_NOTIFY_RANGEではなく、ON_NOTIFY_EX (またはON_NOTIFY_EX_RANGE) を使用できます。 **EX**バージョンと通常バージョンの唯一の違いは **、EX**バージョン用に呼び出されたメンバー関数が、メッセージ処理を続行するかどうかを示す**BOOL**を返す点です。 この関数から**FALSE**を返すと、複数のオブジェクトで同じメッセージを処理できます。

クラス ウィザードはON_NOTIFY_EXまたはON_NOTIFY_EX_RANGEを処理しません。どちらかを使用する場合は、自分でメッセージ マップを編集する必要があります。

ON_NOTIFY_EXとON_NOTIFY_EX_RANGEのメッセージマップエントリと関数プロトタイプは次のとおりです。 パラメータの意味は、非**EX**バージョンの場合と同じです。

```cpp
ON_NOTIFY_EX(nCode, id, memberFxn)
ON_NOTIFY_EX_RANGE(wNotifyCode, id, idLast, memberFxn)
```

上記の両方のプロトタイプは同じです。

```cpp
afx_msg BOOL memberFxn(UINT id, NMHDR* pNotifyStruct, LRESULT* result);
```

どちらの場合も *、id*は通知を送信したコントロールの子識別子を保持します。

通知メッセージが完全に処理された場合は関数が**TRUE** **を返**す必要があります。

## <a name="see-also"></a>関連項目

[番号順テクニカル ノート](../mfc/technical-notes-by-number.md)<br/>
[カテゴリ別テクニカル ノート](../mfc/technical-notes-by-category.md)

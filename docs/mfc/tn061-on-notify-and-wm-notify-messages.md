---
title: 'TN061: ON_NOTIFY メッセージと WM_NOTIFY メッセージ |Microsoft ドキュメント'
ms.custom: ''
ms.date: 11/04/2016
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
ms.openlocfilehash: dc8e49ec04e1932c7bac4faa9a8737b480d8ef54
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="tn061-onnotify-and-wmnotify-messages"></a>テクニカル ノート 61: ON_NOTIFY メッセージと WM_NOTIFY メッセージ
> [!NOTE]
>  次のテクニカル ノートは、最初にオンライン ドキュメントの一部とされてから更新されていません。 結果として、一部のプロシージャおよびトピックが最新でないか、不正になります。 最新の情報について、オンライン ドキュメントのキーワードで関係のあるトピックを検索することをお勧めします。  
  
 このテクニカル ノートでは、背景情報を提供、新しい**WM_NOTIFY**メッセージし、処理の推奨される (および最も一般的な) 方法について説明します**WM_NOTIFY** MFC アプリケーションでのメッセージ。  
  
 **Windows での通知メッセージ 3.x**  
  
 Windows 3.x が親にメッセージを送信してコンテンツの選択、およびコントロールの背景の描画に変更コントロールがマウスのクリックなどのイベントの親に通知します。 単純な通知は送信として特別な**WM_COMMAND**通知コードとのメッセージ (など**BN_CLICKED**) にパックされた ID を制御および`wParam`とでコントロールのハンドル`lParam`. 以降を`wParam`と`lParam`は完全では、その他のデータを渡す方法はありません-これらのメッセージは、単純な通知のみを指定できます。 インスタンスで、 **BN_CLICKED**通知には、ボタンがクリックしてされたときに、マウスのカーソルの場所に関する情報を送信する方法はありません。  
  
 ときにデータを追加する通知メッセージを送信する Windows 3.x 必要で、コントロールが、さまざまな使用など、特殊な用途のメッセージの`WM_CTLCOLOR`、 `WM_VSCROLL`、 `WM_HSCROLL`、 `WM_DRAWITEM`、 `WM_MEASUREITEM`、 `WM_COMPAREITEM`、`WM_DELETEITEM`、 `WM_CHARTOITEM`、`WM_VKEYTOITEM`のようにします。 これらのメッセージは、それらを送信したコントロールに反映できます。 詳細については、次を参照してください。 [TN062: Windows コントロールへのメッセージ リフレクション](../mfc/tn062-message-reflection-for-windows-controls.md)です。  
  
 **Win32 での通知メッセージ**  
  
 Win32 API、Windows 3.1 に存在していたコントロールの Windows で使用された通知メッセージのほとんどを使用して 3.x です。 ただし、Win32 もいくつかの追加、高度で複雑なコントロールを Windows でサポートされている 3.x です。 多くの場合、これらのコントロールは、通知メッセージと共に追加のデータを送信する必要があります。 新しいを追加するのではなく**wm _ で始まる\*** 追加データ、Win32 API の設計が必要な新しい通知が 1 つのメッセージを追加したメッセージ**WM_NOTIFY**、いずれかを通過することができます標準化された方法で追加のデータの量。  
  
 **WM_NOTIFY**メッセージにはメッセージを送信するコントロールの ID が含まれて`wParam`と内の構造体へのポインター`lParam`です。 この構造体は、いずれか、 **NMHDR**構造体またはいくつかの大きな構造を持つ、 **NMHDR**構造体を最初のメンバーです。 以降を**NMHDR**メンバーが最初は、この構造体へのポインターへのポインターとして使用できます、 **NMHDR**またはキャストの方法によってはより大きな構造体へのポインターとして。  
  
 ほとんどの場合、ポインターはより大きな構造体と使用する場合は、それをキャストする必要があります。 共通の通知などのいくつか通知 (で始まる名前**NM_**) とツール ヒント コントロールの**TTN_SHOW**と**TTN_POP**通知は、**NMHDR**構造が実際に使用します。  
  
 **NMHDR**ハンドルと、メッセージと通知コードを送信するコントロールの ID、構造体または最初のメンバーが含まれています (など**TTN_SHOW**)。 形式、 **NMHDR**構造を次に示します。  
  
```  
typedef struct tagNMHDR {  
    HWND hwndFrom;  
    UINT idFrom;  
    UINT code;  
} NMHDR;  
```  
  
 **TTN_SHOW**メッセージ、**コード**にメンバーを設定すると**TTN_SHOW**です。  
  
 ほとんどの通知を含む大きな構造体へのポインターを渡す、 **NMHDR**構造体を最初のメンバーです。 たとえば、リスト ビュー コントロールのによって使用される構造**LVN_KEYDOWN**通知メッセージは、リスト ビュー コントロールで、キーが押されたときに送信されます。 ポインターが指す、 **LV_KEYDOWN**構造は、次に示すように定義されています。  
  
```  
typedef struct tagLV_KEYDOWN {  
    NMHDR hdr;     
    WORD wVKey;    
    UINT flags;    
} LV_KEYDOWN;  
```  
  
 以降を**NMHDR**最初この構造体のメンバーが、通知メッセージに渡されるポインターへのポインターにキャストできる、 **NMHDR**またはへのポインター、 **LV_KEYDOWN**.  
  
 **すべての新しい Windows のコントロールに共通の通知**  
  
 通知の中では、すべての新しい Windows のコントロールに共通です。 これらの通知へのポインターを渡す、 **NMHDR**構造体。  
  
|通知コード|の送信|  
|-----------------------|------------------|  
|**NM_CLICK**|ユーザーがコントロールでマウスの左ボタンをクリックして|  
|**NM_DBLCLK**|ユーザーがコントロールの左ボタンをダブルクリックしました。|  
|**NM_RCLICK**|ユーザーがコントロールでマウスの右ボタンをクリックして|  
|**NM_RDBLCLK**|ユーザーがコントロールで右ボタンをダブルクリック|  
|**NM_RETURN**|コントロールに入力フォーカスがあるときに、ユーザーが ENTER キーを押した|  
|**NM_SETFOCUS**|コントロールに入力フォーカスが指定されました|  
|**NM_KILLFOCUS**|コントロールが入力フォーカスを失った|  
|**NM_OUTOFMEMORY**|十分なメモリがないために、コントロールは、操作を完了できませんでした。|  
  
##  <a name="_mfcnotes_on_notify.3a_.handling_wm_notify_messages_in_mfc_applications"></a> ON_NOTIFY: MFC アプリケーションで WM_NOTIFY メッセージの処理  
 関数は、`CWnd::OnNotify`通知メッセージを処理します。 既定の実装では、通知のハンドラーを呼び出すのメッセージ マップを確認します。 一般に、オーバーライドしていない`OnNotify`です。 代わりに、ハンドラー関数を提供し、そのハンドラーのメッセージ マップ エントリをオーナー ウィンドウのクラスのメッセージ マップに追加します。  
  
 ClassWizard、ClassWizard プロパティ シートを使用して作成できます、`ON_NOTIFY`メッセージ マップ エントリとスケルトン ハンドラー関数を提供します。 ClassWizard を使って簡単に作成する方法の詳細については、次を参照してください。[関数へのメッセージの割り当て](../mfc/reference/mapping-messages-to-functions.md)です。  
  
 `ON_NOTIFY`メッセージ マップ マクロには、次の構文。  
  
```  
 
ON_NOTIFY(
wNotifyCode  ,  
id  ,
    memberFxn)  
 
```  
  
 ここで斜体のパラメーターに置き換えられます。  
  
 `wNotifyCode`  
 コードを処理するように通知メッセージを**LVN_KEYDOWN**です。  
  
 `id`  
 通知を送信するコントロールの子の識別子。  
  
 `memberFxn`  
 この通知が送信されるときに呼び出されるメンバー関数。  
  
 メンバー関数は、次のプロトタイプで宣言する必要があります。  
  
```  
 
afx_msg void  
memberFxn  
(NMHDR* 
pNotifyStruct  , LRESULT* result);

 
```  
  
## <a name="remarks"></a>コメント  
 ここで斜体のパラメーターがあります。  
  
 `pNotifyStruct`  
 上記のセクションで説明した通知構造体へのポインター。  
  
 *結果*  
 結果コードへのポインターを返す前に設定します。  
  
## <a name="example"></a>例  
 このメンバー関数を使用するように指定する`OnKeydownList1`を処理する**LVN_KEYDOWN**からのメッセージ、 `CListCtrl` ID がある`IDC_LIST1`次のメッセージ マップに追加する ClassWizard を使用します。  
  
```  
ON_NOTIFY(LVN_KEYDOWN,
    IDC_LIST1,
    OnKeydownList1)  
```  
  
 上記の例では、ClassWizard で提供される関数は。  
  
```  
void CMessageReflectionDlg::OnKeydownList1(NMHDR* pNMHDR, LRESULT* pResult)  
{  
    LV_KEYDOWN* pLVKeyDow = (LV_KEYDOWN*)pNMHDR; *// TODO: Add your control notification handler *//       code here  
 
 *pResult = 0;  
}  
```  
  
 ClassWizard が自動的に適切な型のポインターを提供することに注意してください。 いずれかから通知の構造体にアクセスできます`pNMHDR`または`pLVKeyDow`です。  
  
##  <a name="_mfcnotes_on_notify_range"></a> ON_NOTIFY_RANGE  
 同じを処理する必要がある場合**WM_NOTIFY**メッセージ、コントロールのセットを使用できます**ON_NOTIFY_RANGE**なく`ON_NOTIFY`です。 たとえば、一連の特定の通知メッセージに対して同じ操作を実行するボタンがあります。  
  
 使用すると**ON_NOTIFY_RANGE**、連続した範囲の先頭を指定して、範囲の子の識別子を終了して、通知メッセージを処理する対象の子の識別子を指定します。  
  
 ClassWizard が処理しない**ON_NOTIFY_RANGE**以外の場合は、使用するメッセージ マップを編集する必要があります。  
  
 メッセージ マップ エントリと関数プロトタイプ**ON_NOTIFY_RANGE**次に示します。  
  
```  
 
ON_NOTIFY_RANGE(
wNotifyCode  ,   
id  ,   
idLast  ,
    memberFxn)  
 
```  
  
 ここで斜体のパラメーターに置き換えられます。  
  
 `wNotifyCode`  
 コードを処理するように通知メッセージを**LVN_KEYDOWN**です。  
  
 `id`  
 連続した範囲の識別子の最初の識別子。  
  
 `idLast`  
 識別子の連続した範囲内の最後の識別子。  
  
 `memberFxn`  
 この通知が送信されるときに呼び出されるメンバー関数。  
  
 メンバー関数は、次のプロトタイプで宣言する必要があります。  
  
```  
 
afx_msg void  
memberFxn  
(UINT   
id  ,
    NMHDR* 
pNotifyStruct  ,
    LRESULT* result);

 
```  
  
## <a name="remarks"></a>コメント  
 ここで斜体のパラメーターがあります。  
  
 `id`  
 通知を送信したコントロールの子の識別子。  
  
 `pNotifyStruct`  
 前述のとおり、通知構造へのポインター。  
  
 *結果*  
 結果コードへのポインターを返す前に設定します。  
  
##  <a name="_mfcnotes_tn061_on_notify_ex.2c_.on_notify_ex_range"></a> ON_NOTIFY_EX、ON_NOTIFY_EX_RANGE  
 場合の通知で 1 つ以上のオブジェクトにルーティングするメッセージを処理は、使用することができます**ON_NOTIFY_EX** (または**ON_NOTIFY_EX_RANGE**) ではなく`ON_NOTIFY`(または**ON_NOTIFY_RANGE**). 唯一の違い、 **EX**バージョンと普通のバージョンは、メンバー関数は、という名前の**EX**バージョンを返します、 **BOOL**を示すかどうかメッセージ処理を継続する必要があります。 返す**FALSE**この関数からを使用する 1 つ以上のオブジェクトに同じメッセージを処理します。  
  
 ClassWizard が処理しない**ON_NOTIFY_EX**または**ON_NOTIFY_EX_RANGE**以外の場合は、それらのいずれかを使用する場合、メッセージ マップを編集する必要があります。  
  
 メッセージ マップ エントリと関数プロトタイプ**ON_NOTIFY_EX**と**ON_NOTIFY_EX_RANGE**次に示します。 パラメーターの意味は同様の非**EX**バージョン。  
  
```  
 
ON_NOTIFY_EX(
nCode  ,  
id  ,
    memberFxn) ON_NOTIFY_EX_RANGE(
wNotifyCode  ,   
id  ,   
idLast  ,
    memberFxn)  
 
```  
  
 上記の両方のプロトタイプは、同じです。  
  
```  
 
afx_msg BOOL  
memberFxn  
(UINT   
id  ,
    NMHDR* 
pNotifyStruct  ,
    LRESULT* result);

 
```  
  
## <a name="remarks"></a>コメント  
 どちらの場合も、`id`通知を送信したコントロールの子の識別子を保持します。  
  
 関数が返す必要があります**TRUE**通知メッセージが完全に処理された場合または**FALSE**かどうかのコマンド ルーティングの他のオブジェクトは、メッセージを処理する機会です。  
  
## <a name="see-also"></a>関連項目  
 [番号順テクニカル ノート](../mfc/technical-notes-by-number.md)   
 [カテゴリ別テクニカル ノート](../mfc/technical-notes-by-category.md)


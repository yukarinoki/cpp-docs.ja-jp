---
title: 'TN062: メッセージの Windows コントロールへのリフレクション |Microsoft ドキュメント'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- vc.controls.messages
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ba8e9cac3b7f7997da8c620966234a630b9b9fbd
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="tn062-message-reflection-for-windows-controls"></a>テクニカル ノート 62: Windows コントロールへのメッセージ リフレクション (メッセージ返送)
> [!NOTE]
>  次のテクニカル ノートは、最初にオンライン ドキュメントの一部とされてから更新されていません。 結果として、一部のプロシージャおよびトピックが最新でないか、不正になります。 最新の情報について、オンライン ドキュメントのキーワードで関係のあるトピックを検索することをお勧めします。  
  
 このテクニカル ノートでは、メッセージは、MFC 4.0 の新機能について説明します。 メッセージ リフレクションを使用する単純な再利用可能なコントロールを作成する手順も含まれています。  
  
 このテクニカル ノートでは、ActiveX コントロール (旧称 OLE コントロール) を適用する際、メッセージ リフレクションは説明しません。 参照してください[ActiveX コントロール: Windows コントロールのサブクラス化](../mfc/mfc-activex-controls-subclassing-a-windows-control.md)です。  
  
 **メッセージ リフレクションとは**  
  
 Windows コントロールは、親ウィンドウに通知メッセージを頻繁に送信します。 多くのコントロールがコントロールの色通知メッセージを送信するのインスタンス (`WM_CTLCOLOR`またはそのバリエーションの 1 つ) を親ウィンドウの親コントロールの背景を描画するブラシを使用できるようにします。  
  
 Windows および MFC バージョン 4.0 より前に、では、親ウィンドウ、ダイアログ ボックスでは多くの場合はこれらのメッセージを処理します。 これは、メッセージを処理するコードを親ウィンドウのクラスである必要があることと、そのメッセージを処理する必要があるすべてのクラスに複製する必要があることを意味します。 上記の例では、独自の背景をコントロールに必要なすべてのダイアログ ボックスは、コントロールの色の通知メッセージを処理する必要があります。 独自の背景色を処理すると、コントロール クラスを書き込むことができた場合は、コードを再利用をより簡単になります。  
  
 MFC 4.0 では、従来の機能でも、親ウィンドウは、通知メッセージを処理できます。 さらに、ただし、MFC 4.0 を容易に再利用「メッセージ リフレクション」と呼ばれる機能を提供することによってこれらの通知メッセージに子コントロールのウィンドウまたは親ウィンドウのいずれかまたは両方で処理することができます。 例では、コントロールの背景色、記述できるように、リフレクションを処理して、独自の背景色を設定したコントロール クラス`WM_CTLCOLOR`メッセージ — すべてを使用せず、親。 (メッセージ リフレクションが MFC によって実装されているためいない Windows で、親ウィンドウ クラス必要がありますを派生させるから`CWnd`動作にリフレクションでメッセージです)。  
  
 MFC の以前のバージョンではメッセージ リフレクションのようなオーナー描画リスト ボックスのメッセージなど、いくつかのメッセージの仮想関数を指定して (`WM_DRAWITEM`など)。 新しいメッセージ リフレクション メカニズムは、汎用で一貫性のあるです。  
  
 メッセージ リフレクションは、4.0 より前に、のバージョンの MFC 用に記述されたコードとの下位互換性です。  
  
 特定のメッセージのハンドラーを指定するか、上書きの親ウィンドウのクラス内のメッセージの範囲の場合、独自のハンドラーの基本クラスのハンドラー関数を呼び出さない限り、同じメッセージのメッセージ ハンドラーに反映されます。 たとえば、処理する`WM_CTLCOLOR`ダイアログ ボックス クラスで、処理には、リフレクション メッセージ ハンドラーもよりも優先されます。  
  
 親ウィンドウ クラスで特定のハンドラーを指定する場合は、 **WM_NOTIFY**メッセージまたは範囲の**WM_NOTIFY**メッセージ、それらのメッセージを送信する子コントロールを使用している場合にのみ、ハンドラーが呼び出されますいないを介して反映されたメッセージのハンドラーを持つ**ON_NOTIFY_REFLECT()** です。 使用する場合**ON_NOTIFY_REFLECT_EX()** メッセージ ハンドラー、メッセージ マップに可能性がありますまたはメッセージを処理する親ウィンドウを許可しない場合があります。 ハンドラーが戻った場合**FALSE**を返す呼び出し中に、同様に、親によってメッセージが処理される**TRUE**親それを処理することはできません。 リフレクション メッセージが通知メッセージの前に処理されることに注意してください。  
  
 ときに、 **WM_NOTIFY**メッセージが送信される、コントロールはそれを処理する最初の機会を提供します。 他のリフレクションされたメッセージを送信する場合、親ウィンドウがそれを処理する最初の機会とコントロール反映されたメッセージが表示されます。 これを行うことが必要ハンドラー関数と、コントロールのクラスのメッセージ マップに適切なエントリです。  
  
 リフレクション メッセージのメッセージ マップ マクロは通常の通知よりも若干異なります: が **_REFLECT**通常の名前に追加されます。 インスタンスを処理する、 **WM_NOTIFY**メッセージ マクロを使用して、親の`ON_NOTIFY`親のメッセージ マップにします。 子コントロールに反映されたメッセージを処理する、 **ON_NOTIFY_REFLECT**で子コントロールのメッセージ マップ マクロです。 場合によっては、パラメーターに異なるも同様です。 ClassWizard のメッセージ マップ エントリを追加および正しいパラメーターを持つ関数の骨組み実装を提供することが通常に注意してください。  
  
 参照してください[TN061: ON_NOTIFY メッセージと WM_NOTIFY メッセージ](../mfc/tn061-on-notify-and-wm-notify-messages.md)については、新しい**WM_NOTIFY**メッセージ。  
  
 **メッセージ マップ エントリと返送されたメッセージのハンドラー関数プロトタイプ**  
  
 リフレクションされたコントロール通知メッセージを処理するには、メッセージ マップ マクロと関数プロトタイプが次の表に一覧表示を使用します。  
  
 ClassWizard 通常これらのメッセージ マップ エントリを追加してスケルトン関数の実装を提供します。 参照してください[リフレクション メッセージ用のメッセージ ハンドラーを定義する](../mfc/reference/defining-a-message-handler-for-a-reflected-message.md)返送されたメッセージのハンドラーを定義する方法についてはします。  
  
 メッセージ名からリフレクションされたマクロ名に変換する前に付けます**on _** および追加 **_REFLECT**です。 たとえば、`WM_CTLCOLOR`なります**ON_WM_CTLCOLOR_REFLECT**です。 (を反映するメッセージを表示するには、次の表に、マクロのエントリを逆の変換をしないでください)。  
  
 上記のルールに 3 つの例外は次のとおりです。  
  
-   マクロ**WM_COMMAND**通知は**ON_CONTROL_REFLECT**です。  
  
-   マクロ**WM_NOTIFY**反射が**ON_NOTIFY_REFLECT**です。  
  
-   マクロ`ON_UPDATE_COMMAND_UI`反射が**ON_UPDATE_COMMAND_UI_REFLECT**です。  
  
 上記の特別なケースの各ハンドラー メンバー関数の名前を指定する必要があります。 他のケースでは、ハンドラー関数の標準の名前を使用する必要があります。  
  
 パラメーターの意味と、関数の戻り値が、関数名または関数名に記載されている**で**先頭に付加します。 たとえば、 **CtlColor**に記載されて`OnCtlColor`です。 リフレクション メッセージ ハンドラーには、親ウィンドウのようなハンドラーより少ないパラメーターが必要があります。 だけ、ドキュメント内で仮パラメーターの名前を持つ次の表の名前に一致します。  
  
|マップのエントリ|関数プロトタイプ|  
|---------------|------------------------|  
|**ON_CONTROL_REFLECT (** `wNotifyCode` **、** `memberFxn` **)**|**afx_msg void** `memberFxn` **();**|  
|**ON_NOTIFY_REFLECT (** `wNotifyCode` **、** `memberFxn` **)**|**afx_msg void** `memberFxn` **(NMHDR \***  `pNotifyStruct` **、LRESULT\***  *結果* **) です。**|  
|**ON_UPDATE_COMMAND_UI_REFLECT (** `memberFxn` **)**|**afx_msg void** `memberFxn` **(CCmdUI\***  `pCmdUI` **) です。**|  
|**ON_WM_CTLCOLOR_REFLECT に関するページ)**|**afx_msg HBRUSH CtlColor (CDC\***  `pDC` **、UINT** `nCtlColor` **) です。**|  
|**ON_WM_DRAWITEM_REFLECT に関するページ)**|**afx_msg void DrawItem (LPDRAWITEMSTRUCT** `lpDrawItemStruct` **) です。**|  
|**ON_WM_MEASUREITEM_REFLECT に関するページ)**|**afx_msg void MeasureItem (LPMEASUREITEMSTRUCT** `lpMeasureItemStruct` **) です。**|  
|**ON_WM_DELETEITEM_REFLECT に関するページ)**|**afx_msg void DeleteItem (LPDELETEITEMSTRUCT** `lpDeleteItemStruct` **) です。**|  
|**ON_WM_COMPAREITEM_REFLECT に関するページ)**|**afx_msg int CompareItem (LPCOMPAREITEMSTRUCT** `lpCompareItemStruct` **) です。**|  
|**ON_WM_CHARTOITEM_REFLECT に関するページ)**|**afx_msg int CharToItem (UINT** `nKey` **、UINT** `nIndex` **) です。**|  
|**ON_WM_VKEYTOITEM_REFLECT に関するページ)**|**afx_msg int VKeyToItem (UINT** `nKey` **、UINT** `nIndex` **) です。**|  
|**ON_WM_HSCROLL_REFLECT に関するページ)**|**afx_msg void HScroll (UINT** `nSBCode` **、UINT** `nPos` **) です。**|  
|**ON_WM_VSCROLL_REFLECT に関するページ)**|**afx_msg void VScroll (UINT** `nSBCode` **、UINT** `nPos` **) です。**|  
|**ON_WM_PARENTNOTIFY_REFLECT に関するページ)**|**afx_msg void ParentNotify (UINT** `message` **、LPARAM** `lParam` **) です。**|  
  
 **ON_NOTIFY_REFLECT**と**ON_CONTROL_REFLECT**マクロものが含まれる特定のメッセージを処理する (コントロールとその親) などの 1 つ以上のオブジェクトを許可します。  
  
|マップのエントリ|関数プロトタイプ|  
|---------------|------------------------|  
|**ON_NOTIFY_REFLECT_EX (** `wNotifyCode` **、** `memberFxn` **)**|**afx_msg BOOL** `memberFxn` **(NMHDR \***  `pNotifyStruct` **、LRESULT\***  *結果* **) です。**|  
|**ON_CONTROL_REFLECT_EX (** `wNotifyCode` **、** `memberFxn` **)**|**afx_msg BOOL** `memberFxn` **();**|  
  
## <a name="handling-reflected-messages-an-example-of-a-reusable-control"></a>リフレクションされたメッセージの処理: 再利用可能なコントロールの例  
 この簡単な例と呼ばれる再利用可能なコントロールを作成する`CYellowEdit`です。 コントロールは、黄色の背景色を黒のテキストを表示する点を除いて、通常のエディット コントロールと同じでは動作します。 簡単に追加を許可するメンバー関数になります、`CYellowEdit`コントロールにさまざまな色が表示されます。  
  
#### <a name="to-try-the-example-that-creates-a-reusable-control"></a>再利用可能なコントロールを作成する例を実行するには  
  
1.  既存のアプリケーションでは、新しいダイアログ ボックスを作成します。 詳細については、次を参照してください。、[ダイアログ エディター](../windows/dialog-editor.md)トピックです。  
  
     再利用可能なコントロールを開発するためのアプリケーションが必要です。 使用する既存のアプリケーションをお持ちでない場合は、AppWizard を使用して、ダイアログ ベースのアプリケーションを作成します。  
  
2.  プロジェクトを Visual C に読み込まれる、ClassWizard を使用してという新しいクラスを作成する`CYellowEdit`に基づいて`CEdit`です。  
  
3.  次の 3 つのメンバー変数を追加して、`CYellowEdit`クラスです。 最初の 2 つになります**COLORREF**テキストの色と背景色を保持する変数。 3 番目になります、`CBrush`背景を描画するブラシを保持するオブジェクト。 `CBrush`オブジェクトを使用するで 1 回だけではその後、参照するブラシを作成するときに自動的にブラシを破棄して、`CYellowEdit`コントロールが破棄されます。  
  
4.  次のように、コンス トラクターを記述して、メンバー変数を初期化します。  
  
 ```  
    CYellowEdit::CYellowEdit() 
 {  
    m_clrText = RGB(0,
    0,
    0);

    m_clrBkgnd = RGB(255,
    255,
    0);

    m_brBkgnd.CreateSolidBrush(m_clrBkgnd);

 }  
 ```  
  
5.  ハンドラーはリフレクションを ClassWizard を使用して追加`WM_CTLCOLOR`メッセージごとに、`CYellowEdit`クラスです。 処理できるメッセージの一覧で、メッセージ名の前に等号 (=) が、メッセージが反映されることを示すことに注意してください。 これに記載されて[リフレクション メッセージ用のメッセージ ハンドラーを定義する](../mfc/reference/defining-a-message-handler-for-a-reflected-message.md)です。  
  
     ClassWizard では、次のメッセージ マップ マクロとスケルトン関数を追加します。  
  
 ```  
    ON_WM_CTLCOLOR_REFLECT() 
 *// Note: other code will be in between....  
 
    HBRUSH CYellowEdit::CtlColor(CDC* pDC, UINT nCtlColor)   
 { *// TODO: Change any attributes of the DC here  
 *// TODO: Return a non-NULL brush if the *//   parent's handler should not be called  
    return NULL;  
 }  
 ```  
  
6.  関数の本体を次のコードに置き換えます。 コードでは、テキストの色、テキストの背景色、および他のコントロールの背景色を指定します。  
  
 ```  
    pDC->SetTextColor(m_clrText);
*// text  
    pDC->SetBkColor(m_clrBkgnd);
*// text bkgnd  
    return m_brBkgnd;            // ctl bkgnd  
 ```  
  
7.  ダイアログ ボックスで、編集コントロールを作成し、コントロールをダブルクリックして、編集コントロールのキーを押しながらメンバー変数にアタッチします。 メンバー変数の追加 ダイアログ ボックスでは、変数名を完了し、カテゴリには、"CYellowEdit"変数の型の「コントロール」を選択します。 ダイアログ ボックスで、タブ オーダーを設定してください。 また、用のヘッダー ファイルは、必ず、 `CYellowEdit`  ダイアログ ボックスのヘッダー ファイル内のコントロールです。  
  
8.  アプリケーションをビルドして実行します。 エディット コントロールでは、黄色の背景色があります。  
  
## <a name="see-also"></a>関連項目  
 [番号順テクニカル ノート](../mfc/technical-notes-by-number.md)   
 [カテゴリ別テクニカル ノート](../mfc/technical-notes-by-category.md)


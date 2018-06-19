---
title: メッセージ マップ マクロ (MFC) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- AFXWIN/DECLARE_MESSAGE_MAP
- AFXWIN/BEGIN_MESSAGE_MAP
- AFXWIN/BEGIN_TEMPLATE_MESSAGE_MAP
- AFXWIN/END_MESSAGE_MAP
- AFXWIN/ON_COMMAND
- AFXWIN/ON_COMMAND_EX
- AFXWIN/ON_CONTROL
- AFXWIN/ON_MESSAGE
- AFXWIN/ON_OLECMD
- AFXWIN/ON_REGISTERED_MESSAGE
- AFXWIN/ON_REGISTERED_THREAD_MESSAGE
- AFXWIN/ON_THREAD_MESSAGE
- AFXWIN/ON_UPDATE_COMMAND_UI
- AFXWIN/ON_COMMAND_RANGE
- AFXWIN/ON_UPDATE_COMMAND_UI_RANGE
- AFXWIN/ON_CONTROL_RANGE
dev_langs:
- C++
helpviewer_keywords:
- message map macros
- Windows messages [MFC], declaration
- demarcating Windows messages
- message maps [MFC], macros
- message maps [MFC], declaration and demarcation
- message mapping macros
- ranges, message map
- message map ranges
ms.assetid: 531b15ce-32b5-4ca0-a849-bb519616c731
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 28b8a6e6e34399cb16ba3ec9e4f25562962c2dd6
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33378477"
---
# <a name="message-map-macros-mfc"></a>メッセージ マップ マクロ (MFC)
メッセージ マップをサポートするためには、MFC は、次のマクロを指定します。  
  
### <a name="message-map-declaration-and-demarcation-macros"></a>メッセージ マップの宣言と定義用マクロ  
  
|||  
|-|-|  
|[DECLARE_MESSAGE_MAP](#declare_message_map)|メッセージ マップがクラスでメッセージを関数にマップ (クラス宣言で使用する必要があります) 使用されることを宣言します。|  
|[BEGIN_MESSAGE_MAP](#begin_message_map)|メッセージ マップ (クラスの実装で使用する必要があります) の定義を開始します。|  
|[同じよう](#begin_template_interface_map)|1 つのテンプレート引数を持つクラス型のメッセージ マップの定義を開始します。 |
|[END_MESSAGE_MAP](#end_message_map)|メッセージ マップ (クラスの実装で使用する必要があります) の定義を終了します。|  
  
### <a name="message-mapping-macros"></a>メッセージ割り当てマクロ  
  
|||  
|-|-|  
|[ON_COMMAND](#on_command)|指定したコマンド メッセージを処理する関数を示します。|  
|[ON_COMMAND_EX](#on_command_ex)|指定したコマンド メッセージを処理する関数を示します。|  
|[ON_CONTROL](#on_control)|指定されたコントロール通知メッセージを処理する関数を示します。|  
|[ON_MESSAGE](#on_message)|ユーザー定義メッセージを処理する関数を示します。|  
|[ON_OLECMD](#on_olecmd)|DocObject またはそのコンテナーからのメニュー コマンドを処理する関数を示します。|  
|[ON_REGISTERED_MESSAGE](#on_registered_message)|登録済みのユーザー定義メッセージを処理する関数を示します。|  
|[ON_REGISTERED_THREAD_MESSAGE](#on_registered_thread_message)|ある場合、関数は、登録済みのユーザー定義メッセージを処理することを示します、`CWinThread`クラスです。|  
|[ON_THREAD_MESSAGE](#on_thread_message)|ある場合、関数は、ユーザー定義メッセージを処理することを示します、`CWinThread`クラスです。|  
|[ON_UPDATE_COMMAND_UI](#on_update_command_ui)|指定されたユーザー インターフェイス更新コマンド メッセージを処理する関数を示します。|  
  
### <a name="message-map-range-macros"></a>範囲指定のメッセージ マップ マクロ  
  
|||  
|-|-|  
|[ON_COMMAND_RANGE](#on_command_range)|マクロに最初の 2 つのパラメーターで指定されたコマンド Id の範囲を処理する関数を示します。|  
|[ON_UPDATE_COMMAND_UI_RANGE](#on_update_command_ui_range)|更新ハンドラーは、最初の 2 つの pa で指定されたコマンド Id の範囲を処理することを示します] rameters マクロにします。|  
|[ON_CONTROL_RANGE](#on_control_range)|コントロールのマクロに 2 番目と 3 番目のパラメーターで指定した Id の範囲からの通知を処理する関数を示します。 最初のパラメーターは、コントロール通知メッセージがなど**BN_CLICKED**です。|  
  
 メッセージ マップ、メッセージ マップの宣言と定義用マクロ、およびメッセージ マップ マクロの詳細については、次を参照してください。[メッセージ マップ](../../mfc/reference/message-maps-mfc.md)と[メッセージの処理とのマッピングに関するトピック](../../mfc/message-handling-and-mapping.md)です。 メッセージ マップの範囲の詳細については、次を参照してください。[メッセージ マップの範囲内のハンドラー](../../mfc/handlers-for-message-map-ranges.md)です。  


## <a name="begin_message_map"></a> BEGIN_MESSAGE_MAP
メッセージ マップの定義を開始します。  
  
### <a name="syntax"></a>構文  
  
```  
BEGIN_MESSAGE_MAP( theClass, baseClass )  
```  
  
### <a name="parameters"></a>パラメーター  
 `theClass`  
 マップを持つメッセージ クラスの名前を指定します。  
  
 `baseClass`  
 基本クラスの名前を指定`theClass`です。  
  
### <a name="remarks"></a>コメント  
 クラスのメンバー関数を定義する実装 (.cpp) ファイル、起動するとメッセージ マップ、`BEGIN_MESSAGE_MAP`マクロ、メッセージ ハンドラー関数の各マクロ エントリを追加、メッセージ マップを完了、`END_MESSAGE_MAP`マクロです。  
  
 メッセージ マップの詳細については、次を参照してください[メッセージ マップ。](message-maps-mfc.md)  
  
### <a name="example"></a>例  
```cpp  
BEGIN_MESSAGE_MAP(CMainFrame, CMDIFrameWnd)
   ON_WM_CREATE()
END_MESSAGE_MAP()
```
  
### <a name="requirements"></a>要件  
 **ヘッダー:** afxwin.h 

##  <a name="begin_template_message_map"></a>同じよう
1 つのテンプレート引数を持つクラス型のメッセージ マップの定義を開始します。  
   
### <a name="syntax"></a>構文  
  ```
BEGIN_TEMPLATE_MESSAGE_MAP( theClass, type_name, baseClass )  
```
### <a name="parameters"></a>パラメーター  
 `theClass`  
 マップを持つメッセージ クラスの名前を指定します。    
 `type_name`  
 クラスの指定されたテンプレート パラメーターの名前。    
 `baseClass`  
 基本クラスの名前を指定`theClass`です。  
   
### <a name="remarks"></a>コメント  
 このマクロがに似ていますが、 [BEGIN_MESSAGE_MAP](message-map-macros-mfc.md#begin_message_map)マクロです。 ただし、このマクロは、1 つのテンプレート引数を含むクラスです。  
  
 クラスのメソッドの実装のセクション、起動するとメッセージ マップ、**同じよう**マクロ; 標準のメッセージ マップの場合と同様に、メッセージ ハンドラー メソッドの各マクロ エントリを追加します。 同様、 **BEGIN_MESSAGE_MAP**マクロとテンプレートのメッセージ マップの完了、 [END_MESSAGE_MAP](message-map-macros-mfc.md#end_message_map)マクロです。  
  
 テンプレート クラスのメッセージ マップを実装する方法についてを参照してください[する方法: テンプレート クラスのメッセージ マップを作成](../how-to-create-a-message-map-for-a-template-class.md)です。  
   
### <a name="requirements"></a>要件  
 **ヘッダー:** afxwin.h  
 
## <a name="declare_message_map"></a>  DECLARE_MESSAGE_MAP
 クラスがメッセージ マップを定義することを宣言します。 各`CCmdTarget`-プログラム内の派生クラスがメッセージを処理するメッセージ マップを用意する必要があります。  
  
### <a name="syntax"></a>構文  
  
```    
DECLARE_MESSAGE_MAP( )  
```  
  
### <a name="remarks"></a>コメント  
 使用して、`DECLARE_MESSAGE_MAP`クラスの宣言の最後にマクロです。 クラスのメンバー関数を定義する .cpp ファイルを使用して、`BEGIN_MESSAGE_MAP`マクロのメッセージ ハンドラー関数の各マクロ エントリと`END_MESSAGE_MAP`マクロです。  
  
> [!NOTE]
>  後の任意のメンバーを宣言する場合`DECLARE_MESSAGE_MAP`、新しいアクセスの種類を指定する必要があります (**パブリック**、 `private`、または`protected`) にします。  
  
 メッセージの詳細については、マップ、および`DECLARE_MESSAGE_MAP`マクロを参照してください[メッセージの処理とマップ」](../../mfc/message-handling-and-mapping.md)です。  
  
### <a name="example"></a>例  
```cpp  
class CMainFrame : public CMDIFrameWnd
{
   DECLARE_MESSAGE_MAP()

   // Remainder of class declaration omitted.
``` 
  
### <a name="requirements"></a>要件  
 **ヘッダー:** afxwin.h  


## <a name="end_message_map"></a>  END_MESSAGE_MAP
メッセージ マップの定義を終了します。  
  
### <a name="syntax"></a>構文  
  
```   
END_MESSAGE_MAP( )  
```  
  
### <a name="remarks"></a>コメント  
 メッセージの詳細については、マップ、および`END_MESSAGE_MAP`マクロを参照してください[メッセージの処理とマップ」](../../mfc/message-handling-and-mapping.md)です。  
  
### <a name="requirements"></a>要件  
 **ヘッダー:** afxwin.h  

## <a name="on_command"></a>  ON_COMMAND
このマクロは、コマンドのメッセージをメンバー関数にマップされます。  
  
### <a name="syntax"></a>構文  
  
```  
ON_COMMAND( id, memberFxn )  
```  
  
### <a name="parameters"></a>パラメーター  
 `id`  
 コマンド ID。  
  
 `memberFxn`  
 コマンドがマップされているメッセージ ハンドラー関数の名前。  
  
### <a name="remarks"></a>コメント  
 メニュー項目またはツール バー ボタンなどのコマンドのユーザー インターフェイス オブジェクトからのコマンド メッセージを処理する関数を示します。  
  
 コマンド ターゲット オブジェクトが、Windows を受信すると**WM_COMMAND**指定の ID を持つメッセージ`ON_COMMAND`メンバー関数を呼び出す`memberFxn`メッセージを処理します。  
  
 使用して`ON_COMMAND`に 1 つのコマンドをメンバー関数にマップします。 使用して[ON_COMMAND_RANGE](#on_command_range)コマンド id の範囲を 1 つのメンバー関数にマップします。 1 つのメッセージ マップ エントリは、指定されたコマンド id と一致できます。つまり、1 つ以上のハンドラーにコマンドを割り当てることはできません。 詳細と例については、次を参照してください。[メッセージの処理とマップ」](../../mfc/message-handling-and-mapping.md)です。  
  
### <a name="example"></a>例  
```cpp  
BEGIN_MESSAGE_MAP(CMFCListViewDoc, CDocument)
   ON_COMMAND(ID_MYCOMMAND, &CMFCListViewDoc::OnMycommand)
END_MESSAGE_MAP()
``` 
  
### <a name="requirements"></a>要件  
 **ヘッダー:** afxmsg_.h  

 ## <a name="on_command_ex"></a>  ON_COMMAND_EX
コマンド ハンドラー メンバー関数を拡張します。  
   
### <a name="syntax"></a>構文  
  ```  
ON_COMMAND_EX(id, memberFxn);  
```
### <a name="parameters"></a>パラメーター  
 `id`  
 コマンド ID。  
  
 `memberFxn`  
 コマンドがマップされているメッセージ ハンドラー関数の名前。  
   
### <a name="remarks"></a>コメント 
コマンド メッセージ ハンドラーの拡張のフォームは、高度な用途で使用します。 `ON_COMMAND_EX`マクロは、このようなメッセージ ハンドラーを使用し、[ON_COMMAND] (#on_command) 機能のスーパー セットが用意されています。  拡張のコマンド ハンドラー メンバー関数は、単一のパラメーターを受け取る、 **UINT**コマンド ID を格納していると、返す、 **BOOL**です。 戻り値が TRUE にする必要があります。 

このマクロは、拡張コマンド ハンドラー メンバー関数にコマンドのメッセージをマップします。  
   
### <a name="syntax"></a>構文  
```  
ON_COMMAND_EX(id,  memberFxn);  
```
### <a name="parameters"></a>パラメーター  
 `id`  
 コマンド ID。  
  
 `memberFxn`  
 コマンドがマップされているメッセージ ハンドラー関数の名前。  
   
### <a name="remarks"></a>コメント  
 コマンド メッセージ ハンドラーの拡張のフォームは、高度な用途で使用します。 `ON_COMMAND_EX`マクロは、このようなメッセージ ハンドラーを使用してのスーパー セットが用意されています、 [ON_COMMAND](message-map-macros-mfc.md#on_command)機能します。 拡張のコマンド ハンドラー メンバー関数は、単一のパラメーターを受け取る、 **UINT**コマンド ID を格納していると、返す、 **BOOL**です。 戻り値は、コマンドが処理されたことを示すために TRUE をする必要があります。それ以外の場合、ルーティングは、他のコマンド ターゲット オブジェクトに続行されます。  
詳細については、テクニカル ノートを参照してください。 [TN006: メッセージ マップ] tm006 メッセージ-maps.md)。  
   
### <a name="requirements"></a>要件  
 ヘッダー ファイル: afxmsg_.h  
   
### <a name="see-also"></a>関連項目  
 [ON_COMMAND](message-map-macros-mfc.md#on_command)   
 [TN006: メッセージ マップ] tm006 メッセージ-maps.md)

  
## <a name="on_control"></a>  ON_CONTROL
カスタム コントロールの通知メッセージを処理する関数を示します。  
  
### <a name="syntax"></a>構文  
  
```  
ON_CONTROL( wNotifyCode, id, memberFxn )  
```  
  
### <a name="parameters"></a>パラメーター  
 `wNotifyCode`  
 コントロールの通知コード。  
  
 `id`  
 コマンド ID。  
  
 `memberFxn`  
 コマンドがマップされているメッセージ ハンドラー関数の名前。  
  
### <a name="remarks"></a>コメント  
 コントロールの通知メッセージは、親ウィンドウにコントロールから送信されたものです。  
  
 正確に 1 つあります`ON_CONTROL`メッセージ ハンドラー関数にマップする必要がありますすべてのコントロール通知メッセージのメッセージ マップにマクロ ステートメントです。  
  
 詳細と例については、次を参照してください。[メッセージの処理とマップ」](../../mfc/message-handling-and-mapping.md)です。  
  
### <a name="requirements"></a>要件  
 **ヘッダー:** afxmsg_.h  
  

## <a name="on_message"></a>  ON_MESSAGE  
ユーザー定義メッセージを処理する関数を示します。  
  
### <a name="syntax"></a>構文  
  
```  
ON_MESSAGE( message, memberFxn )  
```  
  
### <a name="parameters"></a>パラメーター  
 `message`  
 メッセージ ID。  
  
 `memberFxn`  
 メッセージをマップするメッセージ ハンドラー関数の名前。  
  
 関数の型でなければなりません`afx_msg LRESULT (CWnd::*)(WPARAM, LPARAM)`です。  
  
### <a name="remarks"></a>コメント  
 ユーザー定義メッセージは、標準の Windows ではない任意のメッセージ`WM_MESSAGE`メッセージ。 メッセージ ID を選択するときの範囲内の値を使用する必要があります`WM_USER`(0x0400) 0x7FFF にまたは`WM_APP`(0x8000) 0xBFFF にします。 メッセージ Id の詳細については、次を参照してください。 [WM_APP](http://msdn.microsoft.com/library/windows/desktop/ms644930)です。  
  
 正確に 1 つあります`ON_MESSAGE`メッセージ ハンドラー関数にマップする必要がありますすべてのユーザー定義メッセージのメッセージ マップにマクロ ステートメントです。  
  
> [!NOTE]
>  ユーザー定義メッセージだけでなく`ON_MESSAGE`一般的ではない Windows メッセージを処理します。 詳細については、サポート技術情報の記事を参照してください。 [99848: 情報: マップより一般的なメッセージを使用して ON_MESSAGE() マクロ](http://go.microsoft.com/fwlink/p/?linkid=192022)です。  
  
 詳細と例については、次を参照してください[メッセージの処理とマップ」](../../mfc/message-handling-and-mapping.md)と[ユーザー定義のハンドラー。](user-defined-handlers.md)  
  
### <a name="example"></a>例  
```cpp  
#define WM_MYMESSAGE (WM_USER + 100)

BEGIN_MESSAGE_MAP(CMyWnd2, CWnd)
   ON_MESSAGE(WM_MYMESSAGE, OnMyMessage)
END_MESSAGE_MAP()

// inside the class declaration
 afx_msg LRESULT OnMyMessage(WPARAM wParam, LPARAM lParam);

 LRESULT CMyWnd2::OnMyMessage(WPARAM wParam, LPARAM lParam)
{
   UNREFERENCED_PARAMETER(wParam);
   UNREFERENCED_PARAMETER(lParam);

   // Handle message here. 

   return 0;
}
```   
  
### <a name="requirements"></a>要件  
 **ヘッダー:** afxmsg_.h  

## <a name="on_olecmd"></a>  ON_OLECMD  
コマンドをコマンドのディスパッチ インターフェイスを介してルーティング`IOleCommandTarget`です。  
  
### <a name="syntax"></a>構文  
  
```  
ON_OLECMD( pguid, olecmdid, id )  
```  
  
### <a name="parameters"></a>パラメーター  
 `pguid`  
 コマンドが所属するコマンド グループの識別子。 使用して**NULL**標準的なグループです。  
  
 *olecmdid*  
 OLE コマンドの識別子。  
  
 `id`  
 メニュー ID、ツールバー ID、ボタン ID、またはその他の ID のリソースまたはオブジェクトのコマンドを実行します。  
  
### <a name="remarks"></a>コメント  
 `IOleCommandTarget` DocObject のユーザー インターフェイスで送られたコマンドを受信するためのコンテナーにでき、同じコマンドを送信するコンテナー (新規、開く、名前を付けて保存、および [ファイル] メニューで; 印刷など、コピー、貼り付け、元に戻す、[編集] メニュー) DocObject にします。  
  
 `IOleCommandTarget` OLE オートメーションのよりも簡単です`IDispatch`です。 `IOleCommandTarget` コマンドの標準セットに完全に依存していることはほとんどありません引数を持ち、および種類の情報は必要ありません (タイプ セーフはコマンドの引数も低下)。 引数を指定してコマンドをディスパッチする必要がある場合を使用して[COleServerDoc::OnExecOleCmd](coleserverdoc-class.md#onexecolecmd)です。  
  
 `IOleCommandTarget`標準のメニュー コマンドは、次のマクロに MFC によって実装されています。  
  
 **ON_OLECMD_CLEARSELECTION に関するページ)**  
  
 Clear 編集コマンドをディスパッチします。 として実装します。  
  
 `ON_OLECMD(NULL, OLECMDID_CLEARSELECTION, ID_EDIT_CLEAR)`  
  
 **ON_OLECMD_COPY に関するページ)**  
  
 コピーの編集コマンドをディスパッチします。 として実装します。  
  
 `ON_OLECMD(NULL, OLECMDID_COPY, ID_EDIT_COPY)`  
  
 **ON_OLECMD_CUT に関するページ)**  
  
 編集 [切り取り] コマンドをディスパッチします。 として実装します。  
  
 `ON_OLECMD(NULL, OLECMDID_CUT, ID_EDIT_CUT)`  
  
 **ON_OLECMD_NEW に関するページ)**  
  
 ファイルの新規作成 コマンドをディスパッチします。 として実装します。  
  
 `ON_OLECMD(NULL, OLECMDID_NEW, ID_FILE_NEW)`  
  
 **ON_OLECMD_OPEN に関するページ)**  
  
 ファイルを開くコマンドをディスパッチします。 として実装します。  
  
 `ON_OLECMD(NULL, OLECMDID_OPEN, ID_FILE_OPEN)`  
  
 **ON_OLECMD_PAGESETUP に関するページ)**  
  
 ファイルのページ設定 コマンドをディスパッチします。 として実装します。  
  
 `ON_OLECMD(NULL, OLECMDID_PAGESETUP, ID_FILE_PAGE_SETUP)`  
  
 **ON_OLECMD_PASTE に関するページ)**  
  
 編集の貼り付け コマンドをディスパッチします。 として実装します。  
  
 `ON_OLECMD(NULL, OLECMDID_PASTE, ID_EDIT_PASTE)`  
  
 **ON_OLECMD_PASTESPECIAL に関するページ)**  
  
 編集貼り付け コマンドをディスパッチします。 として実装します。  
  
 `ON_OLECMD(NULL, OLECMDID_PASTESPECIAL, ID_EDIT_PASTE_SPECIAL)`  
  
 **ON_OLECMD_PRINT に関するページ)**  
  
 ファイルの印刷 コマンドをディスパッチします。 として実装します。  
  
 `ON_OLECMD(NULL, OLECMDID_PRINT, ID_FILE_PRINT)`  
  
 **ON_OLECMD_PRINTPREVIEW に関するページ)**  
  
 ファイルの印刷プレビュー コマンドをディスパッチします。 として実装します。  
  
 `ON_OLECMD(NULL, OLECMDID_PRINTPREVIEW, ID_FILE_PRINT_PREVIEW)`  
  
 **ON_OLECMD_REDO に関するページ)**  
  
 やり直しコマンドをディスパッチします。 として実装します。  
  
 `ON_OLECMD(NULL, OLECMDID_REDO, ID_EDIT_REDO)`  
  
 **ON_OLECMD_SAVE に関するページ)**  
  
 ファイルの保存のコマンドをディスパッチします。 として実装します。  
  
 `ON_OLECMD(NULL, OLECMDID_SAVE, ID_FILE_SAVE)`  
  
 **ON_OLECMD_SAVE_AS に関するページ)**  
  
 ファイル名を付けて保存 をディスパッチします。 として実装します。  
  
 `ON_OLECMD(NULL, OLECMDID_SAVEAS, ID_FILE_SAVE_AS)`  
  
 **ON_OLECMD_SAVE_COPY_AS に関するページ)**  
  
 ファイルのコピーを付けて保存 をディスパッチします。 として実装します。  
  
 `ON_OLECMD(NULL, OLECMDID_SAVECOPYAS, ID_FILE_SAVE_COPY_AS)`  
  
 **ON_OLECMD_SELECTALL に関するページ)**  
  
 すべての編集コマンドをディスパッチします。 として実装します。  
  
 `ON_OLECMD(NULL, OLECMDID_SELECTALL, ID_EDIT_SELECT_ALL)`  
  
 **ON_OLECMD_UNDO に関するページ)**  
  
 編集を元に戻すコマンドをディスパッチします。 として実装します。  
  
 `ON_OLECMD(NULL, OLECMDID_UNDO, ID_EDIT_UNDO)`  
  
### <a name="requirements"></a>要件  
 **ヘッダー:** afxdocob.h  
  
### <a name="see-also"></a>関連項目  
 [COleCmdUI クラス](colecmdui-class.md)   
 [COleServerDoc::OnExecOleCmd](coleserverdoc-class.md#onexecolecmd)

## <a name="on_registered_message"></a>  ON_REGISTERED_MESSAGE
Windows**を通じて**関数を使用して、システム全体で一意であることが保証されている新しいウィンドウ メッセージを定義します。  
  
### <a name="syntax"></a>構文  
  
```  
ON_REGISTERED_MESSAGE( nMessageVariable, memberFxn )  
```  
  
### <a name="parameters"></a>パラメーター  
 `nMessageVariable`  
 登録されたウィンドウ メッセージ ID 変数です。  
  
 `memberFxn`  
 メッセージをマップするメッセージ ハンドラー関数の名前。  
  
### <a name="remarks"></a>コメント  
 このマクロは、登録済みのメッセージを処理する関数を示します。  
  
 詳細と例については、次を参照してください。[メッセージの処理とマップ」](../../mfc/message-handling-and-mapping.md)です。  
  
### <a name="example"></a>例  
```cpp  
static UINT NEAR WM_FIND = RegisterWindowMessage(_T("COMMDLG_FIND"));


BEGIN_MESSAGE_MAP(CMyWnd3, CWnd)
   ON_REGISTERED_MESSAGE(WM_FIND, OnFind)
END_MESSAGE_MAP()
```  
  
### <a name="requirements"></a>要件  
 **ヘッダー:** afxmsg_.h  
  
### <a name="see-also"></a>関連項目  
 [を通じて](http://msdn.microsoft.com/library/windows/desktop/ms644947)   
 [ユーザー定義によるハンドラー](user-defined-handlers.md)

## <a name="on_registered_thread_message"></a>  ON_REGISTERED_THREAD_MESSAGE    
Windows を通じて関数によって登録されたメッセージを処理する関数を示します。  
  
### <a name="syntax"></a>構文  
  
```  
ON_REGISTERED_THREAD_MESSAGE(nMessageVariable, memberFxn )  
```  
  
### <a name="parameters"></a>パラメーター  
 `nMessageVariable`  
 登録されたウィンドウ メッセージ ID 変数です。  
  
 `memberFxn`  
 メッセージをマップする CWinThread メッセージ ハンドラー関数の名前。  
  
### <a name="remarks"></a>コメント  
 を通じてを使用して、システム全体で一意であることが保証されている新しいウィンドウ メッセージを定義します。 CWinThread クラスがある場合は、ON_REGISTERED_MESSAGE 代わり ON_REGISTERED_THREAD_MESSAGE を使用する必要があります。 
  
### <a name="requirements"></a>要件  
 **ヘッダー:** afxmsg_.h  

## <a name="on_thread_message"></a>  ON_THREAD_MESSAGE  
ユーザー定義メッセージを処理する関数を示します。  
  
### <a name="syntax"></a>構文  
  
```  
ON_THREAD_MESSAGE( message, memberFxn )  
```  
  
### <a name="parameters"></a>パラメーター  
 `message`  
 メッセージ ID。  
  
 `memberFxn`  
 名前、 `CWinThread`-メッセージのメッセージがマップされているハンドラー関数。  
  
### <a name="remarks"></a>コメント  
 `ON_THREAD_MESSAGE` 代わりに使用する必要があります`ON_MESSAGE`がある場合、`CWinThread`クラスです。 ユーザー定義メッセージは、標準の Windows ではない任意のメッセージ**WM_MESSAGE**メッセージ。 正確に 1 つあります`ON_THREAD_MESSAGE`メッセージ ハンドラー関数にマップする必要がありますすべてのユーザー定義メッセージのメッセージ マップにマクロ ステートメントです。  
  
### <a name="requirements"></a>要件  
 **ヘッダー:** afxole.h  

## <a name="on_update_command_ui"></a>  ON_UPDATE_COMMAND_UI    
このマクロは、ユーザー インターフェイス更新コマンド メッセージを処理する関数を示します。  
  
### <a name="syntax"></a>構文  
  
```  
ON_UPDATE_COMMAND_UI( id, memberFxn )  
```  
  
### <a name="parameters"></a>パラメーター  
 `id`  
 メッセージ ID。  
  
 `memberFxn`  
 メッセージをマップするメッセージ ハンドラー関数の名前。  
  
### <a name="remarks"></a>コメント  
 正確に 1 つあります`ON_UPDATE_COMMAND_UI`メッセージ ハンドラー関数にマップする必要がありますすべてのユーザー インターフェイス更新コマンドに対して、メッセージ マップにマクロ ステートメントです。  
  
 詳細と例については、次を参照してください。[メッセージの処理とマップ」](../../mfc/message-handling-and-mapping.md)です。  
  
### <a name="requirements"></a>要件  
 **ヘッダー:** afxole.h  
  
### <a name="see-also"></a>関連項目  
 [CCmdUI クラス](ccmdui-class.md)

## <a name="on_command_range"></a>  ON_COMMAND_RANGE  
コマンド Id の連続する範囲を 1 つのメッセージ ハンドラー関数にマップするのにには、このマクロを使用します。  
  
### <a name="syntax"></a>構文
  
```  
ON_COMMAND_RANGE( id1, id2, memberFxn )  
```  
  
### <a name="parameters"></a>パラメーター  
 `id1`  
 コマンド Id の連続した範囲の先頭のコマンド ID。  
  
 `id2`  
 コマンド Id の連続した範囲の最後のコマンド ID。  
  
 `memberFxn`  
 コマンドがマップされているメッセージ ハンドラー関数の名前。  
  
### <a name="remarks"></a>コメント  
 Id の範囲の始まり`id1`で終わります`id2`です。  
  
 使用して`ON_COMMAND_RANGE`コマンド Id の範囲を 1 つのメンバー関数にマップします。 使用して[ON_COMMAND](#on_command)に 1 つのコマンドをメンバー関数にマップします。 1 つのメッセージ マップ エントリが指定されたコマンド ID と一致できます。 つまり、1 つ以上のハンドラーにコマンドを割り当てることはできません。 メッセージの範囲のマッピングの詳細については、次を参照してください。[メッセージ マップの範囲内のハンドラー](../../mfc/handlers-for-message-map-ranges.md)です。  
  
 メッセージ マップの範囲の自動サポートがないため、自分でマクロを配置する必要があります。  
  
### <a name="example"></a>例  
```cpp  
// The code fragment below shows how to use ON_COMMAND_RANGE macro 
// to map a contiguous range of command IDs to a single message  
// handler function (i.e. OnRangeCmds() in the sample below). In  
// addition, it also shows how to use CheckMenuRadioItem() to check a  
// selected menu item and makes it a radio item.

BEGIN_MESSAGE_MAP(CChildFrame, CMDIChildWnd)
   ON_COMMAND_RANGE(ID_COMMAND_RANGECMD1, ID_COMMAND_RANGECMD3, &CChildFrame::OnRangeCmds)
END_MESSAGE_MAP()

void CChildFrame::OnRangeCmds(UINT nID)
{
   CMenu* mmenu = AfxGetMainWnd()->GetMenu();
   CMenu* submenu = mmenu->GetSubMenu(5);
   submenu->CheckMenuRadioItem(ID_COMMAND_RANGECMD1, ID_COMMAND_RANGECMD3, 
      nID, MF_BYCOMMAND);
}
```
  
### <a name="requirements"></a>要件  
 **ヘッダー:** afxmsg_.h  

## <a name="on_update_command_ui_range"></a>  ON_UPDATE_COMMAND_UI_RANGE    
コマンド Id の連続する範囲を 1 つの更新メッセージ ハンドラー関数にマップします。  
  
### <a name="syntax"></a>構文  
  
```  
ON_UPDATE_COMMAND_UI_RANGE( id1, id2, memberFxn )  
```  
  
### <a name="parameters"></a>パラメーター  
 `id1`  
 コマンド Id の連続した範囲の先頭のコマンド ID。  
  
 `id2`  
 コマンド Id の連続した範囲の最後のコマンド ID。  
  
 `memberFxn`  
 コマンドがマップされている更新メッセージ ハンドラー関数の名前。  
  
### <a name="remarks"></a>コメント  
 更新メッセージ ハンドラーは、メニュー項目と、コマンドに関連付けられたツール バー ボタンの状態を更新します。 Id の範囲の始まり`id1`で終わります`id2`です。  
  
 メッセージ マップの範囲の自動サポートがないため、自分でマクロを配置する必要があります。  
  
### <a name="requirements"></a>要件  
 **ヘッダー:** afxmsg_.h  

## <a name="on_control_range"></a>  ON_CONTROL_RANGE     
このマクロを使用して、連続した範囲のコントロール Id をなど、指定した Windows 通知メッセージの 1 つのメッセージ ハンドラー関数にマップする**BN_CLICKED**です。  
  
### <a name="syntax"></a>構文  
  
```  
ON_CONTROL_RANGE( wNotifyCode, id1, id2, memberFxn )  
```  
  
### <a name="parameters"></a>パラメーター  
 `wNotifyCode`  
 ハンドラーが応答する通知コード。  
  
 `id1`  
 コントロール Id の連続した範囲の先頭のコマンド ID。  
  
 `id2`  
 コントロール Id の連続した範囲の最後のコマンド ID。  
  
 `memberFxn`  
 コントロールがマップされているメッセージ ハンドラー関数の名前。  
  
### <a name="remarks"></a>コメント  
 Id の範囲の始まり`id1`で終わります`id2`です。 マップ コントロールのいずれかから指定された通知のハンドラーが呼び出されます。  
  
 メッセージ マップの範囲の自動サポートがないため、自分でマクロを配置する必要があります。  
  
 コントロール Id の範囲に対するハンドラー関数を実装する方法についてを参照してください[メッセージ マップの範囲内のハンドラー](../../mfc/handlers-for-message-map-ranges.md)です。  
  
### <a name="requirements"></a>要件  
 **ヘッダー:** afxmsg_.h  
  



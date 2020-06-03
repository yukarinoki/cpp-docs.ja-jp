---
title: メッセージ マップ マクロ (MFC)
ms.date: 03/27/2019
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
ms.openlocfilehash: 6e9291f0f39057403bc27c7fe4ff5ca5a82dfe3a
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81356583"
---
# <a name="message-map-macros-mfc"></a>メッセージ マップ マクロ (MFC)

メッセージ マップをサポートするために、MFC には次のマクロが用意されています。

### <a name="message-map-declaration-and-demarcation-macros"></a>メッセージ マップ宣言と区切りマクロ

|||
|-|-|
|[DECLARE_MESSAGE_MAP](#declare_message_map)|メッセージ マップをクラス内で使用して、メッセージを関数にマップすることを宣言します (クラス宣言で使用する必要があります)。|
|[BEGIN_MESSAGE_MAP](#begin_message_map)|メッセージ マップの定義を開始します (クラス実装で使用する必要があります)。|
|[BEGIN_TEMPLATE_MESSAGE_MAP](#begin_template_message_map)|単一のテンプレート引数を含むクラス型でメッセージ マップの定義を開始します。 |
|[END_MESSAGE_MAP](#end_message_map)|メッセージ マップの定義を終了します (クラス実装で使用する必要があります)。|

### <a name="message-mapping-macros"></a>メッセージ マッピング マクロ

|||
|-|-|
|[ON_COMMAND](#on_command)|指定したコマンド メッセージを処理する関数を示します。|
|[ON_COMMAND_EX](#on_command_ex)|指定したコマンド メッセージを処理する関数を示します。|
|[ON_CONTROL](#on_control)|指定したコントロール通知メッセージを処理する関数を示します。|
|[ON_MESSAGE](#on_message)|ユーザー定義メッセージを処理する関数を示します。|
|[ON_OLECMD](#on_olecmd)|どの関数が DocObject またはそのコンテナからメニュー コマンドを処理するかを示します。|
|[ON_REGISTERED_MESSAGE](#on_registered_message)|登録されたユーザー定義メッセージを処理する関数を示します。|
|[ON_REGISTERED_THREAD_MESSAGE](#on_registered_thread_message)|クラスがある場合に、登録されたユーザー定義メッセージを処理する関数を`CWinThread`示します。|
|[ON_THREAD_MESSAGE](#on_thread_message)|クラスがある場合に、ユーザー定義メッセージを処理する関数を示`CWinThread`します。|
|[ON_UPDATE_COMMAND_UI](#on_update_command_ui)|指定したユーザー インターフェイス更新コマンド メッセージを処理する関数を示します。|

### <a name="message-map-range-macros"></a>メッセージ マップ範囲マクロ

|||
|-|-|
|[ON_COMMAND_RANGE](#on_command_range)|マクロに対する最初の 2 つのパラメーターで指定されたコマンド ID の範囲を処理する関数を示します。|
|[ON_UPDATE_COMMAND_UI_RANGE](#on_update_command_ui_range)|マクロに対する最初の 2 つのパラメーターで指定されたコマンド ID の範囲を処理する更新ハンドラーを示します。|
|[ON_CONTROL_RANGE](#on_control_range)|マクロに対して 2 番目と 3 番目のパラメーターで指定されたコントロール ID の範囲から通知を処理する関数を示します。 最初のパラメーターは、BN_CLICKEDなどのコントロール通知メッセージです。|

メッセージ マップ、メッセージ マップ宣言マクロ、およびメッセージ マップ マクロ、およびメッセージ マップ マクロの詳細については、「[メッセージ マップ](../../mfc/reference/message-maps-mfc.md)と[メッセージ処理とマッピングのトピック](../../mfc/message-handling-and-mapping.md)」を参照してください。 メッセージ マップ範囲の詳細については、「メッセージ マップ範囲[のハンドラー](../../mfc/handlers-for-message-map-ranges.md)」を参照してください。

## <a name="begin_message_map"></a><a name="begin_message_map"></a>BEGIN_MESSAGE_MAP

メッセージ マップの定義を開始します。

### <a name="syntax"></a>構文

```cpp
BEGIN_MESSAGE_MAP( theClass, baseClass )
```

### <a name="parameters"></a>パラメーター

*クラス*<br/>
メッセージ マップが指定されているクラスの名前を指定します。

*Baseclass*<br/>
クラスの基本クラスの名前*を*指定します。

### <a name="remarks"></a>解説

クラスのメンバー関数を定義する実装 (.cpp) ファイルで、BEGIN_MESSAGE_MAP マクロを使用してメッセージ マップを開始し、メッセージ ハンドラー関数ごとにマクロ エントリを追加し、END_MESSAGE_MAP マクロを使用してメッセージ マップを完了します。

メッセージ マップの詳細については、「[メッセージ マップ」を](message-maps-mfc.md)参照してください。

### <a name="example"></a>例

```cpp
BEGIN_MESSAGE_MAP(CMainFrame, CMDIFrameWnd)
   ON_WM_CREATE()
END_MESSAGE_MAP()
```

### <a name="requirements"></a>必要条件

**ヘッダー:** afxwin.h

## <a name="begin_template_message_map"></a><a name="begin_template_message_map"></a>BEGIN_TEMPLATE_MESSAGE_MAP

単一のテンプレート引数を含むクラス型でメッセージ マップの定義を開始します。

### <a name="syntax"></a>構文

```cpp
BEGIN_TEMPLATE_MESSAGE_MAP( theClass, type_name, baseClass )
```

### <a name="parameters"></a>パラメーター

*クラス*<br/>
メッセージ マップが指定されているクラスの名前を指定します。

*type_name*<br/>
クラスに指定されたテンプレート パラメーターの名前。

*Baseclass*<br/>
クラスの基本クラスの名前*を*指定します。

### <a name="remarks"></a>解説

このマクロは[、BEGIN_MESSAGE_MAP](message-map-macros-mfc.md#begin_message_map)マクロに似ています。ただし、このマクロは、単一のテンプレート引数を含むクラスを対象としています。

クラスのメソッド実装セクションで、BEGIN_TEMPLATE_MESSAGE_MAP マクロを使用してメッセージ マップを開始します。次に、標準のメッセージ マップの場合と同様に、メッセージ ハンドラー メソッドごとにマクロ エントリを追加します。 BEGIN_MESSAGE_MAP マクロと同様に[、END_MESSAGE_MAP](message-map-macros-mfc.md#end_message_map)マクロを使用してテンプレート メッセージ マップを完成させます。

テンプレート クラスのメッセージ マップの実装の詳細については、「[方法 : テンプレート クラスのメッセージ マップを作成する](../how-to-create-a-message-map-for-a-template-class.md)」を参照してください。

### <a name="requirements"></a>必要条件

**ヘッダー:** afxwin.h

## <a name="declare_message_map"></a><a name="declare_message_map"></a>DECLARE_MESSAGE_MAP

クラスがメッセージ マップを定義することを宣言します。 プログラム`CCmdTarget`内の各派生クラスは、メッセージを処理するためのメッセージ マップを提供する必要があります。

### <a name="syntax"></a>構文

```cpp
DECLARE_MESSAGE_MAP( )
```

### <a name="remarks"></a>解説

クラス宣言の最後にDECLARE_MESSAGE_MAPマクロを使用します。 次に、クラスのメンバー関数を定義する .cpp ファイルで、BEGIN_MESSAGE_MAP マクロ、メッセージ ハンドラー関数ごとにマクロ エントリ、およびEND_MESSAGE_MAP マクロを使用します。

> [!NOTE]
> DECLARE_MESSAGE_MAP後にメンバーを宣言する場合は、新しいアクセスの種類 (**public**、 private 、**または****プロテクト**) を指定する必要があります。

メッセージ マップとDECLARE_MESSAGE_MAP マクロの詳細については、「[メッセージ処理とマッピングのトピック」を参照してください](../../mfc/message-handling-and-mapping.md)。

### <a name="example"></a>例

```cpp
class CMainFrame : public CMDIFrameWnd
{
   DECLARE_MESSAGE_MAP()

   // Remainder of class declaration omitted.
```

### <a name="requirements"></a>必要条件

**ヘッダー:** afxwin.h

## <a name="end_message_map"></a><a name="end_message_map"></a>END_MESSAGE_MAP

メッセージ マップの定義を終了します。

### <a name="syntax"></a>構文

```cpp
END_MESSAGE_MAP( )
```

### <a name="remarks"></a>解説

メッセージ マップとEND_MESSAGE_MAP マクロの詳細については、「[メッセージ処理とマッピングのトピック」を参照してください](../../mfc/message-handling-and-mapping.md)。

### <a name="requirements"></a>必要条件

**ヘッダー:** afxwin.h

## <a name="on_command"></a><a name="on_command"></a>ON_COMMAND

このマクロは、コマンド メッセージをメンバー関数にマップします。

### <a name="syntax"></a>構文

```cpp
ON_COMMAND( commandId, memberFxn )
```

### <a name="parameters"></a>パラメーター

*Commandid*<br/>
コマンド ID。

*メンバーFxn*<br/>
コマンドがマップされるメッセージ ハンドラー関数の名前。

### <a name="remarks"></a>解説

メニュー項目やツール バー ボタンなどのコマンド ユーザー インターフェイス オブジェクトからのコマンド メッセージを処理する関数を示します。

コマンド ターゲット オブジェクトが指定された ID の Windows WM_COMMAND メッセージを受信すると、ON_COMMAND`memberFxn`は、メッセージを処理するメンバー関数を呼び出します。

ON_COMMANDを使用して、単一のコマンドをメンバー関数にマップします。 [ON_COMMAND_RANGE](#on_command_range)を使用して、コマンド ID の範囲を 1 つのメンバー関数にマップします。 1 つのコマンド ID に一致できるメッセージ マップ エントリは 1 つだけです。 つまり、コマンドを複数のハンドラーにマップすることはできません。 詳細と例については、[メッセージ処理とマッピングのトピックを](../../mfc/message-handling-and-mapping.md)参照してください。

### <a name="example"></a>例

```cpp
BEGIN_MESSAGE_MAP(CMFCListViewDoc, CDocument)
   ON_COMMAND(ID_MYCOMMAND, &CMFCListViewDoc::OnMycommand)
END_MESSAGE_MAP()
```

### <a name="requirements"></a>必要条件

**ヘッダー:** afxmsg_.h

## <a name="on_command_ex"></a><a name="on_command_ex"></a>ON_COMMAND_EX

拡張コマンド ハンドラー メンバー関数。

### <a name="syntax"></a>構文

```cpp
ON_COMMAND_EX(commandId, memberFxn);
```

### <a name="parameters"></a>パラメーター

*Commandid*<br/>
コマンド ID。

*メンバーFxn*<br/>
コマンドがマップされるメッセージ ハンドラー関数の名前。

### <a name="remarks"></a>解説

拡張形式のコマンド メッセージ ハンドラは、高度な使用のために使用できます。 ON_COMMAND_EX マクロは、このようなメッセージ ハンドラーに使用され[、ON_COMMAND](message-map-macros-mfc.md#on_command)機能のスーパーセットを提供します。 拡張コマンド ハンドラー メンバー関数は、単一のパラメーターを受け取り、コマンド ID を含む UINT を受け取り、BOOL を返します。 コマンドが処理されたことを示すには、戻り値を TRUE にする必要があります。それ以外の場合は、他のコマンド ターゲット オブジェクトへのルーティングが続行されます。

詳細については、テクニカル ノート [TN006: メッセージ マップ] tm006-メッセージ maps.mdを参照してください。

### <a name="requirements"></a>必要条件

ヘッダー ファイル: afxmsg_.h

## <a name="on_control"></a><a name="on_control"></a>ON_CONTROL

カスタム コントロール通知メッセージを処理する関数を示します。

### <a name="syntax"></a>構文

```cpp
ON_CONTROL( wNotifyCode, commandId, memberFxn )
```

### <a name="parameters"></a>パラメーター

*コードを通知します。*<br/>
コントロールの通知コード。

*Commandid*<br/>
コマンド ID。

*メンバーFxn*<br/>
コマンドがマップされるメッセージ ハンドラー関数の名前。

### <a name="remarks"></a>解説

コントロール通知メッセージは、コントロールから親ウィンドウに送信されるメッセージです。

メッセージ ハンドラー関数にマップする必要があるすべてのコントロール通知メッセージに対して、メッセージ マップ内にマクロ ステートメントが 1 つのみのON_CONTROL必要があります。

詳細と例については、[メッセージ処理とマッピングのトピックを](../../mfc/message-handling-and-mapping.md)参照してください。

### <a name="requirements"></a>必要条件

**ヘッダー:** afxmsg_.h

## <a name="on_message"></a><a name="on_message"></a>ON_MESSAGE

ユーザー定義メッセージを処理する関数を示します。

### <a name="syntax"></a>構文

```cpp
ON_MESSAGE( message, memberFxn )
```

### <a name="parameters"></a>パラメーター

*メッセージ*<br/>
メッセージ ID。

*メンバーFxn*<br/>
メッセージがマップされるメッセージ ハンドラー関数の名前。

関数の型は`afx_msg LRESULT (CWnd::*)(WPARAM, LPARAM)`.

### <a name="remarks"></a>解説

ユーザー定義メッセージは、標準の Windows WM_MESSAGE メッセージではないメッセージです。 メッセージ ID を選択する場合は、WM_USER (0x0400) から 0x7FFF、または WM_APP (0x8000) から 0xBFFF の範囲内の値を使用する必要があります。 メッセージ ID の詳細については、「 [WM_APP](/windows/win32/winmsg/wm-app)」を参照してください。

メッセージ・ハンドラー関数にマップする必要があるユーザー定義メッセージごとに、メッセージ・マップ内に 1 つのマクロ・ステートメントON_MESSAGE必要があります。

> [!NOTE]
> ユーザー定義のメッセージに加えて、ON_MESSAGEは、あまり一般的でない Windows メッセージを処理します。 詳細については、「メッセージ[マップ」を](../../mfc/tn006-message-maps.md)参照してください。

詳細と例については、「[メッセージの処理とマッピングのトピック」](../../mfc/message-handling-and-mapping.md)および[「ユーザー定義ハンドラ](user-defined-handlers.md)」を参照してください。

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

### <a name="requirements"></a>必要条件

**ヘッダー:** afxmsg_.h

## <a name="on_olecmd"></a><a name="on_olecmd"></a>ON_OLECMD

コマンドディスパッチインタフェース`IOleCommandTarget`を介してコマンドをルーティングします。

### <a name="syntax"></a>構文

```cpp
ON_OLECMD( pguid, olecmdid, commandId )
```

### <a name="parameters"></a>パラメーター

*pguid*<br/>
コマンドが属するコマンド・グループの ID。 標準グループには NULL を使用します。

*オレミディディ*<br/>
OLE コマンドの識別子。

*Commandid*<br/>
コマンドを発行するリソースまたはオブジェクトのメニュー ID、ツールバー ID、ボタン ID、またはその他の ID。

### <a name="remarks"></a>解説

`IOleCommandTarget`では、DocObject のユーザー インターフェイスから生成されたコマンドをコンテナが受け取ることができ、同じコマンド ([ファイル] メニューの [新規作成]、[開く]、[名前を付けて保存]、[印刷]、および [編集] メニューの [コピー]、[貼り付け]、[元に戻す]など) を送信できます。

`IOleCommandTarget`は OLE オートメーションよりも簡単です`IDispatch`。 `IOleCommandTarget`引数を持つことはほとんどなく、型情報が関与しない標準のコマンド セットに完全に依存します (コマンド引数のタイプ セーフも減少します)。 引数を指定してコマンドをディスパッチする必要がある場合[は、を使用します](coleserverdoc-class.md#onexecolecmd)。

`IOleCommandTarget`標準のメニュー コマンドは、次のマクロで MFC によって実装されています。

**ON_OLECMD_CLEARSELECTION( )**

[クリアの編集]コマンドを送出します。 次のように実装されます。

`ON_OLECMD(NULL, OLECMDID_CLEARSELECTION, ID_EDIT_CLEAR)`

**ON_OLECMD_COPY( )**

[コピーの編集] コマンドをディスパッチします。 次のように実装されます。

`ON_OLECMD(NULL, OLECMDID_COPY, ID_EDIT_COPY)`

**ON_OLECMD_CUT( )**

[カットを編集]コマンドを送出します。 次のように実装されます。

`ON_OLECMD(NULL, OLECMDID_CUT, ID_EDIT_CUT)`

**ON_OLECMD_NEW( )**

[ファイル新規作成] コマンドをディスパッチします。 次のように実装されます。

`ON_OLECMD(NULL, OLECMDID_NEW, ID_FILE_NEW)`

**ON_OLECMD_OPEN( )**

[ファイルを開く] コマンドをディスパッチします。 次のように実装されます。

`ON_OLECMD(NULL, OLECMDID_OPEN, ID_FILE_OPEN)`

**ON_OLECMD_PAGESETUP( )**

[ファイル ページ設定] コマンドを送出します。 次のように実装されます。

`ON_OLECMD(NULL, OLECMDID_PAGESETUP, ID_FILE_PAGE_SETUP)`

**ON_OLECMD_PASTE( )**

[貼り付けの編集] コマンドをディスパッチします。 次のように実装されます。

`ON_OLECMD(NULL, OLECMDID_PASTE, ID_EDIT_PASTE)`

**ON_OLECMD_PASTESPECIAL( )**

[貼り付け形式の編集]コマンドを送出します。 次のように実装されます。

`ON_OLECMD(NULL, OLECMDID_PASTESPECIAL, ID_EDIT_PASTE_SPECIAL)`

**ON_OLECMD_PRINT( )**

[ファイルの印刷] コマンドをディスパッチします。 次のように実装されます。

`ON_OLECMD(NULL, OLECMDID_PRINT, ID_FILE_PRINT)`

**ON_OLECMD_PRINTPREVIEW( )**

[ファイルの印刷プレビュー] コマンドを送出します。 次のように実装されます。

`ON_OLECMD(NULL, OLECMDID_PRINTPREVIEW, ID_FILE_PRINT_PREVIEW)`

**ON_OLECMD_REDO( )**

[やり直しの編集] コマンドをディスパッチします。 次のように実装されます。

`ON_OLECMD(NULL, OLECMDID_REDO, ID_EDIT_REDO)`

**ON_OLECMD_SAVE( )**

[ファイルの保存] コマンドをディスパッチします。 次のように実装されます。

`ON_OLECMD(NULL, OLECMDID_SAVE, ID_FILE_SAVE)`

**ON_OLECMD_SAVE_AS( )**

[名前を付けてファイルを保存]コマンドを送出します。 次のように実装されます。

`ON_OLECMD(NULL, OLECMDID_SAVEAS, ID_FILE_SAVE_AS)`

**ON_OLECMD_SAVE_COPY_AS( )**

[ファイルのコピーを名前を付けて保存]コマンドを送出します。 次のように実装されます。

`ON_OLECMD(NULL, OLECMDID_SAVECOPYAS, ID_FILE_SAVE_COPY_AS)`

**ON_OLECMD_SELECTALL( )**

[すべて選択を編集]コマンドを送出します。 次のように実装されます。

`ON_OLECMD(NULL, OLECMDID_SELECTALL, ID_EDIT_SELECT_ALL)`

**ON_OLECMD_UNDO( )**

[元に戻す操作を編集]コマンドを送出します。 次のように実装されます。

`ON_OLECMD(NULL, OLECMDID_UNDO, ID_EDIT_UNDO)`

### <a name="requirements"></a>必要条件

**ヘッダー:** afxdocob.h

## <a name="on_registered_message"></a><a name="on_registered_message"></a>ON_REGISTERED_MESSAGE

Windows`RegisterWindowMessage`関数は、システム全体で一意であることが保証される新しいウィンドウ メッセージを定義するために使用されます。

### <a name="syntax"></a>構文

```cpp
ON_REGISTERED_MESSAGE( nMessageVariable, memberFxn )
```

### <a name="parameters"></a>パラメーター

*メッセージ変数*<br/>
登録済みのウィンドウ メッセージ ID 変数。

*メンバーFxn*<br/>
メッセージがマップされるメッセージ ハンドラー関数の名前。

### <a name="remarks"></a>解説

このマクロは、登録されたメッセージを処理する関数を示します。

詳細と例については、[メッセージ処理とマッピングのトピックを](../../mfc/message-handling-and-mapping.md)参照してください。

### <a name="example"></a>例

```cpp
static UINT NEAR WM_FIND = RegisterWindowMessage(_T("COMMDLG_FIND"));

BEGIN_MESSAGE_MAP(CMyWnd3, CWnd)
   ON_REGISTERED_MESSAGE(WM_FIND, OnFind)
END_MESSAGE_MAP()
```

### <a name="requirements"></a>必要条件

**ヘッダー:** afxmsg_.h

## <a name="on_registered_thread_message"></a><a name="on_registered_thread_message"></a>ON_REGISTERED_THREAD_MESSAGE

関数によって登録されたメッセージを処理する関数を示します。

### <a name="syntax"></a>構文

```cpp
ON_REGISTERED_THREAD_MESSAGE(nMessageVariable, memberFxn )
```

### <a name="parameters"></a>パラメーター

*メッセージ変数*<br/>
登録済みのウィンドウ メッセージ ID 変数。

*メンバーFxn*<br/>
メッセージがマップされる CWinThread メッセージ ハンドラー関数の名前。

### <a name="remarks"></a>解説

システム全体で一意であることが保証される新しいウィンドウ メッセージを定義するために使用されます。 ON_REGISTERED_THREAD_MESSAGEは、CWinThread クラスを持っている場合にON_REGISTERED_MESSAGEの代わりに使用する必要があります。

### <a name="requirements"></a>必要条件

**ヘッダー:** afxmsg_.h

## <a name="on_thread_message"></a><a name="on_thread_message"></a>ON_THREAD_MESSAGE

ユーザー定義メッセージを処理する関数を示します。

### <a name="syntax"></a>構文

```cpp
ON_THREAD_MESSAGE( message, memberFxn )
```

### <a name="parameters"></a>パラメーター

*メッセージ*<br/>
メッセージ ID。

*メンバーFxn*<br/>
メッセージが`CWinThread`マップされる -message ハンドラ関数の名前。

### <a name="remarks"></a>解説

ON_THREAD_MESSAGEクラスを持っている場合は、ON_MESSAGEの代`CWinThread`わりに使用する必要があります。 ユーザー定義メッセージは、標準の Windows WM_MESSAGE メッセージではないメッセージです。 メッセージ・ハンドラー関数ON_THREAD_MESSAGEマップする必要があるユーザー定義メッセージごとに、メッセージ・マップ内に 1 つのマクロ・ステートメントが存在する必要があります。

### <a name="requirements"></a>必要条件

**ヘッダー:** afxole.h

## <a name="on_update_command_ui"></a><a name="on_update_command_ui"></a>On_update_command_ui

このマクロは、ユーザー インターフェイス更新コマンド メッセージを処理する関数を示します。

### <a name="syntax"></a>構文

```cpp
ON_UPDATE_COMMAND_UI( messageId, memberFxn )
```

### <a name="parameters"></a>パラメーター

*messageId*<br/>
メッセージ ID。

*メンバーFxn*<br/>
メッセージがマップされるメッセージ ハンドラー関数の名前。

### <a name="remarks"></a>解説

メッセージ ハンドラー関数にマップする必要があるすべてのユーザー インターフェイス更新コマンドに対して、メッセージ マップ内に ON_UPDATE_COMMAND_UI マクロ ステートメントが 1 つだけ存在する必要があります。

詳細と例については、[メッセージ処理とマッピングのトピックを](../../mfc/message-handling-and-mapping.md)参照してください。

### <a name="requirements"></a>必要条件

**ヘッダー:** afxole.h

## <a name="on_command_range"></a><a name="on_command_range"></a>ON_COMMAND_RANGE

このマクロを使用して、連続する範囲のコマンド ID を単一のメッセージ ハンドラー関数にマップします。

### <a name="syntax"></a>構文

```cpp
ON_COMMAND_RANGE( id1, id2, memberFxn )
```

### <a name="parameters"></a>パラメーター

*id1*<br/>
連続する範囲のコマンド ID の先頭にあるコマンド ID。

*id2*<br/>
連続する範囲のコマンド ID の末尾にあるコマンド ID。

*メンバーFxn*<br/>
コマンドがマップされるメッセージ ハンドラー関数の名前。

### <a name="remarks"></a>解説

ID の範囲は*id1*で始まり *、id2*で終わります。

ON_COMMAND_RANGEを使用して、コマンド ID の範囲を 1 つのメンバー関数にマップします。 [ON_COMMAND](#on_command)を使用して、単一のコマンドをメンバー関数にマップします。 1 つのコマンド ID に一致できるメッセージ マップ エントリは 1 つだけです。 つまり、コマンドを複数のハンドラーにマップすることはできません。 メッセージ範囲のマッピングの詳細については、「[メッセージ マップ範囲のハンドラー](../../mfc/handlers-for-message-map-ranges.md)」を参照してください。

メッセージ マップ範囲の自動サポートはないので、マクロは自分で配置する必要があります。

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

### <a name="requirements"></a>必要条件

**ヘッダー:** afxmsg_.h

## <a name="on_update_command_ui_range"></a><a name="on_update_command_ui_range"></a>ON_UPDATE_COMMAND_UI_RANGE

連続した範囲のコマンド ID を単一の更新メッセージ ハンドラー関数に割り当てます。

### <a name="syntax"></a>構文

```cpp
ON_UPDATE_COMMAND_UI_RANGE( id1, id2, memberFxn )
```

### <a name="parameters"></a>パラメーター

*id1*<br/>
連続する範囲のコマンド ID の先頭にあるコマンド ID。

*id2*<br/>
連続する範囲のコマンド ID の末尾にあるコマンド ID。

*メンバーFxn*<br/>
コマンドがマップされる更新メッセージ ハンドラー関数の名前。

### <a name="remarks"></a>解説

更新メッセージ ハンドラーは、コマンドに関連付けられているメニュー項目とツール バー ボタンの状態を更新します。 ID の範囲は*id1*で始まり *、id2*で終わります。

メッセージ マップ範囲の自動サポートはないので、マクロは自分で配置する必要があります。

### <a name="requirements"></a>必要条件

**ヘッダー:** afxmsg_.h

## <a name="on_control_range"></a><a name="on_control_range"></a>ON_CONTROL_RANGE

このマクロを使用して、指定した Windows 通知メッセージ (BN_CLICKEDなど) の単一のメッセージ ハンドラー関数に、連続した範囲のコントロール ID をマップします。

### <a name="syntax"></a>構文

```cpp
ON_CONTROL_RANGE( wNotifyCode, id1, id2, memberFxn )
```

### <a name="parameters"></a>パラメーター

*コードを通知します。*<br/>
ハンドラーが応答する通知コード。

*id1*<br/>
連続する範囲のコントロール ID の先頭にあるコマンド ID。

*id2*<br/>
連続する範囲のコントロール ID の末尾にあるコマンド ID。

*メンバーFxn*<br/>
コントロールがマップされるメッセージ ハンドラー関数の名前。

### <a name="remarks"></a>解説

ID の範囲は*id1*で始まり *、id2*で終わります。 ハンドラーは、マップされたコントロールのいずれかから取得される指定された通知に対して呼び出されます。

メッセージ マップ範囲の自動サポートはないので、マクロは自分で配置する必要があります。

さまざまなコントロール ID のハンドラー関数の実装の詳細については、「[メッセージ マップ範囲のハンドラー](../../mfc/handlers-for-message-map-ranges.md)」を参照してください。

### <a name="requirements"></a>必要条件

**ヘッダー:** afxmsg_.h

## <a name="see-also"></a>関連項目

[ON_COMMAND](message-map-macros-mfc.md#on_command)<br/>
[テクニカル ノート 6: メッセージ マップ](../tn006-message-maps.md)<br/>
[クラス](colecmdui-class.md)<br/>
[をクリックします。](coleserverdoc-class.md#onexecolecmd)<br/>
[ウィンドウメッセージを登録します。](/windows/win32/api/winuser/nf-winuser-registerwindowmessagew)<br/>
[ユーザー定義ハンドラー](user-defined-handlers.md)<br/>
[CCmdUI クラス](ccmdui-class.md)

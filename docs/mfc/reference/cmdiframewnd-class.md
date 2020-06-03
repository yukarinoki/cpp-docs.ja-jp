---
title: CMDIFrameWnd クラス
ms.date: 11/04/2016
f1_keywords:
- CMDIFrameWnd
- AFXWIN/CMDIFrameWnd
- AFXWIN/CMDIFrameWnd::CMDIFrameWnd
- AFXWIN/CMDIFrameWnd::CreateClient
- AFXWIN/CMDIFrameWnd::CreateNewChild
- AFXWIN/CMDIFrameWnd::GetWindowMenuPopup
- AFXWIN/CMDIFrameWnd::MDIActivate
- AFXWIN/CMDIFrameWnd::MDICascade
- AFXWIN/CMDIFrameWnd::MDIGetActive
- AFXWIN/CMDIFrameWnd::MDIIconArrange
- AFXWIN/CMDIFrameWnd::MDIMaximize
- AFXWIN/CMDIFrameWnd::MDINext
- AFXWIN/CMDIFrameWnd::MDIPrev
- AFXWIN/CMDIFrameWnd::MDIRestore
- AFXWIN/CMDIFrameWnd::MDISetMenu
- AFXWIN/CMDIFrameWnd::MDITile
helpviewer_keywords:
- CMDIFrameWnd [MFC], CMDIFrameWnd
- CMDIFrameWnd [MFC], CreateClient
- CMDIFrameWnd [MFC], CreateNewChild
- CMDIFrameWnd [MFC], GetWindowMenuPopup
- CMDIFrameWnd [MFC], MDIActivate
- CMDIFrameWnd [MFC], MDICascade
- CMDIFrameWnd [MFC], MDIGetActive
- CMDIFrameWnd [MFC], MDIIconArrange
- CMDIFrameWnd [MFC], MDIMaximize
- CMDIFrameWnd [MFC], MDINext
- CMDIFrameWnd [MFC], MDIPrev
- CMDIFrameWnd [MFC], MDIRestore
- CMDIFrameWnd [MFC], MDISetMenu
- CMDIFrameWnd [MFC], MDITile
ms.assetid: fa8736e6-511b-4c51-8b4d-eba78378aeb9
ms.openlocfilehash: d5c9bc12e6c3f0ab4742a940547087c9742caf73
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "81754549"
---
# <a name="cmdiframewnd-class"></a>CMDIFrameWnd クラス

Windows のマルチ ドキュメント インターフェイス (MDI: Multiple Document Interface) のフレーム ウィンドウの機能が用意されています。さらに、ウィンドウを管理するメンバーも用意されています。

## <a name="syntax"></a>構文

```
class CMDIFrameWnd : public CFrameWnd
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CMDI フレームウンド::CMDI フレームウンド](#cmdiframewnd)|`CMDIFrameWnd` を構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[コマンドフレーム::クライアントの作成](#createclient)|この`CMDIFrameWnd`ウィンドウのウィンドウを作成します。 の`OnCreate``CWnd`メンバー関数によって呼び出されます。|
|[CMDIフレームウンド::新しい子を作成します。](#createnewchild)|新しい子ウィンドウを作成します。|
|[をクリックします。](#getwindowmenupopup)|ウィンドウポップアップメニューを返します。|
|[コマンドイフレームウンド::MDIアクティベート](#mdiactivate)|別の MDI 子ウィンドウをアクティブにします。|
|[CMDIFrameWnd::MDICascade](#mdicascade)|すべての子ウィンドウを重ねて表示します。|
|[を使用します。](#mdigetactive)|現在アクティブな MDI 子ウィンドウを取得し、子ウィンドウが最大化されているかどうかを示すフラグを指定します。|
|[コミフレームウンド::MDIアイコンの配置](#mdiiconarrange)|最小化されたすべてのドキュメントの子ウィンドウを整列します。|
|[マチフレームウンド::MDI最大化](#mdimaximize)|MDI 子ウィンドウを最大化します。|
|[次のコマンド](#mdinext)|現在アクティブな子ウィンドウのすぐ後ろの子ウィンドウをアクティブにし、現在アクティブな子ウィンドウを他のすべての子ウィンドウの後ろに配置します。|
|[マフティフレームウンド::MDIPrev](#mdiprev)|前の子ウィンドウをアクティブにし、現在アクティブな子ウィンドウをそのすぐ後ろに配置します。|
|[マシフレームウンド::MDI復元](#mdirestore)|MDI 子ウィンドウを最大化または最小化されたサイズから復元します。|
|[メニューメニュー](#mdisetmenu)|MDI フレーム ウィンドウ、ウィンドウ ポップアップ メニュー、またはその両方のメニューを置き換えます。|
|[マチフレームウンド::MDITile](#mditile)|すべての子ウィンドウを並べて表示します。|

## <a name="remarks"></a>解説

アプリケーションに便利な MDI フレーム ウィンドウを作成するには、`CMDIFrameWnd`からクラスを派生させます。 派生クラスにメンバー変数を追加して、アプリケーション固有のデータを格納します。 ウィンドウにメッセージが送られたときに行われる処理を指定するには、派生クラスにメッセージ処理メンバー関数とメッセージ マップを実装します。

の[作成](../../mfc/reference/cframewnd-class.md#create)または[LoadFrame](../../mfc/reference/cframewnd-class.md#loadframe)メンバー関数を呼び出すことによって、MDI`CFrameWnd`フレーム ウィンドウを構築できます。

または`LoadFrame`を`Create`呼び出す前に、C++ **new**演算子を使用してフレーム ウィンドウ オブジェクトをヒープ上に構築する必要があります。 呼び`Create`出す前に、フレームのアイコンとクラス スタイルを設定する[AfxRegisterWndClass](application-information-and-management.md#afxregisterwndclass)グローバル関数を使用してウィンドウ クラスを登録することもできます。

メンバー関数`Create`を使用して、フレームの作成パラメーターを即時引数として渡します。

`LoadFrame`必要な引数は`Create`よりも少なく、代わりに、フレームのキャプション、アイコン、アクセラレータ テーブル、メニューなど、リソースからその既定値のほとんどを取得します。 で`LoadFrame`アクセスするには、これらすべてのリソースに同じリソース ID (たとえば、IDR_MAINFRAME) が必要です。

から`MDIFrameWnd``CFrameWnd`派生していますが、 から`CMDIFrameWnd`派生したフレーム ウィンドウ クラスは、`DECLARE_DYNCREATE`で宣言する必要はありません。

この`CMDIFrameWnd`クラスは、既定の実装の多くを`CFrameWnd`から継承します。 これらの機能の詳細なリストについては[、CFrameWnd](../../mfc/reference/cframewnd-class.md)クラスの説明を参照してください。 この`CMDIFrameWnd`クラスには、次の追加機能があります。

- MDI フレーム ウィンドウは、コントロール バーと共に MDICLIENT ウィンドウの位置を変更して管理します。 MDI クライアント ウィンドウは、MDI 子フレーム ウィンドウの直接の親です。 WS_HSCROLLおよびWS_VSCROLLウィンドウ スタイルは、メイン`CMDIFrameWnd`フレーム ウィンドウではなく MDI クライアント ウィンドウに適用されるため、ユーザーは MDI クライアント領域をスクロールできます (Windows プログラム マネージャなど)。

- MDI フレーム ウィンドウは、アクティブな MDI 子ウィンドウがない場合にメニュー バーとして使用される既定のメニューを所有します。 アクティブな MDI 子がある場合、MDI フレーム ウィンドウのメニュー バーは、MDI 子ウィンドウ メニューに自動的に置き換えられます。

- MDI フレーム ウィンドウは、現在の MDI 子ウィンドウ (存在する場合) と連動して動作します。 たとえば、コマンド メッセージは、MDI フレーム ウィンドウの前に現在アクティブな MDI 子に委任されます。

- MDI フレーム ウィンドウには、次の標準ウィンドウ メニュー コマンドの既定のハンドラーがあります。

  - ID_WINDOW_TILE_VERT

  - ID_WINDOW_TILE_HORZ

  - ID_WINDOW_CASCADE

  - ID_WINDOW_ARRANGE

- MDI フレーム ウィンドウには、ID_WINDOW_NEW の実装も含まれています。 アプリケーションは、これらの既定のコマンド実装をオーバーライドして、MDI ウィンドウ処理をカスタマイズできます。

C++**の delete**演算子を使用してフレーム ウィンドウを破棄しないでください。 代わりに `CWnd::DestroyWindow` を使用してください の`CFrameWnd``PostNcDestroy`実装は、ウィンドウが破棄されると C++ オブジェクトを削除します。 ユーザーがフレーム ウィンドウを閉じると、既定`OnClose`のハンドラーが`DestroyWindow`呼び出されます。

詳細については、「`CMDIFrameWnd`フレーム[ウィンドウ](../../mfc/frame-windows.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CFrameWnd](../../mfc/reference/cframewnd-class.md)

`CMDIFrameWnd`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxwin.h

## <a name="cmdiframewndcmdiframewnd"></a><a name="cmdiframewnd"></a>CMDI フレームウンド::CMDI フレームウンド

`CMDIFrameWnd` オブジェクトを構築します。

```
CMDIFrameWnd();
```

### <a name="remarks"></a>解説

または`LoadFrame``Create`メンバー関数を呼び出して、表示可能な MDI フレーム ウィンドウを作成します。

### <a name="example"></a>例

[!code-cpp[NVC_MFCWindowing#13](../../mfc/reference/codesnippet/cpp/cmdiframewnd-class_1.cpp)]

## <a name="cmdiframewndcreateclient"></a><a name="createclient"></a>コマンドフレーム::クライアントの作成

オブジェクトを管理する MDI クライアント`CMDIChildWnd`ウィンドウを作成します。

```
virtual BOOL CreateClient(
    LPCREATESTRUCT lpCreateStruct,
    CMenu* pWindowMenu);
```

### <a name="parameters"></a>パラメーター

*を作成します。*<br/>
[構造体](/windows/win32/api/winuser/ns-winuser-createstructw)への長いポインター。

*メニュー*<br/>
ウィンドウポップアップ メニューへのポインター。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>解説

メンバー関数を直接オーバーライドする場合は、この`OnCreate`メンバー関数を呼び出す必要があります。

### <a name="example"></a>例

[!code-cpp[NVC_MFCWindowing#14](../../mfc/reference/codesnippet/cpp/cmdiframewnd-class_2.cpp)]

## <a name="cmdiframewndcreatenewchild"></a><a name="createnewchild"></a>CMDIフレームウンド::新しい子を作成します。

新しい子ウィンドウを作成します。

```
CMDIChildWnd* CreateNewChild(
    CRuntimeClass* pClass,
    UINT nResource,
    HMENU hMenu = NULL,
    HACCEL hAccel = NULL);
```

### <a name="parameters"></a>パラメーター

*Pclass*<br/>
作成される子ウィンドウのランタイム クラス。

*nリソース*<br/>
子ウィンドウに関連付けられている共有リソースの ID。

*Hmenu*<br/>
子ウィンドウのメニュー。

*ハッセル*<br/>
子ウィンドウのアクセラレータ。

### <a name="remarks"></a>解説

MDI フレーム ウィンドウの子ウィンドウを作成するには、この関数を使用します。

### <a name="example"></a>例

[!code-cpp[NVC_MFCWindowing#15](../../mfc/reference/codesnippet/cpp/cmdiframewnd-class_3.cpp)]

## <a name="cmdiframewndgetwindowmenupopup"></a><a name="getwindowmenupopup"></a>をクリックします。

現在のポップアップ メニュー "Window" (MDI ウィンドウ管理用のメニュー項目を含むポップアップ メニュー) へのハンドルを取得します。

```
virtual HMENU GetWindowMenuPopup(HMENU hMenuBar);
```

### <a name="parameters"></a>パラメーター

*メニューバー*<br/>
現在のメニュー バー。

### <a name="return-value"></a>戻り値

ウィンドウポップアップメニューが存在する場合は、ウィンドウポップアップメニューを表示します。それ以外の場合は NULL。

### <a name="remarks"></a>解説

既定の実装では、ID_WINDOW_NEWやID_WINDOW_TILE_HORZなどの標準の Window メニュー コマンドを含むポップアップ メニューを検索します。

標準のメニュー コマンド ID を使用しないウィンドウ メニューがある場合は、このメンバー関数をオーバーライドします。

### <a name="example"></a>例

[!code-cpp[NVC_MFCWindowing#16](../../mfc/reference/codesnippet/cpp/cmdiframewnd-class_4.cpp)]

## <a name="cmdiframewndmdiactivate"></a><a name="mdiactivate"></a>コマンドイフレームウンド::MDIアクティベート

別の MDI 子ウィンドウをアクティブにします。

```cpp
void MDIActivate(CWnd* pWndActivate);
```

### <a name="parameters"></a>パラメーター

*アクティブ化*<br/>
アクティブ化する MDI 子ウィンドウへのポインター。

### <a name="remarks"></a>解説

このメンバー関数は、アクティブ化される子ウィンドウと非アクティブ化する子ウィンドウの両方に[WM_MDIACTIVATE](../../mfc/reference/cwnd-class.md#onmdiactivate)メッセージを送信します。

これは、マウスまたはキーボードを使用してユーザーが MDI 子ウィンドウにフォーカスを変更した場合に送信されるメッセージと同じです。

> [!NOTE]
> MDI の子ウィンドウは、MDI フレーム ウィンドウとは独立してアクティブになります。 フレームがアクティブになると、最後にアクティブになった子ウィンドウは、アクティブなウィンドウ フレームとキャプション バーを描画する[WM_NCACTIVATE](../../mfc/reference/cwnd-class.md#onncactivate)メッセージを送信しますが、別のWM_MDIACTIVATE メッセージは表示されません。

### <a name="example"></a>例

[の例を](#getwindowmenupopup)参照してください。

## <a name="cmdiframewndmdicascade"></a><a name="mdicascade"></a>CMDIFrameWnd::MDICascade

すべての MDI 子ウィンドウをカスケード形式で整列します。

```cpp
void MDICascade();
void MDICascade(int nType);
```

### <a name="parameters"></a>パラメーター

*nType*<br/>
カスケード フラグを指定します。 MDITILE_SKIPDISABLED フラグのみ指定できます。

### <a name="remarks"></a>解説

の最初の`MDICascade`バージョンでは、パラメーターを指定しない場合、無効な MDI 子ウィンドウを含むすべての MDI 子ウィンドウがカスケード表示されます。 2 番目のバージョンでは *、nType*パラメーターにMDITILE_SKIPDISABLED指定した場合、オプションで無効になっている MDI 子ウィンドウをカスケードしません。

### <a name="example"></a>例

[!code-cpp[NVC_MFCWindowing#17](../../mfc/reference/codesnippet/cpp/cmdiframewnd-class_5.cpp)]

## <a name="cmdiframewndmdigetactive"></a><a name="mdigetactive"></a>を使用します。

現在アクティブな MDI 子ウィンドウを取得し、子ウィンドウが最大化されているかどうかを示すフラグを付けます。

```
CMDIChildWnd* MDIGetActive(BOOL* pbMaximized = NULL) const;
```

### <a name="parameters"></a>パラメーター

*pb最大化*<br/>
BOOL 戻り値へのポインター。 ウィンドウが最大化されている場合は、戻り値として TRUE に設定します。それ以外の場合は FALSE。

### <a name="return-value"></a>戻り値

アクティブな MDI 子ウィンドウへのポインター。

### <a name="example"></a>例

この例については、[次](../../mfc/reference/cmdichildwnd-class.md#mdimaximize)の例を参照してください。

## <a name="cmdiframewndmdiiconarrange"></a><a name="mdiiconarrange"></a>コミフレームウンド::MDIアイコンの配置

最小化されたすべてのドキュメントの子ウィンドウを整列します。

```cpp
void MDIIconArrange();
```

### <a name="remarks"></a>解説

最小化されていない子ウィンドウには影響しません。

### <a name="example"></a>例

[次](#mdicascade)の例を参照してください。

## <a name="cmdiframewndmdimaximize"></a><a name="mdimaximize"></a>マチフレームウンド::MDI最大化

指定した MDI 子ウィンドウを最大化します。

```cpp
void MDIMaximize(CWnd* pWnd);
```

### <a name="parameters"></a>パラメーター

*Pwnd*<br/>
最大化するウィンドウへのポイント。

### <a name="remarks"></a>解説

子ウィンドウが最大化されると、Windows は、クライアント領域がクライアント ウィンドウ全体に表示されるように、子ウィンドウのサイズを変更します。 Windows では、子ウィンドウのコントロール メニューがフレームのメニュー バーに配置されるため、ユーザーは子ウィンドウを元に戻したり閉じたりできます。 また、フレーム ウィンドウのタイトルに子ウィンドウのタイトルを追加します。

現在アクティブな MDI 子ウィンドウが最大化されているときに別の MDI 子ウィンドウがアクティブ化されている場合、Windows は現在アクティブな子ウィンドウを復元し、新しくアクティブ化された子ウィンドウを最大化します。

### <a name="example"></a>例

この例については、[次](../../mfc/reference/cmdichildwnd-class.md#mdimaximize)の例を参照してください。

## <a name="cmdiframewndmdinext"></a><a name="mdinext"></a>次のコマンド

現在アクティブな子ウィンドウのすぐ後ろの子ウィンドウをアクティブにし、現在アクティブな子ウィンドウを他のすべての子ウィンドウの後ろに配置します。

```cpp
void MDINext();
```

### <a name="remarks"></a>解説

現在アクティブな MDI 子ウィンドウが最大化されている場合、メンバー関数は現在アクティブな子ウィンドウを復元し、新しくアクティブ化された子を最大化します。

### <a name="example"></a>例

[!code-cpp[NVC_MFCWindowing#18](../../mfc/reference/codesnippet/cpp/cmdiframewnd-class_6.cpp)]

## <a name="cmdiframewndmdiprev"></a><a name="mdiprev"></a>マフティフレームウンド::MDIPrev

前の子ウィンドウをアクティブにし、現在アクティブな子ウィンドウをそのすぐ後ろに配置します。

```cpp
void MDIPrev();
```

### <a name="remarks"></a>解説

現在アクティブな MDI 子ウィンドウが最大化されている場合、メンバー関数は現在アクティブな子ウィンドウを復元し、新しくアクティブ化された子を最大化します。

## <a name="cmdiframewndmdirestore"></a><a name="mdirestore"></a>マシフレームウンド::MDI復元

MDI 子ウィンドウを最大化または最小化されたサイズから復元します。

```cpp
void MDIRestore(CWnd* pWnd);
```

### <a name="parameters"></a>パラメーター

*Pwnd*<br/>
復元するウィンドウへのポイント。

### <a name="example"></a>例

[この](../../mfc/reference/cmdichildwnd-class.md#mdirestore)例を参照してください。

## <a name="cmdiframewndmdisetmenu"></a><a name="mdisetmenu"></a>メニューメニュー

MDI フレーム ウィンドウ、ウィンドウ ポップアップ メニュー、またはその両方のメニューを置き換えます。

```
CMenu* MDISetMenu(
    CMenu* pFrameMenu,
    CMenu* pWindowMenu);
```

### <a name="parameters"></a>パラメーター

*メニュー*<br/>
新しいフレーム ウィンドウ メニューのメニューを指定します。 NULL の場合、メニューは変更されません。

*メニュー*<br/>
新しいウィンドウポップアップメニューのメニューを指定します。 NULL の場合、メニューは変更されません。

### <a name="return-value"></a>戻り値

このメッセージに置き換えられたフレーム ウィンドウ メニューへのポインター。 ポインターは一時的である可能性があり、後で使用するために格納しないでください。

### <a name="remarks"></a>解説

を呼`MDISetMenu`び出した後、アプリケーションは、メニュー バーを`CWnd`更新する[の DrawMenuBar](../../mfc/reference/cwnd-class.md#drawmenubar)メンバー関数を呼び出す必要があります。

この呼び出しがウィンドウポップアップメニューに置き換わる場合、MDI の子ウィンドウメニュー項目は前のウィンドウメニューから削除され、新しいウィンドウポップアップメニューに追加されます。

MDI 子ウィンドウが最大化され、この呼び出しが MDI フレーム ウィンドウ メニューを置き換える場合、コントロール メニューと復元コントロールは前のフレーム ウィンドウ メニューから削除され、新しいメニューに追加されます。

MDI 子ウィンドウを管理するためにフレームワークを使用する場合は、このメンバー関数を呼び出しません。

### <a name="example"></a>例

[!code-cpp[NVC_MFCWindowing#19](../../mfc/reference/codesnippet/cpp/cmdiframewnd-class_7.cpp)]

[!code-cpp[NVC_MFCWindowing#20](../../mfc/reference/codesnippet/cpp/cmdiframewnd-class_8.cpp)]

## <a name="cmdiframewndmditile"></a><a name="mditile"></a>マチフレームウンド::MDITile

すべての子ウィンドウを並べて表示します。

```cpp
void MDITile();
void MDITile(int nType);
```

### <a name="parameters"></a>パラメーター

*nType*<br/>
タイル フラグを指定します。 このパラメーターには、次のいずれかのフラグを指定できます。

- MDITILE_HORIZONTAL MDI 子ウィンドウを並べて表示し、1 つのウィンドウが別のウィンドウの上に表示されるようにします。

- MDITILE_SKIPDISABLED 無効な MDI 子ウィンドウが並べて表示されないようにします。

- MDITILE_VERTICAL MDI 子ウィンドウを並べて表示し、1 つのウィンドウが別のウィンドウの横に表示されるようにします。

### <a name="remarks"></a>解説

の最初の`MDITile`バージョンでは、パラメーターなし、Windows バージョン 3.1 以降の下でウィンドウを垂直方向に並べて表示します。 2 番目のバージョンでは *、nType*パラメーターの値に応じて、ウィンドウを垂直方向または水平方向に並べて表示します。

### <a name="example"></a>例

[次](#mdicascade)の例を参照してください。

## <a name="see-also"></a>関連項目

[MDI のサンプル](../../overview/visual-cpp-samples.md)<br/>
[サンプル MDIDOCVW](../../overview/visual-cpp-samples.md)<br/>
[MFC サンプル スナップVW](../../overview/visual-cpp-samples.md)<br/>
[CFrameWnd クラス](../../mfc/reference/cframewnd-class.md)<br/>
[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[CWnd クラス](../../mfc/reference/cwnd-class.md)<br/>
[CMDIChildWnd クラス](../../mfc/reference/cmdichildwnd-class.md)

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
ms.openlocfilehash: 20d74030cdc90ed2e1a7809c121967e74db21b4a
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2020
ms.locfileid: "78866563"
---
# <a name="cmdiframewnd-class"></a>CMDIFrameWnd クラス

Windows のマルチ ドキュメント インターフェイス (MDI: Multiple Document Interface) のフレーム ウィンドウの機能が用意されています。さらに、ウィンドウを管理するメンバーも用意されています。

## <a name="syntax"></a>構文

```
class CMDIFrameWnd : public CFrameWnd
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|Name|Description|
|----------|-----------------|
|[CMDIFrameWnd:: CMDIFrameWnd](#cmdiframewnd)|`CMDIFrameWnd` を構築します。|

### <a name="public-methods"></a>パブリック メソッド

|Name|Description|
|----------|-----------------|
|[CMDIFrameWnd:: CreateClient](#createclient)|この `CMDIFrameWnd`の Windows MDICLIENT ウィンドウを作成します。 `CWnd`の `OnCreate` メンバー関数によって呼び出されます。|
|[CMDIFrameWnd:: CreateNewChild](#createnewchild)|新しい子ウィンドウを作成します。|
|[CMDIFrameWnd:: GetWindowMenuPopup](#getwindowmenupopup)|ウィンドウのポップアップメニューを返します。|
|[CMDIFrameWnd:: MDIActivate](#mdiactivate)|別の MDI 子ウィンドウをアクティブにします。|
|[CMDIFrameWnd:: MDICascade](#mdicascade)|すべての子ウィンドウをカスケード形式で配置します。|
|[CMDIFrameWnd:: MDIGetActive](#mdigetactive)|現在アクティブな MDI 子ウィンドウ、および子が最大化されているかどうかを示すフラグを取得します。|
|[CMDIFrameWnd:: MDIIconArrange](#mdiiconarrange)|最小化されたすべてのドキュメントの子ウィンドウを整列します。|
|[CMDIFrameWnd:: MDIMaximize](#mdimaximize)|MDI 子ウィンドウを最大化します。|
|[CMDIFrameWnd:: MDINext](#mdinext)|現在アクティブな子ウィンドウのすぐ下に子ウィンドウをアクティブにし、現在アクティブな子ウィンドウを他のすべての子ウィンドウの背後に配置します。|
|[CMDIFrameWnd:: MDIPrev](#mdiprev)|前の子ウィンドウをアクティブにし、現在アクティブな子ウィンドウをそのすぐ下に配置します。|
|[CMDIFrameWnd:: MDIRestore](#mdirestore)|MDI 子ウィンドウを最大化または最小化されたサイズから復元します。|
|[CMDIFrameWnd:: MDISetMenu](#mdisetmenu)|MDI フレームウィンドウ、ウィンドウポップアップメニュー、またはその両方のメニューを置き換えます。|
|[CMDIFrameWnd:: MDITile](#mditile)|すべての子ウィンドウを並べて表示された形式で配置します。|

## <a name="remarks"></a>解説

アプリケーションに便利な MDI フレームウィンドウを作成するには、`CMDIFrameWnd`からクラスを派生させます。 アプリケーションに固有のデータを格納するために、派生クラスにメンバー変数を追加します。 ウィンドウにメッセージが送られたときに行われる処理を指定するには、派生クラスにメッセージ処理メンバー関数とメッセージ マップを実装します。

`CFrameWnd`の[Create](../../mfc/reference/cframewnd-class.md#create)または[LoadFrame](../../mfc/reference/cframewnd-class.md#loadframe)メンバー関数を呼び出すことによって、MDI フレームウィンドウを構築できます。

`Create` または `LoadFrame`を呼び出す前に、 C++ **new**演算子を使用して、ヒープ上にフレームウィンドウオブジェクトを作成する必要があります。 `Create` を呼び出す前に、ウィンドウクラスを[AfxRegisterWndClass](application-information-and-management.md#afxregisterwndclass)グローバル関数に登録して、フレームのアイコンとクラスのスタイルを設定することもできます。

`Create` メンバー関数を使用して、フレームの作成パラメーターをイミディエイト引数として渡します。

`LoadFrame` では、`Create`よりも引数の数が少なくて済みます。代わりに、フレームのキャプション、アイコン、アクセラレータテーブル、メニューなど、リソースからほとんどの既定値を取得します。 `LoadFrame`によってアクセスするには、これらすべてのリソースが同じリソース ID (たとえば、IDR_MAINFRAME) を持つ必要があります。

`MDIFrameWnd` は `CFrameWnd`から派生しますが、`CMDIFrameWnd` から派生したフレームウィンドウクラスは `DECLARE_DYNCREATE`で宣言する必要はありません。

`CMDIFrameWnd` クラスは、`CFrameWnd`から既定の実装の多くを継承します。 これらの機能の詳細な一覧については、 [CFrameWnd](../../mfc/reference/cframewnd-class.md)クラスの説明を参照してください。 `CMDIFrameWnd` クラスには、次の追加機能があります。

- MDI フレームウィンドウでは、MDICLIENT ウィンドウが管理され、コントロールバーと一緒に再配置されます。 MDI クライアントウィンドウは、MDI 子フレームウィンドウの直接の親です。 `CMDIFrameWnd` で指定された WS_HSCROLL および WS_VSCROLL ウィンドウスタイルは、メインフレームウィンドウではなく MDI クライアントウィンドウに適用されるので、ユーザーは MDI クライアント領域 (Windows プログラムマネージャーなど) をスクロールできます。

- MDI フレームウィンドウは、アクティブな MDI 子ウィンドウがないときにメニューバーとして使用される既定のメニューを所有します。 アクティブな MDI 子がある場合、mdi フレームウィンドウのメニューバーは MDI 子ウィンドウのメニューに自動的に置き換えられます。

- MDI フレームウィンドウは、現在の MDI 子ウィンドウと連携して動作します (存在する場合)。 たとえば、コマンドメッセージは、MDI フレームウィンドウの前に現在アクティブな MDI 子に委任されます。

- MDI フレームウィンドウには、次の標準ウィンドウメニューコマンドの既定のハンドラーがあります。

    - ID_WINDOW_TILE_VERT

    - ID_WINDOW_TILE_HORZ

    - ID_WINDOW_CASCADE

    - ID_WINDOW_ARRANGE

- また、MDI フレームウィンドウには ID_WINDOW_NEW の実装もあります。これにより、現在のドキュメントに新しいフレームとビューが作成されます。 アプリケーションでは、これらの既定のコマンド実装をオーバーライドして、MDI ウィンドウ処理をカスタマイズできます。

フレームウィンドウを破棄C++するために**delete**演算子は使用しないでください。 代わりに `CWnd::DestroyWindow` を使用してください ウィンドウが破棄されると、`PostNcDestroy` C++の `CFrameWnd` 実装によってオブジェクトが削除されます。 ユーザーがフレームウィンドウを閉じると、既定の `OnClose` ハンドラーが `DestroyWindow`を呼び出します。

`CMDIFrameWnd`の詳細については、「[フレームウィンドウ](../../mfc/frame-windows.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[から派生しているのではない](../../mfc/reference/cwnd-class.md)

[CFrameWnd](../../mfc/reference/cframewnd-class.md)

`CMDIFrameWnd`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxwin.h

##  <a name="cmdiframewnd"></a>CMDIFrameWnd:: CMDIFrameWnd

`CMDIFrameWnd` オブジェクトを構築します。

```
CMDIFrameWnd();
```

### <a name="remarks"></a>解説

`Create` または `LoadFrame` のメンバー関数を呼び出して、表示される MDI フレームウィンドウを作成します。

### <a name="example"></a>例

[!code-cpp[NVC_MFCWindowing#13](../../mfc/reference/codesnippet/cpp/cmdiframewnd-class_1.cpp)]

##  <a name="createclient"></a>CMDIFrameWnd:: CreateClient

`CMDIChildWnd` オブジェクトを管理する MDI クライアントウィンドウを作成します。

```
virtual BOOL CreateClient(
    LPCREATESTRUCT lpCreateStruct,
    CMenu* pWindowMenu);
```

### <a name="parameters"></a>パラメーター

*lpCreateStruct*<br/>
[CREATESTRUCT](/windows/win32/api/winuser/ns-winuser-createstructw)構造体への long ポインター。

*pWindowMenu*<br/>
ウィンドウのポップアップメニューへのポインター。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>解説

`OnCreate` メンバー関数を直接オーバーライドする場合は、このメンバー関数を呼び出す必要があります。

### <a name="example"></a>例

[!code-cpp[NVC_MFCWindowing#14](../../mfc/reference/codesnippet/cpp/cmdiframewnd-class_2.cpp)]

##  <a name="createnewchild"></a>CMDIFrameWnd:: CreateNewChild

新しい子ウィンドウを作成します。

```
CMDIChildWnd* CreateNewChild(
    CRuntimeClass* pClass,
    UINT nResource,
    HMENU hMenu = NULL,
    HACCEL hAccel = NULL);
```

### <a name="parameters"></a>パラメーター

*pClass*<br/>
作成される子ウィンドウのランタイムクラス。

*nResource*<br/>
子ウィンドウに関連付けられている共有リソースの ID。

*hMenu*<br/>
子ウィンドウのメニュー。

*hAccel*<br/>
子ウィンドウのアクセラレータ。

### <a name="remarks"></a>解説

MDI フレームウィンドウの子ウィンドウを作成するには、この関数を使用します。

### <a name="example"></a>例

[!code-cpp[NVC_MFCWindowing#15](../../mfc/reference/codesnippet/cpp/cmdiframewnd-class_3.cpp)]

##  <a name="getwindowmenupopup"></a>CMDIFrameWnd:: GetWindowMenuPopup

このメンバー関数を呼び出して、"Window" という名前の現在のポップアップメニュー (MDI ウィンドウ管理のメニュー項目を含むポップアップメニュー) へのハンドルを取得します。

```
virtual HMENU GetWindowMenuPopup(HMENU hMenuBar);
```

### <a name="parameters"></a>パラメーター

*hMenuBar*<br/>
現在のメニューバー。

### <a name="return-value"></a>戻り値

ウィンドウのポップアップメニュー (存在する場合)。それ以外の場合は NULL。

### <a name="remarks"></a>解説

既定の実装では、ID_WINDOW_NEW や ID_WINDOW_TILE_HORZ などの標準ウィンドウメニューコマンドを含むポップアップメニューが検索されます。

標準のメニューコマンド Id を使用しないウィンドウメニューがある場合は、このメンバー関数をオーバーライドします。

### <a name="example"></a>例

[!code-cpp[NVC_MFCWindowing#16](../../mfc/reference/codesnippet/cpp/cmdiframewnd-class_4.cpp)]

##  <a name="mdiactivate"></a>CMDIFrameWnd:: MDIActivate

別の MDI 子ウィンドウをアクティブにします。

```
void MDIActivate(CWnd* pWndActivate);
```

### <a name="parameters"></a>パラメーター

*pWndActivate*<br/>
アクティブにする MDI 子ウィンドウをポイントします。

### <a name="remarks"></a>解説

このメンバー関数は、アクティブ化されている子ウィンドウと非アクティブ化されている子ウィンドウの両方に[WM_MDIACTIVATE](../../mfc/reference/cwnd-class.md#onmdiactivate)メッセージを送信します。

これは、ユーザーがマウスまたはキーボードを使用して MDI 子ウィンドウにフォーカスを変更した場合に送信されるメッセージと同じです。

> [!NOTE]
>  Mdi 子ウィンドウは、MDI フレームウィンドウとは別にアクティブ化されます。 フレームがアクティブになると、最後にアクティブ化された子ウィンドウに[WM_NCACTIVATE](../../mfc/reference/cwnd-class.md#onncactivate)メッセージが送信され、アクティブなウィンドウフレームとキャプションバーが描画されますが、別の WM_MDIACTIVATE メッセージは受信されません。

### <a name="example"></a>例

[CMDIFrameWnd:: GetWindowMenuPopup](#getwindowmenupopup)の例を参照してください。

##  <a name="mdicascade"></a>CMDIFrameWnd:: MDICascade

すべての MDI 子ウィンドウをカスケード形式で配置します。

```
void MDICascade();
void MDICascade(int nType);
```

### <a name="parameters"></a>パラメーター

*nType*<br/>
Cascade フラグを指定します。 次のフラグのみを指定できます。 MDITILE_SKIPDISABLED、無効になっている MDI 子ウィンドウをカスケードできないようにします。

### <a name="remarks"></a>解説

`MDICascade`の最初のバージョンでは、パラメーターを使用せずに、無効な子ウィンドウを含むすべての MDI 子ウィンドウをカスケードします。 2番目のバージョンでは、 *nType*パラメーターに MDITILE_SKIPDISABLED を指定した場合、無効になっている MDI 子ウィンドウはカスケードされません。

### <a name="example"></a>例

[!code-cpp[NVC_MFCWindowing#17](../../mfc/reference/codesnippet/cpp/cmdiframewnd-class_5.cpp)]

##  <a name="mdigetactive"></a>CMDIFrameWnd:: MDIGetActive

現在アクティブな MDI 子ウィンドウ、および子ウィンドウが最大化されているかどうかを示すフラグを取得します。

```
CMDIChildWnd* MDIGetActive(BOOL* pbMaximized = NULL) const;
```

### <a name="parameters"></a>パラメーター

*pbMaximized*<br/>
BOOL 戻り値へのポインター。 ウィンドウが最大化されている場合は、戻るときに TRUE に設定します。それ以外の場合は FALSE。

### <a name="return-value"></a>戻り値

アクティブな MDI 子ウィンドウへのポインター。

### <a name="example"></a>例

[CMDIChildWnd:: MDIMaximize](../../mfc/reference/cmdichildwnd-class.md#mdimaximize)の例を参照してください。

##  <a name="mdiiconarrange"></a>CMDIFrameWnd:: MDIIconArrange

最小化されたすべてのドキュメントの子ウィンドウを整列します。

```
void MDIIconArrange();
```

### <a name="remarks"></a>解説

最小化されていない子ウィンドウには影響しません。

### <a name="example"></a>例

[CMDIFrameWnd:: MDICascade](#mdicascade)の例を参照してください。

##  <a name="mdimaximize"></a>CMDIFrameWnd:: MDIMaximize

指定した MDI 子ウィンドウを最大化します。

```
void MDIMaximize(CWnd* pWnd);
```

### <a name="parameters"></a>パラメーター

*pWnd*<br/>
最大化するウィンドウをポイントします。

### <a name="remarks"></a>解説

子ウィンドウが最大化されると、クライアント領域がクライアントウィンドウに収まるように、ウィンドウのサイズが変更されます。 子ウィンドウのコントロールメニューがフレームのメニューバーに配置されるため、ユーザーは子ウィンドウを復元したり閉じたりできます。 また、子ウィンドウのタイトルがフレームウィンドウのタイトルに追加されます。

現在アクティブな MDI 子ウィンドウが最大化されているときに、別の MDI 子ウィンドウがアクティブになっている場合、現在アクティブな子ウィンドウが復元され、新しくアクティブになった子ウィンドウが最大化されます。

### <a name="example"></a>例

[CMDIChildWnd:: MDIMaximize](../../mfc/reference/cmdichildwnd-class.md#mdimaximize)の例を参照してください。

##  <a name="mdinext"></a>CMDIFrameWnd:: MDINext

現在アクティブな子ウィンドウのすぐ下に子ウィンドウをアクティブにし、現在アクティブな子ウィンドウを他のすべての子ウィンドウの背後に配置します。

```
void MDINext();
```

### <a name="remarks"></a>解説

現在アクティブな MDI 子ウィンドウが最大化されている場合、メンバー関数は、現在アクティブな子を復元し、新しくアクティブになった子を最大化します。

### <a name="example"></a>例

[!code-cpp[NVC_MFCWindowing#18](../../mfc/reference/codesnippet/cpp/cmdiframewnd-class_6.cpp)]

##  <a name="mdiprev"></a>CMDIFrameWnd:: MDIPrev

前の子ウィンドウをアクティブにし、現在アクティブな子ウィンドウをそのすぐ下に配置します。

```
void MDIPrev();
```

### <a name="remarks"></a>解説

現在アクティブな MDI 子ウィンドウが最大化されている場合、メンバー関数は、現在アクティブな子を復元し、新しくアクティブになった子を最大化します。

##  <a name="mdirestore"></a>CMDIFrameWnd:: MDIRestore

MDI 子ウィンドウを最大化または最小化されたサイズから復元します。

```
void MDIRestore(CWnd* pWnd);
```

### <a name="parameters"></a>パラメーター

*pWnd*<br/>
復元するウィンドウをポイントします。

### <a name="example"></a>例

[CMDIChildWnd:: MDIRestore](../../mfc/reference/cmdichildwnd-class.md#mdirestore)の例を参照してください。

##  <a name="mdisetmenu"></a>CMDIFrameWnd:: MDISetMenu

MDI フレームウィンドウ、ウィンドウポップアップメニュー、またはその両方のメニューを置き換えます。

```
CMenu* MDISetMenu(
    CMenu* pFrameMenu,
    CMenu* pWindowMenu);
```

### <a name="parameters"></a>パラメーター

*pFrameMenu*<br/>
新しいフレームウィンドウメニューのメニューを指定します。 NULL の場合、メニューは変更されません。

*pWindowMenu*<br/>
新しいウィンドウのポップアップメニューのメニューを指定します。 NULL の場合、メニューは変更されません。

### <a name="return-value"></a>戻り値

このメッセージに置き換えられたフレームウィンドウメニューへのポインター。 ポインターは一時的である可能性があり、後で使用するために格納しないでください。

### <a name="remarks"></a>解説

`MDISetMenu`を呼び出した後、アプリケーションは `CWnd` の[DrawMenuBar](../../mfc/reference/cwnd-class.md#drawmenubar)メンバー関数を呼び出してメニューバーを更新する必要があります。

この呼び出しによってウィンドウのポップアップメニューが置き換えられた場合、MDI 子ウィンドウのメニュー項目は、前の [ウィンドウ] メニューから削除され、新しいウィンドウのポップアップメニューに追加されます。

MDI 子ウィンドウが最大化されていて、この呼び出しによって MDI フレームウィンドウメニューが置き換えられた場合、コントロールメニューと復元コントロールは、前のフレームウィンドウメニューから削除され、新しいメニューに追加されます。

フレームワークを使用して MDI 子ウィンドウを管理する場合は、このメンバー関数を呼び出さないでください。

### <a name="example"></a>例

[!code-cpp[NVC_MFCWindowing#19](../../mfc/reference/codesnippet/cpp/cmdiframewnd-class_7.cpp)]

[!code-cpp[NVC_MFCWindowing#20](../../mfc/reference/codesnippet/cpp/cmdiframewnd-class_8.cpp)]

##  <a name="mditile"></a>CMDIFrameWnd:: MDITile

すべての子ウィンドウを並べて表示された形式で配置します。

```
void MDITile();
void MDITile(int nType);
```

### <a name="parameters"></a>パラメーター

*nType*<br/>
タイルフラグを指定します。 このパラメーターには、次のフラグのいずれかを指定できます。

- 1つのウィンドウが別のウィンドウの上に表示されるように、MDI 子ウィンドウを MDITILE_HORIZONTAL タイルします。

- MDITILE_SKIPDISABLED 無効になっている MDI 子ウィンドウがタイル化されないようにします。

- MDITILE_VERTICAL は、MDI 子ウィンドウを並べて表示し、1つのウィンドウを別のウィンドウの横に表示します。

### <a name="remarks"></a>解説

パラメーターを指定せずに `MDITile`の最初のバージョンでは、windows が Windows バージョン3.1 以降で垂直方向に並べて配置されます。 2番目のバージョンでは、 *nType*パラメーターの値に応じて、ウィンドウが垂直方向または水平方向に並べて配置されます。

### <a name="example"></a>例

[CMDIFrameWnd:: MDICascade](#mdicascade)の例を参照してください。

## <a name="see-also"></a>参照

[MFC のサンプル MDI](../../overview/visual-cpp-samples.md)<br/>
[MFC のサンプル MDIDOCVW](../../overview/visual-cpp-samples.md)<br/>
[MFC のサンプル SNAPVW](../../overview/visual-cpp-samples.md)<br/>
[CFrameWnd クラス](../../mfc/reference/cframewnd-class.md)<br/>
[階層図](../../mfc/hierarchy-chart.md)<br/>
[CWnd クラス](../../mfc/reference/cwnd-class.md)<br/>
[CMDIChildWnd クラス](../../mfc/reference/cmdichildwnd-class.md)

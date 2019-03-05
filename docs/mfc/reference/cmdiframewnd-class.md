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
ms.openlocfilehash: d3fc71c3e294b26aea405b8800199cf88120fa08
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/04/2019
ms.locfileid: "57282449"
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
|[CMDIFrameWnd::CMDIFrameWnd](#cmdiframewnd)|`CMDIFrameWnd` を構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CMDIFrameWnd::CreateClient](#createclient)|この Windows の [クイック ウォッチ] ウィンドウを作成します。`CMDIFrameWnd`します。 メソッドを呼び出して、`OnCreate`のメンバー関数`CWnd`します。|
|[CMDIFrameWnd::CreateNewChild](#createnewchild)|新しい子ウィンドウを作成します。|
|[CMDIFrameWnd::GetWindowMenuPopup](#getwindowmenupopup)|ウィンドウのポップアップ メニューを返します。|
|[CMDIFrameWnd::MDIActivate](#mdiactivate)|別の MDI 子ウィンドウをアクティブにします。|
|[CMDIFrameWnd::MDICascade](#mdicascade)|すべての子ウィンドウを重ねて表示を整列します。|
|[CMDIFrameWnd::MDIGetActive](#mdigetactive)|子が最大化されているかどうかを示すフラグと共に、現在アクティブな MDI 子ウィンドウを取得します。|
|[CMDIFrameWnd::MDIIconArrange](#mdiiconarrange)|最小化されたドキュメントのすべての子ウィンドウを整列します。|
|[CMDIFrameWnd::MDIMaximize](#mdimaximize)|MDI 子ウィンドウを最大化します。|
|[CMDIFrameWnd::MDINext](#mdinext)|現在アクティブな子ウィンドウの背後にすぐに子ウィンドウをアクティブにし、その他のすべての子ウィンドウの背後にある現在アクティブな子ウィンドウを配置します。|
|[CMDIFrameWnd::MDIPrev](#mdiprev)|前の子ウィンドウをアクティブにし、すぐ後ろに、現在アクティブな子ウィンドウを配置します。|
|[CMDIFrameWnd::MDIRestore](#mdirestore)|MDI 子ウィンドウを最大化または最小化されたサイズから復元します。|
|[CMDIFrameWnd::MDISetMenu](#mdisetmenu)|MDI フレーム ウィンドウのメニューを開き、ウィンドウのポップアップ メニューで、またはその両方を置き換えます。|
|[CMDIFrameWnd::MDITile](#mditile)|すべての子ウィンドウを並べて整列します。|

## <a name="remarks"></a>Remarks

アプリケーション用の便利な MDI フレーム ウィンドウを作成するには、派生クラスを`CMDIFrameWnd`します。 メンバー変数をアプリケーションに固有のデータを格納する派生クラスに追加します。 ウィンドウにメッセージが送られたときに行われる処理を指定するには、派生クラスにメッセージ処理メンバー関数とメッセージ マップを実装します。

MDI フレーム ウィンドウを作成するには呼び出すことによって、[作成](../../mfc/reference/cframewnd-class.md#create)または[LoadFrame](../../mfc/reference/cframewnd-class.md#loadframe)のメンバー関数`CFrameWnd`します。

呼び出す前に`Create`または`LoadFrame`、C++ を使用して、ヒープ上のフレーム ウィンドウ オブジェクトを構築する必要があります**新しい**演算子。 呼び出しの前に`Create`ウィンドウ クラスを登録することも、 [AfxRegisterWndClass](application-information-and-management.md#afxregisterwndclass)グローバル関数、フレームのアイコンとクラスのスタイルを設定します。

使用して、`Create`メンバー関数は、イミディ エイト引数フレームの作成パラメーターを渡す。

`LoadFrame` も少ない引数が必要です`Create`、代わりに、フレームのキャプション、アイコン、アクセラレータ テーブル、およびメニューなどのリソースからほとんどの既定値を取得します。 アクセスを`LoadFrame`、これらすべてのリソースは resource ID (たとえば、IDR_MAINFRAME) が同じである必要があります。

ただし`MDIFrameWnd`から派生`CFrameWnd`、フレーム ウィンドウ クラスから派生した`CMDIFrameWnd`で宣言されていない必要があります`DECLARE_DYNCREATE`します。

`CMDIFrameWnd`クラスを継承から既定の実装の多く`CFrameWnd`します。 これらの機能の詳細な一覧を参照してください、 [CFrameWnd](../../mfc/reference/cframewnd-class.md)クラスの説明。 `CMDIFrameWnd`クラスには、次の追加機能。

- MDI フレーム ウィンドウは、クイック ウォッチ ウィンドウで、コントロール バーと共に再配置を管理します。 MDI クライアント ウィンドウは、MDI 子フレーム ウィンドウの直接の親です。 指定された WS_HSCROLL と WS_VSCROLL ウィンドウ スタイル、 `CMDIFrameWnd` MDI クライアント ウィンドウに適用、ユーザーは、MDI クライアント領域 (のように、Windows プログラム マネージャー、たとえば) をスクロールできるように、メイン フレーム ウィンドウではなく。

- MDI フレーム ウィンドウには、アクティブな MDI 子ウィンドウがない場合、メニュー バーとして使用される既定のメニューが所有しています。 アクティブな MDI 子がある場合に、MDI フレーム ウィンドウのメニュー バーは MDI 子ウィンドウのメニューに自動的に置換されます。

- MDI フレーム ウィンドウは、1 つを使用する必要がある場合、現在の MDI 子ウィンドウと組み合わせて動作します。 たとえば、コマンド メッセージは、MDI フレーム ウィンドウの前に、現在アクティブな MDI 子に委任されます。

- MDI フレーム ウィンドウには、次の標準的なウィンドウ メニュー コマンドの既定のハンドラーがあります。

    - ID_WINDOW_TILE_VERT

    - ID_WINDOW_TILE_HORZ

    - ID_WINDOW_CASCADE

    - ID_WINDOW_ARRANGE

- MDI フレーム ウィンドウには、新しいフレームと現在のドキュメントのビューを作成、ID_WINDOW_NEW の実装もあります。 アプリケーションでは、MDI ウィンドウの処理をカスタマイズするこれら既定のコマンドの実装をオーバーライドできます。

C++ を使用しないでください**削除**フレーム ウィンドウを破棄する演算子。 代わりに、`CWnd::DestroyWindow` を使用してください。 `CFrameWnd`の実装`PostNcDestroy`ウィンドウが破棄されるときに、C++ のオブジェクトが削除されます。 ユーザーが既定値であるフレーム ウィンドウを閉じるときに`OnClose`ハンドラーが呼び出す`DestroyWindow`します。

詳細については`CMDIFrameWnd`を参照してください[フレーム Windows](../../mfc/frame-windows.md)します。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CFrameWnd](../../mfc/reference/cframewnd-class.md)

`CMDIFrameWnd`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxwin.h

##  <a name="cmdiframewnd"></a>  CMDIFrameWnd::CMDIFrameWnd

`CMDIFrameWnd` オブジェクトを構築します。

```
CMDIFrameWnd();
```

### <a name="remarks"></a>Remarks

呼び出す、`Create`または`LoadFrame`表示 MDI フレーム ウィンドウを作成します。

### <a name="example"></a>例

[!code-cpp[NVC_MFCWindowing#13](../../mfc/reference/codesnippet/cpp/cmdiframewnd-class_1.cpp)]

##  <a name="createclient"></a>  CMDIFrameWnd::CreateClient

管理する MDI クライアント ウィンドウを作成、`CMDIChildWnd`オブジェクト。

```
virtual BOOL CreateClient(
    LPCREATESTRUCT lpCreateStruct,
    CMenu* pWindowMenu);
```

### <a name="parameters"></a>パラメーター

*lpCreateStruct*<br/>
Long ポインター、 [CREATESTRUCT](/windows/desktop/api/winuser/ns-winuser-tagcreatestructa)構造体。

*pWindowMenu*<br/>
ウィンドウのポップアップ メニューへのポインター。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>Remarks

オーバーライドする場合、このメンバー関数を呼び出す必要があります、`OnCreate`直接のメンバー関数。

### <a name="example"></a>例

[!code-cpp[NVC_MFCWindowing#14](../../mfc/reference/codesnippet/cpp/cmdiframewnd-class_2.cpp)]

##  <a name="createnewchild"></a>  CMDIFrameWnd::CreateNewChild

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
作成する子ウィンドウのランタイム クラスです。

*リソース*<br/>
子ウィンドウに関連付けられている共有リソースの ID。

*hMenu*<br/>
子ウィンドウのメニュー。

*hAccel*<br/>
子ウィンドウのアクセラレータです。

### <a name="remarks"></a>Remarks

子 MDI フレーム ウィンドウのウィンドウを作成するのにには、この関数を使用します。

### <a name="example"></a>例

[!code-cpp[NVC_MFCWindowing#15](../../mfc/reference/codesnippet/cpp/cmdiframewnd-class_3.cpp)]

##  <a name="getwindowmenupopup"></a>  CMDIFrameWnd::GetWindowMenuPopup

という名前の「ウィンドウ」(MDI ウィンドウの管理のためのメニュー項目を含むポップアップ メニュー)、現在のポップアップ メニューへのハンドルを取得するには、このメンバー関数を呼び出します。

```
virtual HMENU GetWindowMenuPopup(HMENU hMenuBar);
```

### <a name="parameters"></a>パラメーター

*hMenuBar*<br/>
現在のメニュー バー。

### <a name="return-value"></a>戻り値

場合 1 つのウィンドウのポップアップ メニューが存在します。それ以外の場合は NULL です。

### <a name="remarks"></a>Remarks

既定の実装は、ID_WINDOW_NEW ID_WINDOW_TILE_HORZ など標準のウィンドウ メニューのコマンドを含むポップアップ メニューを検索します。

標準のメニュー コマンド Id を使用しないウィンドウ メニューがある場合は、このメンバー関数をオーバーライドします。

### <a name="example"></a>例

[!code-cpp[NVC_MFCWindowing#16](../../mfc/reference/codesnippet/cpp/cmdiframewnd-class_4.cpp)]

##  <a name="mdiactivate"></a>  CMDIFrameWnd::MDIActivate

別の MDI 子ウィンドウをアクティブにします。

```
void MDIActivate(CWnd* pWndActivate);
```

### <a name="parameters"></a>パラメーター

*pWndActivate*<br/>
アクティブ化する MDI 子ウィンドウへのポインター。

### <a name="remarks"></a>Remarks

このメンバー関数は送信、 [WM_MDIACTIVATE](../../mfc/reference/cwnd-class.md#onmdiactivate)子ウィンドウをアクティブ化して、子ウィンドウを非アクティブ化の両方にメッセージ。

これは、ユーザーは、マウスまたはキーボードを使用して MDI 子ウィンドウにフォーカスを変更した場合に送信されるのと同じメッセージです。

> [!NOTE]
>  MDI フレーム ウィンドウとは無関係に MDI 子ウィンドウがアクティブ化されます。 最後にアクティブ化する子ウィンドウが送信されるフレームがアクティブになったとき、[ため](../../mfc/reference/cwnd-class.md#onncactivate)がアクティブなウィンドウ フレームとキャプション バーを描画するためにメッセージが別の WM_MDIACTIVATE メッセージを受信しません。

### <a name="example"></a>例

例をご覧ください[CMDIFrameWnd::GetWindowMenuPopup](#getwindowmenupopup)します。

##  <a name="mdicascade"></a>  CMDIFrameWnd::MDICascade

Cascade 形式ですべての MDI 子ウィンドウを整列します。

```
void MDICascade();
void MDICascade(int nType);
```

### <a name="parameters"></a>パラメーター

*nType*<br/>
Cascade フラグを指定します。 次のフラグだけを指定できます。もう、MDI 子ウィンドウを無効になっているが重ねて表示されていることを防ぎます。

### <a name="remarks"></a>Remarks

最初のバージョンの`MDICascade`、パラメーターなしで、無効になっているものを含むすべての MDI 子ウィンドウを重ねて表示します。 もう cascade が無効になっている MDI 子ウィンドウされませんが 2 番目のバージョンによってオプションでは、 *%n タイプ*パラメーター。

### <a name="example"></a>例

[!code-cpp[NVC_MFCWindowing#17](../../mfc/reference/codesnippet/cpp/cmdiframewnd-class_5.cpp)]

##  <a name="mdigetactive"></a>  CMDIFrameWnd::MDIGetActive

現在アクティブな MDI 子ウィンドウ、と共に子ウィンドウを最大化するかどうかを示すフラグを取得します。

```
CMDIChildWnd* MDIGetActive(BOOL* pbMaximized = NULL) const;
```

### <a name="parameters"></a>パラメーター

*pbMaximized*<br/>
ブール型の戻り値へのポインター。 ウィンドウを最大化します。 場合、返された場合に TRUE に設定します。それ以外の場合は FALSE です。

### <a name="return-value"></a>戻り値

アクティブな MDI 子ウィンドウへのポインター。

### <a name="example"></a>例

例をご覧ください[CMDIChildWnd::MDIMaximize](../../mfc/reference/cmdichildwnd-class.md#mdimaximize)します。

##  <a name="mdiiconarrange"></a>  CMDIFrameWnd::MDIIconArrange

最小化されたドキュメントのすべての子ウィンドウを整列します。

```
void MDIIconArrange();
```

### <a name="remarks"></a>Remarks

最小化されていない子ウィンドウには影響しません。

### <a name="example"></a>例

例をご覧ください[CMDIFrameWnd::MDICascade](#mdicascade)します。

##  <a name="mdimaximize"></a>  CMDIFrameWnd::MDIMaximize

指定の MDI 子ウィンドウを最大化します。

```
void MDIMaximize(CWnd* pWnd);
```

### <a name="parameters"></a>パラメーター

*我が物*<br/>
最大化するウィンドウへのポインター。

### <a name="remarks"></a>Remarks

子ウィンドウを最大化したときに Windows では、クライアント ウィンドウのクライアント領域にサイズ変更されます。 Windows は、ユーザーが復元または子ウィンドウを閉じるようにフレームのメニュー バーで、子ウィンドウのコントロール メニューを配置します。 また、子ウィンドウのタイトルをフレーム ウィンドウのタイトルに追加します。

現在アクティブな MDI 子ウィンドウが最大表示されたときに別の MDI 子ウィンドウがアクティブの場合、Windows は現在アクティブな子を復元し、新しくアクティブになった子ウィンドウを最大化します。

### <a name="example"></a>例

例をご覧ください[CMDIChildWnd::MDIMaximize](../../mfc/reference/cmdichildwnd-class.md#mdimaximize)します。

##  <a name="mdinext"></a>  CMDIFrameWnd::MDINext

現在アクティブな子ウィンドウの背後にすぐに子ウィンドウをアクティブにし、その他のすべての子ウィンドウの背後にある現在アクティブな子ウィンドウを配置します。

```
void MDINext();
```

### <a name="remarks"></a>Remarks

現在アクティブな MDI 子ウィンドウを最大化した場合、メンバー関数は現在アクティブな子を復元し、新しくアクティブになった子を最大化します。

### <a name="example"></a>例

[!code-cpp[NVC_MFCWindowing#18](../../mfc/reference/codesnippet/cpp/cmdiframewnd-class_6.cpp)]

##  <a name="mdiprev"></a>  CMDIFrameWnd::MDIPrev

前の子ウィンドウをアクティブにし、すぐ後ろに、現在アクティブな子ウィンドウを配置します。

```
void MDIPrev();
```

### <a name="remarks"></a>Remarks

現在アクティブな MDI 子ウィンドウを最大化した場合、メンバー関数は現在アクティブな子を復元し、新しくアクティブになった子を最大化します。

##  <a name="mdirestore"></a>  CMDIFrameWnd::MDIRestore

MDI 子ウィンドウを最大化または最小化されたサイズから復元します。

```
void MDIRestore(CWnd* pWnd);
```

### <a name="parameters"></a>パラメーター

*我が物*<br/>
元に戻すウィンドウへのポインター。

### <a name="example"></a>例

例をご覧ください[CMDIChildWnd::MDIRestore](../../mfc/reference/cmdichildwnd-class.md#mdirestore)します。

##  <a name="mdisetmenu"></a>  CMDIFrameWnd::MDISetMenu

MDI フレーム ウィンドウのメニューを開き、ウィンドウのポップアップ メニューで、またはその両方を置き換えます。

```
CMenu* MDISetMenu(
    CMenu* pFrameMenu,
    CMenu* pWindowMenu);
```

### <a name="parameters"></a>パラメーター

*pFrameMenu*<br/>
新しいフレーム ウィンドウ メニューのメニューを指定します。 NULL の場合、メニューは変更されません。

*pWindowMenu*<br/>
新しいウィンドウ ポップアップ メニューのメニューを指定します。 NULL の場合、メニューは変更されません。

### <a name="return-value"></a>戻り値

このメッセージに置き換え、フレーム ウィンドウのメニューへのポインター。 ポインターは一時的である可能性があり、後で使用するために格納しないでください。

### <a name="remarks"></a>Remarks

呼び出した後`MDISetMenu`、アプリケーションを呼び出す必要があります、 [DrawMenuBar](../../mfc/reference/cwnd-class.md#drawmenubar)のメンバー関数`CWnd`メニュー バーを更新します。

この呼び出しに代わるウィンドウ ポップアップ メニューで場合、MDI 子ウィンドウのメニュー項目が前のウィンドウ メニューから削除し、新しいウィンドウ ポップアップ メニューに追加します。

MDI 子ウィンドウを最大化すると、この呼び出しに置き換えられます MDI フレーム ウィンドウのメニューのコントロールのメニューと復元のコントロールが前のフレーム ウィンドウ メニューから削除し、新しいメニューに追加します。

MDI 子ウィンドウを管理するために、フレームワークを使用する場合、このメンバー関数を呼び出さないでください。

### <a name="example"></a>例

[!code-cpp[NVC_MFCWindowing#19](../../mfc/reference/codesnippet/cpp/cmdiframewnd-class_7.cpp)]

[!code-cpp[NVC_MFCWindowing#20](../../mfc/reference/codesnippet/cpp/cmdiframewnd-class_8.cpp)]

##  <a name="mditile"></a>  CMDIFrameWnd::MDITile

すべての子ウィンドウを並べて整列します。

```
void MDITile();
void MDITile(int nType);
```

### <a name="parameters"></a>パラメーター

*nType*<br/>
並べて表示フラグを指定します。 このパラメーターは、次のフラグのいずれかを指定できます。

- MDITILE_HORIZONTAL タイルの MDI 子ウィンドウを 1 つのウィンドウが別の上に表示します。

- もうできないようにするには、並べて表示する対象の MDI 子ウィンドウを無効になっています。

- MDITILE_VERTICAL タイルの MDI 子ウィンドウを 1 つのウィンドウが別の横に表示されます。

### <a name="remarks"></a>Remarks

最初のバージョンの`MDITile`パラメーターを指定せずには、Windows 3.1 以降のバージョンで垂直方向にウィンドウを並べて表示します。 2 番目のバージョン ウィンドウを並べて表示上下左右の方向の値に応じて、 *%n タイプ*パラメーター。

### <a name="example"></a>例

例をご覧ください[CMDIFrameWnd::MDICascade](#mdicascade)します。

## <a name="see-also"></a>関連項目

[MFC サンプル MDI](../../visual-cpp-samples.md)<br/>
[MFC のサンプルは](../../visual-cpp-samples.md)<br/>
[MFC サンプル SNAPVW](../../visual-cpp-samples.md)<br/>
[CFrameWnd クラス](../../mfc/reference/cframewnd-class.md)<br/>
[階層図](../../mfc/hierarchy-chart.md)<br/>
[CWnd クラス](../../mfc/reference/cwnd-class.md)<br/>
[CMDIChildWnd クラス](../../mfc/reference/cmdichildwnd-class.md)

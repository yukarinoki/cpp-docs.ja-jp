---
title: CMDIFrameWnd クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
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
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7bb9f87ed5ae3027e7743a36c2484017d6381f95
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33374040"
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
|[CMDIFrameWnd::CreateClient](#createclient)|Windows の作成**MDICLIENT**このウィンドウ`CMDIFrameWnd`します。 によって呼び出される、`OnCreate`のメンバー関数`CWnd`です。|  
|[CMDIFrameWnd::CreateNewChild](#createnewchild)|新しい子ウィンドウを作成します。|  
|[CMDIFrameWnd::GetWindowMenuPopup](#getwindowmenupopup)|ウィンドウのポップアップ メニューを返します。|  
|[CMDIFrameWnd::MDIActivate](#mdiactivate)|さまざまな MDI 子ウィンドウをアクティブにします。|  
|[CMDIFrameWnd::MDICascade](#mdicascade)|すべての子ウィンドウを重ねて表示を整列します。|  
|[CMDIFrameWnd::MDIGetActive](#mdigetactive)|子が最大化されているかどうかを示すフラグと共に、現在アクティブな MDI 子ウィンドウを取得します。|  
|[ある最小化されました。](#mdiiconarrange)|最小化されたドキュメントのすべての子ウィンドウを整列します。|  
|[CMDIFrameWnd::MDIMaximize](#mdimaximize)|MDI 子ウィンドウを最大化します。|  
|[CMDIFrameWnd::MDINext](#mdinext)|現在アクティブな子ウィンドウの背後にすぐに子ウィンドウをアクティブにし、その他のすべての子ウィンドウの背後にある、現在アクティブな子ウィンドウを配置します。|  
|[CMDIFrameWnd::MDIPrev](#mdiprev)|前の子ウィンドウをアクティブにし、すぐ後ろに、現在アクティブな子ウィンドウを置きます。|  
|[CMDIFrameWnd::MDIRestore](#mdirestore)|MDI 子ウィンドウを最大化または最小化されているサイズから復元します。|  
|[CMDIFrameWnd::MDISetMenu](#mdisetmenu)|MDI フレーム ウィンドウのメニューのウィンドウのポップアップ メニューのまたはその両方を置換します。|  
|[CMDIFrameWnd::MDITile](#mditile)|タイル化された形式ですべての子ウィンドウを整列します。|  
  
## <a name="remarks"></a>コメント  
 アプリケーションに役立ちます MDI フレーム ウィンドウを作成するには、派生クラスを`CMDIFrameWnd`です。 メンバー変数をアプリケーションに固有のデータを格納する派生クラスに追加します。 ウィンドウにメッセージが送られたときに行われる処理を指定するには、派生クラスにメッセージ処理メンバー関数とメッセージ マップを実装します。  
  
 MDI フレーム ウィンドウを作成するには呼び出すことによって、[作成](../../mfc/reference/cframewnd-class.md#create)または[LoadFrame](../../mfc/reference/cframewnd-class.md#loadframe)のメンバー関数`CFrameWnd`です。  
  
 呼び出す前に**作成**または`LoadFrame`、C++ を使用して、ヒープ上のフレーム ウィンドウ オブジェクトを構築する必要があります**新しい**演算子。 呼び出しの前に**作成**でウィンドウ クラスを登録することも、 [AfxRegisterWndClass](application-information-and-management.md#afxregisterwndclass)グローバル関数、フレームのアイコンとクラスのスタイルを設定します。  
  
 使用して、**作成**引数を渡す、フレームの作成パラメーターとして直接のメンバー関数。  
  
 `LoadFrame` も少ない引数を必要と**作成**、代わりに、フレームのキャプション、アイコン、アクセラレータ テーブル、およびメニューなどのリソースからほとんどの既定値を取得します。 アクセスする`LoadFrame`、これらすべてのリソースが同じリソース ID を持つ必要があります (たとえば、 **IDR_MAINFRAME**)。  
  
 **MDIFrameWnd**から派生した`CFrameWnd`、フレーム ウィンドウ クラスから派生した`CMDIFrameWnd`で宣言する必要がありますいない`DECLARE_DYNCREATE`です。  
  
 `CMDIFrameWnd`クラスを継承から既定の実装の大部分`CFrameWnd`です。 これらの機能の詳細な一覧についてを参照してください、 [CFrameWnd](../../mfc/reference/cframewnd-class.md)クラスの説明。 `CMDIFrameWnd`クラスには次の追加機能。  
  
-   MDI フレーム ウィンドウの管理、 **MDICLIENT**ウィンドウ、コントロール バーと共に移動します。 MDI クライアント ウィンドウは、MDI 子フレーム ウィンドウの直接の親です。 **WS_HSCROLL**と**WS_VSCROLL**で指定されたウィンドウのスタイル、`CMDIFrameWnd`ユーザー (つまり、Windows MDI クライアント領域をスクロールできるように、メイン フレーム ウィンドウではなく、MDI クライアント ウィンドウに適用Program Manager, など)。  
  
-   MDI フレーム ウィンドウには、アクティブな MDI 子ウィンドウがない場合は、メニュー バーとして使用する既定のメニューが所有しています。 アクティブな MDI 子がある場合は、MDI フレーム ウィンドウのメニュー バーが MDI 子ウィンドウのメニューで自動的に置き換えられます。  
  
-   MDI フレーム ウィンドウは、1 つを使用する必要がある場合、現在の MDI 子ウィンドウと共に動作します。 たとえば、コマンド メッセージは、MDI フレーム ウィンドウの前に、現在アクティブな MDI 子に委任されます。  
  
-   MDI フレーム ウィンドウには、次の標準的なウィンドウ メニュー コマンドの既定のハンドラーがあります。  
  
    - **ID_WINDOW_TILE_VERT**  
  
    - **ID_WINDOW_TILE_HORZ**  
  
    - **ID_WINDOW_CASCADE**  
  
    - **ID_WINDOW_ARRANGE**  
  
-   MDI フレーム ウィンドウにも、実装の**ID_WINDOW_NEW**、これは、新しいフレームと現在のドキュメントのビューを作成します。 アプリケーションでは、MDI ウィンドウの処理をカスタマイズするこれら既定コマンドの実装をオーバーライドできます。  
  
 C++ を使用しないでください**削除**フレーム ウィンドウを破棄する演算子です。 代わりに、`CWnd::DestroyWindow` を使用してください。 `CFrameWnd`の実装`PostNcDestroy`ウィンドウが破棄されるときに、C++ オブジェクトが削除されます。 ユーザーが既定値であるフレーム ウィンドウを閉じたとき`OnClose`ハンドラーを呼び出す`DestroyWindow`です。  
  
 詳細については`CMDIFrameWnd`を参照してください[フレーム ウィンドウ](../../mfc/frame-windows.md)します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CFrameWnd](../../mfc/reference/cframewnd-class.md)  
  
 `CMDIFrameWnd`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxwin.h  
  
##  <a name="cmdiframewnd"></a>  CMDIFrameWnd::CMDIFrameWnd  
 `CMDIFrameWnd` オブジェクトを構築します。  
  
```  
CMDIFrameWnd();
```  
  
### <a name="remarks"></a>コメント  
 呼び出す、**作成**または`LoadFrame`可視 MDI フレーム ウィンドウを作成するメンバー関数。  
  
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
 `lpCreateStruct`  
 Long ポインター、 [CREATESTRUCT](../../mfc/reference/createstruct-structure.md)構造体。  
  
 `pWindowMenu`  
 ウィンドウのポップアップ メニューへのポインター。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
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
 `pClass`  
 子ウィンドウを作成できるのランタイム クラスです。  
  
 *nResource*  
 子ウィンドウに関連付けられている共有リソースの ID。  
  
 `hMenu`  
 子ウィンドウのメニュー。  
  
 `hAccel`  
 子ウィンドウのアクセラレータです。  
  
### <a name="remarks"></a>コメント  
 子 MDI フレーム ウィンドウのウィンドウを作成するのにには、この関数を使用します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCWindowing#15](../../mfc/reference/codesnippet/cpp/cmdiframewnd-class_3.cpp)]  
  
 この例は、サポート技術情報の記事 Q201045、抜粋"HOWTO: 以外のドキュメント/ビュー MDI アプリケーションに複数のウィンドウの種類を追加します"。 サポート技術情報については、「 [ http://support.microsoft.com](http://support.microsoft.com/)です。  
  
##  <a name="getwindowmenupopup"></a>  CMDIFrameWnd::GetWindowMenuPopup  
 「ウィンドウ」(MDI ウィンドウの管理のメニュー項目を含むポップアップ メニュー) をという名前の現在のポップアップ メニューへのハンドルを取得するには、このメンバー関数を呼び出します。  
  
```  
virtual HMENU GetWindowMenuPopup(HMENU hMenuBar);
```  
  
### <a name="parameters"></a>パラメーター  
 *hMenuBar*  
 現在のメニュー バー。  
  
### <a name="return-value"></a>戻り値  
 存在する場合は 1 つのウィンドウのポップアップ メニューそれ以外の場合**NULL**です。  
  
### <a name="remarks"></a>コメント  
 既定の実装は標準のウィンドウ メニューのコマンドをなどを含むポップアップ メニューの検索**ID_WINDOW_NEW**と**ID_WINDOW_TILE_HORZ**です。  
  
 標準のメニュー コマンド Id を使用しないウィンドウ メニューがある場合は、このメンバー関数をオーバーライドします。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCWindowing#16](../../mfc/reference/codesnippet/cpp/cmdiframewnd-class_4.cpp)]  
  
##  <a name="mdiactivate"></a>  CMDIFrameWnd::MDIActivate  
 さまざまな MDI 子ウィンドウをアクティブにします。  
  
```  
void MDIActivate(CWnd* pWndActivate);
```  
  
### <a name="parameters"></a>パラメーター  
 *pWndActivate*  
 アクティブ化する MDI 子ウィンドウへのポインター。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、 [WM_MDIACTIVATE](../../mfc/reference/cwnd-class.md#onmdiactivate)子ウィンドウがアクティブ化されていると、子ウィンドウの両方の非アクティブ化するメッセージ。  
  
 これは、ユーザーは、マウスまたはキーボードを使用して MDI 子ウィンドウにフォーカスを変更した場合に送信されるのと同じメッセージです。  
  
> [!NOTE]
>  MDI フレーム ウィンドウとは無関係に、MDI 子ウィンドウがアクティブ化されます。 最後にアクティブになった子ウィンドウが送信される、フレームがアクティブになったときに、[ため](../../mfc/reference/cwnd-class.md#onncactivate)をアクティブなウィンドウ フレームおよびキャプション バーが描画メッセージを受け取りません別`WM_MDIACTIVATE`メッセージ。  
  
### <a name="example"></a>例  
 例を参照して[CMDIFrameWnd::GetWindowMenuPopup](#getwindowmenupopup)です。  
  
##  <a name="mdicascade"></a>  CMDIFrameWnd::MDICascade  
 Cascade 形式でのすべての MDI 子ウィンドウを整列します。  
  
```  
void MDICascade();  
void MDICascade(int nType);
```  
  
### <a name="parameters"></a>パラメーター  
 `nType`  
 Cascade フラグを指定します。 次のフラグだけを指定することができます: `MDITILE_SKIPDISABLED`、ため、無効になっている MDI 子ウィンドウを重ねて表示されています。  
  
### <a name="remarks"></a>コメント  
 最初のバージョンの`MDICascade`、パラメーターなしで、無効になっているものを含め、すべての MDI 子ウィンドウを重ねて表示します。 2 番目のバージョンは cascade が無効になっている MDI 子ウィンドウされませんを指定した場合に必要に応じて`MDITILE_SKIPDISABLED`の`nType`パラメーター。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCWindowing#17](../../mfc/reference/codesnippet/cpp/cmdiframewnd-class_5.cpp)]  
  
##  <a name="mdigetactive"></a>  CMDIFrameWnd::MDIGetActive  
 現在アクティブな MDI 子ウィンドウ、および子ウィンドウを最大化するかどうかを示すフラグを取得します。  
  
```  
CMDIChildWnd* MDIGetActive(BOOL* pbMaximized = NULL) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 *pbMaximized*  
 ポインター、 **BOOL**値を返します。 設定**TRUE**ウィンドウが最大化、それ以外の場合に返された**FALSE**です。  
  
### <a name="return-value"></a>戻り値  
 アクティブな MDI 子ウィンドウへのポインター。  
  
### <a name="example"></a>例  
 例を参照して[CMDIChildWnd::MDIMaximize](../../mfc/reference/cmdichildwnd-class.md#mdimaximize)です。  
  
##  <a name="mdiiconarrange"></a>  ある最小化されました。  
 最小化されたドキュメントのすべての子ウィンドウを整列します。  
  
```  
void MDIIconArrange();
```  
  
### <a name="remarks"></a>コメント  
 最小化されていない子ウィンドウには影響しません。  
  
### <a name="example"></a>例  
 例を参照して[CMDIFrameWnd::MDICascade](#mdicascade)です。  
  
##  <a name="mdimaximize"></a>  CMDIFrameWnd::MDIMaximize  
 指定した MDI 子ウィンドウを最大化します。  
  
```  
void MDIMaximize(CWnd* pWnd);
```  
  
### <a name="parameters"></a>パラメーター  
 `pWnd`  
 最大表示するウィンドウへのポインター。  
  
### <a name="remarks"></a>コメント  
 子ウィンドウを最大表示しているときに Windows のサイズを変更するために、そのクライアント、クライアント ウィンドウを埋めることです。 Windows は、フレームのメニュー バーで、子ウィンドウのコントロールのメニューを配置するユーザーが復元または子ウィンドウを閉じるようにします。 また、フレーム ウィンドウのタイトルに子ウィンドウのタイトルを追加します。  
  
 現在アクティブな MDI 子ウィンドウを最大化時に別の MDI 子ウィンドウがアクティブな場合、Windows は現在アクティブな子を復元し、新しくアクティブにされた子ウィンドウを最大化します。  
  
### <a name="example"></a>例  
 例を参照して[CMDIChildWnd::MDIMaximize](../../mfc/reference/cmdichildwnd-class.md#mdimaximize)です。  
  
##  <a name="mdinext"></a>  CMDIFrameWnd::MDINext  
 現在アクティブな子ウィンドウの背後にすぐに子ウィンドウをアクティブにし、その他のすべての子ウィンドウの背後にある、現在アクティブな子ウィンドウを配置します。  
  
```  
void MDINext();
```  
  
### <a name="remarks"></a>コメント  
 現在アクティブな MDI 子ウィンドウを最大表示している場合、メンバー関数は現在アクティブな子を復元し、新しくアクティブにされた子を最大化します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCWindowing#18](../../mfc/reference/codesnippet/cpp/cmdiframewnd-class_6.cpp)]  
  
##  <a name="mdiprev"></a>  CMDIFrameWnd::MDIPrev  
 前の子ウィンドウをアクティブにし、すぐ後ろに、現在アクティブな子ウィンドウを置きます。  
  
```  
void MDIPrev();
```  
  
### <a name="remarks"></a>コメント  
 現在アクティブな MDI 子ウィンドウを最大表示している場合、メンバー関数は現在アクティブな子を復元し、新しくアクティブにされた子を最大化します。  
  
##  <a name="mdirestore"></a>  CMDIFrameWnd::MDIRestore  
 MDI 子ウィンドウを最大化または最小化されているサイズから復元します。  
  
```  
void MDIRestore(CWnd* pWnd);
```  
  
### <a name="parameters"></a>パラメーター  
 `pWnd`  
 復元するウィンドウへのポインター。  
  
### <a name="example"></a>例  
 例を参照して[CMDIChildWnd::MDIRestore](../../mfc/reference/cmdichildwnd-class.md#mdirestore)です。  
  
##  <a name="mdisetmenu"></a>  CMDIFrameWnd::MDISetMenu  
 MDI フレーム ウィンドウのメニューのウィンドウのポップアップ メニューのまたはその両方を置換します。  
  
```  
CMenu* MDISetMenu(
    CMenu* pFrameMenu,  
    CMenu* pWindowMenu);
```  
  
### <a name="parameters"></a>パラメーター  
 *pFrameMenu*  
 新しいフレーム ウィンドウ メニューのメニューを指定します。 場合**NULL**メニューは変更されません。  
  
 `pWindowMenu`  
 新しいウィンドウのポップアップ メニューのメニューを指定します。 場合**NULL**メニューは変更されません。  
  
### <a name="return-value"></a>戻り値  
 このメッセージに置き換え、フレーム ウィンドウ メニューへのポインター。 ポインターは一時的である可能性があり、後で使用するために格納しないでください。  
  
### <a name="remarks"></a>コメント  
 呼び出した後`MDISetMenu`、アプリケーションを呼び出す必要があります、 [DrawMenuBar](../../mfc/reference/cwnd-class.md#drawmenubar)のメンバー関数`CWnd`をメニュー バーを更新します。  
  
 この呼び出しに代わる、ウィンドウのポップアップ メニューで場合、MDI 子ウィンドウのメニュー項目が前のウィンドウ メニューから削除され、新しいウィンドウのポップアップ メニューに追加します。  
  
 MDI 子ウィンドウが最大化されて、この関数は、MDI フレーム ウィンドウのメニューを置き換える場合は、コントロールのメニューと復元のコントロールが前のフレーム ウィンドウ メニューから削除し、新しいメニューに追加します。  
  
 MDI 子ウィンドウを管理するために、フレームワークを使用する場合は、このメンバー関数を呼び出さないでください。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCWindowing#19](../../mfc/reference/codesnippet/cpp/cmdiframewnd-class_7.cpp)]  
  
 [!code-cpp[NVC_MFCWindowing#20](../../mfc/reference/codesnippet/cpp/cmdiframewnd-class_8.cpp)]  
  
##  <a name="mditile"></a>  CMDIFrameWnd::MDITile  
 タイル化された形式ですべての子ウィンドウを整列します。  
  
```  
void MDITile();  
void MDITile(int nType);
```  
  
### <a name="parameters"></a>パラメーター  
 `nType`  
 並べて表示フラグを指定します。 このパラメーターは、次のフラグのいずれかを指定できます。  
  
- `MDITILE_HORIZONTAL` MDI 子ウィンドウが並べて別上その 1 つのウィンドウに表示されます。  
  
- `MDITILE_SKIPDISABLED` 無効になっている MDI 子ウィンドウが並べて表示する対象するを防ぎます。  
  
- `MDITILE_VERTICAL` MDI 子ウィンドウが並べて別の横にあるその 1 つのウィンドウが表示されます。  
  
### <a name="remarks"></a>コメント  
 最初のバージョンの`MDITile`パラメーターを指定せずには、Windows 3.1 以降のバージョンで垂直方向にウィンドウを並べて表示します。 2 番目のバージョン ウィンドウを並べて表示垂直または水平方向の値に応じて、`nType`パラメーター。  
  
### <a name="example"></a>例  
 例を参照して[CMDIFrameWnd::MDICascade](#mdicascade)です。  
  
## <a name="see-also"></a>関連項目  
 [MFC サンプル MDI](../../visual-cpp-samples.md)   
 [MFC サンプルは](../../visual-cpp-samples.md)   
 [MFC サンプル SNAPVW](../../visual-cpp-samples.md)   
 [CFrameWnd クラス](../../mfc/reference/cframewnd-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CWnd クラス](../../mfc/reference/cwnd-class.md)   
 [CMDIChildWnd クラス](../../mfc/reference/cmdichildwnd-class.md)

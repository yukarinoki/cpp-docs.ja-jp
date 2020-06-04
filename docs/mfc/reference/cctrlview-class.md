---
title: クラスを表示します。
ms.date: 11/04/2016
f1_keywords:
- CCtrlView
- AFXWIN/CCtrlView
- AFXWIN/CCtrlView::CCtrlView
- AFXWIN/CCtrlView::OnDraw
- AFXWIN/CCtrlView::PreCreateWindow
- AFXWIN/CCtrlView::m_dwDefaultStyle
- AFXWIN/CCtrlView::m_strClass
helpviewer_keywords:
- CCtrlView [MFC], CCtrlView
- CCtrlView [MFC], OnDraw
- CCtrlView [MFC], PreCreateWindow
- CCtrlView [MFC], m_dwDefaultStyle
- CCtrlView [MFC], m_strClass
ms.assetid: ff488596-1e71-451f-8fec-b0831a7b44e0
ms.openlocfilehash: f77f1c265920bd160da790647ef754c55e6dbda3
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81369352"
---
# <a name="cctrlview-class"></a>クラスを表示します。

Windows 98 および Windows NT Version 3.51 以降がサポートするコモン コントロールにドキュメント/ビュー アーキテクチャを適合させます。

## <a name="syntax"></a>構文

```
class CCtrlView : public CView
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[ビュー::CCtrl ビュー](#cctrlview)|`CCtrlView` オブジェクトを構築します。|

### <a name="protected-methods"></a>プロテクト メソッド

|名前|説明|
|----------|-----------------|
|[を表示します。](#ondraw)|指定したデバイス コンテキストを使用して描画するフレームワークによって呼び出されます。|
|[ウィンドウを再作成:P](#precreatewindow)|`CCtrlView` オブジェクトに関連付けられている Windows のウィンドウが作成される前に呼び出されます。|

### <a name="protected-data-members"></a>プロテクト データ メンバー

|名前|説明|
|----------|-----------------|
|[m_dwDefaultStyle](#m_dwdefaultstyle)|ビュー クラスの既定のスタイルを格納します。|
|[M_strClass](#m_strclass)|ビュー クラスの Windows クラス名を格納します。|

## <a name="remarks"></a>解説

クラス`CCtrlView`とその派生物である[CEditView](../../mfc/reference/ceditview-class.md) [、CListView](../../mfc/reference/clistview-class.md) [、CTreeView](../../mfc/reference/ctreeview-class.md)、および[CRichEditView](../../mfc/reference/cricheditview-class.md)は、ドキュメント ビュー アーキテクチャを Windows 95/98 および Windows NT バージョン 3.51 以降でサポートされる新しいコモン コントロールに適合させます。 ドキュメント ビュー アーキテクチャの詳細については、「[ドキュメント/ビュー アーキテクチャ](../../mfc/document-view-architecture.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CView](../../mfc/reference/cview-class.md)

`CCtrlView`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxwin.h

## <a name="cctrlviewcctrlview"></a><a name="cctrlview"></a>ビュー::CCtrl ビュー

`CCtrlView` オブジェクトを構築します。

```
CCtrlView(
    LPCTSTR lpszClass,
    DWORD dwStyle);
```

### <a name="parameters"></a>パラメーター

*クラス*<br/>
ビュー クラスの Windows クラス名。

*Dwstyle*<br/>
ビュー クラスのスタイル。

### <a name="remarks"></a>解説

フレームワークは、新しいフレーム ウィンドウが作成されたとき、またはウィンドウが分割されるときに、コンストラクターを呼び出します。 ドキュメントが添付された後にビューを初期化するには[、CView::OnInitialUpdate](../../mfc/reference/cview-class.md#oninitialupdate)をオーバーライドします。 [CWnd::作成](../../mfc/reference/cwnd-class.md#create)または[CWnd::CreateEx](../../mfc/reference/cwnd-class.md#createex)を呼び出して、Windowsオブジェクトを作成します。

## <a name="cctrlviewm_strclass"></a><a name="m_strclass"></a>M_strClass

ビュー クラスの Windows クラス名を格納します。

```
CString m_strClass;
```

## <a name="cctrlviewm_dwdefaultstyle"></a><a name="m_dwdefaultstyle"></a>m_dwDefaultStyle

ビュー クラスの既定のスタイルを格納します。

```
DWORD m_dwDefaultStyle;
```

### <a name="remarks"></a>解説

このスタイルは、ウィンドウが作成されるときに適用されます。

## <a name="cctrlviewondraw"></a><a name="ondraw"></a>を表示します。

指定したデバイス コンテキストを使用してオブジェクトの`CCtrlView`内容を描画するために、フレームワークによって呼び出されます。

```
virtual void OnDraw(CDC* pDC);
```

### <a name="parameters"></a>パラメーター

*pDC*<br/>
描画が発生するデバイス コンテキストへのポインター。

### <a name="remarks"></a>解説

`OnDraw`通常は、画面表示用に呼び出され *、pDC*で指定された画面デバイス コンテキストを渡します。

## <a name="cctrlviewprecreatewindow"></a><a name="precreatewindow"></a>ウィンドウを再作成:P

`CWnd` オブジェクトに関連付けられている Windows のウィンドウが作成される前に呼び出されます。

```
virtual BOOL PreCreateWindow(CREATESTRUCT& cs);
```

### <a name="parameters"></a>パラメーター

*cs*<br/>
[構造体を作成します](/windows/win32/api/winuser/ns-winuser-createstructw)。

### <a name="return-value"></a>戻り値

ウィンドウの作成を続行する場合は 0 以外。0 を指定すると、作成エラーが発生します。

### <a name="remarks"></a>解説

この関数を直接呼び出さないでください。

この関数の既定の実装では、NULL ウィンドウ クラス名をチェックし、適切な既定値を置き換えます。 ウィンドウを作成する前に構造体`CREATESTRUCT`を変更するには、このメンバー関数をオーバーライドします。

派生`CCtrlView`した各クラスは、 のオーバーライドに独自の`PreCreateWindow`機能を追加します。 仕様上、これらの派生`PreCreateWindow`は文書化されていません。 各クラスに適したスタイルとスタイル間の相互依存関係を確認するには、アプリケーションの基本クラスの MFC ソース コードを調べます。 オーバーライド`PreCreateWindow`を選択した場合は、MFC ソース コードから収集した情報を使用して、アプリケーションの基本クラスで使用されるスタイルが必要な機能を提供するかどうかを決定できます。

ウィンドウ スタイルの変更の詳細については、「 [MFC で作成されるウィンドウのスタイルを変更する](../../mfc/changing-the-styles-of-a-window-created-by-mfc.md)」を参照してください。

## <a name="see-also"></a>関連項目

[Cビュークラス](../../mfc/reference/cview-class.md)<br/>
[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[クラス](../../mfc/reference/ctreeview-class.md)<br/>
[クラスを表示します。](../../mfc/reference/clistview-class.md)<br/>
[クラスを表示します。](../../mfc/reference/cricheditview-class.md)

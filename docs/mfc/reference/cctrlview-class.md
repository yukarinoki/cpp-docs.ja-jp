---
description: '詳細情報: CCtrlView クラス'
title: CCtrlView クラス
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
ms.openlocfilehash: b9cb3d9e32772e0d54d23acfc7606dbc45071446
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97227768"
---
# <a name="cctrlview-class"></a>CCtrlView クラス

Windows 98 および Windows NT Version 3.51 以降がサポートするコモン コントロールにドキュメント/ビュー アーキテクチャを適合させます。

## <a name="syntax"></a>構文

```
class CCtrlView : public CView
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CCtrlView::CCtrlView](#cctrlview)|`CCtrlView` オブジェクトを構築します。|

### <a name="protected-methods"></a>プロテクト メソッド

|名前|説明|
|----------|-----------------|
|[CCtrlView:: OnDraw](#ondraw)|指定されたデバイスコンテキストを使用して描画するために、フレームワークによって呼び出されます。|
|[CCtrlView::P reCreateWindow](#precreatewindow)|`CCtrlView` オブジェクトに関連付けられている Windows のウィンドウが作成される前に呼び出されます。|

### <a name="protected-data-members"></a>プロテクト データ メンバー

|名前|説明|
|----------|-----------------|
|[CCtrlView:: m_dwDefaultStyle](#m_dwdefaultstyle)|ビュークラスの既定のスタイルを格納します。|
|[CCtrlView:: m_strClass](#m_strclass)|ビュークラスの Windows クラス名を格納します。|

## <a name="remarks"></a>解説

クラス `CCtrlView` とその派生クラスである CEditView、 [CEditView](../../mfc/reference/ceditview-class.md)、 [CListView](../../mfc/reference/clistview-class.md)、 [CTreeView](../../mfc/reference/ctreeview-class.md)、および [CRichEditView](../../mfc/reference/cricheditview-class.md)は、ドキュメント/ビューアーキテクチャを、windows 95/98 および windows NT バージョン3.51 以降でサポートされる新しいコモンコントロールに適応させます。 ドキュメント/ビューアーキテクチャの詳細については、「 [ドキュメント/ビューアーキテクチャ](../../mfc/document-view-architecture.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CView](../../mfc/reference/cview-class.md)

`CCtrlView`

## <a name="requirements"></a>要件

**ヘッダー:** afxwin.h

## <a name="cctrlviewcctrlview"></a><a name="cctrlview"></a> CCtrlView::CCtrlView

`CCtrlView` オブジェクトを構築します。

```
CCtrlView(
    LPCTSTR lpszClass,
    DWORD dwStyle);
```

### <a name="parameters"></a>パラメーター

*lpszClass*<br/>
ビュークラスの Windows クラス名。

*dwStyle*<br/>
ビュークラスのスタイル。

### <a name="remarks"></a>解説

フレームワークは、新しいフレームウィンドウが作成されたとき、またはウィンドウが分割されたときにコンストラクターを呼び出します。 ドキュメントが添付された後にビューを初期化するには、 [CView:: OnInitialUpdate](../../mfc/reference/cview-class.md#oninitialupdate) をオーバーライドします。 [Cwnd:: create](../../mfc/reference/cwnd-class.md#create)または[Cwnd:: CreateEx](../../mfc/reference/cwnd-class.md#createex)を呼び出して、Windows オブジェクトを作成します。

## <a name="cctrlviewm_strclass"></a><a name="m_strclass"></a> CCtrlView:: m_strClass

ビュークラスの Windows クラス名を格納します。

```
CString m_strClass;
```

## <a name="cctrlviewm_dwdefaultstyle"></a><a name="m_dwdefaultstyle"></a> CCtrlView:: m_dwDefaultStyle

ビュークラスの既定のスタイルを格納します。

```
DWORD m_dwDefaultStyle;
```

### <a name="remarks"></a>解説

このスタイルは、ウィンドウの作成時に適用されます。

## <a name="cctrlviewondraw"></a><a name="ondraw"></a> CCtrlView:: OnDraw

`CCtrlView`指定されたデバイスコンテキストを使用してオブジェクトのコンテンツを描画するために、フレームワークによって呼び出されます。

```
virtual void OnDraw(CDC* pDC);
```

### <a name="parameters"></a>パラメーター

*pDC*<br/>
描画が発生するデバイスコンテキストへのポインター。

### <a name="remarks"></a>解説

`OnDraw` は、通常、画面表示のために呼び出され、 *pDC* によって指定された画面デバイスコンテキストを渡します。

## <a name="cctrlviewprecreatewindow"></a><a name="precreatewindow"></a> CCtrlView::P reCreateWindow

`CWnd` オブジェクトに関連付けられている Windows のウィンドウが作成される前に呼び出されます。

```
virtual BOOL PreCreateWindow(CREATESTRUCT& cs);
```

### <a name="parameters"></a>パラメーター

*cs*<br/>
[CREATESTRUCT](/windows/win32/api/winuser/ns-winuser-createstructw)構造体。

### <a name="return-value"></a>戻り値

ウィンドウの作成を続行する場合は0以外の。作成エラーを示す場合は0。

### <a name="remarks"></a>解説

この関数を直接呼び出さないでください。

この関数の既定の実装では、ウィンドウクラス名が NULL かどうかがチェックされ、適切な既定値に置き換えられます。 `CREATESTRUCT`ウィンドウが作成される前に構造を変更するには、このメンバー関数をオーバーライドします。

から派生 `CCtrlView` した各クラスは、のオーバーライドに独自の機能を追加し `PreCreateWindow` ます。 仕様として、これらの派生 `PreCreateWindow` は記載されていません。 各クラスに適したスタイルとスタイル間の相互依存関係を判断するには、アプリケーションの基本クラスの MFC ソースコードを確認します。 をオーバーライドすることを選択した場合は `PreCreateWindow` 、MFC ソースコードから収集された情報を使用して、アプリケーションの基本クラスで使用されるスタイルが必要な機能を提供するかどうかを判断できます。

ウィンドウスタイルの変更の詳細については、「 [MFC で作成されたウィンドウのスタイルを変更](../../mfc/changing-the-styles-of-a-window-created-by-mfc.md)する」を参照してください。

## <a name="see-also"></a>関連項目

[CView クラス](../../mfc/reference/cview-class.md)<br/>
[階層図](../../mfc/hierarchy-chart.md)<br/>
[CTreeView クラス](../../mfc/reference/ctreeview-class.md)<br/>
[CListView クラス](../../mfc/reference/clistview-class.md)<br/>
[CRichEditView クラス](../../mfc/reference/cricheditview-class.md)

---
title: CMFCDropDownFrame クラス
ms.date: 11/04/2016
f1_keywords:
- CMFCDropDownFrame
- AFXDROPDOWNTOOLBAR/CMFCDropDownFrame
- AFXDROPDOWNTOOLBAR/CMFCDropDownFrame::Create
- AFXDROPDOWNTOOLBAR/CMFCDropDownFrame::GetParentMenuBar
- AFXDROPDOWNTOOLBAR/CMFCDropDownFrame::GetParentPopupMenu
- AFXDROPDOWNTOOLBAR/CMFCDropDownFrame::RecalcLayout
- AFXDROPDOWNTOOLBAR/CMFCDropDownFrame::SetAutoDestroy
helpviewer_keywords:
- CMFCDropDownFrame [MFC], Create
- CMFCDropDownFrame [MFC], GetParentMenuBar
- CMFCDropDownFrame [MFC], GetParentPopupMenu
- CMFCDropDownFrame [MFC], RecalcLayout
- CMFCDropDownFrame [MFC], SetAutoDestroy
ms.assetid: 09ff81a9-de00-43ec-9df9-b626f7728c4b
ms.openlocfilehash: 534dc90443371c8440e0cb317540f2cf80f6eacc
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/04/2019
ms.locfileid: "57284750"
---
# <a name="cmfcdropdownframe-class"></a>CMFCDropDownFrame クラス

ドロップダウン ツールバーとドロップダウン ツール バー ボタンのドロップダウン リストのフレーム ウィンドウの機能を提供します。

## <a name="syntax"></a>構文

```
class CMFCDropDownFrame : public CMiniFrameWnd
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|||
|-|-|
|名前|説明|
|`CMFCDropDownFrame::CMFCDropDownFrame`|既定のコンストラクターです。|
|`CMFCDropDownFrame::~CMFCDropDownFrame`|デストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|||
|-|-|
|名前|説明|
|[CMFCDropDownFrame::Create](#create)|`CMFCDropDownFrame` オブジェクトを作成します。|
|`CMFCDropDownFrame::CreateObject`|このクラス型の動的インスタンスを作成するために、フレームワークで使用されます。|
|[CMFCDropDownFrame::GetParentMenuBar](#getparentmenubar)|ドロップダウン リストのフレームの親メニュー バーを取得します。|
|[CMFCDropDownFrame::GetParentPopupMenu](#getparentpopupmenu)|ドロップダウン リストのフレームの親のポップアップ メニューを取得します。|
|`CMFCDropDownFrame::GetThisClass`|ポインターを取得する、framework によって使用される、 [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md)このクラス型に関連付けられているオブジェクト。|
|[CMFCDropDownFrame::RecalcLayout](#recalclayout)|ドロップダウン リストのフレームを再配置されます。|
|[CMFCDropDownFrame::SetAutoDestroy](#setautodestroy)|子のドロップダウン ツール バー ウィンドウが自動的に破棄されるかどうかを設定します。|

### <a name="remarks"></a>Remarks

このクラスは、コードから直接使用するものではありません。

フレームワークでは、このクラスを使用するフレームの動作を提供する、`CMFCDropDownToolbar`と`CMFCDropDownToolbarButton`クラス。 これらのクラスの詳細については、[CMFCDropDownToolBar クラス](../../mfc/reference/cmfcdropdowntoolbar-class.md)と[CMFCDropDownToolbarButton クラス](../../mfc/reference/cmfcdropdowntoolbarbutton-class.md)を参照してください。

## <a name="example"></a>例

次の例へのポインターを取得する方法を示します、`CMFCDropDownFrame`オブジェクトから、`CFrameWnd`クラス、および子に自動的に破棄するツールバーのドロップダウン ウィンドウを設定する方法。

[!code-cpp[NVC_MFC_RibbonApp#36](../../mfc/reference/codesnippet/cpp/cmfcdropdownframe-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CFrameWnd](../../mfc/reference/cframewnd-class.md)

[CMiniFrameWnd](../../mfc/reference/cminiframewnd-class.md)

[CMFCDropDownFrame](../../mfc/reference/cmfcdropdownframe-class.md)

## <a name="requirements"></a>必要条件

**ヘッダー:** afxdropdowntoolbar.h

##  <a name="create"></a>  CMFCDropDownFrame::Create

`CMFCDropDownFrame` オブジェクトを作成します。

```
virtual BOOL Create(
    CWnd* pWndParent,
    int x,
    int y,
    CMFCDropDownToolBar* pWndOriginToolbar);
```

### <a name="parameters"></a>パラメーター

|||
|-|-|
|パラメーター|説明|
|*pWndParent*|[in]ドロップダウン リストのフレームの親ウィンドウ。|
|*x*|[in]ドロップダウンのフレームの位置の水平画面座標。|
|*y*|[in]ドロップダウンのフレームの位置の垂直画面座標。|
|*pWndOriginToolbar*|[in]このツールバーは、このメソッドを使用して新しいドロップダウン フレーム オブジェクトに設定するドロップダウン ボタンがあります。|

### <a name="return-value"></a>戻り値

ドロップダウン リストのフレームが作成された場合は TRUE。それ以外の場合は FALSE です。

### <a name="remarks"></a>Remarks

このメソッドは、ベース[CMiniFrameWnd::CreateEx](../../mfc/reference/cminiframewnd-class.md#createex) WS_POPUP スタイルを使用して、ドロップダウン リストのフレーム ウィンドウを作成します。 指定した画面座標にあるドロップダウン リストのフレーム ウィンドウが表示されます。 このメソッドは失敗、 [CMiniFrameWnd::CreateEx](../../mfc/reference/cminiframewnd-class.md#createex)メソッドは FALSE を返します。

`CMFCDropDownFrame`クラスは、指定されたのコピーを作成`CMFCDropDownToolBar`パラメーター。 このメソッドは、ボタンの状態から、ボタンのイメージをコピー、`pWndOriginToolbar`パラメーターを`m_pWndOriginToolbar`データ メンバー。

##  <a name="getparentmenubar"></a>  CMFCDropDownFrame::GetParentMenuBar

ドロップダウン リストのフレームの親メニュー バーを取得します。

```
CMFCMenuBar* GetParentMenuBar() const;
```

### <a name="return-value"></a>戻り値

ドロップダウンのフレームまたはフレームが親を持たない場合は NULL の親メニュー バーへのポインター。

### <a name="remarks"></a>Remarks

このメソッドは、親のボタンから、親メニュー バーを取得します。 このメソッドは、ドロップダウン リストのフレームが親ボタン、または親のボタンがメニュー バーの親を持たない場合に NULL を返します。

##  <a name="getparentpopupmenu"></a>  CMFCDropDownFrame::GetParentPopupMenu

ドロップダウン リストのフレームの親のポップアップ メニューを取得します。

```
CMFCDropDownFrame* GetParentPopupMenu() const;
```

### <a name="return-value"></a>戻り値

ドロップダウンのフレームまたはフレームが親を持たない場合は NULL の親のドロップダウン メニューへのポインター。

### <a name="remarks"></a>Remarks

このメソッドは、親のボタンから、親メニューを取得します。 ドロップダウンのフレームが親ボタン、または親ボタンには、親メニューがない場合、このメソッドは NULL を返します。

##  <a name="recalclayout"></a>  CMFCDropDownFrame::RecalcLayout

ドロップダウン リストのフレームを再配置されます。

```
virtual void RecalcLayout(BOOL bNotify = TRUE);
```

### <a name="parameters"></a>パラメーター

|||
|-|-|
|パラメーター|説明|
|*bNotify*|[in]使用されていません。|

### <a name="remarks"></a>Remarks

フレームワークは、ドロップダウンのフレームが作成されるか、親ウィンドウのサイズが変更されたときに、このメソッドを呼び出します。 このメソッドは、親ウィンドウのサイズと位置を使用して、ドロップダウン リストのフレームのサイズと位置を計算します。

##  <a name="setautodestroy"></a>  CMFCDropDownFrame::SetAutoDestroy

子のドロップダウン ツール バー ウィンドウが自動的に破棄されるかどうかを設定します。

```
void SetAutoDestroy(BOOL bAutoDestroy = TRUE);
```

### <a name="parameters"></a>パラメーター

*bAutoDestroy*<br/>
[in]ドロップダウン ツール バーが関連付けられているウィンドウを自動的に破棄する場合は TRUEそれ以外の場合、FALSE です。

### <a name="remarks"></a>Remarks

場合*bAutoDestroy*が true の場合、次に、`CMFCDropDownFrame`デストラクターが関連付けられているドロップダウン ツール バー ウィンドウを破棄します。 既定値は TRUE です。

## <a name="see-also"></a>関連項目

[階層図](../../mfc/hierarchy-chart.md)<br/>
[クラス](../../mfc/reference/mfc-classes.md)<br/>
[CMFCDropDownToolBar クラス](../../mfc/reference/cmfcdropdowntoolbar-class.md)<br/>
[CMFCDropDownToolbarButton クラス](../../mfc/reference/cmfcdropdowntoolbarbutton-class.md)

---
description: '詳細情報: CMFCDropDownFrame クラス'
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
ms.openlocfilehash: 9ab5cbaf600fe7970bdff229b43d34fd04c8fbb9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97294042"
---
# <a name="cmfcdropdownframe-class"></a>CMFCDropDownFrame クラス

ドロップダウンツールバーとドロップダウンツールバーボタンにドロップダウンのフレームウィンドウ機能を提供します。

## <a name="syntax"></a>構文

```
class CMFCDropDownFrame : public CMiniFrameWnd
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|-|-|
|`CMFCDropDownFrame::CMFCDropDownFrame`|既定のコンストラクターです。|
|`CMFCDropDownFrame::~CMFCDropDownFrame`|デストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|-|-|
|[CMFCDropDownFrame:: Create](#create)|`CMFCDropDownFrame` オブジェクトを作成します。|
|`CMFCDropDownFrame::CreateObject`|このクラス型の動的インスタンスを作成するために、フレームワークで使用されます。|
|[CMFCDropDownFrame:: GetParentMenuBar](#getparentmenubar)|ドロップダウンフレームの親メニューバーを取得します。|
|[CMFCDropDownFrame:: GetParentPopupMenu](#getparentpopupmenu)|ドロップダウンフレームの親ポップアップメニューを取得します。|
|`CMFCDropDownFrame::GetThisClass`|このクラス型に関連付けられている [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) オブジェクトへのポインターを取得するために、フレームワークによって使用されます。|
|[CMFCDropDownFrame:: RecalcLayout](#recalclayout)|ドロップダウンフレームを移動します。|
|[CMFCDropDownFrame:: SetAutoDestroy](#setautodestroy)|子のドロップダウンツールバーウィンドウを自動的に破棄するかどうかを設定します。|

### <a name="remarks"></a>解説

このクラスは、コードで直接使用するためのものではありません。

フレームワークは、このクラスを使用して、クラスおよびクラスにフレーム動作を提供し `CMFCDropDownToolbar` `CMFCDropDownToolbarButton` ます。 これらのクラスの詳細については、「 [Cmfcdropdowntoolbar クラス](../../mfc/reference/cmfcdropdowntoolbar-class.md) および [CMFCDropDownToolbarButton クラス](../../mfc/reference/cmfcdropdowntoolbarbutton-class.md)」を参照してください。

## <a name="example"></a>例

次の例は、クラスからオブジェクトへのポインターを取得する方法 `CMFCDropDownFrame` `CFrameWnd` と、子のドロップダウンツールバーウィンドウを自動的に破棄するように設定する方法を示しています。

[!code-cpp[NVC_MFC_RibbonApp#36](../../mfc/reference/codesnippet/cpp/cmfcdropdownframe-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CFrameWnd](../../mfc/reference/cframewnd-class.md)

[CMiniFrameWnd](../../mfc/reference/cminiframewnd-class.md)

[CMFCDropDownFrame](../../mfc/reference/cmfcdropdownframe-class.md)

## <a name="requirements"></a>要件

**ヘッダー:** afxdropdowntoolbar.h

## <a name="cmfcdropdownframecreate"></a><a name="create"></a> CMFCDropDownFrame:: Create

`CMFCDropDownFrame` オブジェクトを作成します。

```
virtual BOOL Create(
    CWnd* pWndParent,
    int x,
    int y,
    CMFCDropDownToolBar* pWndOriginToolbar);
```

### <a name="parameters"></a>パラメーター

*pWndParent*\
からドロップダウンフレームの親ウィンドウ。

*閉じる*\
からダウンフレームの位置を表示する水平方向の画面座標。

*前年*\
から下方向のフレームの位置を表示する垂直方向の画面座標。

*pWndOriginToolbar*\
からこのメソッドが新しいドロップダウンフレームオブジェクトを設定するために使用するドロップダウンボタンを持つツールバー。

### <a name="return-value"></a>戻り値

ドロップダウンフレームが正常に作成された場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

このメソッドは、base [CMiniFrameWnd:: CreateEx](../../mfc/reference/cminiframewnd-class.md#createex) メソッドを呼び出して、WS_POPUP スタイルのドロップダウンフレームウィンドウを作成します。 ドロップダウンフレームウィンドウは、指定した画面座標で表示されます。 [CMiniFrameWnd:: CreateEx](../../mfc/reference/cminiframewnd-class.md#createex)メソッドが FALSE を返す場合、このメソッドは失敗します。

クラスは、 `CMFCDropDownFrame` 指定されたパラメーターのコピーを作成し `CMFCDropDownToolBar` ます。 このメソッドは、ボタンイメージとボタンの状態を `pWndOriginToolbar` パラメーターからデータメンバーにコピーし `m_pWndOriginToolbar` ます。

## <a name="cmfcdropdownframegetparentmenubar"></a><a name="getparentmenubar"></a> CMFCDropDownFrame:: GetParentMenuBar

ドロップダウンフレームの親メニューバーを取得します。

```
CMFCMenuBar* GetParentMenuBar() const;
```

### <a name="return-value"></a>戻り値

ドロップダウンフレームの親メニューバーへのポインター。フレームに親がない場合は NULL。

### <a name="remarks"></a>解説

このメソッドは、親のメニューバーを親ボタンから取得します。 このメソッドは、ドロップダウンフレームに親ボタンがない場合、または親ボタンに親メニューバーがない場合に NULL を返します。

## <a name="cmfcdropdownframegetparentpopupmenu"></a><a name="getparentpopupmenu"></a> CMFCDropDownFrame:: GetParentPopupMenu

ドロップダウンフレームの親ポップアップメニューを取得します。

```
CMFCDropDownFrame* GetParentPopupMenu() const;
```

### <a name="return-value"></a>戻り値

ドロップダウンフレームの親ドロップダウンメニューへのポインター。フレームに親がない場合は NULL。

### <a name="remarks"></a>解説

このメソッドは、親メニューを親ボタンから取得します。 ドロップダウンフレームに親ボタンがない場合、または親ボタンに親メニューがない場合、このメソッドは NULL を返します。

## <a name="cmfcdropdownframerecalclayout"></a><a name="recalclayout"></a> CMFCDropDownFrame:: RecalcLayout

ドロップダウンフレームを移動します。

```
virtual void RecalcLayout(BOOL bNotify = TRUE);
```

### <a name="parameters"></a>パラメーター

*bNotify*\
から未使用.

### <a name="remarks"></a>解説

このメソッドは、ドロップダウンフレームが作成されたとき、または親ウィンドウのサイズが変更されたときに、フレームワークによって呼び出されます。 このメソッドは、親ウィンドウの位置とサイズを使用して、ドロップダウンフレームの位置とサイズを計算します。

## <a name="cmfcdropdownframesetautodestroy"></a><a name="setautodestroy"></a> CMFCDropDownFrame:: SetAutoDestroy

子のドロップダウンツールバーウィンドウを自動的に破棄するかどうかを設定します。

```cpp
void SetAutoDestroy(BOOL bAutoDestroy = TRUE);
```

### <a name="parameters"></a>パラメーター

*bAutoDestroy*<br/>
から関連付けられているドロップダウンツールバーウィンドウを自動的に破棄する場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

*Bautodestroy* が TRUE の場合、デストラクターは、 `CMFCDropDownFrame` 関連付けられているドロップダウンツールバーウィンドウを破棄します。 既定値は TRUE です。

## <a name="see-also"></a>関連項目

[階層図](../../mfc/hierarchy-chart.md)<br/>
[Classes](../../mfc/reference/mfc-classes.md)<br/>
[CMFCDropDownToolBar クラス](../../mfc/reference/cmfcdropdowntoolbar-class.md)<br/>
[CMFCDropDownToolbarButton クラス](../../mfc/reference/cmfcdropdowntoolbarbutton-class.md)

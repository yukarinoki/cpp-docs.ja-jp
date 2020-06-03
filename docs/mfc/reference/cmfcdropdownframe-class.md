---
title: クラスをドロップダウンする
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
ms.openlocfilehash: 508b27acd0a2004b1b8f75fde0bddcdf91194948
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "81752432"
---
# <a name="cmfcdropdownframe-class"></a>クラスをドロップダウンする

ドロップダウン ツール バーおよびドロップダウン ツール バー ボタンにドロップダウン フレーム ウィンドウ機能を提供します。

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
|[CMFCドロップダウンフレーム::作成](#create)|`CMFCDropDownFrame` オブジェクトを作成します。|
|`CMFCDropDownFrame::CreateObject`|このクラス型の動的インスタンスを作成するために、フレームワークで使用されます。|
|[CMFCドロップダウンフレーム::取得親メニューバー](#getparentmenubar)|ドロップダウン フレームの親メニュー バーを取得します。|
|[メニューメニューを取得します。](#getparentpopupmenu)|ドロップダウン フレームの親ポップアップ メニューを取得します。|
|`CMFCDropDownFrame::GetThisClass`|このクラス型に関連付けられている[CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md)オブジェクトへのポインターを取得するために、フレームワークによって使用されます。|
|[CMFCドロップダウンフレーム::リカルクレイアウト](#recalclayout)|ドロップダウン フレームを再配置します。|
|[CMFCドロップダウンフレーム::セットオートデストロイ](#setautodestroy)|子ドロップダウン ツール バー ウィンドウを自動的に破棄するかどうかを設定します。|

### <a name="remarks"></a>解説

このクラスは、コードで直接使用するためのものではありません。

フレームワークは、このクラスを使用して`CMFCDropDownToolbar`、 クラスと`CMFCDropDownToolbarButton`クラスにフレーム動作を提供します。 これらのクラスの詳細については、「クラス」および[「CMFCDropDown](../../mfc/reference/cmfcdropdowntoolbar-class.md) [ツールバー クラス」](../../mfc/reference/cmfcdropdowntoolbarbutton-class.md)を参照してください。

## <a name="example"></a>例

`CFrameWnd`クラスから`CMFCDropDownFrame`オブジェクトへのポインターを取得する方法と、子ドロップダウン ツール バー ウィンドウを自動的に破棄する設定方法を次の例に示します。

[!code-cpp[NVC_MFC_RibbonApp#36](../../mfc/reference/codesnippet/cpp/cmfcdropdownframe-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CFrameWnd](../../mfc/reference/cframewnd-class.md)

[CMiniFrameWnd](../../mfc/reference/cminiframewnd-class.md)

[ダウンフレーム](../../mfc/reference/cmfcdropdownframe-class.md)

## <a name="requirements"></a>必要条件

**ヘッダー:** afxdropdowntoolbar.h

## <a name="cmfcdropdownframecreate"></a><a name="create"></a>CMFCドロップダウンフレーム::作成

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
|*親の子*|[in]ドロップダウン フレームの親ウィンドウ。|
|*x*|[in]下向きフレームの位置を示す水平画面座標。|
|*Y*|[in]下向きフレームの位置を示す垂直画面座標。|
|*ツール バー*|[in]このメソッドが新しいドロップダウン フレーム オブジェクトを設定するために使用するドロップダウン ボタンがあるツール バー。|

### <a name="return-value"></a>戻り値

ドロップダウン フレームが正常に作成された場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

このメソッドは、基本[CMiniFrameWnd::CreateEx](../../mfc/reference/cminiframewnd-class.md#createex)メソッドを呼び出して、WS_POPUP スタイルのドロップダウン フレーム ウィンドウを作成します。 ドロップダウン フレーム ウィンドウが、指定した画面座標に表示されます。 このメソッドは[、CMiniFrameWnd::CreateEx](../../mfc/reference/cminiframewnd-class.md#createex)メソッドが FALSE を返す場合に失敗します。

クラス`CMFCDropDownFrame`は、指定された`CMFCDropDownToolBar`パラメーターのコピーを作成します。 このメソッドは、ボタン イメージとボタンの状態`pWndOriginToolbar`をパラメーターから`m_pWndOriginToolbar`データ メンバーにコピーします。

## <a name="cmfcdropdownframegetparentmenubar"></a><a name="getparentmenubar"></a>CMFCドロップダウンフレーム::取得親メニューバー

ドロップダウン フレームの親メニュー バーを取得します。

```
CMFCMenuBar* GetParentMenuBar() const;
```

### <a name="return-value"></a>戻り値

ドロップダウン フレームの親メニュー バーへのポインター。

### <a name="remarks"></a>解説

このメソッドは、親ボタンから親メニュー バーを取得します。 ドロップダウン フレームに親ボタンがない場合、または親ボタンに親メニュー バーがない場合、このメソッドは NULL を返します。

## <a name="cmfcdropdownframegetparentpopupmenu"></a><a name="getparentpopupmenu"></a>メニューメニューを取得します。

ドロップダウン フレームの親ポップアップ メニューを取得します。

```
CMFCDropDownFrame* GetParentPopupMenu() const;
```

### <a name="return-value"></a>戻り値

ドロップダウン フレームの親ドロップダウン メニューへのポインター。

### <a name="remarks"></a>解説

このメソッドは、親ボタンから親メニューを取得します。 ドロップダウン フレームに親ボタンがない場合、または親ボタンに親メニューがない場合、このメソッドは NULL を返します。

## <a name="cmfcdropdownframerecalclayout"></a><a name="recalclayout"></a>CMFCドロップダウンフレーム::リカルクレイアウト

ドロップダウン フレームを再配置します。

```
virtual void RecalcLayout(BOOL bNotify = TRUE);
```

### <a name="parameters"></a>パラメーター

|||
|-|-|
|パラメーター|説明|
|*通知する*|[in]未使用。|

### <a name="remarks"></a>解説

フレームワークは、ドロップダウン フレームが作成されたとき、または親ウィンドウのサイズが変更されたときに、このメソッドを呼び出します。 このメソッドは、親ウィンドウの位置とサイズを使用して、ドロップダウン フレームの位置とサイズを計算します。

## <a name="cmfcdropdownframesetautodestroy"></a><a name="setautodestroy"></a>CMFCドロップダウンフレーム::セットオートデストロイ

子ドロップダウン ツール バー ウィンドウを自動的に破棄するかどうかを設定します。

```cpp
void SetAutoDestroy(BOOL bAutoDestroy = TRUE);
```

### <a name="parameters"></a>パラメーター

*b自動破壊*<br/>
[in]関連付けられたドロップダウン ツール バー ウィンドウを自動的に破棄する場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

*bAutoDestroy*が TRUE の`CMFCDropDownFrame`場合、デストラクタは関連付けられたドロップダウン ツール バー ウィンドウを破棄します。 既定値は TRUE です。

## <a name="see-also"></a>関連項目

[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[クラス](../../mfc/reference/mfc-classes.md)<br/>
[クラスをドロップダウンメニューバー](../../mfc/reference/cmfcdropdowntoolbar-class.md)<br/>
[クラスをドロップダウンダウンツール バーボタン](../../mfc/reference/cmfcdropdowntoolbarbutton-class.md)

---
title: クラスを自動非表示にする
ms.date: 11/04/2016
f1_keywords:
- CAutoHideDockSite
- AFXAUTOHIDEDOCKSITE/CAutoHideDockSite
- AFXAUTOHIDEDOCKSITE/CAutoHideDockSite::CanAcceptPane
- AFXAUTOHIDEDOCKSITE/CAutoHideDockSite::DockPane
- AFXAUTOHIDEDOCKSITE/CAutoHideDockSite::GetAlignRect
- AFXAUTOHIDEDOCKSITE/CAutoHideDockSite::RepositionPanes
- AFXAUTOHIDEDOCKSITE/CAutoHideDockSite::SetOffsetLeft
- AFXAUTOHIDEDOCKSITE/CAutoHideDockSite::SetOffsetRight
- AFXAUTOHIDEDOCKSITE/CAutoHideDockSite::UnSetAutoHideMode
- AFXAUTOHIDEDOCKSITE/CAutoHideDockSite::m_nExtraSpace
helpviewer_keywords:
- CAutoHideDockSite [MFC], CanAcceptPane
- CAutoHideDockSite [MFC], DockPane
- CAutoHideDockSite [MFC], GetAlignRect
- CAutoHideDockSite [MFC], RepositionPanes
- CAutoHideDockSite [MFC], SetOffsetLeft
- CAutoHideDockSite [MFC], SetOffsetRight
- CAutoHideDockSite [MFC], UnSetAutoHideMode
- CAutoHideDockSite [MFC], m_nExtraSpace
ms.assetid: 2a0f6bec-c369-4ab7-977d-564e7946ebad
ms.openlocfilehash: 1f23729ced02a151c6186bdcc72cb8938416be46
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "81753003"
---
# <a name="cautohidedocksite-class"></a>クラスを自動非表示にする

`CAutoHideDockSite` [CDockSite クラス](../../mfc/reference/cdocksite-class.md)を拡張して、ドッキング ペインの自動非表示を実装します。

## <a name="syntax"></a>構文

```
class CAutoHideDockSite : public CDockSite
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|||
|-|-|
|名前|説明|
|`CAutoHideDockSite::CAutoHideDockSite`|`CAutoHideDockSite` オブジェクトを構築します。|
|`CAutoHideDockSite::~CAutoHideDockSite`|デストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|||
|-|-|
|名前|説明|
|`CAutoHideDockSite::AllowShowOnPaneMenu`|が`CAutoHideDockSite`ペイン メニューに表示されるかどうかを示します。|
|[C 自動ハイドドックサイト::缶アクセプドペイン](#canacceptpane)|基本ペイン オブジェクトが[CMFCAutoHideBar クラス](../../mfc/reference/cmfcautohidebar-class.md)から派生しているかどうかを判断します。|
|[C オートハイドドックサイト::DockPane](#dockpane)|ペインをこの`CAuotHideDockSite`オブジェクトにドッキングします。|
|[を取得します。](#getalignrect)|ドッキング サイトのサイズを画面座標で取得します。|
|[C 自動ハイドドックサイト::ペインの位置変更](#repositionpanes)|グローバルマージンとボタン間隔を`CAutoHideDockSite`持つペインを再描画します。|
|[C オートハイドドックサイト::オフセット左](#setoffsetleft)|ドッキング バーの左側の余白を設定します。|
|[C オートハイドドックサイト::オフセット右](#setoffsetright)|ドッキング バーの右側に余白を設定します。|
|[C 自動ハイドドックサイト::自動隠しモードを設定解除](#unsetautohidemode)|上のオブジェクト[に対して CMFC 自動隠しバー::自動非表示モードを呼](../../mfc/reference/cmfcautohidebar-class.md#unsetautohidemode)び出します。 `CAutoHideDockSite`|

### <a name="data-members"></a>データ メンバー

|||
|-|-|
|名前|説明|
|[C オートハイドドックサイト::m_nExtraSpace](#m_nextraspace)|ツール バーとドッキング バーの端の間のスペースのサイズを定義します。 このスペースは、ドッキングスペースの配置に応じて、左端または上端から測定されます。|

## <a name="remarks"></a>解説

[CFrameWndEx::有効に自動非表示ウィンドウを](../../mfc/reference/cframewndex-class.md#enableautohidepanes)呼び出すと、フレームワークは自動的`CAutoHideDockSite`にオブジェクトを作成します。 ほとんどの場合、このクラスを直接インスタンス化したり使用したりする必要はありません。

ドッキング バーは、ドッキング ペインの左側と[CMFCAutoHideButton クラス](../../mfc/reference/cmfcautohidebutton-class.md)の左側との間のギャップです。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CBasePane](../../mfc/reference/cbasepane-class.md)

[CDockSite](../../mfc/reference/cdocksite-class.md)

## <a name="example"></a>例

オブジェクトから`CAutoHideDockSite``CMFCAutoHideBar`オブジェクトを取得する方法と、ドッキング バーの左右の余白を設定する方法を次の例に示します。

[!code-cpp[NVC_MFC_RibbonApp#29](../../mfc/reference/codesnippet/cpp/cautohidedocksite-class_1.cpp)]

## <a name="requirements"></a>必要条件

**ヘッダー:** afx オートハイドドックサイト.h

## <a name="cautohidedocksitecanacceptpane"></a><a name="canacceptpane"></a>C 自動ハイドドックサイト::缶アクセプドペイン

基本ペインが[CMFCAutoHideBar](../../mfc/reference/cmfcautohidebar-class.md)オブジェクトであるか、またはから`CMFCAutoHideBar`派生しているかどうかを判断します。

```
virtual BOOL CanAcceptPane(const CBasePane* pBar) const;
```

### <a name="parameters"></a>パラメーター

|||
|-|-|
|パラメーター|説明|
|*pバー*|[in]フレームワークがテストする基本ペイン。|

### <a name="return-value"></a>戻り値

*pBar*がから`CMFCAutoHideBar`派生している場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

ベース ペイン オブジェクトが から`CMFCAutoHideBar`派生している場合は、`CAutoHideDockSite`を格納できます。

## <a name="cautohidedocksitedockpane"></a><a name="dockpane"></a>C オートハイドドックサイト::DockPane

この[CAutoHideDockSite](../../mfc/reference/cautohidedocksite-class.md)オブジェクトにペインをドッキングします。

```
virtual void DockPane(
    CPane* pWnd,
    AFX_DOCK_METHOD dockMethod,
    LPRECT lpRect = NULL);
```

### <a name="parameters"></a>パラメーター

|||
|-|-|
|パラメーター|説明|
|*Pwnd*|[in]フレームワークがドッキングするペイン。|
|*ドックメソッド*|[in]ペインのドッキング オプション。|
|*Lprect*|[in]ドッキングペインの境界を指定する四角形。|

### <a name="remarks"></a>解説

既定の実装では、将来使用するために用意されているパラメーター *dockMethod*は使用されません。

*lpRect*が NULL の場合、フレームワークは、ドッキング サイトの既定の場所にペインを配置します。 ドッキング サイトが水平である場合、既定の位置はドッキング サイトの左端にあります。 それ以外の場合、既定の場所は、ドッキング サイトの上部にあります。

## <a name="cautohidedocksitegetalignrect"></a><a name="getalignrect"></a>を取得します。

ドッキング サイトのサイズを画面座標で取得します。

```cpp
void GetAlignRect(CRect& rect) const;
```

### <a name="parameters"></a>パラメーター

|||
|-|-|
|パラメーター|説明|
|*Rect*|[in]四角形への参照。 このメソッドは、ドッキング サイトのサイズをこの四角形に格納します。|

### <a name="remarks"></a>解説

四角形はオフセットマージンに合わせて調整され、含まれないようにします。

## <a name="cautohidedocksitem_nextraspace"></a><a name="m_nextraspace"></a>C オートハイドドックサイト::m_nExtraSpace

[CAutoHideDockSite クラス](../../mfc/reference/cautohidedocksite-class.md)の端と[CMFCAutoHideBar クラスの間](../../mfc/reference/cmfcautohidebar-class.md)のスペースのサイズです。

```
static int m_nExtraSpace;
```

### <a name="remarks"></a>解説

に`CMFCAutoHideBar`ドッキングされている場合、`CAutoHideDockSite`は、ドッキング サイト全体を占有しないでください。 このグローバル変数は、左または上の境界`CMFCAutoHideBar`と対応する`CAutoHideDockSite`エッジの間の余分なスペースを制御します。 上端または左端のどちらを使用するかは、現在の配置によって異なります。

## <a name="cautohidedocksitesetoffsetleft"></a><a name="setoffsetleft"></a>C オートハイドドックサイト::オフセット左

ドッキング バーの左側の余白を設定します。

```cpp
void SetOffsetLeft(int nOffset);
```

### <a name="parameters"></a>パラメーター

*オフセット*<br/>
[in]新しいオフセット。

### <a name="remarks"></a>解説

[CMFCAutoHideBar](../../mfc/reference/cmfcautohidebar-class.md)オブジェクトは、オブジェクト上に`CAutoHideDockSite`静的に配置されます。 つまり、ユーザーはオブジェクトの`CMFCAutoHideBar`場所を手動で変更できません。 この`SetOffsetLeft`メソッドは、左端`CMFCAutoHideBar`の左側と左端の間の間隔を制御します`CAutoHideDockSite`。

## <a name="cautohidedocksitesetoffsetright"></a><a name="setoffsetright"></a>C オートハイドドックサイト::オフセット右

ドッキング バーの右側に余白を設定します。

```cpp
void SetOffsetRight(int nOffset);
```

### <a name="parameters"></a>パラメーター

*オフセット*<br/>
[in]新しいオフセット。

### <a name="remarks"></a>解説

[CMFCAutoHideBar](../../mfc/reference/cmfcautohidebar-class.md)オブジェクトは、オブジェクト上に`CAutoHideDockSite`静的に配置されます。 つまり、ユーザーは`CMFCAutoHideBar`オブジェクトの場所を手動で変更できません。 この`SetOffsetRight`メソッドは、右端`CMFCAutoHideBar`の右側と右側の間の間隔を制御します`CAutoHideDockSite`。

## <a name="cautohidedocksiterepositionpanes"></a><a name="repositionpanes"></a>C 自動ハイドドックサイト::ペインの位置変更

ペインを[再描画します](../../mfc/reference/cautohidedocksite-class.md)。

```
virtual void RepositionPanes(CRect& rectNewClientArea);
```

### <a name="parameters"></a>パラメーター

|||
|-|-|
|パラメーター|説明|
|*レクトニュークライアントエリア*|[in]予約値。|

### <a name="remarks"></a>解説

既定の実装では *、rectNewClientArea を*使用しません。 グローバル ツールバーの余白とボタンの間隔を使用してペインを再描画します。

## <a name="cautohidedocksiteunsetautohidemode"></a><a name="unsetautohidemode"></a>C 自動ハイドドックサイト::自動隠しモードを設定解除

ドッキング サイト上のオブジェクトに対[して CMFCAutoHideBar::UnSetAutoHideMode](../../mfc/reference/cmfcautohidebar-class.md#unsetautohidemode)を呼び出します。

```cpp
void UnSetAutoHideMode(CMFCAutoHideBar* pAutoHideToolbar);
```

### <a name="parameters"></a>パラメーター

|||
|-|-|
|パラメーター|説明|
|*閉じ込ツールバー*|[in]上にある[CMFCAutoHideBar](../../mfc/reference/cmfcautohidebar-class.md)オブジェクト ペインへのポインター `CAutoHideDockSite`。|

### <a name="remarks"></a>解説

このメソッドは *、pAutoHideToolbar*を含む行を検索します。 この場合`CMFCAutoHideBar.UnSetAutoHideMode`、その行`CMFCAutoHideBar`のすべてのオブジェクトが必要になります。 *pAutoHideToolbar*が見つからないか、NULL の場合、この`CMFCAutoHideBar.UnSetAutoHideMode`メソッド`CMFCAutoHideBar``CAutoHideDockSite`は、 .

## <a name="see-also"></a>関連項目

[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[クラス](../../mfc/reference/mfc-classes.md)<br/>
[CDockSite クラス](../../mfc/reference/cdocksite-class.md)

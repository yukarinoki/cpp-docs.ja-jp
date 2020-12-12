---
description: '詳細情報: CAutoHideDockSite クラス'
title: CAutoHideDockSite クラス
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
ms.openlocfilehash: 00ac5224d559f84378bd87bd9abe56756a6f4d97
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97261282"
---
# <a name="cautohidedocksite-class"></a>CAutoHideDockSite クラス

は `CAutoHideDockSite` [CDockSite クラス](../../mfc/reference/cdocksite-class.md) を拡張して、自動非表示のドッキングペインを実装します。

## <a name="syntax"></a>構文

```
class CAutoHideDockSite : public CDockSite
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

| 名前 | 説明 |
|-|-|
|名前|説明|
|`CAutoHideDockSite::CAutoHideDockSite`|`CAutoHideDockSite` オブジェクトを構築します。|
|`CAutoHideDockSite::~CAutoHideDockSite`|デストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

| 名前 | 説明 |
|-|-|
|名前|説明|
|`CAutoHideDockSite::AllowShowOnPaneMenu`|がペインメニューに表示されるかどうかを示し `CAutoHideDockSite` ます。|
|[CAutoHideDockSite:: CanAcceptPane](#canacceptpane)|基本ペインオブジェクトが [Cmfcautohidebar クラス](../../mfc/reference/cmfcautohidebar-class.md)から派生したものかどうかを判断します。|
|[CAutoHideDockSite::D ockPane](#dockpane)|このオブジェクトにペインをドッキング `CAuotHideDockSite` します。|
|[CAutoHideDockSite:: GetAlignRect](#getalignrect)|ドックサイトのサイズを画面座標で取得します。|
|[CAutoHideDockSite:: RepositionPanes](#repositionpanes)|`CAutoHideDockSite`全体の余白とボタンの間隔を使用して、ペインを上に再描画します。|
|[CAutoHideDockSite:: SetOffsetLeft](#setoffsetleft)|ドッキングバーの左側に余白を設定します。|
|[CAutoHideDockSite:: SetOffsetRight](#setoffsetright)|ドッキングバーの右側に余白を設定します。|
|[CAutoHideDockSite:: UnSetAutoHideMode](#unsetautohidemode)|のオブジェクトに対して [Cmfcautohidebar:: UnSetAutoHideMode](../../mfc/reference/cmfcautohidebar-class.md#unsetautohidemode) を呼び出し `CAutoHideDockSite` ます。|

### <a name="data-members"></a>データ メンバー

| 名前 | 説明 |
|-|-|
|名前|説明|
|[CAutoHideDockSite:: m_nExtraSpace](#m_nextraspace)|ツールバーとドッキングバーの端との間のスペースのサイズを定義します。 この領域は、ドッキング領域の配置に応じて左端または上端から測定されます。|

## <a name="remarks"></a>解説

[CFrameWndEx:: EnableAutoHidePanes](../../mfc/reference/cframewndex-class.md#enableautohidepanes)を呼び出すと、フレームワークによってオブジェクトが自動的に作成さ `CAutoHideDockSite` れます。 ほとんどの場合、このクラスを直接インスタンス化または使用する必要はありません。

ドッキングバーは、dock ペインの左側と [Cmfcautohidebutton クラス](../../mfc/reference/cmfcautohidebutton-class.md)の左側との間の間隔です。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CBasePane](../../mfc/reference/cbasepane-class.md)

[CDockSite](../../mfc/reference/cdocksite-class.md)

## <a name="example"></a>例

次の例は、オブジェクトからオブジェクトを取得する方法 `CAutoHideDockSite` `CMFCAutoHideBar` と、ドッキングバーの左右の余白を設定する方法を示しています。

[!code-cpp[NVC_MFC_RibbonApp#29](../../mfc/reference/codesnippet/cpp/cautohidedocksite-class_1.cpp)]

## <a name="requirements"></a>要件

**ヘッダー:** afxautohidedocksite

## <a name="cautohidedocksitecanacceptpane"></a><a name="canacceptpane"></a> CAutoHideDockSite:: CanAcceptPane

基本ペインが [Cmfcautohidebar](../../mfc/reference/cmfcautohidebar-class.md) オブジェクトであるか、またはから派生しているかを判断し `CMFCAutoHideBar` ます。

```
virtual BOOL CanAcceptPane(const CBasePane* pBar) const;
```

### <a name="parameters"></a>パラメーター

*pBar*\
からフレームワークによってテストされる基本ペイン。

### <a name="return-value"></a>戻り値

*Pbar* がから派生している場合は TRUE `CMFCAutoHideBar` 。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

基本ペインオブジェクトがから派生している場合は、 `CMFCAutoHideBar` を含めることができ `CAutoHideDockSite` ます。

## <a name="cautohidedocksitedockpane"></a><a name="dockpane"></a> CAutoHideDockSite::D ockPane

この [CAutoHideDockSite](../../mfc/reference/cautohidedocksite-class.md) オブジェクトにペインをドッキングします。

```
virtual void DockPane(
    CPane* pWnd,
    AFX_DOCK_METHOD dockMethod,
    LPRECT lpRect = NULL);
```

### <a name="parameters"></a>パラメーター

*pWnd*\
からフレームワークがドッキングするウィンドウ。

*dockMethod*\
からペインのドッキングオプション。

*lpRect*\
からドッキングされたペインの境界を指定する四角形。

### <a name="remarks"></a>解説

既定の実装では、パラメーター *dockMethod* は使用されません。このパラメーターは将来使用するために用意されています。

*LpRect* が NULL の場合、フレームワークはペインをドッキングサイトの既定の場所に配置します。 Dock サイトが横方向の場合、既定の場所は dock サイトの左端にあります。 それ以外の場合、既定の場所は dock サイトの上部にあります。

## <a name="cautohidedocksitegetalignrect"></a><a name="getalignrect"></a> CAutoHideDockSite:: GetAlignRect

ドックサイトのサイズを画面座標で取得します。

```cpp
void GetAlignRect(CRect& rect) const;
```

### <a name="parameters"></a>パラメーター

*rect*\
から四角形への参照。 メソッドは、この四角形にドッキングサイトのサイズを格納します。

### <a name="remarks"></a>解説

四角形は、余白が含まれないように調整されます。

## <a name="cautohidedocksitem_nextraspace"></a><a name="m_nextraspace"></a> CAutoHideDockSite:: m_nExtraSpace

[CAutoHideDockSite クラス](../../mfc/reference/cautohidedocksite-class.md)の端と[Cmfcautohidebar クラス](../../mfc/reference/cmfcautohidebar-class.md)オブジェクトとの間のスペースのサイズ。

```
static int m_nExtraSpace;
```

### <a name="remarks"></a>解説

`CMFCAutoHideBar`がにドッキングされている場合 `CAutoHideDockSite` 、dock サイト全体を占有することはできません。 このグローバル変数は、の左または上の境界線と、対応するエッジとの間の余分なスペースを制御し `CMFCAutoHideBar` `CAutoHideDockSite` ます。 上端と左端のどちらを使用するかは、現在の配置によって異なります。

## <a name="cautohidedocksitesetoffsetleft"></a><a name="setoffsetleft"></a> CAutoHideDockSite:: SetOffsetLeft

ドッキングバーの左側に余白を設定します。

```cpp
void SetOffsetLeft(int nOffset);
```

### <a name="parameters"></a>パラメーター

*nOffset*<br/>
から新しいオフセット。

### <a name="remarks"></a>解説

[Cmfcautohidebar](../../mfc/reference/cmfcautohidebar-class.md) オブジェクトは、オブジェクトに静的に配置され `CAutoHideDockSite` ます。 これは、ユーザーがオブジェクトの場所を手動で変更できないことを意味し `CMFCAutoHideBar` ます。 `SetOffsetLeft`メソッドは、の左端と左側の間の間隔を制御し `CMFCAutoHideBar` `CAutoHideDockSite` ます。

## <a name="cautohidedocksitesetoffsetright"></a><a name="setoffsetright"></a> CAutoHideDockSite:: SetOffsetRight

ドッキングバーの右側に余白を設定します。

```cpp
void SetOffsetRight(int nOffset);
```

### <a name="parameters"></a>パラメーター

*nOffset*<br/>
から新しいオフセット。

### <a name="remarks"></a>解説

[Cmfcautohidebar](../../mfc/reference/cmfcautohidebar-class.md) オブジェクトは、オブジェクトに静的に配置され `CAutoHideDockSite` ます。 これは、ユーザーがオブジェクトの場所を手動で変更できないことを意味し `CMFCAutoHideBar` ます。 メソッドは、の右端 `SetOffsetRight` と右端の間の間隔を制御し `CMFCAutoHideBar` `CAutoHideDockSite` ます。

## <a name="cautohidedocksiterepositionpanes"></a><a name="repositionpanes"></a> CAutoHideDockSite:: RepositionPanes

[CAutoHideDockSite](../../mfc/reference/cautohidedocksite-class.md)のペインを再描画します。

```
virtual void RepositionPanes(CRect& rectNewClientArea);
```

### <a name="parameters"></a>パラメーター

*rectNewClientArea*\
から予約済みの値。

### <a name="remarks"></a>解説

既定の実装では、 *rectNewClientArea* は使用されません。 グローバルツールバーの余白とボタンの間隔を使用して、ウィンドウを再描画します。

## <a name="cautohidedocksiteunsetautohidemode"></a><a name="unsetautohidemode"></a> CAutoHideDockSite:: UnSetAutoHideMode

Dock サイトのオブジェクトに対して [Cmfcautohidebar:: UnSetAutoHideMode](../../mfc/reference/cmfcautohidebar-class.md#unsetautohidemode) を呼び出します。

```cpp
void UnSetAutoHideMode(CMFCAutoHideBar* pAutoHideToolbar);
```

### <a name="parameters"></a>パラメーター

*pAutoHideToolbar*\
からにある [Cmfcautohidebar](../../mfc/reference/cmfcautohidebar-class.md) オブジェクトペインへのポインター `CAutoHideDockSite` 。

### <a name="remarks"></a>解説

このメソッドは、 *Pautohidetoolbar* を含む行を検索します。 このメソッドは `CMFCAutoHideBar.UnSetAutoHideMode` 、 `CMFCAutoHideBar` その行のすべてのオブジェクトを呼び出します。 *Pautohidetoolbar* が見つからないか、NULL の場合、このメソッドはの `CMFCAutoHideBar.UnSetAutoHideMode` すべてのオブジェクトに対してを呼び出し `CMFCAutoHideBar` `CAutoHideDockSite` ます。

## <a name="see-also"></a>関連項目

[階層図](../../mfc/hierarchy-chart.md)<br/>
[Classes](../../mfc/reference/mfc-classes.md)<br/>
[CDockSite クラス](../../mfc/reference/cdocksite-class.md)

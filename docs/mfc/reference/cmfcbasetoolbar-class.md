---
title: CMFCBaseToolBar クラス
ms.date: 11/04/2016
f1_keywords:
- CMFCBaseToolBar
- AFXBASETOOLBAR/CMFCBaseToolBar
- AFXBASETOOLBAR/CMFCBaseToolBar::GetDockingMode
- AFXBASETOOLBAR/CMFCBaseToolBar::GetMinSize
- AFXBASETOOLBAR/CMFCBaseToolBar::OnAfterChangeParent
helpviewer_keywords:
- CMFCBaseToolBar [MFC], GetDockingMode
- CMFCBaseToolBar [MFC], GetMinSize
- CMFCBaseToolBar [MFC], OnAfterChangeParent
ms.assetid: 5d79206d-55e4-46f8-b1b8-042e34d7f9da
ms.openlocfilehash: 027fe8569ff133bb3f348c9d0607f19c6d778c4e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81367828"
---
# <a name="cmfcbasetoolbar-class"></a>CMFCBaseToolBar クラス

ツール バーの基本クラス。

## <a name="syntax"></a>構文

```
class CMFCBaseToolBar : public CPane
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|`CMFCBaseToolBar::CMFCBaseToolBar`|既定のコンストラクターです。|
|`CMFCBaseToolBar::~CMFCBaseToolBar`|デストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|`CMFCBaseToolBar::CreateObject`|このクラス型の動的インスタンスを作成するために、フレームワークで使用されます。|
|[コントロール バー::取得モード](#getdockingmode)|ドッキングのモードを返します。 (CBase ペインをオーバーライド[します::GetDockingMode](../../mfc/reference/cbasepane-class.md#getdockingmode).)|
|[コントロール バー::ゲットミンサイズ](#getminsize)|ツール バーの最小サイズを返します。 (CPane をオーバーライド[します。::GetMinSize](../../mfc/reference/cpane-class.md#getminsize).)|
|[コントロール バー::オンアフターチェンジペアレント](#onafterchangeparent)|ペインの親が変更された後に、フレームワークによって呼び出されます。 (CBase ペインをオーバーライド[します。::オンアフターチェンジ親](../../mfc/reference/cbasepane-class.md#onafterchangeparent).)|

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CBasePane](../../mfc/reference/cbasepane-class.md)

[CPane](../../mfc/reference/cpane-class.md)

[ツールバー](../../mfc/reference/cmfcbasetoolbar-class.md)

## <a name="requirements"></a>必要条件

**ヘッダー:** afxbase ツールバー.h

## <a name="cmfcbasetoolbargetdockingmode"></a><a name="getdockingmode"></a>コントロール バー::取得モード

ドッキングのモードを返します。

```
virtual AFX_DOCK_TYPE GetDockingMode() const;
```

### <a name="return-value"></a>戻り値

ドッキング モード。

## <a name="cmfcbasetoolbargetminsize"></a><a name="getminsize"></a>コントロール バー::ゲットミンサイズ

ツール バーの最小サイズを返します。

```
virtual void GetMinSize(CSize& size) const;
```

### <a name="parameters"></a>パラメーター

*サイズ*<br/>
[アウト]ツール バーの最小サイズ。

## <a name="cmfcbasetoolbaronafterchangeparent"></a><a name="onafterchangeparent"></a>コントロール バー::オンアフターチェンジペアレント

ペインの親が変更された後に、フレームワークによって呼び出されます。

```
virtual void OnAfterChangeParent(CWnd* pWndOldParent);
```

### <a name="parameters"></a>パラメーター

*親の子*<br/>
[in]前の親ウィンドウへのポインター。

## <a name="see-also"></a>関連項目

[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[クラス](../../mfc/reference/mfc-classes.md)

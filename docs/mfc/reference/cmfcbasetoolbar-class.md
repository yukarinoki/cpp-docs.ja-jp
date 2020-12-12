---
description: '詳細情報: CMFCBaseToolBar クラス'
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
ms.openlocfilehash: 37597e4cb300e0d6d16c92f105e332c18c5beda7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97247918"
---
# <a name="cmfcbasetoolbar-class"></a>CMFCBaseToolBar クラス

ツールバーの基本クラスです。

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
|[CMFCBaseToolBar:: Getdocによるモード](#getdockingmode)|ドッキングのモードを返します。 ( [Cbasepane:: GetDockingMode](../../mfc/reference/cbasepane-class.md#getdockingmode)をオーバーライドします)。|
|[CMFCBaseToolBar:: GetMinSize](#getminsize)|ツールバーの最小サイズを返します。 ( [CPane:: GetMinSize](../../mfc/reference/cpane-class.md#getminsize)をオーバーライドします。)|
|[CMFCBaseToolBar:: OnAfterChangeParent](#onafterchangeparent)|ペインの親が変更された後に、フレームワークによって呼び出されます。 ( [Cbasepane:: OnAfterChangeParent](../../mfc/reference/cbasepane-class.md#onafterchangeparent)をオーバーライドします)。|

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CBasePane](../../mfc/reference/cbasepane-class.md)

[CPane](../../mfc/reference/cpane-class.md)

[CMFCBaseToolBar](../../mfc/reference/cmfcbasetoolbar-class.md)

## <a name="requirements"></a>要件

**ヘッダー:** afxbasetoolbar

## <a name="cmfcbasetoolbargetdockingmode"></a><a name="getdockingmode"></a> CMFCBaseToolBar:: Getdocによるモード

ドッキングのモードを返します。

```
virtual AFX_DOCK_TYPE GetDockingMode() const;
```

### <a name="return-value"></a>戻り値

ドッキングモード。

## <a name="cmfcbasetoolbargetminsize"></a><a name="getminsize"></a> CMFCBaseToolBar:: GetMinSize

ツールバーの最小サイズを返します。

```
virtual void GetMinSize(CSize& size) const;
```

### <a name="parameters"></a>パラメーター

*size*<br/>
入出力ツールバーの最小サイズ。

## <a name="cmfcbasetoolbaronafterchangeparent"></a><a name="onafterchangeparent"></a> CMFCBaseToolBar:: OnAfterChangeParent

ペインの親が変更された後に、フレームワークによって呼び出されます。

```
virtual void OnAfterChangeParent(CWnd* pWndOldParent);
```

### <a name="parameters"></a>パラメーター

*pWndOldParent*<br/>
から前の親ウィンドウへのポインター。

## <a name="see-also"></a>関連項目

[階層図](../../mfc/hierarchy-chart.md)<br/>
[クラス](../../mfc/reference/mfc-classes.md)

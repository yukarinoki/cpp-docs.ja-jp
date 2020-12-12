---
description: '詳細情報: CDockablePaneAdapter クラス'
title: CDockablePaneAdapter クラス
ms.date: 11/04/2016
f1_keywords:
- CDockablePaneAdapter
- AFXDOCKABLEPANEADAPTER/CDockablePaneAdapter
- AFXDOCKABLEPANEADAPTER/CDockablePaneAdapter::GetWrappedWnd
- AFXDOCKABLEPANEADAPTER/CDockablePaneAdapter::LoadState
- AFXDOCKABLEPANEADAPTER/CDockablePaneAdapter::SaveState
- AFXDOCKABLEPANEADAPTER/CDockablePaneAdapter::SetWrappedWnd
helpviewer_keywords:
- CDockablePaneAdapter [MFC], GetWrappedWnd
- CDockablePaneAdapter [MFC], LoadState
- CDockablePaneAdapter [MFC], SaveState
- CDockablePaneAdapter [MFC], SetWrappedWnd
ms.assetid: 6ed6cf82-f39c-4d0c-bf7c-8641495cf8f3
ms.openlocfilehash: 0a46ef15d35194203d6e5c035555de0d80b63c72
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97185038"
---
# <a name="cdockablepaneadapter-class"></a>CDockablePaneAdapter クラス

`CWnd`の派生ペインのドッキングをサポートします。

## <a name="syntax"></a>構文

```
class CDockablePaneAdapter : public CDockablePane
```

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CDockablePaneAdapter:: GetWrappedWnd](#getwrappedwnd)|ラップされたウィンドウを返します。|
|[CDockablePaneAdapter::LoadState](#loadstate)|( [CDockablePane:: LoadState](cdockablepane-class.md#loadstate)をオーバーライドします。)|
|[CDockablePaneAdapter::SaveState](#savestate)|( [CDockablePane:: SaveState](cdockablepane-class.md)をオーバーライドします。)|
|[CDockablePaneAdapter::SetWrappedWnd](#setwrappedwnd)||

## <a name="remarks"></a>解説

通常、フレームワークは、 [CMFCBaseTabCtrl:: addtab](../../mfc/reference/cmfcbasetabctrl-class.md#addtab) メソッドまたは [CMFCBaseTabCtrl:: inserttab](../../mfc/reference/cmfcbasetabctrl-class.md#inserttab) メソッドを使用するときに、このクラスのオブジェクトをインスタンス化します。

動作をカスタマイズする場合は `CDockablePaneAdapter` 、そこから新しいクラスを派生させ、 [CMFCBaseTabCtrl:: SetDockingBarWrapperRTC](../../mfc/reference/cmfcbasetabctrl-class.md#setdockingbarwrapperrtc)を使用して、ランタイムクラス情報をタブ付きウィンドウに設定するだけです。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)\
└ &nbsp; [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)\
&nbsp;&nbsp;&nbsp;&nbsp;└ &nbsp; [CWnd](../../mfc/reference/cwnd-class.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;└ &nbsp; [Cbasepane](../../mfc/reference/cbasepane-class.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;└ &nbsp; [CPane](../../mfc/reference/cpane-class.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;└ &nbsp; [CDockablePane](../../mfc/reference/cdockablepane-class.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;└ &nbsp; [CDockablePaneAdapter](../../mfc/reference/cdockablepaneadapter-class.md)

## <a name="requirements"></a>要件

**ヘッダー:** afxDockablePaneAdapter

## <a name="cdockablepaneadaptergetwrappedwnd"></a><a name="getwrappedwnd"></a> CDockablePaneAdapter:: GetWrappedWnd

ドッキング可能なペインアダプターの基になるウィンドウを返します。

```
virtual CWnd* GetWrappedWnd() const;
```

### <a name="return-value"></a>戻り値

ラップされたウィンドウへのポインター。

### <a name="remarks"></a>解説

ラップされたウィンドウにアクセスするには、この関数を使用します。

## <a name="cdockablepaneadapterloadstate"></a><a name="loadstate"></a> CDockablePaneAdapter:: LoadState

レジストリからペインの状態を読み込みます。

```
virtual BOOL LoadState(
    LPCTSTR lpszProfileName = NULL,
    int nIndex = -1,
    UINT uiID = (UINT) -1);
```

### <a name="parameters"></a>パラメーター

*lpszProfileName*<br/>
からプロファイル名。

*nIndex*<br/>
からプロファイルインデックス。

*uiID*<br/>
からペイン ID。

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cdockablepaneadaptersavestate"></a><a name="savestate"></a> CDockablePaneAdapter:: SaveState

ペインの状態をレジストリに保存します。

```
virtual BOOL SaveState(
    LPCTSTR lpszProfileName = NULL,
    int nIndex = -1,
    UINT uiID = (UINT) -1);
```

### <a name="parameters"></a>パラメーター

*lpszProfileName*<br/>
からプロファイル名。

*nIndex*<br/>
からプロファイルのインデックス (既定ではウィンドウのコントロール ID に設定されます)。

*uiID*<br/>
からペイン ID。

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cdockablepaneadaptersetwrappedwnd"></a><a name="setwrappedwnd"></a> CDockablePaneAdapter:: SetWrappedWnd

ドッキング可能なペインアダプターの基になるウィンドウを設定します。

```
virtual BOOL SetWrappedWnd(CWnd* pWnd);
```

### <a name="parameters"></a>パラメーター

*pWnd*<br/>
からウィンドウに対してラップするウィンドウへのポインター。

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="see-also"></a>関連項目

[階層図](../../mfc/hierarchy-chart.md)<br/>
[Classes](../../mfc/reference/mfc-classes.md)<br/>
[CDockablePane クラス](../../mfc/reference/cdockablepane-class.md)

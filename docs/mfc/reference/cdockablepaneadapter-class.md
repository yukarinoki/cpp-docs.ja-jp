---
title: CDockablePaneAdapter クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CDockablePaneAdapter
- AFXDOCKABLEPANEADAPTER/CDockablePaneAdapter
- AFXDOCKABLEPANEADAPTER/CDockablePaneAdapter::GetWrappedWnd
- AFXDOCKABLEPANEADAPTER/CDockablePaneAdapter::LoadState
- AFXDOCKABLEPANEADAPTER/CDockablePaneAdapter::SaveState
- AFXDOCKABLEPANEADAPTER/CDockablePaneAdapter::SetWrappedWnd
dev_langs:
- C++
helpviewer_keywords:
- CDockablePaneAdapter [MFC], GetWrappedWnd
- CDockablePaneAdapter [MFC], LoadState
- CDockablePaneAdapter [MFC], SaveState
- CDockablePaneAdapter [MFC], SetWrappedWnd
ms.assetid: 6ed6cf82-f39c-4d0c-bf7c-8641495cf8f3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1cec0a5c40d7937e8df20b5437b6dcc83b1b9ec1
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46441177"
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
|[CDockablePaneAdapter::GetWrappedWnd](#getwrappedwnd)|ラップされたウィンドウを返します。|
|[CDockablePaneAdapter::LoadState](#loadstate)|(上書き[cdockablepane::loadstate](cdockablepane-class.md#loadstate))。|
|[CDockablePaneAdapter::SaveState](#savestate)|(上書き[cdockablepane::savestate](cdockablepane-class.md))。|
|[CDockablePaneAdapter::SetWrappedWnd](#setwrappedwnd)||

## <a name="remarks"></a>Remarks

通常、フレームワークでは使用すると、このクラスのオブジェクトがインスタンス化します、 [::addtab](../../mfc/reference/cmfcbasetabctrl-class.md#addtab)または[cmfcbasetabctrl::inserttab](../../mfc/reference/cmfcbasetabctrl-class.md#inserttab)メソッド。

カスタマイズする場合、`CDockablePaneAdapter`動作、そこから新しいクラスを派生して、ランタイム クラス情報を使用して、タブ付きウィンドウに設定だけ[cmfcbasetabctrl::setdockingbarwrapperrtc](../../mfc/reference/cmfcbasetabctrl-class.md#setdockingbarwrapperrtc)します。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md) [CCmdTarget](../../mfc/reference/ccmdtarget-class.md) [CWnd](../../mfc/reference/cwnd-class.md)

[CBasePane](../../mfc/reference/cbasepane-class.md) [CPane](../../mfc/reference/cpane-class.md) [CDockablePane](../../mfc/reference/cdockablepane-class.md)

[CDockablePaneAdapter](../../mfc/reference/cdockablepaneadapter-class.md)

## <a name="requirements"></a>要件

**ヘッダー:** afxDockablePaneAdapter.h

##  <a name="getwrappedwnd"></a>  CDockablePaneAdapter::GetWrappedWnd

ウィンドウのドッキング可能なアダプターの基になるウィンドウを返します。

```
virtual CWnd* GetWrappedWnd() const;
```

### <a name="return-value"></a>戻り値

ラップされたウィンドウへのポインター。

### <a name="remarks"></a>Remarks

ラップされたウィンドウにアクセスするのにには、この関数を使用します。

##  <a name="loadstate"></a>  CDockablePaneAdapter::LoadState

レジストリからペインの状態を読み込みます。

```
virtual BOOL LoadState(
    LPCTSTR lpszProfileName = NULL,
    int nIndex = -1,
    UINT uiID = (UINT) -1);
```

### <a name="parameters"></a>パラメーター

*lpszProfileName*<br/>
[in]プロファイルの名前。

*nIndex*<br/>
[in]プロファイルのインデックス。

*uiID*<br/>
[in]ペインの ID

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>Remarks

##  <a name="savestate"></a>  CDockablePaneAdapter::SaveState

レジストリにペインの状態を保存します。

```
virtual BOOL SaveState(
    LPCTSTR lpszProfileName = NULL,
    int nIndex = -1,
    UINT uiID = (UINT) -1);
```

### <a name="parameters"></a>パラメーター

*lpszProfileName*<br/>
[in]プロファイルの名前。

*nIndex*<br/>
[in]プロファイルのインデックス (既定値は、ウィンドウのコントロール ID)。

*uiID*<br/>
[in]ペインの ID

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>Remarks

##  <a name="setwrappedwnd"></a>  CDockablePaneAdapter::SetWrappedWnd

ウィンドウのドッキング可能なアダプターの基になるウィンドウを設定します。

```
virtual BOOL SetWrappedWnd(CWnd* pWnd);
```

### <a name="parameters"></a>パラメーター

*我が物*<br/>
[in]ラップするウィンドウのアダプターは、ウィンドウへのポインター。

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>コメント

## <a name="see-also"></a>関連項目

[階層図](../../mfc/hierarchy-chart.md)<br/>
[クラス](../../mfc/reference/mfc-classes.md)<br/>
[CDockablePane クラス](../../mfc/reference/cdockablepane-class.md)

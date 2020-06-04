---
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
ms.openlocfilehash: 2fbaf99e4cc9bcbecf1a94012713b34e986f7ecb
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81375592"
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
|[ウィンドウブルペインアダプター::ゲットラップウンド](#getwrappedwnd)|ラップされたウィンドウを返します。|
|[CDockablePaneAdapter::LoadState](#loadstate)|[(CDockable ペインをオーバーライドします。:ロードステート](cdockablepane-class.md#loadstate).)|
|[CDockablePaneAdapter::SaveState](#savestate)|[(CDockable ペインをオーバーライドします。:セーブステート](cdockablepane-class.md).)|
|[CDockablePaneAdapter::SetWrappedWnd](#setwrappedwnd)||

## <a name="remarks"></a>解説

通常、フレームワークは、[この](../../mfc/reference/cmfcbasetabctrl-class.md#addtab)クラスのオブジェクトをインスタンス化します。 [CMFCBaseTabCtrl::InsertTab](../../mfc/reference/cmfcbasetabctrl-class.md#inserttab)

`CDockablePaneAdapter`動作をカスタマイズする場合は、そのクラスから新しいクラスを派生させ[、CMFCBaseTabCtrl::SetDockingBarWrapperRTC](../../mfc/reference/cmfcbasetabctrl-class.md#setdockingbarwrapperrtc)を使用して、ランタイム クラス情報をタブ付きウィンドウに設定するだけです。

## <a name="inheritance-hierarchy"></a>継承階層

[Cobject](../../mfc/reference/cobject-class.md)\
└&nbsp;[CCmdターゲット](../../mfc/reference/ccmdtarget-class.md)\
&nbsp;&nbsp;&nbsp;&nbsp;└&nbsp;[CWnd](../../mfc/reference/cwnd-class.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;└&nbsp;[CBasePane](../../mfc/reference/cbasepane-class.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;└&nbsp;[CPane](../../mfc/reference/cpane-class.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;└&nbsp;[CDockable ペイン](../../mfc/reference/cdockablepane-class.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[└ CDockablePaneアダプター](../../mfc/reference/cdockablepaneadapter-class.md)

## <a name="requirements"></a>必要条件

**ヘッダー:** afxDockablePane アダプター.h

## <a name="cdockablepaneadaptergetwrappedwnd"></a><a name="getwrappedwnd"></a>ウィンドウブルペインアダプター::ゲットラップウンド

ドッキング可能ペイン アダプターの基になるウィンドウを返します。

```
virtual CWnd* GetWrappedWnd() const;
```

### <a name="return-value"></a>戻り値

ラップされたウィンドウへのポインター。

### <a name="remarks"></a>解説

ラップされたウィンドウにアクセスするには、この関数を使用します。

## <a name="cdockablepaneadapterloadstate"></a><a name="loadstate"></a>ウィンドウブルウィンドウアダプター::ロードステート

レジストリからペインの状態を読み込みます。

```
virtual BOOL LoadState(
    LPCTSTR lpszProfileName = NULL,
    int nIndex = -1,
    UINT uiID = (UINT) -1);
```

### <a name="parameters"></a>パラメーター

*名前を指定します。*<br/>
[in]プロファイル名。

*nIndex*<br/>
[in]プロファイル インデックス。

*Uiid*<br/>
[in]ペイン ID。

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cdockablepaneadaptersavestate"></a><a name="savestate"></a>ウィンドウブルウィンドウアダプター::セーブステート

ペインの状態をレジストリに保存します。

```
virtual BOOL SaveState(
    LPCTSTR lpszProfileName = NULL,
    int nIndex = -1,
    UINT uiID = (UINT) -1);
```

### <a name="parameters"></a>パラメーター

*名前を指定します。*<br/>
[in]プロファイル名。

*nIndex*<br/>
[in]プロファイルインデックス (デフォルトはウィンドウのコントロール ID です)。

*Uiid*<br/>
[in]ペイン ID。

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cdockablepaneadaptersetwrappedwnd"></a><a name="setwrappedwnd"></a>ウィンドウブルペインアダプター::セットラップウンド

ドッキング可能ペイン アダプターの基になるウィンドウを設定します。

```
virtual BOOL SetWrappedWnd(CWnd* pWnd);
```

### <a name="parameters"></a>パラメーター

*Pwnd*<br/>
[in]ラップするペイン アダプターのウィンドウへのポインター。

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="see-also"></a>関連項目

[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[クラス](../../mfc/reference/mfc-classes.md)<br/>
[CDockablePane クラス](../../mfc/reference/cdockablepane-class.md)

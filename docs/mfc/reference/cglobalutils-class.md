---
title: クラス
ms.date: 10/18/2018
f1_keywords:
- CGlobalUtils
- AFXGLOBALUTILS/CGlobalUtils
- AFXGLOBALUTILS/CGlobalUtils::AdjustRectToWorkArea
- AFXGLOBALUTILS/CGlobalUtils::CalcExpectedDockedRect
- AFXGLOBALUTILS/CGlobalUtils::CanBeAttached
- AFXGLOBALUTILS/CGlobalUtils::CanPaneBeInFloatingMultiPaneFrameWnd
- AFXGLOBALUTILS/CGlobalUtils::CheckAlignment
- AFXGLOBALUTILS/CGlobalUtils::CyFromString
- AFXGLOBALUTILS/CGlobalUtils::DecimalFromString
- AFXGLOBALUTILS/CGlobalUtils::FlipRect
- AFXGLOBALUTILS/CGlobalUtils::ForceAdjustLayout
- AFXGLOBALUTILS/CGlobalUtils::GetDockingManager
- AFXGLOBALUTILS/CGlobalUtils::GetOppositeAlignment
- AFXGLOBALUTILS/CGlobalUtils::GetPaneAndAlignFromPoint
- AFXGLOBALUTILS/CGlobalUtils::GetWndIcon
- AFXGLOBALUTILS/CGlobalUtils::SetNewParent
- AFXGLOBALUTILS/CGlobalUtils::StringFromCy
- AFXGLOBALUTILS/CGlobalUtils::StringFromDecimal
helpviewer_keywords:
- CGlobalUtils [MFC], AdjustRectToWorkArea
- CGlobalUtils [MFC], CalcExpectedDockedRect
- CGlobalUtils [MFC], CanBeAttached
- CGlobalUtils [MFC], CanPaneBeInFloatingMultiPaneFrameWnd
- CGlobalUtils [MFC], CheckAlignment
- CGlobalUtils [MFC], CyFromString
- CGlobalUtils [MFC], DecimalFromString
- CGlobalUtils [MFC], FlipRect
- CGlobalUtils [MFC], ForceAdjustLayout
- CGlobalUtils [MFC], GetDockingManager
- CGlobalUtils [MFC], GetOppositeAlignment
- CGlobalUtils [MFC], GetPaneAndAlignFromPoint
- CGlobalUtils [MFC], GetWndIcon
- CGlobalUtils [MFC], SetNewParent
- CGlobalUtils [MFC], StringFromCy
- CGlobalUtils [MFC], StringFromDecimal
ms.assetid: 2c5bd1a6-f80c-4e79-a476-b4ceebabfb2f
ms.openlocfilehash: 66c1663774076fcc4b62b766b1781efc8cc33c93
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81373723"
---
# <a name="cglobalutils-class"></a>クラス

詳細については、Visual Studio のインストールの**\\VC\\atlmfc\\src mfc**フォルダーにあるソース コードを参照してください。

## <a name="syntax"></a>構文

```
class CGlobalUtils
```

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CGlobalUtils::AdjustRectToWorkArea](#adjustrecttoworkarea)||
|[CGlobalUtils::CalcExpectedDockedRect](#calcexpecteddockedrect)||
|[CGlobalUtils::CanBeAttached](#canbeattached)||
|[CGlobalUtils::CanPaneBeInFloatingMultiPaneFrameWnd](#canpanebeinfloatingmultipaneframewnd)||
|[CGlobalUtils::CheckAlignment](#checkalignment)||
|[CGlobalUtils::CyFromString](#cyfromstring)||
|[CGlobalUtils::DecimalFromString](#decimalfromstring)||
|[CGlobalUtils::FlipRect](#fliprect)||
|[CGlobalUtils::ForceAdjustLayout](#forceadjustlayout)||
|[CGlobalUtils::GetDockingManager](#getdockingmanager)||
|[CGlobalUtils::GetOppositeAlignment](#getoppositealignment)||
|[CGlobalUtils::GetPaneAndAlignFromPoint](#getpaneandalignfrompoint)||
|[CGlobalUtils::GetWndIcon](#getwndicon)||
|[CGlobalUtils::SetNewParent](#setnewparent)||
|[CGlobalUtils::StringFromCy](#stringfromcy)||
|[CGlobalUtils::StringFromDecimal](#stringfromdecimal)||

## <a name="remarks"></a>解説

## <a name="inheritance-hierarchy"></a>継承階層

[CGlobalUtils](../../mfc/reference/cglobalutils-class.md)

## <a name="requirements"></a>必要条件

**ヘッダー:** afxglobalutils.h

## <a name="cglobalutilsadjustrecttoworkarea"></a><a name="adjustrecttoworkarea"></a>クリオルティバ::アジャストレックワークエリア

```
void AdjustRectToworkArea(
    CRect& rect,
    CRect* pRectDelta = NULL);
```

### <a name="parameters"></a>パラメーター

[イン、アウト]*レクト*<br/>
[in]*デルタ*<br/>

### <a name="remarks"></a>解説

## <a name="cglobalutilscalcexpecteddockedrect"></a><a name="calcexpecteddockedrect"></a>を切り出す

```
void CalcExpectedDockedRect(
    CPaneContainerManager& barContainerManager,
    CWnd* pWndTodock,
    CPoint ptMouse,
    CRect& rectResult,
    BOOL& bDrawTab,
    CDockablePane** ppTargetBar);
```

### <a name="parameters"></a>パラメーター

[in]*バーコンテナマネージャー*<br/>

[in]*pWndトドック*<br/>

[in]*ptマウス*<br/>

[アウト]*レクト結果*<br/>

[アウト]*タブを描く*<br/>

[アウト]*ターゲットバー*<br/>

### <a name="remarks"></a>解説

## <a name="cglobalutilscanbeattached"></a><a name="canbeattached"></a>コブ・エ・シブ

```
BOOL CanBeAttached(CWnd* pWnd) const;
```

### <a name="parameters"></a>パラメーター

[in]*pWnd*<br/>

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cglobalutilscanpanebeinfloatingmultipaneframewnd"></a><a name="canpanebeinfloatingmultipaneframewnd"></a>::缶パネベフローティングマルチペインフレームオーンド

```
BOOL CanPaneBeInFloatingMultiPaneFrameWnd(CWnd* pWnd) const;
```

### <a name="parameters"></a>パラメーター

[in]*pWnd*<br/>

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cglobalutilscheckalignment"></a><a name="checkalignment"></a>を選択します。

```
BOOL CheckAlignment(
    CPoint point,
    CBasePane* pBar,
    int nSensitivity,
    const CDockingManager* pDockManager,
    BOOL bOuterEdge,
    DWORD& dwAlignment,
    DWORD dwEnabledDockBars = CBRS_ALIGN_ANY,
    LPCRECT lpRectBounds = NULL) const;
```

### <a name="parameters"></a>パラメーター

[in]*ポイント*<br/>

[in]*pバー*<br/>

[in]*n感度*<br/>

[in]*をクリックします。*<br/>

[in]*ボターエッジ*<br/>

[アウト]*dw配置*<br/>

[in]*ドウイネーブルドックバー*<br/>

[in]*を指定します。*<br/>

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cglobalutilscyfromstring"></a><a name="cyfromstring"></a>文字列を使用します。

```
BOOL CyFromString(
    CY& cy,
    LPCTSTR psz);
```

### <a name="parameters"></a>パラメーター

[アウト]*サイ*<br/>

[in]*psz*<br/>

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cglobalutilsdecimalfromstring"></a><a name="decimalfromstring"></a>文字列から:D

```
BOOL DecimalFromString(
    DECIMAL& decimal,
    LPCTSTR psz);
```

### <a name="parameters"></a>パラメーター

[アウト]*10 進数*<br/>

[in]*psz*<br/>

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cglobalutilsfliprect"></a><a name="fliprect"></a>クリオレクト

```
void FlipRect(
    CRect& rect,
    int nDegrees);
```

### <a name="parameters"></a>パラメーター

[イン、アウト]*レクト*<br/>
[in]*n度*<br/>

### <a name="remarks"></a>解説

## <a name="cglobalutilsforceadjustlayout"></a><a name="forceadjustlayout"></a>を調整する

```
void ForceAdjustLayout(
    CDockingManager* pDockManager,
    BOOL bForce = FALSE,
    BOOL bForceInvisible = FALSE);
```

### <a name="parameters"></a>パラメーター

[イン、アウト]*をクリックします。*<br/>

[in]*bフォース*<br/>

[in]*bフォースインビジブル*<br/>

### <a name="remarks"></a>解説

## <a name="cglobalutilsgetdockingmanager"></a><a name="getdockingmanager"></a>を使用します。

```
CDockingManager* GetDockingManager(CWnd* pWnd);
```

### <a name="parameters"></a>パラメーター

[in]*pWnd*<br/>

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cglobalutilsgetoppositealignment"></a><a name="getoppositealignment"></a>コリオシティ::ゲット・アノメント・アライメント

```
DWORD GetOppositeAlignment(DWORD dwAlign);
```

### <a name="parameters"></a>パラメーター

[in]*dwAlign*<br/>

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cglobalutilsgetpaneandalignfrompoint"></a><a name="getpaneandalignfrompoint"></a>ポイントを取得します。

```
BOOL GetPaneAndAlignFromPoint(
    CPaneContainerManager& barContainerManager,
    CPoint pt,
    CDockablePane** ppTargetControlBar,
    DWORD& dwAlignment,
    BOOL& bTabArea,
    BOOL& bCaption);
```

### <a name="parameters"></a>パラメーター

[in]*バーコンテナマネージャー*<br/>

[in]*pt*<br/>

[アウト]*コントロール バー*<br/>

[アウト]*dw配置*<br/>

[アウト]*タブエリア*<br/>

[アウト]*bキャプション*<br/>

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cglobalutilsgetwndicon"></a><a name="getwndicon"></a>を見る

```
HICON GetWndIcon(CWnd* pWnd);
```

### <a name="parameters"></a>パラメーター

[in]*pWnd*<br/>

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cglobalutilssetnewparent"></a><a name="setnewparent"></a>を切り離します。

```
void SetNewParent(
    CObList& lstControlBars,
    CWnd* pNewParent,
    BOOL bCheckVisibility = TRUE);
```

### <a name="parameters"></a>パラメーター

[in]*コントロールバー*<br/>

[in]*親の親会社*<br/>

[in]*可視性を確認する*<br/>

### <a name="remarks"></a>解説

## <a name="cglobalutilsstringfromcy"></a><a name="stringfromcy"></a>文字列から

```
BOOL StringFromCy(
    CString& str,
    CY& cy);
```

### <a name="parameters"></a>パラメーター

[アウト]*str*<br/>

[in]*サイ*<br/>

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cglobalutilsstringfromdecimal"></a><a name="stringfromdecimal"></a>10 進数から文字列を取得します。

```
BOOL StringFromDecimal(
    CString& str,
    DECIMAL& decimal);
```

### <a name="parameters"></a>パラメーター

[アウト]*str*<br/>

[in]*10 進数*<br/>

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="see-also"></a>関連項目

[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[クラス](../../mfc/reference/mfc-classes.md)

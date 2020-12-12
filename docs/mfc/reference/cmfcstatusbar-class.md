---
description: '詳細情報: CMFCStatusBar クラス'
title: CMFCStatusBar クラス
ms.date: 11/19/2018
f1_keywords:
- CMFCStatusBar
- AFXSTATUSBAR/CMFCStatusBar
- AFXSTATUSBAR/CMFCStatusBar::CalcFixedLayout
- AFXSTATUSBAR/CMFCStatusBar::CommandToIndex
- AFXSTATUSBAR/CMFCStatusBar::Create
- AFXSTATUSBAR/CMFCStatusBar::CreateEx
- AFXSTATUSBAR/CMFCStatusBar::DoesAllowDynInsertBefore
- AFXSTATUSBAR/CMFCStatusBar::EnablePaneDoubleClick
- AFXSTATUSBAR/CMFCStatusBar::EnablePaneProgressBar
- AFXSTATUSBAR/CMFCStatusBar::GetCount
- AFXSTATUSBAR/CMFCStatusBar::GetDrawExtendedArea
- AFXSTATUSBAR/CMFCStatusBar::GetExtendedArea
- AFXSTATUSBAR/CMFCStatusBar::GetItemID
- AFXSTATUSBAR/CMFCStatusBar::GetItemRect
- AFXSTATUSBAR/CMFCStatusBar::GetPaneInfo
- AFXSTATUSBAR/CMFCStatusBar::GetPaneProgress
- AFXSTATUSBAR/CMFCStatusBar::GetPaneStyle
- AFXSTATUSBAR/CMFCStatusBar::GetPaneText
- AFXSTATUSBAR/CMFCStatusBar::GetPaneWidth
- AFXSTATUSBAR/CMFCStatusBar::GetTipText
- AFXSTATUSBAR/CMFCStatusBar::InvalidatePaneContent
- AFXSTATUSBAR/CMFCStatusBar::PreCreateWindow
- AFXSTATUSBAR/CMFCStatusBar::SetDrawExtendedArea
- AFXSTATUSBAR/CMFCStatusBar::SetIndicators
- AFXSTATUSBAR/CMFCStatusBar::SetPaneAnimation
- AFXSTATUSBAR/CMFCStatusBar::SetPaneBackgroundColor
- AFXSTATUSBAR/CMFCStatusBar::SetPaneIcon
- AFXSTATUSBAR/CMFCStatusBar::SetPaneInfo
- AFXSTATUSBAR/CMFCStatusBar::SetPaneProgress
- AFXSTATUSBAR/CMFCStatusBar::SetPaneStyle
- AFXSTATUSBAR/CMFCStatusBar::SetPaneText
- AFXSTATUSBAR/CMFCStatusBar::SetPaneTextColor
- AFXSTATUSBAR/CMFCStatusBar::SetPaneWidth
- AFXSTATUSBAR/CMFCStatusBar::SetTipText
- AFXSTATUSBAR/CMFCStatusBar::OnDrawPane
helpviewer_keywords:
- CMFCStatusBar [MFC], CalcFixedLayout
- CMFCStatusBar [MFC], CommandToIndex
- CMFCStatusBar [MFC], Create
- CMFCStatusBar [MFC], CreateEx
- CMFCStatusBar [MFC], DoesAllowDynInsertBefore
- CMFCStatusBar [MFC], EnablePaneDoubleClick
- CMFCStatusBar [MFC], EnablePaneProgressBar
- CMFCStatusBar [MFC], GetCount
- CMFCStatusBar [MFC], GetDrawExtendedArea
- CMFCStatusBar [MFC], GetExtendedArea
- CMFCStatusBar [MFC], GetItemID
- CMFCStatusBar [MFC], GetItemRect
- CMFCStatusBar [MFC], GetPaneInfo
- CMFCStatusBar [MFC], GetPaneProgress
- CMFCStatusBar [MFC], GetPaneStyle
- CMFCStatusBar [MFC], GetPaneText
- CMFCStatusBar [MFC], GetPaneWidth
- CMFCStatusBar [MFC], GetTipText
- CMFCStatusBar [MFC], InvalidatePaneContent
- CMFCStatusBar [MFC], PreCreateWindow
- CMFCStatusBar [MFC], SetDrawExtendedArea
- CMFCStatusBar [MFC], SetIndicators
- CMFCStatusBar [MFC], SetPaneAnimation
- CMFCStatusBar [MFC], SetPaneBackgroundColor
- CMFCStatusBar [MFC], SetPaneIcon
- CMFCStatusBar [MFC], SetPaneInfo
- CMFCStatusBar [MFC], SetPaneProgress
- CMFCStatusBar [MFC], SetPaneStyle
- CMFCStatusBar [MFC], SetPaneText
- CMFCStatusBar [MFC], SetPaneTextColor
- CMFCStatusBar [MFC], SetPaneWidth
- CMFCStatusBar [MFC], SetTipText
- CMFCStatusBar [MFC], OnDrawPane
ms.assetid: f2960d1d-f4ed-41e8-bd99-0382b2f8d88e
ms.openlocfilehash: 79ba7c749a73406893173d7486fd5df208a37b83
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97307081"
---
# <a name="cmfcstatusbar-class"></a>CMFCStatusBar クラス

クラスは、 `CMFCStatusBar` クラスに似たステータスバーを実装し `CStatusBar` ます。 ただし、`CMFCStatusBar` クラスには、イメージ、アニメーション、およびプログレス バーを表示する機能や、マウスのダブルクリックに応答する機能など、`CStatusBar` クラスでは提供されない機能が含まれています。

詳細については、Visual Studio のインストールの **VC \\ atlmfc \\ src \\ mfc** フォルダーにあるソースコードを参照してください。

## <a name="syntax"></a>構文

```
class CMFCStatusBar : public CPane
```

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CMFCStatusBar:: CalcFixedLayout](#calcfixedlayout)|( [Cbasepane:: CalcFixedLayout](../../mfc/reference/cbasepane-class.md#calcfixedlayout)をオーバーライドします)。|
|[CMFCStatusBar:: CommandToIndex](#commandtoindex)||
|[CMFCStatusBar:: Create](#create)|コントロールバーを作成し、 [CPane](../../mfc/reference/cpane-class.md) オブジェクトにアタッチします。 ( [CPane:: Create](../../mfc/reference/cpane-class.md#create)をオーバーライドします)。|
|[CMFCStatusBar:: CreateEx](#createex)|コントロールバーを作成し、 [CPane](../../mfc/reference/cpane-class.md) オブジェクトにアタッチします。 ( [CPane:: CreateEx](../../mfc/reference/cpane-class.md#createex)をオーバーライドします。)|
|[CMFCStatusBar::D oesAllowDynInsertBefore](#doesallowdyninsertbefore)|このペインと親フレームの間に別のペインを動的に挿入できるかどうかを決定します。 ( [Cbasepane::D oesallowdyninsertbefore](../../mfc/reference/cbasepane-class.md#doesallowdyninsertbefore)をオーバーライドします)。|
|[CMFCStatusBar:: EnablePaneDoubleClick](#enablepanedoubleclick)|ステータスバーでのマウスのダブルクリックの処理を有効または無効にします。|
|[CMFCStatusBar:: Enable Progressbar](#enablepaneprogressbar)|指定したペインにプログレスバーを表示します。|
|[CMFCStatusBar:: GetCount](#getcount)|ステータスバーのウィンドウの数を返します。|
|[CMFCStatusBar:: GetDrawExtendedArea](#getdrawextendedarea)||
|[CMFCStatusBar:: GetExtendedArea](#getextendedarea)||
|[CMFCStatusBar:: GetItemID](#getitemid)||
|[CMFCStatusBar:: GetItemRect](#getitemrect)||
|[CMFCStatusBar:: Get Info](#getpaneinfo)||
|[CMFCStatusBar:: Get Progress](#getpaneprogress)||
|[CMFCStatusBar:: Get Style](#getpanestyle)|ペインのスタイルを返します。 ( [Cbasepane:: Getpane style](../../mfc/reference/cbasepane-class.md#getpanestyle)をオーバーライドします)。|
|[CMFCStatusBar:: Getて Text](#getpanetext)||
|[CMFCStatusBar:: Get Width](#getpanewidth)|ステータスバーの指定されたペインの幅 (ピクセル単位) を返します。|
|[CMFCStatusBar:: GetTipText](#gettiptext)|ステータスバーの指定されたペインのツールヒントテキストを返します。|
|[CMFCStatusBar:: InvalidatePaneContent](#invalidatepanecontent)|指定されたペインを無効にし、そのコンテンツを再描画します。|
|[CMFCStatusBar::P reCreateWindow](#precreatewindow)|このオブジェクトに関連付けられた Windows ウィンドウを作成する前に、フレームワークによって呼び出され `CWnd` ます。 ( [CWnd::P recreatewindow](../../mfc/reference/cwnd-class.md#precreatewindow)をオーバーライドします)。|
|[CMFCStatusBar:: SetDrawExtendedArea](#setdrawextendedarea)||
|[CMFCStatusBar:: SetIndicators](#setindicators)||
|[CMFCStatusBar:: Setて Animation](#setpaneanimation)|指定したペインにアニメーションを割り当てます。|
|[CMFCStatusBar:: Set区画 Backgroundcolor](#setpanebackgroundcolor)|ステータスバーの指定したペインの背景色を設定します。|
|[CMFCStatusBar:: Set区画アイコン](#setpaneicon)|ステータスバーの指定したペインのインジケーターアイコンを設定します。|
|[CMFCStatusBar:: Setて Info](#setpaneinfo)||
|[CMFCStatusBar:: Set Progress](#setpaneprogress)|ステータスバーの指定したペインの進行状況バーの現在の進行状況を設定します。|
|[CMFCStatusBar:: Setて Style](#setpanestyle)|ペインのスタイルを設定します。 ( [Cbasepane:: Setpane style](../../mfc/reference/cbasepane-class.md#setpanestyle)をオーバーライドします)。|
|[CMFCStatusBar:: Setて Text](#setpanetext)||
|[CMFCStatusBar:: SetPaneTextColor](#setpanetextcolor)|ステータスバーの指定したペインのテキストの色を設定します。|
|[CMFCStatusBar:: Set区画の幅](#setpanewidth)|ステータスバーの指定したペインの幅をピクセル単位で設定します。|
|[CMFCStatusBar:: SetTipText](#settiptext)|ステータスバーの指定したペインにツールヒントテキストを設定します。|

### <a name="protected-methods"></a>プロテクト メソッド

|名前|説明|
|----------|-----------------|
|[CMFCStatusBar:: OnDrawPane](#ondrawpane)|ステータスバーのペインを再描画するときに、フレームワークによって呼び出されます。|

## <a name="remarks"></a>解説

次の図は、 [ステータスバーのデモサンプル](../../overview/visual-cpp-samples.md) アプリケーションのステータスバーの図を示しています。

![CMFCStatusBar の例](../../mfc/reference/media/cmfcstatusbar.png "CMFCStatusBar の例")

## <a name="examples"></a>例

次の例は、アプリケーションがクラス内のさまざまなメソッドを呼び出すために使用するローカル変数を示して `CMFCStatusBar` います。 これらの変数は、StatusBarDemoView で宣言されています。 メインフレームは Mainfrm.cpp で宣言され、ドキュメントは StatusBarDemoDoc で宣言され、ビューは StatusBarDemoView で宣言されます。 このコードスニペットは、 [ステータスバーのデモサンプル](../../overview/visual-cpp-samples.md)に含まれています。

[!code-cpp[NVC_MFC_StatusBarDemo#9](../../mfc/reference/codesnippet/cpp/cmfcstatusbar-class_1.h)]

次の例は、 `CMFCStatusBar` mainfrm.cpp にメソッドを導入し、 `GetStatusBar` StatusBarDemoView のメソッドからこのメソッドを呼び出すことによって、オブジェクトへの参照を取得する方法を示しています。 `GetStatusBar` このコードスニペットは、 [ステータスバーのデモサンプル](../../overview/visual-cpp-samples.md)に含まれています。

[!code-cpp[NVC_MFC_StatusBarDemo#7](../../mfc/reference/codesnippet/cpp/cmfcstatusbar-class_2.h)]
[!code-cpp[NVC_MFC_StatusBarDemo#8](../../mfc/reference/codesnippet/cpp/cmfcstatusbar-class_3.h)]

次の例は、StatusBarDemoView でクラスのさまざまなメソッドを呼び出す方法を示して `CMFCStatusBar` います。 定数は、Mainfrm.cpp で宣言されています。 この例では、アイコンを設定する方法、ステータスバーペインのツールヒントテキストを設定する方法、指定したウィンドウに進行状況バーを表示する方法、指定したペインにアニメーションを割り当てる方法、ステータスバーペインのテキストと幅を設定する方法、ステータスバーペインの進行状況バーの現在の進行状況インジケーターを設定する方法を示します。 このコードスニペットは、 [ステータスバーのデモサンプル](../../overview/visual-cpp-samples.md)に含まれています。

[!code-cpp[NVC_MFC_StatusBarDemo#6](../../mfc/reference/codesnippet/cpp/cmfcstatusbar-class_4.h)]
[!code-cpp[NVC_MFC_StatusBarDemo#1](../../mfc/reference/codesnippet/cpp/cmfcstatusbar-class_5.cpp)]
[!code-cpp[NVC_MFC_StatusBarDemo#2](../../mfc/reference/codesnippet/cpp/cmfcstatusbar-class_6.cpp)]
[!code-cpp[NVC_MFC_StatusBarDemo#3](../../mfc/reference/codesnippet/cpp/cmfcstatusbar-class_7.cpp)]
[!code-cpp[NVC_MFC_StatusBarDemo#4](../../mfc/reference/codesnippet/cpp/cmfcstatusbar-class_8.cpp)]
[!code-cpp[NVC_MFC_StatusBarDemo#5](../../mfc/reference/codesnippet/cpp/cmfcstatusbar-class_9.cpp)]

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CBasePane](../../mfc/reference/cbasepane-class.md)

[CPane](../../mfc/reference/cpane-class.md)

[CMFCStatusBar](../../mfc/reference/cmfcstatusbar-class.md)

## <a name="requirements"></a>要件

**ヘッダー:** afxstatusbar

## <a name="cmfcstatusbarcalcfixedlayout"></a><a name="calcfixedlayout"></a> CMFCStatusBar:: CalcFixedLayout

```
virtual CSize CalcFixedLayout(
    BOOL bStretch,
    BOOL bHorz);
```

### <a name="parameters"></a>パラメーター

から *Bstretch*<br/>
から *bHorz*<br/>

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cmfcstatusbarcommandtoindex"></a><a name="commandtoindex"></a> CMFCStatusBar:: CommandToIndex

```
int CommandToIndex(UINT nIDFind) const;
```

### <a name="parameters"></a>パラメーター

から *nIDFind*<br/>

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cmfcstatusbarcreate"></a><a name="create"></a> CMFCStatusBar:: Create

```
BOOL Create(
    CWnd* pParentWnd,
    DWORD dwStyle = WS_CHILD | WS_VISIBLE | CBRS_BOTTOM,
    UINT nID = AFX_IDW_STATUS_BAR);
```

### <a name="parameters"></a>パラメーター

から *pParentWnd*<br/>
から *dwStyle*<br/>
から *nID*<br/>

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cmfcstatusbarcreateex"></a><a name="createex"></a> CMFCStatusBar:: CreateEx

```
BOOL CreateEx(
    CWnd* pParentWnd,
    DWORD dwCtrlStyle = 0,
    DWORD dwStyle = WS_CHILD | WS_VISIBLE | CBRS_BOTTOM,
    UINT nID = AFX_IDW_STATUS_BAR);
```

### <a name="parameters"></a>パラメーター

から *pParentWnd*<br/>
から *dwCtrlStyle*<br/>
から *dwStyle*<br/>
から *nID*<br/>

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cmfcstatusbardoesallowdyninsertbefore"></a><a name="doesallowdyninsertbefore"></a> CMFCStatusBar::D oesAllowDynInsertBefore

```
virtual BOOL DoesAllowDynInsertBefore() const;
```

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cmfcstatusbarenablepanedoubleclick"></a><a name="enablepanedoubleclick"></a> CMFCStatusBar:: EnablePaneDoubleClick

ステータスバーでのマウスのダブルクリックの処理を有効または無効にします。

```cpp
void EnablePaneDoubleClick(BOOL bEnable=TRUE);
```

### <a name="parameters"></a>パラメーター

*bEnable*<br/>
からTRUE の場合は、マウスのダブルクリックの処理を有効にします。 それ以外の場合は、マウスのダブルクリックの処理を無効にします。

### <a name="remarks"></a>解説

ステータスバーでダブルクリックの処理が有効になっている場合、ユーザーがステータスバーペインをダブルクリックするたびに、Windows によって、WM_COMMAND 通知がリソース ID と共にステータスバーの所有者に送信されます。

## <a name="cmfcstatusbarenablepaneprogressbar"></a><a name="enablepaneprogressbar"></a> CMFCStatusBar:: Enable Progressbar

指定されたウィンドウに進行状況バーを表示します。

```cpp
void EnablePaneProgressBar(
    int nIndex,
    long nTotal=100,
    BOOL bDisplayText=FALSE,
    COLORREF clrBar=-1,
    COLORREF clrBarDest=-1,
    COLORREF clrProgressText=-1);
```

### <a name="parameters"></a>パラメーター

*nIndex*<br/>
からプログレスバーを有効にするペインのインデックスを指定します。

*nTotal*<br/>
からプログレスバーの最大値を指定します。

*bDisplayText テキスト*<br/>
からプログレスバーに現在の進行状況の値を表示するかどうかを指定します。

*clrBar*<br/>
からプログレスバーの背景色を指定します。

*clrBarDest*<br/>
からプログレスバーの背景の2番目の色を指定します。 グラデーションにブレンドする色で塗りつぶすには、 *Clrbar* とは異なる値を使用します。

*clrProgressText*<br/>
からプログレスバーのテキストの色を指定します。

### <a name="remarks"></a>解説

`EnablePaneProgressBar` *Ntotal* が-1 に設定された進行状況バーの呼び出しを無効にする場合。 既定では、 *Ntotal* は100に設定されています。 そのため、進行状況をパーセンテージとして表示するための追加の計算は必要ありません。

状態バーの背景色にグラデーションの色が表示されるように、 *clrbar* と *clrbardest* に異なる値を渡す必要があります。 .

現在の進行状況を設定するには、 [CMFCStatusBar:: Setて progress](#setpaneprogress) メソッドを呼び出します。

## <a name="cmfcstatusbargetcount"></a><a name="getcount"></a> CMFCStatusBar:: GetCount

ステータスバーのウィンドウの数を取得します。

```
int GetCount() const;
```

### <a name="return-value"></a>戻り値

ステータスバーのウィンドウの数。

## <a name="cmfcstatusbargetdrawextendedarea"></a><a name="getdrawextendedarea"></a> CMFCStatusBar:: GetDrawExtendedArea

```
BOOL GetDrawExtendedArea() const;
```

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cmfcstatusbargetextendedarea"></a><a name="getextendedarea"></a> CMFCStatusBar:: GetExtendedArea

```
virtual BOOL GetExtendedArea(CRect& rect) const;
```

### <a name="parameters"></a>パラメーター

から *rect*<br/>

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cmfcstatusbargetitemid"></a><a name="getitemid"></a> CMFCStatusBar:: GetItemID

```
UINT GetItemID(int nIndex) const;
```

### <a name="parameters"></a>パラメーター

から *nIndex*<br/>

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cmfcstatusbargetitemrect"></a><a name="getitemrect"></a> CMFCStatusBar:: GetItemRect

```cpp
void GetItemRect(
    int nIndex,
    LPRECT lpRect) const;
```

### <a name="parameters"></a>パラメーター

から *nIndex*<br/>
から *lpRect*<br/>

### <a name="remarks"></a>解説

## <a name="cmfcstatusbargetpaneinfo"></a><a name="getpaneinfo"></a> CMFCStatusBar:: Get Info

```cpp
void GetPaneInfo(
    int nIndex,
    UINT& nID,
    UINT& nStyle,
    int& cxWidth) const;
```

### <a name="parameters"></a>パラメーター

から *nIndex*<br/>
から *nID*<br/>
から *Nstyle*<br/>
から *Cxwidth*<br/>

### <a name="remarks"></a>解説

## <a name="cmfcstatusbargetpaneprogress"></a><a name="getpaneprogress"></a> CMFCStatusBar:: Get Progress

```
long GetPaneProgress(int nIndex) const;
```

### <a name="parameters"></a>パラメーター

から *nIndex*<br/>

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cmfcstatusbargetpanestyle"></a><a name="getpanestyle"></a> CMFCStatusBar:: Get Style

```
UINT GetPaneStyle(int nIndex) const;
```

### <a name="parameters"></a>パラメーター

から *nIndex*<br/>

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cmfcstatusbargetpanetext"></a><a name="getpanetext"></a> CMFCStatusBar:: Getて Text

```cpp
void GetPaneText(
    int nIndex,
    CString& s) const;

CString GetPaneText(int nIndex) const;
```

### <a name="parameters"></a>パラメーター

から *nIndex*<br/>
から *s*<br/>

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cmfcstatusbargetpanewidth"></a><a name="getpanewidth"></a> CMFCStatusBar:: Get Width

ステータスバーのペインの幅を取得します。

```
int GetPaneWidth(int nIndex) const;
```

### <a name="parameters"></a>パラメーター

*nIndex*<br/>
からステータスバーペインのインデックスを指定します。

### <a name="return-value"></a>戻り値

*NIndex* が指定するステータスバーペインの幅。それ以外の場合は、ステータスバーペインが存在しない場合は0です。

## <a name="cmfcstatusbargettiptext"></a><a name="gettiptext"></a> CMFCStatusBar:: GetTipText

ステータスバーのペインのツールヒントテキストを取得します。

```
CString GetTipText(int nIndex) const;
```

### <a name="parameters"></a>パラメーター

*nIndex*<br/>
からツールヒントのテキストを取得するペインのインデックスを指定します。

### <a name="return-value"></a>戻り値

*NIndex* が指定するステータスバーペインのツールヒントテキスト。 それ以外の場合は、指定された *nIndex* にステータスバーペインが存在しない場合、またはツールヒントテキストが空の場合は空の文字列。

## <a name="cmfcstatusbarinvalidatepanecontent"></a><a name="invalidatepanecontent"></a> CMFCStatusBar:: InvalidatePaneContent

ステータスバーペインを無効にして、コンテンツを再描画します。

```cpp
void InvalidatePaneContent(int nIndex);
```

### <a name="parameters"></a>パラメーター

*nIndex*<br/>
からコンテンツを無効にして再描画するペインのインデックスを指定します。

### <a name="remarks"></a>解説

ステータスバーが無効化されると、再描画のマークが付けられます。 `UpdateWindow`メソッドがメソッドに WM_PAINT メッセージを送信すると、Windows はそれを再描画し `OnPaint` ます。

## <a name="cmfcstatusbarondrawpane"></a><a name="ondrawpane"></a> CMFCStatusBar:: OnDrawPane

ステータスバーのウィンドウを再描画します。

```
virtual void OnDrawPane(
    CDC* pDC,
    CMFCStatusBarPaneInfo* pPane);
```

### <a name="parameters"></a>パラメーター

*pDC*<br/>
から描画するデバイスコンテキストへのポインター。

*pPane*<br/>
から再 `CMFCStatusBarPaneInfo` 描画するペインに関する情報を格納している構造体へのポインター。

### <a name="remarks"></a>解説

既定では、 `OnDrawPane` ウィンドウのスタイルと内容に応じて、デバイスコンテキスト *pDC* を使用してウィンドウを再描画します。

派生クラスでこのメソッド `CMFCStatusBar` をオーバーライドして、ペインの外観をカスタマイズします。

## <a name="cmfcstatusbarprecreatewindow"></a><a name="precreatewindow"></a> CMFCStatusBar::P reCreateWindow

```
virtual BOOL PreCreateWindow(CREATESTRUCT& cs);
```

### <a name="parameters"></a>パラメーター

から *cs*<br/>

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cmfcstatusbarsetdrawextendedarea"></a><a name="setdrawextendedarea"></a> CMFCStatusBar:: SetDrawExtendedArea

```cpp
void SetDrawExtendedArea(BOOL bSet = TRUE);
```

### <a name="parameters"></a>パラメーター

から *Bset*<br/>

### <a name="remarks"></a>解説

## <a name="cmfcstatusbarsetindicators"></a><a name="setindicators"></a> CMFCStatusBar:: SetIndicators

```
BOOL SetIndicators(
    const UINT* lpIDArray,
    int nIDCount);
```

### <a name="parameters"></a>パラメーター

から *Lpidarray*<br/>
から *nIDCount*<br/>

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cmfcstatusbarsetpaneanimation"></a><a name="setpaneanimation"></a> CMFCStatusBar:: Setて Animation

指定したペインにアニメーションを割り当てます。

```cpp
void SetPaneAnimation(
    int nIndex,
    HIMAGELIST hImageList,
    UINT nFrameRate=500,
    BOOL bUpdate=TRUE);
```

### <a name="parameters"></a>パラメーター

*nIndex*<br/>
からアニメーションの割り当て先となるペインのインデックスを指定します。

*hImageList*<br/>
からアニメーションフレームを保持するイメージリストへのハンドルを指定します。

*nFrameRate レート*<br/>
からアニメーションのフレームレートをミリ秒単位で指定します。

*bUpdate*<br/>
からTRUE の場合は、すぐにウィンドウコンテンツを更新します。 それ以外の場合は、無効になったときにウィンドウの内容が更新されます。

### <a name="remarks"></a>解説

現在のアニメーションを無効にする場合は、 `SetPaneAnimation` `hImageList` を NULL に設定してを呼び出します。

## <a name="cmfcstatusbarsetpanebackgroundcolor"></a><a name="setpanebackgroundcolor"></a> CMFCStatusBar:: Set区画 Backgroundcolor

ステータスバーペインの背景色を設定します。

```cpp
void SetPaneBackgroundColor(
    int nIndex,
    COLORREF clrBackground=(COLORREF)-1,
    BOOL bUpdate=TRUE);
```

### <a name="parameters"></a>パラメーター

*nIndex*<br/>
から新しい背景色を設定するペインのインデックスを指定します。

*clrBackground*<br/>
から新しい背景色を指定します。

*bUpdate*<br/>
からTRUE の場合は、すぐにウィンドウコンテンツを更新します。 それ以外の場合は、別の方法でペインが無効になるまで、ペインの内容を更新しないでください。

## <a name="cmfcstatusbarsetpaneicon"></a><a name="setpaneicon"></a> CMFCStatusBar:: Set区画アイコン

ステータスバーペインのアイコンを設定します。

```cpp
void SetPaneIcon(
    int nIndex,
    HICON hIcon,
    BOOL bUpdate=TRUE);

void SetPaneIcon(
    int nIndex,
    HBITMAP hBmp,
    COLORREF clrTransparent=RGB(255, 0, 255),
    BOOL bUpdate=TRUE);
```

### <a name="parameters"></a>パラメーター

*nIndex*<br/>
からイメージを設定するペインのインデックスを指定します。

*hIcon*<br/>
からペインイメージとして設定するアイコンへのハンドルを指定します。

*bUpdate*<br/>
からペインコンテンツをすぐに更新するかどうかを指定します。

*hBmp*<br/>
からペインイメージとして設定するビットマップへのハンドルを指定します。

*clrTransparent*<br/>
から *HBmp* が示すビットマップの透明色を指定します。

### <a name="remarks"></a>解説

HICON または HBITMAP を透明色と共に渡して、ウィンドウのイメージを設定できます。 イメージを今後表示しない場合は、イメージハンドルとして NULL 値を渡します。

[CMFCStatusBar:: Setて animation](#setpaneanimation)で設定されている実行中のアニメーションがある場合、アニメーションは停止されます。

## <a name="cmfcstatusbarsetpaneinfo"></a><a name="setpaneinfo"></a> CMFCStatusBar:: Setて Info

```cpp
void SetPaneInfo(
    int nIndex,
    UINT nID,
    UINT nStyle,
    int cxWidth);
```

### <a name="parameters"></a>パラメーター

から *nIndex*<br/>
から *nID*<br/>
から *Nstyle*<br/>
から *Cxwidth*<br/>

### <a name="remarks"></a>解説

## <a name="cmfcstatusbarsetpaneprogress"></a><a name="setpaneprogress"></a> CMFCStatusBar:: Set Progress

指定したペインのプログレスバーの現在の進行状況インジケーターを設定します。

```cpp
void SetPaneProgress(
    int nIndex,
    long nCurr,
    BOOL bUpdate=TRUE);
```

### <a name="parameters"></a>パラメーター

*nIndex*<br/>
からプログレスインジケーターを更新するペインのインデックスを指定します。

*nCurr*<br/>
から進行状況インジケーターの現在の値を指定します。

*bUpdate*<br/>
からペインをすぐに更新するかどうかを指定します。

### <a name="remarks"></a>解説

指定したペインのプログレスバーの進行状況インジケーターを更新する場合は、このメソッドを呼び出します。

特定のペインに対してこの関数を使用するには、最初に [CMFCStatusBar:: Enablepane progressbar](#enablepaneprogressbar) を呼び出す必要があります。

## <a name="cmfcstatusbarsetpanestyle"></a><a name="setpanestyle"></a> CMFCStatusBar:: Setて Style

```cpp
void SetPaneStyle(
    int nIndex,
    UINT nStyle);
```

### <a name="parameters"></a>パラメーター

から *nIndex*<br/>
から *Nstyle*<br/>

### <a name="remarks"></a>解説

## <a name="cmfcstatusbarsetpanetext"></a><a name="setpanetext"></a> CMFCStatusBar:: Setて Text

```
virtual BOOL SetPaneText(
    int nIndex,
    LPCTSTR lpszNewText,
    BOOL bUpdate = TRUE);
```

### <a name="parameters"></a>パラメーター

から *nIndex*<br/>
から *lpszNewText*<br/>
から *bUpdate*<br/>

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cmfcstatusbarsetpanetextcolor"></a><a name="setpanetextcolor"></a> CMFCStatusBar:: SetPaneTextColor

指定したペインのテキストの色を設定します。

```cpp
void SetPaneTextColor(
    int nIndex,
    COLORREF clrText=(COLORREF)-1,
    BOOL bUpdate=TRUE);
```

### <a name="parameters"></a>パラメーター

*nIndex*<br/>
から新しいテキストの色を割り当てるペインのインデックスを指定します。

*clrText*<br/>
からテキストの色を指定します。

*bUpdate*<br/>
からTRUE の場合は、すぐにウィンドウコンテンツを更新します。 それ以外の場合は、別の方法でペインが無効になるまで、ペインの内容を更新しないでください。

## <a name="cmfcstatusbarsetpanewidth"></a><a name="setpanewidth"></a> CMFCStatusBar:: Set区画の幅

ステータスバーペインの幅を設定します。

```cpp
void SetPaneWidth(
    int nIndex,
    int cx);
```

### <a name="parameters"></a>パラメーター

*nIndex*<br/>
から新しい幅を設定するステータスバーペインのインデックス。

*シリーズ*<br/>
からステータスバーウィンドウの新しい幅 (ピクセル単位)。

## <a name="cmfcstatusbarsettiptext"></a><a name="settiptext"></a> CMFCStatusBar:: SetTipText

ステータスバーペインのツールヒントテキストを設定します。

```cpp
void SetTipText(
    int nIndex,
    LPCTSTR pszTipText);
```

### <a name="parameters"></a>パラメーター

*nIndex*<br/>
からツールヒントテキストの割り当て先となるペインのインデックス。

*pszTipText*<br/>
から新しいツールヒントのテキスト。

## <a name="see-also"></a>関連項目

[階層図](../../mfc/hierarchy-chart.md)<br/>
[Classes](../../mfc/reference/mfc-classes.md)<br/>
[CPane クラス](../../mfc/reference/cpane-class.md)<br/>
[CStatusBar クラス](../../mfc/reference/cstatusbar-class.md)

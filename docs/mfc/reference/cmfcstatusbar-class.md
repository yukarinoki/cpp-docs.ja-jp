---
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
ms.openlocfilehash: 024fbad44af2fb11e967141fc8e7ccc0aad0ccbe
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "81753470"
---
# <a name="cmfcstatusbar-class"></a>CMFCStatusBar クラス

クラス`CMFCStatusBar`は、クラスに似たステータス バー`CStatusBar`を実装します。 ただし、`CMFCStatusBar` クラスには、イメージ、アニメーション、およびプログレス バーを表示する機能や、マウスのダブルクリックに応答する機能など、`CStatusBar` クラスでは提供されない機能が含まれています。

詳細については、Visual Studio のインストールの**\\VC\\atlmfc\\src mfc**フォルダーにあるソース コードを参照してください。

## <a name="syntax"></a>構文

```
class CMFCStatusBar : public CPane
```

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CMFC ステータスバー::計算式レイアウト](#calcfixedlayout)|(CBase ペインをオーバーライド[します::計算固定レイアウト](../../mfc/reference/cbasepane-class.md#calcfixedlayout).)|
|[をクリックします。](#commandtoindex)||
|[ステータスバー::作成](#create)|コントロール バーを作成し[、CPane](../../mfc/reference/cpane-class.md)オブジェクトにアタッチします。 (CPane をオーバーライド[::作成](../../mfc/reference/cpane-class.md#create).)|
|[CMFC ステータスバー::作成します。](#createex)|コントロール バーを作成し[、CPane](../../mfc/reference/cpane-class.md)オブジェクトにアタッチします。 (CPane をオーバーライド[します::CreateEx](../../mfc/reference/cpane-class.md#createex).)|
|[前に :D挿入します。](#doesallowdyninsertbefore)|このペインと親フレームの間に別のペインを動的に挿入できるかどうかを指定します。 [(CBase ペインをオーバーライドします::DoesAllowDynInsert前に](../../mfc/reference/cbasepane-class.md#doesallowdyninsertbefore).)|
|[CMFC ステータスバー::有効ペインダブルクリック](#enablepanedoubleclick)|ステータス バーでのマウスダブルクリックの処理を有効または無効にします。|
|[CMFC ステータスバー::有効ペインプログレスバー](#enablepaneprogressbar)|指定したペインにプログレス バーを表示します。|
|[ステータスバー::カウントを取得します。](#getcount)|ステータス バーのペインの数を返します。|
|[状態バー::ページ拡張エリア](#getdrawextendedarea)||
|[を使用します。](#getextendedarea)||
|[をクリックします。](#getitemid)||
|[ステータスバー::ゲットアイテムレクト](#getitemrect)||
|[ステータスバー::GetPaneInfo](#getpaneinfo)||
|[ステータスバー::ペインの進行状況](#getpaneprogress)||
|[ステータスバー::ゲパネスタイル](#getpanestyle)|ペインのスタイルを返します。 [(CBasePane をオーバーライドします。::GetPaneStyle](../../mfc/reference/cbasepane-class.md#getpanestyle).)|
|[ステータスバー::テキストを取得します。](#getpanetext)||
|[ウィンドウの幅を取得します。](#getpanewidth)|ステータス バーの指定されたペインの幅をピクセル単位で返します。|
|[ステータスバー::テキストを取得します。](#gettiptext)|ステータス バーの指定されたペインのツール ヒント テキストを返します。|
|[コンテンツを無効にする](#invalidatepanecontent)|指定されたペインを無効にし、その内容を再描画します。|
|[ウィンドウを:P](#precreatewindow)|この`CWnd`オブジェクトにアタッチされたウィンドウの作成前に、フレームワークによって呼び出されます。 [(CWnd::P再作成ウィンドウ](../../mfc/reference/cwnd-class.md#precreatewindow)をオーバーライドします。|
|[を使用します。](#setdrawextendedarea)||
|[ステータスバー::セットインディケータ](#setindicators)||
|[CMFC ステータスバー::セットペインアニメーション](#setpaneanimation)|指定したペインにアニメーションを割り当てます。|
|[コントロール の状態バー::設定ウィンドウの背景色](#setpanebackgroundcolor)|ステータス バーの指定されたペインの背景色を設定します。|
|[ステータスバー::セットペインアイコン](#setpaneicon)|ステータス バーの指定されたペインのインジケーター アイコンを設定します。|
|[ステータスバー::設定ウィンドウ情報](#setpaneinfo)||
|[ステータスバー::設定ウィンドウの進行状況](#setpaneprogress)|ステータス バーの指定されたペインの進行状況バーの現在の進行状況を設定します。|
|[ステータスバー::セットペインスタイル](#setpanestyle)|ペインのスタイルを設定します。 (CBase ペインをオーバーライド[します::セットペインスタイル](../../mfc/reference/cbasepane-class.md#setpanestyle).)|
|[ステータスバー::テキストを設定します。](#setpanetext)||
|[ステータスバー::テキストの色を設定します。](#setpanetextcolor)|ステータス バーの指定されたペインのテキストの色を設定します。|
|[ステータスバー::ウィンドウ幅の設定](#setpanewidth)|ステータス バーの指定されたペインの幅をピクセル単位で設定します。|
|[ステータスバー::テキストを設定します。](#settiptext)|ステータス バーの指定されたペインにツール ヒントテキストを設定します。|

### <a name="protected-methods"></a>プロテクト メソッド

|名前|説明|
|----------|-----------------|
|[ウィンドウの状態バー::オンドローペイン](#ondrawpane)|ステータス バーのペインを再描画するときに、フレームワークによって呼び出されます。|

## <a name="remarks"></a>解説

次の図は、ステータス バー デモ[サンプル](../../overview/visual-cpp-samples.md)アプリケーションのステータス バーの図を示しています。

![CMFCStatusBar の例](../../mfc/reference/media/cmfcstatusbar.png "CMFCStatusBar の例")

## <a name="example"></a>例

次の例は、アプリケーションがクラス内のさまざまなメソッドを呼び出すために使用する`CMFCStatusBar`ローカル変数を示しています。 これらの変数は、ステータスバーデモビュー.hで宣言されています。 メイン フレームは MainFrm.h で宣言され、ドキュメントは StatusBarDemoDoc.h で宣言され、ビューは StatusBarDemoView.h で宣言されます。 このコード スニペットは、[ステータス バーデモのサンプル](../../overview/visual-cpp-samples.md)の一部です。

[!code-cpp[NVC_MFC_StatusBarDemo#9](../../mfc/reference/codesnippet/cpp/cmfcstatusbar-class_1.h)]

## <a name="example"></a>例

次の例は、MainFrm.h`CMFCStatusBar`で`GetStatusBar`メソッドを導入し、StatusBarDemoView.h のメソッドからこのメソッドを`GetStatusBar`呼び出すことによって、オブジェクトへの参照を取得する方法を示しています。 このコード スニペットは、[ステータス バーデモのサンプル](../../overview/visual-cpp-samples.md)の一部です。

[!code-cpp[NVC_MFC_StatusBarDemo#7](../../mfc/reference/codesnippet/cpp/cmfcstatusbar-class_2.h)]
[!code-cpp[NVC_MFC_StatusBarDemo#8](../../mfc/reference/codesnippet/cpp/cmfcstatusbar-class_3.h)]

## <a name="example"></a>例

次の例は、クラス内のさまざまなメソッドを呼び`CMFCStatusBar`出す方法を示しています。 定数は MainFrm.h で宣言されます。 この例では、アイコンの設定方法、ステータス バー ペインのツールヒント テキストの設定、指定したペインへのプログレス バーの表示、指定したペインへのアニメーションの割り当て、ステータス バー ペインのテキストと幅の設定、ステータス バー ペインの進行状況バーの現在の進行状況インジケータの設定方法を示します。 このコード スニペットは、[ステータス バーデモのサンプル](../../overview/visual-cpp-samples.md)の一部です。

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

## <a name="requirements"></a>必要条件

**ヘッダー:** afxstatusbar.h

## <a name="cmfcstatusbarcalcfixedlayout"></a><a name="calcfixedlayout"></a>CMFC ステータスバー::計算式レイアウト

```
virtual CSize CalcFixedLayout(
    BOOL bStretch,
    BOOL bHorz);
```

### <a name="parameters"></a>パラメーター

[in]*bストレッチ*<br/>
[in]*bHorz*<br/>

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cmfcstatusbarcommandtoindex"></a><a name="commandtoindex"></a>をクリックします。

```
int CommandToIndex(UINT nIDFind) const;
```

### <a name="parameters"></a>パラメーター

[in]*nID検索*<br/>

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cmfcstatusbarcreate"></a><a name="create"></a>ステータスバー::作成

```
BOOL Create(
    CWnd* pParentWnd,
    DWORD dwStyle = WS_CHILD | WS_VISIBLE | CBRS_BOTTOM,
    UINT nID = AFX_IDW_STATUS_BAR);
```

### <a name="parameters"></a>パラメーター

[in]*親子*<br/>
[in]*ドウスタイル*<br/>
[in]*nID*<br/>

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cmfcstatusbarcreateex"></a><a name="createex"></a>CMFC ステータスバー::作成します。

```
BOOL CreateEx(
    CWnd* pParentWnd,
    DWORD dwCtrlStyle = 0,
    DWORD dwStyle = WS_CHILD | WS_VISIBLE | CBRS_BOTTOM,
    UINT nID = AFX_IDW_STATUS_BAR);
```

### <a name="parameters"></a>パラメーター

[in]*親子*<br/>
[in]*スタイル*<br/>
[in]*ドウスタイル*<br/>
[in]*nID*<br/>

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cmfcstatusbardoesallowdyninsertbefore"></a><a name="doesallowdyninsertbefore"></a>前に :D挿入します。

```
virtual BOOL DoesAllowDynInsertBefore() const;
```

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cmfcstatusbarenablepanedoubleclick"></a><a name="enablepanedoubleclick"></a>CMFC ステータスバー::有効ペインダブルクリック

ステータス バーでのマウスダブルクリックの処理を有効または無効にします。

```cpp
void EnablePaneDoubleClick(BOOL bEnable=TRUE);
```

### <a name="parameters"></a>パラメーター

*b 有効にする*<br/>
[in]TRUE の場合は、マウスダブルクリックの処理を有効にします。 それ以外の場合は、マウスのダブルクリックの処理を無効にします。

### <a name="remarks"></a>解説

ステータス バーでダブルクリックの処理が有効になっている場合、Windows は、ユーザーがステータス バー ペインをダブルクリックするたびに、リソース ID と共にWM_COMMAND通知をステータス バーの所有者に送信します。

## <a name="cmfcstatusbarenablepaneprogressbar"></a><a name="enablepaneprogressbar"></a>CMFC ステータスバー::有効ペインプログレスバー

指定したペインにプログレス バーを表示します。

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
[in]プログレス バーを有効にするペインのインデックスを指定します。

*n合計*<br/>
[in]プログレス バーの最大値を指定します。

*テキストを表示します。*<br/>
[in]進行状況バーに現在の進行状況の値を表示するかどうかを指定します。

*clrBar*<br/>
[in]プログレス バーの背景色を指定します。

*clrBarDest*<br/>
[in]プログレス バーの背景の 2 番目の色を指定します。 グラデーションにブレンドされたカラーで塗りつぶすには *、clrBar*とは異なる値を使用します。

*clrProgressText*<br/>
[in]プログレス バーのテキストの色を指定します。

### <a name="remarks"></a>解説

*nTotal*を -1 に`EnablePaneProgressBar`設定してプログレス バーの呼び出しを無効にする場合。 デフォルトでは *、nTotal*は 100 に設定されています。 したがって、進捗状況をパーセンテージで表示するために追加の計算は必要ありません。

プログレス バーの背景色にグラデーションにブレンドされた色が表示されるように *、clrBar*と*clrBarDest*に異なる値を渡す必要があります。 .

現在の進行状況を設定するには、[メソッド](#setpaneprogress)を呼び出します。

## <a name="cmfcstatusbargetcount"></a><a name="getcount"></a>ステータスバー::カウントを取得します。

ステータス バーのペインの数を取得します。

```
int GetCount() const;
```

### <a name="return-value"></a>戻り値

ステータス バーのペインの数。

## <a name="cmfcstatusbargetdrawextendedarea"></a><a name="getdrawextendedarea"></a>状態バー::ページ拡張エリア

```
BOOL GetDrawExtendedArea() const;
```

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cmfcstatusbargetextendedarea"></a><a name="getextendedarea"></a>を使用します。

```
virtual BOOL GetExtendedArea(CRect& rect) const;
```

### <a name="parameters"></a>パラメーター

[in]*レクト*<br/>

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cmfcstatusbargetitemid"></a><a name="getitemid"></a>をクリックします。

```
UINT GetItemID(int nIndex) const;
```

### <a name="parameters"></a>パラメーター

[in]*nインデックス*<br/>

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cmfcstatusbargetitemrect"></a><a name="getitemrect"></a>ステータスバー::ゲットアイテムレクト

```cpp
void GetItemRect(
    int nIndex,
    LPRECT lpRect) const;
```

### <a name="parameters"></a>パラメーター

[in]*nインデックス*<br/>
[in]*lpRect*<br/>

### <a name="remarks"></a>解説

## <a name="cmfcstatusbargetpaneinfo"></a><a name="getpaneinfo"></a>ステータスバー::GetPaneInfo

```cpp
void GetPaneInfo(
    int nIndex,
    UINT& nID,
    UINT& nStyle,
    int& cxWidth) const;
```

### <a name="parameters"></a>パラメーター

[in]*nインデックス*<br/>
[in]*nID*<br/>
[in]*nスタイル*<br/>
[in]*幅*<br/>

### <a name="remarks"></a>解説

## <a name="cmfcstatusbargetpaneprogress"></a><a name="getpaneprogress"></a>ステータスバー::ペインの進行状況

```
long GetPaneProgress(int nIndex) const;
```

### <a name="parameters"></a>パラメーター

[in]*nインデックス*<br/>

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cmfcstatusbargetpanestyle"></a><a name="getpanestyle"></a>ステータスバー::ゲパネスタイル

```
UINT GetPaneStyle(int nIndex) const;
```

### <a name="parameters"></a>パラメーター

[in]*nインデックス*<br/>

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cmfcstatusbargetpanetext"></a><a name="getpanetext"></a>ステータスバー::テキストを取得します。

```cpp
void GetPaneText(
    int nIndex,
    CString& s) const;

CString GetPaneText(int nIndex) const;
```

### <a name="parameters"></a>パラメーター

[in]*nインデックス*<br/>
[in]*s*<br/>

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cmfcstatusbargetpanewidth"></a><a name="getpanewidth"></a>ウィンドウの幅を取得します。

ステータス バーのペインの幅を取得します。

```
int GetPaneWidth(int nIndex) const;
```

### <a name="parameters"></a>パラメーター

*nIndex*<br/>
[in]ステータス バー ペインのインデックスを指定します。

### <a name="return-value"></a>戻り値

*nIndex*が指定するステータス バー ペインの幅。それ以外の場合は 0 を返します。

## <a name="cmfcstatusbargettiptext"></a><a name="gettiptext"></a>ステータスバー::テキストを取得します。

ステータス バーのペインのツールヒント テキストを取得します。

```
CString GetTipText(int nIndex) const;
```

### <a name="parameters"></a>パラメーター

*nIndex*<br/>
[in]ツール ヒント テキストを取得するペインのインデックスを指定します。

### <a name="return-value"></a>戻り値

*nIndex*が指定するステータス バー ペインのツールヒント テキスト。 それ以外の場合は、指定した*nIndex*に対してステータス バー ペインが存在しない場合、またはツールヒント のテキストが空の場合は、空の文字列を返します。

## <a name="cmfcstatusbarinvalidatepanecontent"></a><a name="invalidatepanecontent"></a>コンテンツを無効にする

ステータス バー ペインを無効にし、コンテンツを再描画します。

```cpp
void InvalidatePaneContent(int nIndex);
```

### <a name="parameters"></a>パラメーター

*nIndex*<br/>
[in]コンテンツを無効にして再描画するペインのインデックスを指定します。

### <a name="remarks"></a>解説

ステータス バーが無効になると、再描画のマークが付けられます。 メソッドがメソッドにWM_PAINTメッセージ`UpdateWindow`を送信すると、Windows は`OnPaint`再描画します。

## <a name="cmfcstatusbarondrawpane"></a><a name="ondrawpane"></a>ウィンドウの状態バー::オンドローペイン

ステータス バーのペインを再描画します。

```
virtual void OnDrawPane(
    CDC* pDC,
    CMFCStatusBarPaneInfo* pPane);
```

### <a name="parameters"></a>パラメーター

*pDC*<br/>
[in]描画するデバイス コンテキストへのポインター。

*pペイン*<br/>
[in]再描画する`CMFCStatusBarPaneInfo`ペインに関する情報を含む構造体へのポインター。

### <a name="remarks"></a>解説

既定では、`OnDrawPane`ウィンドウのスタイルと内容に従ってデバイス コンテキスト*pDC*を使用してペインを再描画します。

ペインの外観をカスタマイズ`CMFCStatusBar`するには、このメソッドを派生クラスでオーバーライドします。

## <a name="cmfcstatusbarprecreatewindow"></a><a name="precreatewindow"></a>ウィンドウを:P

```
virtual BOOL PreCreateWindow(CREATESTRUCT& cs);
```

### <a name="parameters"></a>パラメーター

[in]*cs*<br/>

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cmfcstatusbarsetdrawextendedarea"></a><a name="setdrawextendedarea"></a>を使用します。

```cpp
void SetDrawExtendedArea(BOOL bSet = TRUE);
```

### <a name="parameters"></a>パラメーター

[in]*bセット*<br/>

### <a name="remarks"></a>解説

## <a name="cmfcstatusbarsetindicators"></a><a name="setindicators"></a>ステータスバー::セットインディケータ

```
BOOL SetIndicators(
    const UINT* lpIDArray,
    int nIDCount);
```

### <a name="parameters"></a>パラメーター

[in]*を指定します。*<br/>
[in]*NIDカウント*<br/>

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cmfcstatusbarsetpaneanimation"></a><a name="setpaneanimation"></a>CMFC ステータスバー::セットペインアニメーション

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
[in]アニメーションを割り当てるペインのインデックスを指定します。

*一覧*<br/>
[in]アニメーション フレームを保持するイメージ リストへのハンドルを指定します。

*nフレームレート*<br/>
[in]アニメーションのフレーム レートをミリ秒単位で指定します。

*b更新*<br/>
[in]TRUE の場合は、ペインの内容を直ちに更新します。 それ以外の場合、ペインの内容は無効化されたときに更新されます。

### <a name="remarks"></a>解説

現在のアニメーションを無効にする場合は、NULL`hImageList`を設定して呼び出します`SetPaneAnimation`。

## <a name="cmfcstatusbarsetpanebackgroundcolor"></a><a name="setpanebackgroundcolor"></a>コントロール の状態バー::設定ウィンドウの背景色

ステータス バー ペインの背景色を設定します。

```cpp
void SetPaneBackgroundColor(
    int nIndex,
    COLORREF clrBackground=(COLORREF)-1,
    BOOL bUpdate=TRUE);
```

### <a name="parameters"></a>パラメーター

*nIndex*<br/>
[in]新しい背景色を設定するペインのインデックスを指定します。

*clrBackground*<br/>
[in]新しい背景色を指定します。

*b更新*<br/>
[in]TRUE の場合は、ペインの内容を直ちに更新します。 それ以外の場合は、ペインが別のメソッドによって無効になるまで、ペインの内容を更新しないでください。

## <a name="cmfcstatusbarsetpaneicon"></a><a name="setpaneicon"></a>ステータスバー::セットペインアイコン

ステータス バー ペインのアイコンを設定します。

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
[in]イメージを設定するペインのインデックスを指定します。

*Hicon*<br/>
[in]ペイン イメージとして設定するアイコンへのハンドルを指定します。

*b更新*<br/>
[in]ペインの内容を直ちに更新するかどうかを指定します。

*hBmp*<br/>
[in]ペイン イメージとして設定するビットマップへのハンドルを指定します。

*clr透明*<br/>
[in]*hBmp*が示すビットマップの透明色を指定します。

### <a name="remarks"></a>解説

HICON または HBITMAP を透明色と共に渡して、ペインのイメージを設定できます。 イメージを表示しない場合は、イメージ ハンドルとして NULL 値を渡します。

[CMFCStatusBar::SetPaneAnimation](#setpaneanimation)が設定したアニメーションが実行されている場合、アニメーションは停止します。

## <a name="cmfcstatusbarsetpaneinfo"></a><a name="setpaneinfo"></a>ステータスバー::設定ウィンドウ情報

```cpp
void SetPaneInfo(
    int nIndex,
    UINT nID,
    UINT nStyle,
    int cxWidth);
```

### <a name="parameters"></a>パラメーター

[in]*nインデックス*<br/>
[in]*nID*<br/>
[in]*nスタイル*<br/>
[in]*幅*<br/>

### <a name="remarks"></a>解説

## <a name="cmfcstatusbarsetpaneprogress"></a><a name="setpaneprogress"></a>ステータスバー::設定ウィンドウの進行状況

指定したペインの進行状況バーの現在の進行状況インジケーターを設定します。

```cpp
void SetPaneProgress(
    int nIndex,
    long nCurr,
    BOOL bUpdate=TRUE);
```

### <a name="parameters"></a>パラメーター

*nIndex*<br/>
[in]進行状況インジケーターを更新するペインのインデックスを指定します。

*nカー*<br/>
[in]進行状況インジケーターの現在の値を指定します。

*b更新*<br/>
[in]ペインを直ちに更新するかどうかを指定します。

### <a name="remarks"></a>解説

指定したペインの進行状況バーの進行状況インジケーターを更新する場合は、このメソッドを呼び出します。

指定されたペインに対してこの関数を使用するには、最初に[CMFCStatusBar::EnablePaneProgressBar を](#enablepaneprogressbar)呼び出す必要があります。

## <a name="cmfcstatusbarsetpanestyle"></a><a name="setpanestyle"></a>ステータスバー::セットペインスタイル

```cpp
void SetPaneStyle(
    int nIndex,
    UINT nStyle);
```

### <a name="parameters"></a>パラメーター

[in]*nインデックス*<br/>
[in]*nスタイル*<br/>

### <a name="remarks"></a>解説

## <a name="cmfcstatusbarsetpanetext"></a><a name="setpanetext"></a>ステータスバー::テキストを設定します。

```
virtual BOOL SetPaneText(
    int nIndex,
    LPCTSTR lpszNewText,
    BOOL bUpdate = TRUE);
```

### <a name="parameters"></a>パラメーター

[in]*nインデックス*<br/>
[in]*テキスト*<br/>
[in]*b更新*<br/>

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cmfcstatusbarsetpanetextcolor"></a><a name="setpanetextcolor"></a>ステータスバー::テキストの色を設定します。

指定したペインのテキストの色を設定します。

```cpp
void SetPaneTextColor(
    int nIndex,
    COLORREF clrText=(COLORREF)-1,
    BOOL bUpdate=TRUE);
```

### <a name="parameters"></a>パラメーター

*nIndex*<br/>
[in]新しいテキストの色を割り当てるペインのインデックスを指定します。

*clrText*<br/>
[in]テキストの色を指定します。

*b更新*<br/>
[in]TRUE の場合は、ペインの内容を直ちに更新します。 それ以外の場合は、ペインが別のメソッドによって無効になるまで、ペインの内容を更新しないでください。

## <a name="cmfcstatusbarsetpanewidth"></a><a name="setpanewidth"></a>ステータスバー::ウィンドウ幅の設定

ステータス バー ペインの幅を設定します。

```cpp
void SetPaneWidth(
    int nIndex,
    int cx);
```

### <a name="parameters"></a>パラメーター

*nIndex*<br/>
[in]新しい幅を設定するステータス バー ペインのインデックス。

*Cx*<br/>
[in]ステータス バー ペインの新しい幅 (ピクセル単位)。

## <a name="cmfcstatusbarsettiptext"></a><a name="settiptext"></a>ステータスバー::テキストを設定します。

ステータス バー ペインのツールヒント テキストを設定します。

```cpp
void SetTipText(
    int nIndex,
    LPCTSTR pszTipText);
```

### <a name="parameters"></a>パラメーター

*nIndex*<br/>
[in]ツールヒント テキストを割り当てるペインのインデックス。

*テキスト*<br/>
[in]新しいツールヒント テキスト。

## <a name="see-also"></a>関連項目

[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[クラス](../../mfc/reference/mfc-classes.md)<br/>
[CPane Class](../../mfc/reference/cpane-class.md)<br/>
[クラス](../../mfc/reference/cstatusbar-class.md)

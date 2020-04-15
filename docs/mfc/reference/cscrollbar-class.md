---
title: CScrollBar クラス
ms.date: 11/04/2016
f1_keywords:
- CScrollBar
- AFXWIN/CScrollBar
- AFXWIN/CScrollBar::CScrollBar
- AFXWIN/CScrollBar::Create
- AFXWIN/CScrollBar::EnableScrollBar
- AFXWIN/CScrollBar::GetScrollBarInfo
- AFXWIN/CScrollBar::GetScrollInfo
- AFXWIN/CScrollBar::GetScrollLimit
- AFXWIN/CScrollBar::GetScrollPos
- AFXWIN/CScrollBar::GetScrollRange
- AFXWIN/CScrollBar::SetScrollInfo
- AFXWIN/CScrollBar::SetScrollPos
- AFXWIN/CScrollBar::SetScrollRange
- AFXWIN/CScrollBar::ShowScrollBar
helpviewer_keywords:
- CScrollBar [MFC], CScrollBar
- CScrollBar [MFC], Create
- CScrollBar [MFC], EnableScrollBar
- CScrollBar [MFC], GetScrollBarInfo
- CScrollBar [MFC], GetScrollInfo
- CScrollBar [MFC], GetScrollLimit
- CScrollBar [MFC], GetScrollPos
- CScrollBar [MFC], GetScrollRange
- CScrollBar [MFC], SetScrollInfo
- CScrollBar [MFC], SetScrollPos
- CScrollBar [MFC], SetScrollRange
- CScrollBar [MFC], ShowScrollBar
ms.assetid: f3735ca5-73ea-46dc-918b-4d824c9fe47f
ms.openlocfilehash: 761d7e9db650c6d95e916c85bd7456d9b1c647c5
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81318534"
---
# <a name="cscrollbar-class"></a>CScrollBar クラス

Windows のスクロール バー コントロールの機能を提供します。

## <a name="syntax"></a>構文

```
class CScrollBar : public CWnd
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[スクロールバー::スクロールバー](#cscrollbar)|`CScrollBar` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[スクロールバー::作成](#create)|Windows スクロール バーを作成し、オブジェクトに`CScrollBar`アタッチします。|
|[スクロールバー::有効スクロールバー](#enablescrollbar)|スクロール バーの矢印の一方または両方を有効または無効にします。|
|[スクロールバー::ゲットスクロールバーインフォ](#getscrollbarinfo)|構造体を使用して、スクロール バーに`SCROLLBARINFO`関する情報を取得します。|
|[スクロールバー::ゲットスクロール情報](#getscrollinfo)|スクロール バーに関する情報を取得します。|
|[スクロールバー::ゲットスクロールリミット](#getscrolllimit)|スクロール バーの制限を取得します。|
|[スクロールバー::ゲットスクロールポッ](#getscrollpos)|スクロール ボックスの現在位置を取得します。|
|[スクロールバー::ゲットスクロール範囲](#getscrollrange)|指定されたスクロール バーの現在の最小および最大スクロール バーの位置を取得します。|
|[スクロールバー::セットスクロール情報](#setscrollinfo)|スクロール バーの情報を設定します。|
|[スクロールバー::セットスクロールポッ](#setscrollpos)|スクロール ボックスの現在位置を設定します。|
|[スクロールバー::セットスクロール範囲](#setscrollrange)|指定されたスクロール バーの最小位置と最大位置の値を設定します。|
|[スクロールバー::ショースクロールバー](#showscrollbar)|スクロール バーの表示と非表示を切り替えます。|

## <a name="remarks"></a>解説

スクロール バー コントロールは、2 つの手順で作成します。 `CScrollBar`まず、コンストラクタを呼び出して`CScrollBar`オブジェクトを構築し、次に[Create](#create)メンバー関数を呼び出して Windows スクロール`CScrollBar`バー コントロールを作成し、オブジェクトにアタッチします。

ダイアログ ボックス内`CScrollBar`で (ダイアログ リソースを使用して) オブジェクト`CScrollBar`を作成すると、ユーザーがダイアログ ボックスを閉じると、 が自動的に破棄されます。

ウィンドウ内にオブジェクト`CScrollBar`を作成する場合は、オブジェクトを破棄する必要もあります。

スタック上にオブジェクト`CScrollBar`を作成すると、オブジェクトは自動的に破棄されます。 **新しい**関数を`CScrollBar`使用してヒープ上にオブジェクトを作成する場合は、ユーザーが Windows のスクロール バーを終了したときに破棄するには、オブジェクトの**delete**を呼び出す必要があります。

オブジェクトにメモリを`CScrollBar`割り当てる場合は、`CScrollBar`デストラクタをオーバーライドして割り当てを破棄します。

の使用`CScrollBar`に関する関連情報については、「[コントロール](../../mfc/controls-mfc.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CScrollBar`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxwin.h

## <a name="cscrollbarcreate"></a><a name="create"></a>スクロールバー::作成

Windows スクロール バーを作成し、オブジェクトに`CScrollBar`アタッチします。

```
virtual BOOL Create(
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>パラメーター

*Dwstyle*<br/>
スクロール バーのスタイルを指定します。 スクロール バーの[スタイル](../../mfc/reference/styles-used-by-mfc.md#scroll-bar-styles)を任意に組み合わせてスクロール バーに適用します。

*Rect*<br/>
スクロール バーのサイズと位置を指定します。 `RECT`構造体または`CRect`オブジェクトのいずれかです。

*pParentWnd*<br/>
スクロール バーの親ウィンドウ (通常はオブジェクト`CDialog`) を指定します。 NULL にすることはできません。

*nID*<br/>
スクロール バーのコントロール ID。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>解説

オブジェクトは`CScrollBar`2 つの手順で作成します。 まず、オブジェクトを構築するコンストラクターを`CScrollBar`呼び出します。次に`Create`、 を呼び出すと、関連付けられた Windows スクロール バー`CScrollBar`が作成および初期化され、オブジェクトにアタッチされます。

スクロール バーに次の[ウィンドウ スタイル](../../mfc/reference/styles-used-by-mfc.md#window-styles)を適用します。

- WS_CHILD常に

- WS_VISIBLE通常

- WS_DISABLEDまれ

- WS_GROUP グループ コントロールへ

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CScrollBar#1](../../mfc/reference/codesnippet/cpp/cscrollbar-class_1.cpp)]

## <a name="cscrollbarcscrollbar"></a><a name="cscrollbar"></a>スクロールバー::スクロールバー

`CScrollBar` オブジェクトを構築します。

```
CScrollBar();
```

### <a name="remarks"></a>解説

オブジェクトを構築した後、メンバー関数`Create`を呼び出して、Windows のスクロール バーを作成して初期化します。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CScrollBar#2](../../mfc/reference/codesnippet/cpp/cscrollbar-class_2.h)]

## <a name="cscrollbarenablescrollbar"></a><a name="enablescrollbar"></a>スクロールバー::有効スクロールバー

スクロール バーの矢印の一方または両方を有効または無効にします。

```
BOOL EnableScrollBar(UINT nArrowFlags = ESB_ENABLE_BOTH);
```

### <a name="parameters"></a>パラメーター

*フラグ*<br/>
スクロール矢印を有効にするか無効にするか、どの矢印を有効にするか無効にするかを指定します。 このパラメーターには、次のいずれかの値を指定できます。

- ESB_ENABLE_BOTH スクロール バーの両方の矢印を有効にします。

- ESB_DISABLE_LTUP 水平スクロール バーの左矢印または垂直スクロール バーの上矢印を無効にします。

- ESB_DISABLE_RTDN水平スクロール バーの右矢印または垂直スクロール バーの下向き矢印を無効にします。

- ESB_DISABLE_BOTH スクロール バーの両方の矢印を無効にします。

### <a name="return-value"></a>戻り値

矢印が指定どおりに有効または無効になっている場合は 0 以外。それ以外の場合は 0 で、矢印が既に要求された状態にあるか、エラーが発生したことを示します。

### <a name="example"></a>例

  [「スクロールバー::セットスクロール範囲](#setscrollrange)」の例を参照してください。

## <a name="cscrollbargetscrollbarinfo"></a><a name="getscrollbarinfo"></a>スクロールバー::ゲットスクロールバーインフォ

`SCROLLBARINFO` 構造体がスクロール バーについて保持している情報を取得します。

```
BOOL GetScrollBarInfo(PSCROLLBARINFO pScrollInfo) const;
```

### <a name="parameters"></a>パラメーター

*をクリックします。*<br/>
[構造体](/windows/win32/api/winuser/ns-winuser-scrollbarinfo)へのポインター。

### <a name="return-value"></a>戻り値

成功した場合は TRUE を返し、失敗した場合は FALSE を返します。

### <a name="remarks"></a>解説

このメンバー関数は、Windows SDK で説明されているように[、SBM_SCROLLBARINFO](/windows/win32/Controls/sbm-getscrollbarinfo)メッセージの機能をエミュレートします。

## <a name="cscrollbargetscrollinfo"></a><a name="getscrollinfo"></a>スクロールバー::ゲットスクロール情報

`SCROLLINFO` 構造体がスクロール バーについて保持している情報を取得します。

```
BOOL GetScrollInfo(
    LPSCROLLINFO lpScrollInfo,
    UINT nMask = SIF_ALL);
```

### <a name="parameters"></a>パラメーター

*をクリックします。*<br/>
[スクロール情報](/windows/win32/api/winuser/ns-winuser-scrollinfo)構造体へのポインター。 この構造体の詳細については、Windows SDK を参照してください。

*nマスク*<br/>
取得するスクロール バーのパラメーターを指定します。 一般的な使用法SIF_ALLでは、SIF_PAGE、SIF_POS、SIF_TRACKPOS、およびSIF_RANGEの組み合わせを指定します。 nMask 値の詳細については、「」を参照してください`SCROLLINFO`。

### <a name="return-value"></a>戻り値

メッセージが値を取得した場合、戻り値は TRUE です。 それ以外の場合は FALSE です。

### <a name="remarks"></a>解説

`GetScrollInfo`アプリケーションで 32 ビットのスクロール位置を使用できます。

[SCROLLINFO](/windows/win32/api/winuser/ns-winuser-scrollinfo)構造体には、スクロール バーに関する情報が含まれています。 構造の`SCROLLINFO`既定値の変更の詳細については、Windows SDK の構造トピックを参照してください。

スクロール バーの位置を示す MFC Windows メッセージ ハンドラー、[CWnd::OnHScroll、および[CWnd::OnVScroll](../../mfc/reference/cwnd-class.md#onvscroll)は、位置データの 16 ビットのみを提供します。 `GetScrollInfo`32`SetScrollInfo`ビットのスクロール バー位置データを提供します。 したがって、アプリケーションは、32 ビット`CWnd::OnHScroll`の`CWnd::OnVScroll`スクロール バー位置データの処理中に呼び出`GetScrollInfo`すことができます。

### <a name="example"></a>例

  [「CWnd::OnHScroll」](../../mfc/reference/cwnd-class.md#onhscroll)の例を参照してください。

## <a name="cscrollbargetscrolllimit"></a><a name="getscrolllimit"></a>スクロールバー::ゲットスクロールリミット

スクロール バーの最大スクロール位置を取得します。

```
int GetScrollLimit();
```

### <a name="return-value"></a>戻り値

正常終了した場合は、スクロール バーの最大位置を指定します。それ以外の場合は 0。

### <a name="example"></a>例

  [「CWnd::OnHScroll」](../../mfc/reference/cwnd-class.md#onhscroll)の例を参照してください。

## <a name="cscrollbargetscrollpos"></a><a name="getscrollpos"></a>スクロールバー::ゲットスクロールポッ

スクロール ボックスの現在位置を取得します。

```
int GetScrollPos() const;
```

### <a name="return-value"></a>戻り値

正常に実行された場合は、スクロール ボックスの現在位置を指定します。それ以外の場合は 0。

### <a name="remarks"></a>解説

現在位置は、現在のスクロール範囲に依存する相対値です。 たとえば、スクロール範囲が 100 ~ 200 で、スクロール ボックスがバーの中央にある場合、現在の位置は 150 になります。

### <a name="example"></a>例

  [「CWnd::OnHScroll」](../../mfc/reference/cwnd-class.md#onhscroll)の例を参照してください。

## <a name="cscrollbargetscrollrange"></a><a name="getscrollrange"></a>スクロールバー::ゲットスクロール範囲

指定されたスクロール バーの現在の最小および最大スクロール バーの位置を *、lpMinPos*および*lpMaxPos*で指定された位置にコピーします。

```
void GetScrollRange(
    LPINT lpMinPos,
    LPINT lpMaxPos) const;
```

### <a name="parameters"></a>パラメーター

*lpMinPos*<br/>
最小位置を受け取る整数変数へのポインタ。

*lpMaxPos*<br/>
最大位置を受け取る整数変数へのポインタ。

### <a name="remarks"></a>解説

スクロール バー コントロールの既定の範囲は空です (両方の値は 0)。

### <a name="example"></a>例

  [「CWnd::OnHScroll」](../../mfc/reference/cwnd-class.md#onhscroll)の例を参照してください。

## <a name="cscrollbarsetscrollinfo"></a><a name="setscrollinfo"></a>スクロールバー::セットスクロール情報

スクロール バーに関`SCROLLINFO`する構造体が保持する情報を設定します。

```
BOOL SetScrollInfo(
    LPSCROLLINFO lpScrollInfo,
    BOOL bRedraw = TRUE);
```

### <a name="parameters"></a>パラメーター

*をクリックします。*<br/>
[スクロール情報](/windows/win32/api/winuser/ns-winuser-scrollinfo)構造体へのポインター。

*引き出し*<br/>
スクロール バーを再描画して新しい情報を反映するかどうかを指定します。 *bredraw*が TRUE の場合、スクロール バーが再描画されます。 FALSE の場合は、再描画されません。 スクロール バーは既定で再描画されます。

### <a name="return-value"></a>戻り値

成功した場合、戻り値は TRUE です。 それ以外の場合は FALSE です。

### <a name="remarks"></a>解説

フラグ値を含む、構造体パラメーター`SCROLLINFO`に必要な値を指定する必要があります。

この`SCROLLINFO`構造体には、スクロール バーに関する情報 (スクロール位置の最小値と最大値、ページ サイズ、スクロール ボックス (つまみ) の位置など) が含まれます。 構造の既定値の変更の詳細については、Windows SDK の[「SCROLLINFO](/windows/win32/api/winuser/ns-winuser-scrollinfo)構造体」のトピックを参照してください。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CScrollBar#3](../../mfc/reference/codesnippet/cpp/cscrollbar-class_3.cpp)]

## <a name="cscrollbarsetscrollpos"></a><a name="setscrollpos"></a>スクロールバー::セットスクロールポッ

nPos で指定された位置にスクロール ボックスの*nPos*現在位置を設定し、指定した場合は、新しい位置を反映するようにスクロール バーを再描画します。

```
int SetScrollPos(
    int nPos,
    BOOL bRedraw = TRUE);
```

### <a name="parameters"></a>パラメーター

*Npo*<br/>
スクロール ボックスの新しい位置を指定します。 スクロール範囲内になければなりません。

*引き出し*<br/>
スクロール バーを再描画して新しい位置を反映するかどうかを指定します。 *bredraw*が TRUE の場合、スクロール バーが再描画されます。 FALSE の場合は、再描画されません。 スクロール バーは既定で再描画されます。

### <a name="return-value"></a>戻り値

正常に実行された場合は、スクロール ボックスの前の位置を指定します。それ以外の場合は 0。

### <a name="remarks"></a>解説

スクロール バーが別の関数を呼び出して再描画される場合は *、bRedraw*を FALSE に設定し、スクロール バーが短い間隔で 2 回再描画されないようにします。

### <a name="example"></a>例

  [「スクロールバー::セットスクロール範囲](#setscrollrange)」の例を参照してください。

## <a name="cscrollbarsetscrollrange"></a><a name="setscrollrange"></a>スクロールバー::セットスクロール範囲

指定されたスクロール バーの最小位置と最大位置の値を設定します。

```
void SetScrollRange(
    int nMinPos,
    int nMaxPos,
    BOOL bRedraw = TRUE);
```

### <a name="parameters"></a>パラメーター

*nMinPos*<br/>
最小スクロール位置を指定します。

*をクリックします。*<br/>
最大スクロール位置を指定します。

*引き出し*<br/>
スクロール バーを再描画して変更を反映するかどうかを指定します。 *bRedraw*が TRUE の場合、スクロール バーは再描画されます。FALSE の場合は再描画されません。 既定では再描画されます。

### <a name="remarks"></a>解説

*nMinPos*と*nMaxPos*を 0 に設定すると、標準のスクロール バーが非表示になります。

スクロール バー通知メッセージの処理中にスクロール バーを非表示にする場合は、この関数を呼び出しません。

メンバー関数の呼`SetScrollRange`び出しの直後に呼び出しを行う場合は`SetScrollPos`*、bRedraw* in を 0 に設定して、スクロール バーが 2 回再描画されないようにします。 `SetScrollPos`

*nMinPos*と*nMaxPos*で指定される値の差は 32,767 を超えてはなりません。 スクロール バー コントロールの既定の範囲は空です *(nMinPos*と*nMaxPos*の両方が 0 です)。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CScrollBar#4](../../mfc/reference/codesnippet/cpp/cscrollbar-class_4.cpp)]

## <a name="cscrollbarshowscrollbar"></a><a name="showscrollbar"></a>スクロールバー::ショースクロールバー

スクロール バーの表示と非表示を切り替えます。

```
void ShowScrollBar(BOOL bShow = TRUE);
```

### <a name="parameters"></a>パラメーター

*bショー*<br/>
スクロール バーを表示するか非表示にするかを指定します。 このパラメーターが TRUE の場合は、スクロール バーが表示されます。それ以外の場合は非表示になります。

### <a name="remarks"></a>解説

アプリケーションは、スクロール バー通知メッセージの処理中にスクロール バーを非表示にするために、この関数を呼び出す必要があります。

### <a name="example"></a>例

  [「CScrollBar::作成](#create)」の例を参照してください。

## <a name="see-also"></a>関連項目

[CWnd クラス](../../mfc/reference/cwnd-class.md)<br/>
[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[CWnd クラス](../../mfc/reference/cwnd-class.md)<br/>
[CButton クラス](../../mfc/reference/cbutton-class.md)<br/>
[Cコンボボックスクラス](../../mfc/reference/ccombobox-class.md)<br/>
[CEdit Class](../../mfc/reference/cedit-class.md)<br/>
[CListBox クラス](../../mfc/reference/clistbox-class.md)<br/>
[CStatic クラス](../../mfc/reference/cstatic-class.md)<br/>
[クラス](../../mfc/reference/cdialog-class.md)

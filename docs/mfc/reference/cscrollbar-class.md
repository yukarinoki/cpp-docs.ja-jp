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
ms.openlocfilehash: d677d72b7e758fcdaa7df0e2918e9bbec3e18ee9
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62324234"
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
|[CScrollBar::CScrollBar](#cscrollbar)|`CScrollBar` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CScrollBar::Create](#create)|Windows のスクロール バーを作成しにアタッチします、`CScrollBar`オブジェクト。|
|[CScrollBar::EnableScrollBar](#enablescrollbar)|スクロール バーの矢印の一方または両方を有効または無効にします。|
|[CScrollBar::GetScrollBarInfo](#getscrollbarinfo)|スクロール バーを使用して情報を取得します、`SCROLLBARINFO`構造体。|
|[CScrollBar::GetScrollInfo](#getscrollinfo)|スクロール バーに関する情報を取得します。|
|[CScrollBar::GetScrollLimit](#getscrolllimit)|スクロール バーの上限を取得します。|
|[CScrollBar::GetScrollPos](#getscrollpos)|スクロール ボックスの現在位置を取得します。|
|[CScrollBar::GetScrollRange](#getscrollrange)|指定されたスクロール バーの現在の最小値と最大のスクロール バーの位置を取得します。|
|[CScrollBar::SetScrollInfo](#setscrollinfo)|スクロール バーの情報を設定します。|
|[CScrollBar::SetScrollPos](#setscrollpos)|スクロール ボックスの現在の位置を設定します。|
|[CScrollBar::SetScrollRange](#setscrollrange)|指定されたスクロール バーの最小位置と最大位置の値を設定します。|
|[CScrollBar::ShowScrollBar](#showscrollbar)|スクロール バーの表示と非表示を切り替えます。|

## <a name="remarks"></a>Remarks

2 つの手順では、スクロール バー コントロールを作成します。 最初に、コンス トラクターを呼び出す`CScrollBar`を構築する、`CScrollBar`オブジェクトを呼び出して、[作成](#create)メンバー関数は、Windows のスクロール バー コントロールを作成し、アタッチ先、`CScrollBar`オブジェクト。

作成する場合、 `CScrollBar` (ダイアログ リソースの場合) を使ってダイアログ ボックス内のオブジェクト、 `CScrollBar`  ダイアログ ボックスを閉じたときに自動的に破棄されます。

作成する場合、`CScrollBar`を破棄する必要がありますも、ウィンドウ内でオブジェクトします。

作成する場合、`CScrollBar`スタック上のオブジェクトは自動的に破棄します。 作成する場合、`CScrollBar`を使用して、ヒープ上のオブジェクト、**新しい**関数を呼び出す必要があります**削除**をユーザーが Windows のスクロール バーが終了するときに破棄するオブジェクト。

メモリを割り当てることがある場合、`CScrollBar`オブジェクト、オーバーライド、`CScrollBar`デストラクターの割り当てを破棄します。

使用しての詳細については`CScrollBar`を参照してください[コントロール](../../mfc/controls-mfc.md)します。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CScrollBar`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxwin.h

##  <a name="create"></a>  CScrollBar::Create

Windows のスクロール バーを作成しにアタッチします、`CScrollBar`オブジェクト。

```
virtual BOOL Create(
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>パラメーター

*dwStyle*<br/>
スクロールを指定します。 バーのスタイル。 任意の組み合わせを適用[スクロール バー スタイル](../../mfc/reference/styles-used-by-mfc.md#scroll-bar-styles)スクロール バーにします。

*rect*<br/>
スクロール バーのサイズと位置を指定します。 いずれかになります、`RECT`構造または`CRect`オブジェクト。

*pParentWnd*<br/>
スクロールを指定します。 バーの親ウィンドウ、通常、`CDialog`オブジェクト。 NULL は指定できません。

*nID*<br/>
スクロール バーのコントロール id です。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>Remarks

構築する、 `CScrollBar` 2 つのステップ内のオブジェクト。 最初に、構築するコンス トラクターを呼び出し、`CScrollBar`オブジェクト; 呼び出して`Create`が作成し、関連付けられている Windows のスクロール バーが初期化されにアタッチします、`CScrollBar`オブジェクト。

次の適用[ウィンドウ スタイル](../../mfc/reference/styles-used-by-mfc.md#window-styles)スクロール バーに。

- WS_CHILD 常に

- WS_VISIBLE 通常

- WS_DISABLED ことはほとんどありません。

- WS_GROUP コントロールをグループ化

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CScrollBar#1](../../mfc/reference/codesnippet/cpp/cscrollbar-class_1.cpp)]

##  <a name="cscrollbar"></a>  CScrollBar::CScrollBar

`CScrollBar` オブジェクトを構築します。

```
CScrollBar();
```

### <a name="remarks"></a>Remarks

オブジェクトを構築した後、`Create`メンバー関数を作成し、Windows のスクロール バーを初期化します。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CScrollBar#2](../../mfc/reference/codesnippet/cpp/cscrollbar-class_2.h)]

##  <a name="enablescrollbar"></a>  CScrollBar::EnableScrollBar

スクロール バーの矢印の一方または両方を有効または無効にします。

```
BOOL EnableScrollBar(UINT nArrowFlags = ESB_ENABLE_BOTH);
```

### <a name="parameters"></a>パラメーター

*nArrowFlags*<br/>
どちらの矢印は、有効または無効にし、スクロール バーの矢印を有効または無効にするかどうかを指定します。 このパラメーターには、次の値のいずれかを指定できます。

- ESB_ENABLE_BOTH では、両方のスクロール バーの矢印を使用できます。

- ESB_DISABLE_LTUP には、水平スクロール バーの左の方向または垂直スクロール バーの上向きの矢印が無効にします。

- ESB_DISABLE_RTDN には、水平スクロール バーの右矢印ボタンまたは垂直スクロール バーの下向きの矢印が無効にします。

- ESB_DISABLE_BOTH には、両方のスクロール バーの矢印が無効にします。

### <a name="return-value"></a>戻り値

矢印が有効になっているまたは; 指定された無効になっている場合、0 以外の場合それ以外の場合 0-矢印が、まだは要求された状態またはエラーが発生したことを示します。

### <a name="example"></a>例

  例をご覧ください[CScrollBar::SetScrollRange](#setscrollrange)します。

##  <a name="getscrollbarinfo"></a>  CScrollBar::GetScrollBarInfo

`SCROLLBARINFO` 構造体がスクロール バーについて保持している情報を取得します。

```
BOOL GetScrollBarInfo(PSCROLLBARINFO pScrollInfo) const;
```

### <a name="parameters"></a>パラメーター

*pScrollInfo*<br/>
ポインター、 [SCROLLBARINFO](/windows/desktop/api/winuser/ns-winuser-tagscrollbarinfo)構造体。

### <a name="return-value"></a>戻り値

成功した場合、true を返します。

### <a name="remarks"></a>Remarks

このメンバー関数の機能をエミュレートする、 [SBM_SCROLLBARINFO](/windows/desktop/Controls/sbm-getscrollbarinfo)メッセージ、Windows SDK で説明されているとします。

##  <a name="getscrollinfo"></a>  CScrollBar::GetScrollInfo

`SCROLLINFO` 構造体がスクロール バーについて保持している情報を取得します。

```
BOOL GetScrollInfo(
    LPSCROLLINFO lpScrollInfo,
    UINT nMask = SIF_ALL);
```

### <a name="parameters"></a>パラメーター

*lpScrollInfo*<br/>
ポインターを[SCROLLINFO](/windows/desktop/api/winuser/ns-winuser-tagscrollinfo)構造体。 この構造体の詳細については、Windows SDK を参照してください。

*いる*<br/>
取得するスクロール バーのパラメーターを指定します。 一般的な使用状況、SIF_ALL、SIF_PAGE、SIF_POS、SIF_TRACKPOS、SIF_RANGE の組み合わせを指定します。 参照してください`SCROLLINFO`いる値の詳細についてはします。

### <a name="return-value"></a>戻り値

戻り値が TRUE の場合、メッセージは、任意の値を取得します。 それ以外の場合、FALSE になります。

### <a name="remarks"></a>Remarks

`GetScrollInfo` 32 ビットのスクロール位置を使用するアプリケーションを有効にします。

[SCROLLINFO](/windows/desktop/api/winuser/ns-winuser-tagscrollinfo)構造体には、スクロール バーの最小値と最大スクロール位置、ページ サイズおよびスクロール ボックス (つまみ) の位置などに関する情報が含まれています。 参照してください、`SCROLLINFO`構造」のトピックの詳細については、構造体の既定値を変更する方法について、Windows SDK。

MFC Windows メッセージ ハンドラーのスクロール バーの位置を示す[CWnd::OnHScroll](../../mfc/reference/cwnd-class.md#onhscroll)と[ために](../../mfc/reference/cwnd-class.md#onvscroll)、位置データの 16 ビットのみを提供します。 `GetScrollInfo` `SetScrollInfo` 32 ビットのスクロール バーの位置データを提供します。 したがって、アプリケーションを呼び出すことができます`GetScrollInfo`いずれかの処理中に`CWnd::OnHScroll`または`CWnd::OnVScroll`32 ビットのスクロール バーの位置データを取得します。

### <a name="example"></a>例

  例をご覧ください[CWnd::OnHScroll](../../mfc/reference/cwnd-class.md#onhscroll)します。

##  <a name="getscrolllimit"></a>  CScrollBar::GetScrollLimit

最大スクロールのスクロール バーの位置を取得します。

```
int GetScrollLimit();
```

### <a name="return-value"></a>戻り値

成功した場合は、スクロール バーの最大の位置を指定しますそれ以外の場合 0 を返します。

### <a name="example"></a>例

  例をご覧ください[CWnd::OnHScroll](../../mfc/reference/cwnd-class.md#onhscroll)します。

##  <a name="getscrollpos"></a>  CScrollBar::GetScrollPos

スクロール ボックスの現在位置を取得します。

```
int GetScrollPos() const;
```

### <a name="return-value"></a>戻り値

成功した場合のスクロール ボックスの現在位置を指定しますそれ以外の場合 0 を返します。

### <a name="remarks"></a>Remarks

現在の位置は、現在のスクロール範囲に依存する相対値です。 たとえば、スクロールの範囲は 100 ~ 200 のスクロール ボックスが、バーの中では、現在の位置は 150 です。

### <a name="example"></a>例

  例をご覧ください[CWnd::OnHScroll](../../mfc/reference/cwnd-class.md#onhscroll)します。

##  <a name="getscrollrange"></a>  CScrollBar::GetScrollRange

指定された場所にコピーして、指定されたスクロール バーの現在の最小値と最大のスクロール バーの位置*lpMinPos*と*最大位置*します。

```
void GetScrollRange(
    LPINT lpMinPos,
    LPINT lpMaxPos) const;
```

### <a name="parameters"></a>パラメーター

*lpMinPos*<br/>
最小の位置を受け取る整数変数を指します。

*lpMaxPos*<br/>
最大の位置を受け取る整数変数を指します。

### <a name="remarks"></a>Remarks

スクロール バー コントロールの既定の範囲が空 (両方の値は 0)。

### <a name="example"></a>例

  例をご覧ください[CWnd::OnHScroll](../../mfc/reference/cwnd-class.md#onhscroll)します。

##  <a name="setscrollinfo"></a>  CScrollBar::SetScrollInfo

情報の設定、`SCROLLINFO`構造体がスクロール バーについて保持します。

```
BOOL SetScrollInfo(
    LPSCROLLINFO lpScrollInfo,
    BOOL bRedraw = TRUE);
```

### <a name="parameters"></a>パラメーター

*lpScrollInfo*<br/>
ポインターを[SCROLLINFO](/windows/desktop/api/winuser/ns-winuser-tagscrollinfo)構造体。

*bRedraw*<br/>
スクロール バーが、新しい情報を反映するように再描画が必要かどうかを指定します。 場合*bRedraw*が true の場合、スクロール バーが再描画します。 FALSE の場合は描画されません。 既定では、スクロール バーが再描画されます。

### <a name="return-value"></a>戻り値

成功した場合、戻り値は TRUE です。 それ以外の場合、FALSE になります。

### <a name="remarks"></a>Remarks

必要な値を指定する必要があります、`SCROLLINFO`フラグの値を含むパラメーターは、構造体します。

`SCROLLINFO`構造体には、スクロール バーの最小値と最大スクロール位置、ページ サイズおよびスクロール ボックス (つまみ) の位置などに関する情報が含まれています。 参照してください、 [SCROLLINFO](/windows/desktop/api/winuser/ns-winuser-tagscrollinfo)構造」のトピックの詳細については、構造体の既定値を変更する方法について、Windows SDK。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CScrollBar#3](../../mfc/reference/codesnippet/cpp/cscrollbar-class_3.cpp)]

##  <a name="setscrollpos"></a>  CScrollBar::SetScrollPos

スクロール ボックスの現在の位置に設定で指定されている*nPos*し、指定した場合は、新しい位置を反映するように、スクロール バーを再描画します。

```
int SetScrollPos(
    int nPos,
    BOOL bRedraw = TRUE);
```

### <a name="parameters"></a>パラメーター

*nPos*<br/>
スクロール ボックスの新しい位置を指定します。 スクロールの範囲でなければなりません。

*bRedraw*<br/>
スクロール バーが新しい位置を反映するように再描画が必要かどうかを指定します。 場合*bRedraw*が true の場合、スクロール バーが再描画します。 FALSE の場合は描画されません。 既定では、スクロール バーが再描画されます。

### <a name="return-value"></a>戻り値

成功した場合のスクロール ボックスの前の位置を指定しますそれ以外の場合 0 を返します。

### <a name="remarks"></a>Remarks

設定*bRedraw*を FALSE にされるたびに、スクロール バーが再描画されますを回避すること、短い間隔内で 2 回再描画するスクロール バーを別の関数の後続の呼び出しで。

### <a name="example"></a>例

  例をご覧ください[CScrollBar::SetScrollRange](#setscrollrange)します。

##  <a name="setscrollrange"></a>  CScrollBar::SetScrollRange

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

*とき*<br/>
最大スクロール位置を指定します。

*bRedraw*<br/>
スクロール バーが、変更を反映するように再描画が必要かどうかを指定します。 場合*bRedraw*が true の場合、スクロール バーが再描画されます。 FALSE の場合は描画されません。 これは既定で再描画されます。

### <a name="remarks"></a>Remarks

設定*nMinPos*と*とき*標準スクロール バーを非表示にします。

スクロール バーの通知メッセージの処理中に、スクロール バーを非表示にするには、この関数を呼び出さないでください。

呼び出し`SetScrollRange`への呼び出しの直後に、`SetScrollPos`メンバー関数は、設定*bRedraw*で`SetScrollPos`スクロール バーが 2 回再描画されることを防ぐために 0 にします。

指定された値の差*nMinPos*と*とき*32,767 を超えていない必要があります。 スクロール バー コントロールの既定の範囲が空 (両方*nMinPos*と*とき*は 0)。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CScrollBar#4](../../mfc/reference/codesnippet/cpp/cscrollbar-class_4.cpp)]

##  <a name="showscrollbar"></a>  CScrollBar::ShowScrollBar

スクロール バーの表示と非表示を切り替えます。

```
void ShowScrollBar(BOOL bShow = TRUE);
```

### <a name="parameters"></a>パラメーター

*bShow*<br/>
スクロール バーを表示するか非表示かどうかを指定します。 このパラメーターが TRUE の場合、スクロール バーが表示されます。それ以外の場合は表示されません。

### <a name="remarks"></a>Remarks

アプリケーションは、スクロール バーの通知メッセージの処理中に、スクロール バーを非表示にするには、この関数を呼び出さないでください。

### <a name="example"></a>例

  例をご覧ください[CScrollBar::Create](#create)します。

## <a name="see-also"></a>関連項目

[CWnd クラス](../../mfc/reference/cwnd-class.md)<br/>
[階層図](../../mfc/hierarchy-chart.md)<br/>
[CWnd クラス](../../mfc/reference/cwnd-class.md)<br/>
[CButton クラス](../../mfc/reference/cbutton-class.md)<br/>
[CComboBox クラス](../../mfc/reference/ccombobox-class.md)<br/>
[CEdit クラス](../../mfc/reference/cedit-class.md)<br/>
[CListBox クラス](../../mfc/reference/clistbox-class.md)<br/>
[CStatic クラス](../../mfc/reference/cstatic-class.md)<br/>
[CDialog クラス](../../mfc/reference/cdialog-class.md)

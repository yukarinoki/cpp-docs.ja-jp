---
title: クラス
ms.date: 11/04/2016
f1_keywords:
- CSliderCtrl
- AFXCMN/CSliderCtrl
- AFXCMN/CSliderCtrl::CSliderCtrl
- AFXCMN/CSliderCtrl::ClearSel
- AFXCMN/CSliderCtrl::ClearTics
- AFXCMN/CSliderCtrl::Create
- AFXCMN/CSliderCtrl::CreateEx
- AFXCMN/CSliderCtrl::GetBuddy
- AFXCMN/CSliderCtrl::GetChannelRect
- AFXCMN/CSliderCtrl::GetLineSize
- AFXCMN/CSliderCtrl::GetNumTics
- AFXCMN/CSliderCtrl::GetPageSize
- AFXCMN/CSliderCtrl::GetPos
- AFXCMN/CSliderCtrl::GetRange
- AFXCMN/CSliderCtrl::GetRangeMax
- AFXCMN/CSliderCtrl::GetRangeMin
- AFXCMN/CSliderCtrl::GetSelection
- AFXCMN/CSliderCtrl::GetThumbLength
- AFXCMN/CSliderCtrl::GetThumbRect
- AFXCMN/CSliderCtrl::GetTic
- AFXCMN/CSliderCtrl::GetTicArray
- AFXCMN/CSliderCtrl::GetTicPos
- AFXCMN/CSliderCtrl::GetToolTips
- AFXCMN/CSliderCtrl::SetBuddy
- AFXCMN/CSliderCtrl::SetLineSize
- AFXCMN/CSliderCtrl::SetPageSize
- AFXCMN/CSliderCtrl::SetPos
- AFXCMN/CSliderCtrl::SetRange
- AFXCMN/CSliderCtrl::SetRangeMax
- AFXCMN/CSliderCtrl::SetRangeMin
- AFXCMN/CSliderCtrl::SetSelection
- AFXCMN/CSliderCtrl::SetThumbLength
- AFXCMN/CSliderCtrl::SetTic
- AFXCMN/CSliderCtrl::SetTicFreq
- AFXCMN/CSliderCtrl::SetTipSide
- AFXCMN/CSliderCtrl::SetToolTips
helpviewer_keywords:
- CSliderCtrl [MFC], CSliderCtrl
- CSliderCtrl [MFC], ClearSel
- CSliderCtrl [MFC], ClearTics
- CSliderCtrl [MFC], Create
- CSliderCtrl [MFC], CreateEx
- CSliderCtrl [MFC], GetBuddy
- CSliderCtrl [MFC], GetChannelRect
- CSliderCtrl [MFC], GetLineSize
- CSliderCtrl [MFC], GetNumTics
- CSliderCtrl [MFC], GetPageSize
- CSliderCtrl [MFC], GetPos
- CSliderCtrl [MFC], GetRange
- CSliderCtrl [MFC], GetRangeMax
- CSliderCtrl [MFC], GetRangeMin
- CSliderCtrl [MFC], GetSelection
- CSliderCtrl [MFC], GetThumbLength
- CSliderCtrl [MFC], GetThumbRect
- CSliderCtrl [MFC], GetTic
- CSliderCtrl [MFC], GetTicArray
- CSliderCtrl [MFC], GetTicPos
- CSliderCtrl [MFC], GetToolTips
- CSliderCtrl [MFC], SetBuddy
- CSliderCtrl [MFC], SetLineSize
- CSliderCtrl [MFC], SetPageSize
- CSliderCtrl [MFC], SetPos
- CSliderCtrl [MFC], SetRange
- CSliderCtrl [MFC], SetRangeMax
- CSliderCtrl [MFC], SetRangeMin
- CSliderCtrl [MFC], SetSelection
- CSliderCtrl [MFC], SetThumbLength
- CSliderCtrl [MFC], SetTic
- CSliderCtrl [MFC], SetTicFreq
- CSliderCtrl [MFC], SetTipSide
- CSliderCtrl [MFC], SetToolTips
ms.assetid: dd12b084-4eda-4550-a810-8f3cfb06b871
ms.openlocfilehash: 2e3572b34f930bb6a7d99b437c01c8aaf970e6c3
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "81751277"
---
# <a name="csliderctrl-class"></a>クラス

Windows コモン スライダー コントロールの機能を提供します。

## <a name="syntax"></a>構文

```
class CSliderCtrl : public CWnd
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CスライダーCtrl::CスライダーCtrl](#csliderctrl)|`CSliderCtrl` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CスライダーCtrl::クリアセル](#clearsel)|スライダー コントロールの現在の選択範囲をクリアします。|
|[CスライダーCtrl::クリアティクス](#cleartics)|スライダー コントロールから現在の目盛りを削除します。|
|[CスライダーCtrl::作成](#create)|スライダー コントロールを作成し、`CSliderCtrl`オブジェクトにアタッチします。|
|[CスライダーCtrl::作成します。](#createex)|指定した Windows 拡張スタイルを使用してスライダー コントロールを作成し`CSliderCtrl`、オブジェクトにアタッチします。|
|[CスライダーCtrl::ゲットバディ](#getbuddy)|指定した位置にあるスライダー コントロールの関連ウィンドウへのハンドルを取得します。|
|[をクリックします。](#getchannelrect)|スライダー コントロールのチャネルのサイズを取得します。|
|[次の値を指定します。](#getlinesize)|スライダー コントロールの行サイズを取得します。|
|[CスライダーCtrl::ゲットナムティクス](#getnumtics)|スライダー コントロールの目盛りの数を取得します。|
|[をクリックします。](#getpagesize)|スライダー コントロールのページ サイズを取得します。|
|[をクリックします。](#getpos)|スライダーの現在の位置を取得します。|
|[をクリックします。](#getrange)|スライダーの最小位置と最大位置を取得します。|
|[をクリックします。](#getrangemax)|スライダーの最大位置を取得します。|
|[CスライダーCtrl::ゲットレンジミン](#getrangemin)|スライダーの最小位置を取得します。|
|[を選択します。](#getselection)|現在の選択範囲の範囲を取得します。|
|[をクリックします。](#getthumblength)|現在のトラック バー コントロールのスライダーの長さを取得します。|
|[をクリックします。](#getthumbrect)|スライダー コントロールのつまみのサイズを取得します。|
|[コメティックCtrl::ゲティック](#gettic)|指定された目盛りの位置を取得します。|
|[をクリックします。](#getticarray)|スライダー コントロールの目盛りの位置の配列を取得します。|
|[コティスティックポス](#getticpos)|クライアント座標で指定された目盛りの位置を取得します。|
|[ヒントを取得します。](#gettooltips)|スライダー コントロールに割り当てられているツールヒント コントロールのハンドルを取得します (存在する場合)。|
|[CスライダーCtrl::セットバディ](#setbuddy)|ウィンドウをスライダー コントロールの対応ウィンドウとして割り当てます。|
|[をクリックします。](#setlinesize)|スライダー コントロールの線のサイズを設定します。|
|[をクリックします。](#setpagesize)|スライダー コントロールのページ サイズを設定します。|
|[CスライダーCtrl::セットポス](#setpos)|スライダーの現在位置を設定します。|
|[をクリックします。](#setrange)|スライダーの最小位置と最大位置を設定します。|
|[をクリックします。](#setrangemax)|スライダーの最大位置を設定します。|
|[CスライダーCtrl::セットレンジミン](#setrangemin)|スライダーの最小位置を設定します。|
|[を選択します。](#setselection)|現在の選択範囲の範囲を設定します。|
|[を設定します。](#setthumblength)|現在のトラックバー コントロールのスライダーの長さを設定します。|
|[CスライダーCtrl::セットティック](#settic)|指定された目盛りの位置を設定します。|
|[CスライダーCtrl::セットティックフレク](#setticfreq)|スライダー コントロールインクリメントあたりの目盛りの頻度を設定します。|
|[CスライダーCtrl::セットチップサイド](#settipside)|トラック バー コントロールで使用されるツールヒント コントロールを配置します。|
|[ヒントを設定します。](#settooltips)|ツールヒント コントロールをスライダー コントロールに割り当てます。|

## <a name="remarks"></a>解説

"スライダー コントロール" (トラック バーとも呼ばれる) は、スライダーとオプションの目盛りを含むウィンドウです。 ユーザーがマウスまたは方向キーを使用してスライダーを移動すると、コントロールは変更を示す通知メッセージを送信します。

スライダー コントロールは、ユーザーが範囲内の個別の値または連続する値のセットを選択する場合に便利です。 たとえば、スライダー コントロールを使用して、スライダーを特定の目盛りに移動して、キーボードの繰り返しレートを設定できます。

このコントロール (および`CSliderCtrl`クラス) は、Windows 95/98 および Windows NT バージョン 3.51 以降で実行されているプログラムでのみ使用できます。

スライダーは、作成時に指定した増分で移動します。 たとえば、スライダーの範囲を 5 に指定した場合、スライダーはスライダー コントロールの左側の位置と範囲内の増分ごとに 1 つの位置の 6 つの位置のみを占めることができます。 通常、これらの位置は目盛で識別されます。

スライダを作成する場合は、 のコンストラクター`Create`とメンバー関数`CSliderCtrl`を使用します。 スライダー コントロールを作成したら、 で`CSliderCtrl`メンバー関数を使用して、そのプロパティの多くを変更できます。 変更には、スライダーの最小位置と最大位置の設定、目盛りの描画、選択範囲の設定、スライダーの位置変更などがあります。

の詳細`CSliderCtrl`については、「[コントロール](../../mfc/controls-mfc.md)」および[「CSliderCtrl を使用する](../../mfc/using-csliderctrl.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CSliderCtrl`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxcmn.h

## <a name="csliderctrlclearsel"></a><a name="clearsel"></a>CスライダーCtrl::クリアセル

スライダー コントロールの現在の選択範囲をクリアします。

```cpp
void ClearSel(BOOL bRedraw = FALSE);
```

### <a name="parameters"></a>パラメーター

*引き出し*<br/>
フラグを再描画します。 このパラメーターが TRUE の場合、選択範囲がクリアされた後にスライダーが再描画されます。それ以外の場合、スライダーは再描画されません。

## <a name="csliderctrlcleartics"></a><a name="cleartics"></a>CスライダーCtrl::クリアティクス

スライダー コントロールから現在の目盛りを削除します。

```cpp
void ClearTics(BOOL bRedraw = FALSE);
```

### <a name="parameters"></a>パラメーター

*引き出し*<br/>
フラグを再描画します。 このパラメーターが TRUE の場合、目盛りがクリアされた後にスライダーが再描画されます。それ以外の場合、スライダーは再描画されません。

## <a name="csliderctrlcreate"></a><a name="create"></a>CスライダーCtrl::作成

スライダー コントロールを作成し、`CSliderCtrl`オブジェクトにアタッチします。

```
virtual BOOL Create(
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>パラメーター

*Dwstyle*<br/>
スライダー コントロールのスタイルを指定します。 Windows SDK で説明されている[スライダー コントロール スタイル](/windows/win32/Controls/trackbar-control-styles)の任意の組み合わせをコントロールに適用します。

*Rect*<br/>
スライダー コントロールのサイズと位置を指定します。 [CRect](../../atl-mfc-shared/reference/crect-class.md)オブジェクトまたは[RECT](/windows/win32/api/windef/ns-windef-rect)構造体を指定できます。

*pParentWnd*<br/>
スライダー コントロールの親ウィンドウを指定します`CDialog`。 NULL にすることはできません。

*nID*<br/>
スライダー コントロールの ID を指定します。

### <a name="return-value"></a>戻り値

初期化が成功した場合は 0 以外。それ以外の場合は 0。

### <a name="remarks"></a>解説

を`CSliderCtrl`2 つの手順で作成します。 まず、コンストラクターを呼び出し、`Create`次に`CSliderCtrl`を呼び出します。

*dwStyle*に設定された値に応じて、スライダー コントロールは垂直方向または水平方向のいずれかに設定できます。 どちらの側にも目盛りが付いているか、両側に刻印が付いているか、どちらにも目盛りが付けることもできます。 連続する値の範囲を指定するためにも使用できます。

拡張ウィンドウ スタイルをスライダー コントロールに適用するには、 の代`Create`わりに[CreateEx](#createex)を呼び出します。

## <a name="csliderctrlcreateex"></a><a name="createex"></a>CスライダーCtrl::作成します。

コントロール (子ウィンドウ) を作成し、オブジェクトに関連`CSliderCtrl`付けます。

```
virtual BOOL CreateEx(
    DWORD dwExStyle,
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>パラメーター

*ドウェエクススタイル*<br/>
作成するコントロールの拡張スタイルを指定します。 拡張 Windows スタイルの一覧については、Windows SDK の*DwExStyle*パラメーター[を](/windows/win32/api/winuser/nf-winuser-createwindowexw)参照してください。

*Dwstyle*<br/>
スライダー コントロールのスタイルを指定します。 Windows SDK で説明されている[スライダー コントロール スタイル](/windows/win32/Controls/trackbar-control-styles)の任意の組み合わせをコントロールに適用します。

*Rect*<br/>
作成するウィンドウのサイズと位置を記述する[RECT](/windows/win32/api/windef/ns-windef-rect)構造体への参照を *、 pParentWnd*のクライアント座標で指定します。

*pParentWnd*<br/>
コントロールの親であるウィンドウへのポインター。

*nID*<br/>
コントロールの子ウィンドウ ID。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>解説

[`CreateEx`[作成]](#create)の代わりに、Windows 拡張スタイルの序文で指定された拡張 Windows スタイル**を適用WS_EX_。**

## <a name="csliderctrlcsliderctrl"></a><a name="csliderctrl"></a>CスライダーCtrl::CスライダーCtrl

`CSliderCtrl` オブジェクトを構築します。

```
CSliderCtrl();
```

## <a name="csliderctrlgetbuddy"></a><a name="getbuddy"></a>CスライダーCtrl::ゲットバディ

指定した位置にあるスライダー コントロールの関連ウィンドウへのハンドルを取得します。

```
CWnd* GetBuddy(BOOL fLocation = TRUE) const;
```

### <a name="parameters"></a>パラメーター

*fロケーション*<br/>
取得する 2 つの関連ウィンドウ ハンドルのどちらを示すブール値。 次の値のいずれかです。

- TRUE スライダーの左側にある関連ハンドルを取得します。 スライダー コントロールでTBS_VERTスタイルを使用している場合、メッセージはスライダーの上にある関連付けを取得します。

- FALSE スライダーの右側にある関連するハンドルを取得します。 スライダー コントロールでTBS_VERTスタイルを使用している場合、メッセージはスライダーの下にある関連付けを取得します。

### <a name="return-value"></a>戻り値

*fLocation*で指定された位置にある、その位置にバディ ウィンドウが存在しない場合は NULL を指定する[CWnd](../../mfc/reference/cwnd-class.md)オブジェクトへのポインター。

### <a name="remarks"></a>解説

このメンバー関数は、Windows SDK で説明されているように、Win32 メッセージ[TBM_GETBUDDY](/windows/win32/Controls/tbm-getbuddy)の動作を実装します。 スライダー コントロールスタイルの詳細については、Windows SDK の[トラックバー コントロール スタイル](/windows/win32/Controls/trackbar-control-styles)を参照してください。

## <a name="csliderctrlgetchannelrect"></a><a name="getchannelrect"></a>をクリックします。

スライダー コントロールのチャネルに外接する四角形のサイズと位置を取得します。

```cpp
void GetChannelRect(LPRECT lprc) const;
```

### <a name="parameters"></a>パラメーター

*Lprc*<br/>
関数が返されるときに、チャネルの外接する四角形のサイズと位置を格納する[CRect](../../atl-mfc-shared/reference/crect-class.md)オブジェクトへのポインター。

### <a name="remarks"></a>解説

チャンネルは、スライダーが移動する領域で、範囲が選択されたときにハイライトが含まれます。

## <a name="csliderctrlgetlinesize"></a><a name="getlinesize"></a>次の値を指定します。

スライダー コントロールの行のサイズを取得します。

```
int GetLineSize() const;
```

### <a name="return-value"></a>戻り値

スライダー コントロールの線のサイズ。

### <a name="remarks"></a>解説

行のサイズは、TB_LINEUPとTB_LINEDOWN通知のスライダーの動きに影響します。 ライン サイズのデフォルト設定は 1 です。

## <a name="csliderctrlgetnumtics"></a><a name="getnumtics"></a>CスライダーCtrl::ゲットナムティクス

スライダー コントロールの目盛りの数を取得します。

```
UINT GetNumTics() const;
```

### <a name="return-value"></a>戻り値

スライダー コントロールの目盛りの数。

## <a name="csliderctrlgetpagesize"></a><a name="getpagesize"></a>をクリックします。

スライダー コントロールのページのサイズを取得します。

```
int GetPageSize() const;
```

### <a name="return-value"></a>戻り値

スライダー コントロールのページのサイズ。

### <a name="remarks"></a>解説

ページ サイズは、TB_PAGEUPとTB_PAGEDOWN通知のスライダーの動きに影響します。

## <a name="csliderctrlgetpos"></a><a name="getpos"></a>をクリックします。

スライダー コントロール内のスライダーの現在の位置を取得します。

```
int GetPos() const;
```

### <a name="return-value"></a>戻り値

現在位置を返します。

## <a name="csliderctrlgetrange"></a><a name="getrange"></a>をクリックします。

スライダー コントロール内のスライダーの最大位置と最小位置を取得します。

```cpp
void GetRange(
    int& nMin,
    int& nMax) const;
```

### <a name="parameters"></a>パラメーター

*nMin*<br/>
最小位置を受け取る整数への参照。

*nMax*<br/>
最大位置を受け取る整数への参照。

### <a name="remarks"></a>解説

この関数は *、nMin*と*nMax*によって参照される整数に値をコピーします。

## <a name="csliderctrlgetrangemax"></a><a name="getrangemax"></a>をクリックします。

スライダー コントロール内のスライダーの最大位置を取得します。

```
int GetRangeMax() const;
```

### <a name="return-value"></a>戻り値

コントロールの最大位置。

## <a name="csliderctrlgetrangemin"></a><a name="getrangemin"></a>CスライダーCtrl::ゲットレンジミン

スライダー コントロール内のスライダーの最小位置を取得します。

```
int GetRangeMin() const;
```

### <a name="return-value"></a>戻り値

コントロールの最小位置。

## <a name="csliderctrlgetselection"></a><a name="getselection"></a>を選択します。

スライダー コントロール内の現在の選択範囲の開始位置と終了位置を取得します。

```cpp
void GetSelection(
    int& nMin,
    int& nMax) const;
```

### <a name="parameters"></a>パラメーター

*nMin*<br/>
現在の選択範囲の開始位置を受け取る整数への参照。

*nMax*<br/>
現在の選択範囲の終了位置を受け取る整数への参照。

## <a name="csliderctrlgetthumblength"></a><a name="getthumblength"></a>をクリックします。

現在のトラック バー コントロールのスライダーの長さを取得します。

```
int GetThumbLength() const;
```

### <a name="return-value"></a>戻り値

スライダーの長さ (ピクセル単位)。

### <a name="remarks"></a>解説

このメソッドは、Windows SDK で説明されている[TBM_GETTHUMBLENGTH](/windows/win32/Controls/tbm-getthumblength)メッセージを送信します。

## <a name="csliderctrlgetthumbrect"></a><a name="getthumbrect"></a>をクリックします。

スライダー コントロールのスライダー (つまみ) に外接する四角形のサイズと位置を取得します。

```cpp
void GetThumbRect(LPRECT lprc) const;
```

### <a name="parameters"></a>パラメーター

*Lprc*<br/>
関数が`CRect`返されるときに、スライダーの外接する四角形を含むオブジェクトへのポインター。

## <a name="csliderctrlgettic"></a><a name="gettic"></a>コメティックCtrl::ゲティック

スライダー コントロール内の目盛りの位置を取得します。

```
int GetTic(int nTic) const;
```

### <a name="parameters"></a>パラメーター

*ntic*<br/>
目盛りを識別する 0 から始まるインデックス。

### <a name="return-value"></a>戻り値

nTic が有効なインデックスを指定しない場合*nTic*は、指定された目盛りの位置を指定します。

## <a name="csliderctrlgetticarray"></a><a name="getticarray"></a>をクリックします。

スライダー コントロールの目盛りの位置を含む配列のアドレスを取得します。

```
DWORD* GetTicArray() const;
```

### <a name="return-value"></a>戻り値

スライダー コントロールの目盛りの位置を含む配列のアドレス。

## <a name="csliderctrlgetticpos"></a><a name="getticpos"></a>コティスティックポス

スライダー コントロールの目盛りの現在の物理的な位置を取得します。

```
int GetTicPos(int nTic) const;
```

### <a name="parameters"></a>パラメーター

*ntic*<br/>
目盛りを識別する 0 から始まるインデックス。

### <a name="return-value"></a>戻り値

指定された目盛りの物理的位置 (クライアント座標) または*nTic*が有効なインデックスを指定しない場合は - 1。

## <a name="csliderctrlgettooltips"></a><a name="gettooltips"></a>ヒントを取得します。

スライダー コントロールに割り当てられているツールヒント コントロールのハンドルを取得します (存在する場合)。

```
CToolTipCtrl* GetToolTips() const;
```

### <a name="return-value"></a>戻り値

[CToolTipCtrl](../../mfc/reference/ctooltipctrl-class.md)オブジェクトへのポインター、またはツールヒントが使用されていない場合は NULL。 スライダー コントロールでTBS_TOOLTIPS スタイルを使用しない場合、戻り値は NULL になります。

### <a name="remarks"></a>解説

このメンバー関数は、Windows SDK で説明されているように、Win32 メッセージ[TBM_GETTOOLTIPS](/windows/win32/Controls/tbm-gettooltips)の動作を実装します。 このメンバー関数は、コントロールへの`CToolTipCtrl`ハンドルではなくオブジェクトを返します。

スライダー コントロールスタイルの詳細については、Windows SDK の[トラックバー コントロール スタイル](/windows/win32/Controls/trackbar-control-styles)を参照してください。

## <a name="csliderctrlsetbuddy"></a><a name="setbuddy"></a>CスライダーCtrl::セットバディ

ウィンドウをスライダー コントロールの対応ウィンドウとして割り当てます。

```
CWnd* SetBuddy(
    CWnd* pWndBuddy,
    BOOL fLocation = TRUE);
```

### <a name="parameters"></a>パラメーター

*ド・ド・バ*<br/>
スライダー コントロールの`CWnd`対応するオブジェクトへのポインター。

*fロケーション*<br/>
[相棒] ウィンドウを表示する位置を指定する値。 この値は、次のいずれかです。

- TRUE トラックバー コントロールがTBS_HORZスタイルを使用している場合、トラックバーの左側に関連付けが表示されます。 トラックバーがTBS_VERTスタイルを使用している場合、トラックバーコントロールの上に同じコントロールが表示されます。

- トラックバーコントロールがTBS_HORZスタイルを使用している場合、トラックバーの右側にバディが表示されます。 トラックバーがTBS_VERTスタイルを使用している場合、トラックバーコントロールの下に関連付けが表示されます。

### <a name="return-value"></a>戻り値

その位置にあるスライダー コントロールに割り当てられた[CWnd](../../mfc/reference/cwnd-class.md)オブジェクトへのポインター。

### <a name="remarks"></a>解説

このメンバー関数は、Windows SDK で説明されているように、Win32 メッセージ[TBM_SETBUDDY](/windows/win32/Controls/tbm-setbuddy)の動作を実装します。 このメンバー関数は、戻り値と`CWnd`パラメーターの両方にウィンドウ ハンドルではなく、オブジェクトへのポインターを使用することに注意してください。

スライダー コントロールスタイルの詳細については、Windows SDK の[トラックバー コントロール スタイル](/windows/win32/Controls/trackbar-control-styles)を参照してください。

## <a name="csliderctrlsetlinesize"></a><a name="setlinesize"></a>をクリックします。

スライダー コントロールの線のサイズを設定します。

```
int SetLineSize(int nSize);
```

### <a name="parameters"></a>パラメーター

*Nsize*<br/>
スライダー コントロールの新しい行サイズ。

### <a name="return-value"></a>戻り値

前の行のサイズ。

### <a name="remarks"></a>解説

行のサイズは、TB_LINEUPとTB_LINEDOWN通知のスライダーの動きに影響します。

## <a name="csliderctrlsetpagesize"></a><a name="setpagesize"></a>をクリックします。

スライダー コントロールのページのサイズを設定します。

```
int SetPageSize(int nSize);
```

### <a name="parameters"></a>パラメーター

*Nsize*<br/>
スライダー コントロールの新しいページ サイズ。

### <a name="return-value"></a>戻り値

前のページ サイズ。

### <a name="remarks"></a>解説

ページ サイズは、TB_PAGEUPとTB_PAGEDOWN通知のスライダーの動きに影響します。

## <a name="csliderctrlsetpos"></a><a name="setpos"></a>CスライダーCtrl::セットポス

スライダー コントロールのスライダーの現在位置を設定します。

```cpp
void SetPos(int nPos);
```

### <a name="parameters"></a>パラメーター

*Npo*<br/>
新しいスライダの位置を指定します。

## <a name="csliderctrlsetrange"></a><a name="setrange"></a>をクリックします。

スライダー コントロールのスライダーの範囲 (最小位置と最大位置) を設定します。

```cpp
void SetRange(
    int nMin,
    int nMax,
    BOOL bRedraw = FALSE);
```

### <a name="parameters"></a>パラメーター

*nMin*<br/>
スライダーの最小位置。

*nMax*<br/>
スライダーの最大位置。

*引き出し*<br/>
再描画フラグ。 このパラメーターが TRUE の場合、スライダーは範囲が設定された後に再描画されます。それ以外の場合、スライダーは再描画されません。

## <a name="csliderctrlsetrangemax"></a><a name="setrangemax"></a>をクリックします。

スライダー コントロールのスライダーの最大範囲を設定します。

```cpp
void SetRangeMax(
    int nMax,
    BOOL bRedraw = FALSE);
```

### <a name="parameters"></a>パラメーター

*nMax*<br/>
スライダーの最大位置。

*引き出し*<br/>
再描画フラグ。 このパラメーターが TRUE の場合、スライダーは範囲が設定された後に再描画されます。それ以外の場合、スライダーは再描画されません。

## <a name="csliderctrlsetrangemin"></a><a name="setrangemin"></a>CスライダーCtrl::セットレンジミン

スライダー コントロールのスライダーの最小範囲を設定します。

```cpp
void SetRangeMin(
    int nMin,
    BOOL bRedraw = FALSE);
```

### <a name="parameters"></a>パラメーター

*nMin*<br/>
スライダーの最小位置。

*引き出し*<br/>
再描画フラグ。 このパラメーターが TRUE の場合、スライダーは範囲が設定された後に再描画されます。それ以外の場合、スライダーは再描画されません。

## <a name="csliderctrlsetselection"></a><a name="setselection"></a>を選択します。

スライダー コントロールの現在の選択範囲の開始位置と終了位置を設定します。

```cpp
void SetSelection(
    int nMin,
    int nMax);
```

### <a name="parameters"></a>パラメーター

*nMin*<br/>
スライダーの開始位置。

*nMax*<br/>
スライダーの終了位置。

## <a name="csliderctrlsetthumblength"></a><a name="setthumblength"></a>を設定します。

現在のトラックバー コントロールのスライダーの長さを設定します。

```cpp
void SetThumbLength(int nLength);
```

### <a name="parameters"></a>パラメーター

|パラメーター|説明|
|---------------|-----------------|
|*nレングス*|[in]スライダーの長さ (ピクセル単位)。|

### <a name="remarks"></a>解説

このメソッドでは、トラック バー コントロールを[TBS_FIXEDLENGTH](/windows/win32/Controls/trackbar-control-styles)スタイルに設定する必要があります。

このメソッドは、Windows SDK に記載されている[TBM_SETTHUMBLENGTH](/windows/win32/Controls/tbm-setthumblength)メッセージを送信します。

### <a name="example"></a>例

次のコード例では、`m_sliderCtrl`現在のトラックバー コントロールにアクセスするために使用される変数 を定義します。 また、`thumbLength`トラックバー コントロールのサム コンポーネントの既定の長さを格納するために使用される変数を定義します。 これらの変数は、次の例で使用されます。

[!code-cpp[NVC_MFC_CSliderCtrl_s1#1](../../mfc/reference/codesnippet/cpp/csliderctrl-class_1.h)]

### <a name="example"></a>例

トラックバー コントロールのつまみコンポーネントを既定の長さの 2 倍に設定するコード例を次に示します。

[!code-cpp[NVC_MFC_CSliderCtrl_s1#2](../../mfc/reference/codesnippet/cpp/csliderctrl-class_2.cpp)]

## <a name="csliderctrlsettic"></a><a name="settic"></a>CスライダーCtrl::セットティック

スライダー コントロールの目盛りの位置を設定します。

```
BOOL SetTic(int nTic);
```

### <a name="parameters"></a>パラメーター

*ntic*<br/>
目盛りの位置。 このパラメーターには正の値を指定する必要があります。

### <a name="return-value"></a>戻り値

目盛が設定されている場合は 0 以外の値を返します。それ以外の場合は 0。

## <a name="csliderctrlsetticfreq"></a><a name="setticfreq"></a>CスライダーCtrl::セットティックフレク

スライダーで目盛りを表示する頻度を設定します。

```cpp
void SetTicFreq(int nFreq);
```

### <a name="parameters"></a>パラメーター

*ニスフレク*<br/>
目盛りの頻度。

### <a name="remarks"></a>解説

たとえば、周波数が 2 に設定されている場合、スライダーの範囲内の増分ごとに目盛りが表示されます。 頻度のデフォルト設定は 1 です (つまり、範囲内のすべての増分が目盛りに関連付けられます)。

この関数を使用するには、TBS_AUTOTICKSスタイルを持つコントロールを作成する必要があります。 詳細については[、「CSliderCtrl::作成](#create)」を参照してください。

## <a name="csliderctrlsettipside"></a><a name="settipside"></a>CスライダーCtrl::セットチップサイド

トラック バー コントロールで使用されるツールヒント コントロールを配置します。

```
int SetTipSide(int nLocation);
```

### <a name="parameters"></a>パラメーター

*nロケーション*<br/>
ツールヒント コントロールを表示する位置を表す値。 使用可能な値の一覧については、Windows SDK で説明されているように、Win32 メッセージ[TBM_SETTIPSIDE](/windows/win32/Controls/tbm-settipside)を参照してください。

### <a name="return-value"></a>戻り値

ツールヒント コントロールの前の位置を表す値。 戻り値は*nLocation*に指定できる値の 1 つに等しい値です。

### <a name="remarks"></a>解説

このメンバー関数は、Windows SDK で説明されているように、Win32 メッセージ TBM_SETTIPSIDEの動作を実装します。 TBS_TOOLTIPSスタイルを使用するスライダー コントロールは、ツールチップを表示します。 スライダー コントロールスタイルの詳細については、Windows SDK の[トラックバー コントロール スタイル](/windows/win32/Controls/trackbar-control-styles)を参照してください。

## <a name="csliderctrlsettooltips"></a><a name="settooltips"></a>ヒントを設定します。

ツールヒント コントロールをスライダー コントロールに割り当てます。

```cpp
void SetToolTips(CToolTipCtrl* pWndTip);
```

### <a name="parameters"></a>パラメーター

*プーンドチップ*<br/>
スライダー コントロールで使用するツールヒントを含む[CToolTipCtrl](../../mfc/reference/ctooltipctrl-class.md)オブジェクトへのポインター。

### <a name="remarks"></a>解説

このメンバー関数は、Windows SDK で説明されているように、Win32 メッセージ[TBM_SETTOOLTIPS](/windows/win32/Controls/tbm-settooltips)の動作を実装します。 TBS_TOOLTIPSスタイルでスライダー コントロールを作成すると、スライダーの横に表示される既定のツールヒント コントロールが作成され、スライダーの現在の位置が表示されます。 スライダー コントロールスタイルの詳細については、Windows SDK の[トラックバー コントロール スタイル](/windows/win32/Controls/trackbar-control-styles)を参照してください。

## <a name="see-also"></a>関連項目

[サンプル CMNCTRL2](../../overview/visual-cpp-samples.md)<br/>
[CWnd クラス](../../mfc/reference/cwnd-class.md)<br/>
[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[CProgressCtrl クラス](../../mfc/reference/cprogressctrl-class.md)

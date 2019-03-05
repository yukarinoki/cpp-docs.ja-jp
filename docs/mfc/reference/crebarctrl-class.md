---
title: CReBarCtrl クラス
ms.date: 11/19/2018
f1_keywords:
- CReBarCtrl
- AFXCMN/CReBarCtrl
- AFXCMN/CReBarCtrl::CReBarCtrl
- AFXCMN/CReBarCtrl::BeginDrag
- AFXCMN/CReBarCtrl::Create
- AFXCMN/CReBarCtrl::CreateEx
- AFXCMN/CReBarCtrl::DeleteBand
- AFXCMN/CReBarCtrl::DragMove
- AFXCMN/CReBarCtrl::EndDrag
- AFXCMN/CReBarCtrl::GetBandBorders
- AFXCMN/CReBarCtrl::GetBandCount
- AFXCMN/CReBarCtrl::GetBandInfo
- AFXCMN/CReBarCtrl::GetBandMargins
- AFXCMN/CReBarCtrl::GetBarHeight
- AFXCMN/CReBarCtrl::GetBarInfo
- AFXCMN/CReBarCtrl::GetBkColor
- AFXCMN/CReBarCtrl::GetColorScheme
- AFXCMN/CReBarCtrl::GetDropTarget
- AFXCMN/CReBarCtrl::GetExtendedStyle
- AFXCMN/CReBarCtrl::GetImageList
- AFXCMN/CReBarCtrl::GetPalette
- AFXCMN/CReBarCtrl::GetRect
- AFXCMN/CReBarCtrl::GetRowCount
- AFXCMN/CReBarCtrl::GetRowHeight
- AFXCMN/CReBarCtrl::GetTextColor
- AFXCMN/CReBarCtrl::GetToolTips
- AFXCMN/CReBarCtrl::HitTest
- AFXCMN/CReBarCtrl::IDToIndex
- AFXCMN/CReBarCtrl::InsertBand
- AFXCMN/CReBarCtrl::MaximizeBand
- AFXCMN/CReBarCtrl::MinimizeBand
- AFXCMN/CReBarCtrl::MoveBand
- AFXCMN/CReBarCtrl::PushChevron
- AFXCMN/CReBarCtrl::RestoreBand
- AFXCMN/CReBarCtrl::SetBandInfo
- AFXCMN/CReBarCtrl::SetBandWidth
- AFXCMN/CReBarCtrl::SetBarInfo
- AFXCMN/CReBarCtrl::SetBkColor
- AFXCMN/CReBarCtrl::SetColorScheme
- AFXCMN/CReBarCtrl::SetExtendedStyle
- AFXCMN/CReBarCtrl::SetImageList
- AFXCMN/CReBarCtrl::SetOwner
- AFXCMN/CReBarCtrl::SetPalette
- AFXCMN/CReBarCtrl::SetTextColor
- AFXCMN/CReBarCtrl::SetToolTips
- AFXCMN/CReBarCtrl::SetWindowTheme
- AFXCMN/CReBarCtrl::ShowBand
- AFXCMN/CReBarCtrl::SizeToRect
helpviewer_keywords:
- CReBarCtrl [MFC], CReBarCtrl
- CReBarCtrl [MFC], BeginDrag
- CReBarCtrl [MFC], Create
- CReBarCtrl [MFC], CreateEx
- CReBarCtrl [MFC], DeleteBand
- CReBarCtrl [MFC], DragMove
- CReBarCtrl [MFC], EndDrag
- CReBarCtrl [MFC], GetBandBorders
- CReBarCtrl [MFC], GetBandCount
- CReBarCtrl [MFC], GetBandInfo
- CReBarCtrl [MFC], GetBandMargins
- CReBarCtrl [MFC], GetBarHeight
- CReBarCtrl [MFC], GetBarInfo
- CReBarCtrl [MFC], GetBkColor
- CReBarCtrl [MFC], GetColorScheme
- CReBarCtrl [MFC], GetDropTarget
- CReBarCtrl [MFC], GetExtendedStyle
- CReBarCtrl [MFC], GetImageList
- CReBarCtrl [MFC], GetPalette
- CReBarCtrl [MFC], GetRect
- CReBarCtrl [MFC], GetRowCount
- CReBarCtrl [MFC], GetRowHeight
- CReBarCtrl [MFC], GetTextColor
- CReBarCtrl [MFC], GetToolTips
- CReBarCtrl [MFC], HitTest
- CReBarCtrl [MFC], IDToIndex
- CReBarCtrl [MFC], InsertBand
- CReBarCtrl [MFC], MaximizeBand
- CReBarCtrl [MFC], MinimizeBand
- CReBarCtrl [MFC], MoveBand
- CReBarCtrl [MFC], PushChevron
- CReBarCtrl [MFC], RestoreBand
- CReBarCtrl [MFC], SetBandInfo
- CReBarCtrl [MFC], SetBandWidth
- CReBarCtrl [MFC], SetBarInfo
- CReBarCtrl [MFC], SetBkColor
- CReBarCtrl [MFC], SetColorScheme
- CReBarCtrl [MFC], SetExtendedStyle
- CReBarCtrl [MFC], SetImageList
- CReBarCtrl [MFC], SetOwner
- CReBarCtrl [MFC], SetPalette
- CReBarCtrl [MFC], SetTextColor
- CReBarCtrl [MFC], SetToolTips
- CReBarCtrl [MFC], SetWindowTheme
- CReBarCtrl [MFC], ShowBand
- CReBarCtrl [MFC], SizeToRect
ms.assetid: 154570d7-e48c-425d-8c7e-c64542bcb4cc
ms.openlocfilehash: f1e9c6e4505c67b881d479817ec8b45e4ae5dc8b
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/04/2019
ms.locfileid: "57304556"
---
# <a name="crebarctrl-class"></a>CReBarCtrl クラス

Rebar コントロールの機能がカプセル化されています。Rebar コントロールは、子ウィンドウを含むコンテナーです。

## <a name="syntax"></a>構文

```
class CReBarCtrl : public CWnd
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CReBarCtrl::CReBarCtrl](#crebarctrl)|`CReBarCtrl` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CReBarCtrl::BeginDrag](#begindrag)|Rebar コントロールをドラッグ アンド ドロップ モードに配置します。|
|[CReBarCtrl::Create](#create)|Rebar コントロールを作成し、それにアタッチします、`CReBarCtrl`オブジェクト。|
|[CReBarCtrl::CreateEx](#createex)|指定した Windows の拡張スタイルを使用して、rebar コントロールを作成しにアタッチします、`CReBarCtrl`オブジェクト。|
|[CReBarCtrl::DeleteBand](#deleteband)|Rebar コントロールからの band を削除します。|
|[CReBarCtrl::DragMove](#dragmove)|更新プログラムの呼び出しの後に rebar コントロールでドラッグ位置`BeginDrag`します。|
|[CReBarCtrl::EndDrag](#enddrag)|Rebar コントロールのドラッグ アンド ドロップ操作を終了します。|
|[CReBarCtrl::GetBandBorders](#getbandborders)|バンドの境界線を取得します。|
|[CReBarCtrl::GetBandCount](#getbandcount)|Rebar コントロールの現在のバンドの数を取得します。|
|[CReBarCtrl::GetBandInfo](#getbandinfo)|Rebar コントロールで指定されたバンドに関する情報を取得します。|
|[CReBarCtrl::GetBandMargins](#getbandmargins)|バンドの余白を取得します。|
|[CReBarCtrl::GetBarHeight](#getbarheight)|Rebar コントロールの高さを取得します。|
|[CReBarCtrl::GetBarInfo](#getbarinfo)|Rebar コントロールと、イメージ リストの使用に関する情報を取得します。|
|[CReBarCtrl::GetBkColor](#getbkcolor)|Rebar コントロールの既定の背景色を取得します。|
|[CReBarCtrl::GetColorScheme](#getcolorscheme)|取得、 [COLORSCHEME](/windows/desktop/api/commctrl/ns-commctrl-tagcolorscheme) rebar コントロールに関連付けられている構造体。|
|[CReBarCtrl::GetDropTarget](#getdroptarget)|Rebar コントロールの取得`IDropTarget`インターフェイス ポインター。|
|[CReBarCtrl::GetExtendedStyle](#getextendedstyle)|現在の rebar コントロールの拡張スタイルを取得します。|
|[CReBarCtrl::GetImageList](#getimagelist)|Rebar コントロールに関連付けられているイメージ リストを取得します。|
|[CReBarCtrl::GetPalette](#getpalette)|Rebar コントロールの現在のパレットを取得します。|
|[CReBarCtrl::GetRect](#getrect)|Rebar コントロールの特定のバンドの外接する四角形を取得します。|
|[CReBarCtrl::GetRowCount](#getrowcount)|Rebar コントロールのバンドの行の数を取得します。|
|[CReBarCtrl::GetRowHeight](#getrowheight)|Rebar コントロールの指定した行の高さを取得します。|
|[CReBarCtrl::GetTextColor](#gettextcolor)|Rebar コントロールの既定のテキストの色を取得します。|
|[CReBarCtrl::GetToolTips](#gettooltips)|Rebar コントロールに関連付けられた任意のツール ヒント コントロールを識別するハンドルを取得します。|
|[CReBarCtrl::HitTest](#hittest)|Rebar バンドがその時点で存在する場合に、画面で、特定の時点に rebar バンドのどの部分が判断します。|
|[CReBarCtrl::IDToIndex](#idtoindex)|Rebar コントロールのバンド インデックス域外識別子 (ID) に変換します。|
|[CReBarCtrl::InsertBand](#insertband)|Rebar コントロールで新しいバンドを挿入します。|
|[CReBarCtrl::MaximizeBand](#maximizeband)|最大サイズに rebar コントロールのバンドのサイズを変更します。|
|[CReBarCtrl::MinimizeBand](#minimizeband)|最小サイズに rebar コントロールのバンドのサイズを変更します。|
|[CReBarCtrl::MoveBand](#moveband)|バンドを別の 1 つのインデックスに移動します。|
|[CReBarCtrl::PushChevron](#pushchevron)|プログラムで、シェブロンをプッシュします。|
|[CReBarCtrl::RestoreBand](#restoreband)|理想的なサイズに rebar コントロールのバンドのサイズを変更します。|
|[CReBarCtrl::SetBandInfo](#setbandinfo)|Rebar コントロールでは、既存のバンドの特性を設定します。|
|[CReBarCtrl::SetBandWidth](#setbandwidth)|現在の rebar コントロールでの指定されたドッキングされた帯域幅を設定します。|
|[CReBarCtrl::SetBarInfo](#setbarinfo)|Rebar コントロールの特性を設定します。|
|[CReBarCtrl::SetBkColor](#setbkcolor)|Rebar コントロールの既定の背景色を設定します。|
|[CReBarCtrl::SetColorScheme](#setcolorscheme)|Rebar コントロールのボタンの配色を設定します。|
|[CReBarCtrl::SetExtendedStyle](#setextendedstyle)|現在の rebar コントロールの拡張スタイルを設定します。|
|[CReBarCtrl::SetImageList](#setimagelist)|Rebar コントロールのイメージ リストを設定します。|
|[CReBarCtrl::SetOwner](#setowner)|Rebar コントロールのオーナー ウィンドウを設定します。|
|[CReBarCtrl::SetPalette](#setpalette)|Rebar コントロールの現在のパレットを設定します。|
|[CReBarCtrl::SetTextColor](#settextcolor)|Rebar コントロールの既定のテキストの色を設定します。|
|[CReBarCtrl::SetToolTips](#settooltips)|Rebar コントロールで、ツール ヒント コントロールに関連付けます。|
|[CReBarCtrl::SetWindowTheme](#setwindowtheme)|Rebar コントロールの視覚スタイルを設定します。|
|[CReBarCtrl::ShowBand](#showband)|Rebar コントロールの特定のバンドを非表示に表示を切り替えます。|
|[CReBarCtrl::SizeToRect](#sizetorect)|指定した四角形に rebar コントロールが収まるようにします。|

## <a name="remarks"></a>Remarks

Rebar コントロールが存在するアプリケーションでは、rebar バンドを rebar コントロールに含まれる子ウィンドウを割り当てます。 子ウィンドウには、通常、別の一般的なコントロールです。

Rebar コントロールには、1 つまたは複数のバンドが含まれます。 各バンドはグリッパー バー、ビットマップ、テキスト ラベル、および子ウィンドウの組み合わせを含めることができます。 Band では、これらの各項目の 1 つだけ含めることができます。

Rebar コントロールでは、指定した背景ビットマップを子ウィンドウを表示できます。 すべての rebar コントロール バンド サイズを変更できる、RBBS_FIXEDSIZE スタイルを使用するものを除く。 位置を変更または rebar コントロール バンドのサイズを変更すると、rebar コントロールはそのバンドに割り当てられている子ウィンドウの位置とサイズを管理します。 サイズを変更またはコントロール内のバンドの順序を変更、 をクリックし、バンドのグリップ バーをドラッグします。

次の図を 3 つのバンドを持つ rebar コントロールを示しています。

- バンド 0 にはには、フラットで透過的なツール バー コントロールが含まれています。

- バンド 1 には、両方の透過的な標準および透過的なドロップダウン ボタンが含まれています。

- バンド 2 には、コンボ ボックスと 4 つの標準ボタンが含まれています。

   ![Rebar メニューの例](../../mfc/reference/media/vc4scc1.gif "Rebar メニューの例")

## <a name="rebar-control"></a>Rebar コントロール

コントロールのサポートを rebar:

- イメージが一覧表示します。

- メッセージ処理します。

- カスタム描画機能。

- さまざまな標準のウィンドウ スタイルだけでなく、コントロールのスタイル。 これらのスタイルの一覧は、次を参照してください。 [Rebar コントロールのスタイル](/windows/desktop/Controls/rebar-control-styles)Windows SDK に含まれています。

詳細については、次を参照してください。[を使用して CReBarCtrl](../../mfc/using-crebarctrl.md)します。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CReBarCtrl`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxcmn.h

##  <a name="begindrag"></a>  CReBarCtrl::BeginDrag

Win32 メッセージの動作を実装[RB_BEGINDRAG](/windows/desktop/Controls/rb-begindrag)」の説明に従って、Windows SDK。

```
void BeginDrag(
    UINT uBand,
    DWORD dwPos = (DWORD)-1);
```

### <a name="parameters"></a>パラメーター

*uBand*<br/>
ドラッグ アンド ドロップ操作に影響を与えるバンドの 0 から始まるインデックス。

*dwPos*<br/>
開始を含む DWORD 値のマウス座標。 水平方向の座標は、LOWORD に含まれ、HIWORD に垂直方向の座標が含まれています。 Rebar コントロールで最後に、呼び出されたコントロールのスレッドのマウスの位置を使用して (DWORD)-1 を渡す場合`GetMessage`または`PeekMessage`します。

##  <a name="create"></a>  CReBarCtrl::Create

Rebar コントロールを作成し、それにアタッチします、`CReBarCtrl`オブジェクト。

```
virtual BOOL Create(
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>パラメーター

*dwStyle*<br/>
Rebar コントロールのスタイルがコントロールに適用の組み合わせを指定します。 参照してください[Rebar コントロールのスタイル](/windows/desktop/Controls/rebar-control-styles)でサポートされているスタイルの一覧については、Windows SDK。

*rect*<br/>
参照を[CRect](../../atl-mfc-shared/reference/crect-class.md)オブジェクトまたは[RECT](https://msdn.microsoft.com/library/windows/desktop/dd162897) rebar コントロールのサイズと位置である構造体。

*pParentWnd*<br/>
ポインターを[CWnd](../../mfc/reference/cwnd-class.md) rebar コントロールの親ウィンドウであるオブジェクト。 NULL は指定できません。

*nID*<br/>
Rebar コントロールのコントロール ID を指定します

### <a name="return-value"></a>戻り値

オブジェクトが正常に作成された場合は 0 以外それ以外の場合 0 を返します。

### <a name="remarks"></a>Remarks

2 つの手順では、rebar コントロールを作成します。

1. 呼び出す[crebarctrl の比較](#crebarctrl)を構築する、`CReBarCtrl`オブジェクト。

1. このメンバー関数は、Windows の rebar コントロールの作成およびにアタッチしますを呼び出し、`CReBarCtrl`オブジェクト。

呼び出すと`Create`、一般的なコントロールが初期化されます。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CReBarCtrl#3](../../mfc/reference/codesnippet/cpp/crebarctrl-class_1.cpp)]

##  <a name="createex"></a>  CReBarCtrl::CreateEx

コントロール (子ウィンドウ) を作成しに関連付けます、`CReBarCtrl`オブジェクト。

```
virtual BOOL CreateEx(
    DWORD dwExStyle,
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>パラメーター

*dwExStyle*<br/>
作成されるコントロールの拡張スタイルを指定します。 拡張 Windows スタイルの一覧は、次を参照してください。、 *dwExStyle*パラメーターを[CreateWindowEx](/windows/desktop/api/winuser/nf-winuser-createwindowexa) Windows SDK に含まれています。

*dwStyle*<br/>
Rebar コントロールのスタイルがコントロールに適用の組み合わせを指定します。 サポートされているスタイルの一覧は、次を参照してください。 [Rebar コントロールのスタイル](/windows/desktop/Controls/rebar-control-styles)Windows SDK に含まれています。

*rect*<br/>
参照を[RECT](https://msdn.microsoft.com/library/windows/desktop/dd162897)のクライアント座標で、作成するには、ウィンドウの位置とサイズを記述する構造体*pParentWnd*します。

*pParentWnd*<br/>
コントロールの親であるウィンドウへのポインター。

*nID*<br/>
コントロールの子ウィンドウ ID

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>Remarks

使用`CreateEx`の代わりに[作成](#create)、Windows の拡張スタイルの先頭で指定された、Windows の拡張スタイルを適用する**WS_EX**します。

##  <a name="crebarctrl"></a>  CReBarCtrl::CReBarCtrl

`CReBarCtrl` オブジェクトを作成します。

```
CReBarCtrl();
```

### <a name="example"></a>例

  例をご覧ください[CReBarCtrl::Create](#create)します。

##  <a name="deleteband"></a>  CReBarCtrl::DeleteBand

Win32 メッセージの動作を実装[RB_DELETEBAND](/windows/desktop/Controls/rb-deleteband)」の説明に従って、Windows SDK。

```
BOOL DeleteBand(UINT uBand);
```

### <a name="parameters"></a>パラメーター

*uBand*<br/>
削除するバンドの 0 から始まるインデックス。

### <a name="return-value"></a>戻り値

バンドが正常に削除された場合、0 以外の場合それ以外の場合 0 を返します。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CReBarCtrl#4](../../mfc/reference/codesnippet/cpp/crebarctrl-class_2.cpp)]

##  <a name="dragmove"></a>  CReBarCtrl::DragMove

Win32 メッセージの動作を実装[RB_DRAGMOVE](/windows/desktop/Controls/rb-dragmove)」の説明に従って、Windows SDK。

```
void DragMove(DWORD dwPos = (DWORD)-1);
```

### <a name="parameters"></a>パラメーター

*dwPos*<br/>
新しいマウス座標を含む DWORD 値を指定します。 水平方向の座標は、LOWORD に含まれ、HIWORD に垂直方向の座標が含まれています。 Rebar コントロールで最後に、呼び出されたコントロールのスレッドのマウスの位置を使用して (DWORD)-1 を渡す場合`GetMessage`または`PeekMessage`します。

##  <a name="enddrag"></a>  CReBarCtrl::EndDrag

Win32 メッセージの動作を実装[RB_ENDDRAG](/windows/desktop/Controls/rb-enddrag)」の説明に従って、Windows SDK。

```
void EndDrag();
```

##  <a name="getbandborders"></a>  CReBarCtrl::GetBandBorders

Win32 メッセージの動作を実装[RB_GETBANDBORDERS](/windows/desktop/Controls/rb-getbandborders)」の説明に従って、Windows SDK。

```
void GetBandBorders(
    UINT uBand,
    LPRECT prc) const;
```

### <a name="parameters"></a>パラメーター

*uBand*<br/>
境界線を取得するのバンドの 0 から始まるインデックス。

*中華人民共和国*<br/>
ポインターを[RECT](https://msdn.microsoft.com/library/windows/desktop/dd162897)バンド境界線が受け取る構造体。 Rebar コントロールに RBS_BANDBORDERS スタイルがある場合は、この構造体の各メンバーによって境界を構成する、バンドの対応する側のピクセルの数が表示されます。 Rebar コントロールが RBS_BANDBORDERS スタイルを持たない場合は左側のこの構造体のメンバーのみが有効な情報を受け取ります。 Rebar コントロールのスタイルの説明は、次を参照してください。 [Rebar コントロールのスタイル](/windows/desktop/Controls/rebar-control-styles)Windows SDK に含まれています。

##  <a name="getbandcount"></a>  CReBarCtrl::GetBandCount

Win32 メッセージの動作を実装[RB_GETBANDCOUNT](/windows/desktop/Controls/rb-getbandcount)」の説明に従って、Windows SDK。

```
UINT GetBandCount() const;
```

### <a name="return-value"></a>戻り値

バンドがコントロールに割り当ての数。

##  <a name="getbandinfo"></a>  CReBarCtrl::GetBandInfo

Win32 メッセージの動作を実装[RB_GETBANDINFO](/windows/desktop/Controls/rb-getbandinfo) Windows SDK で説明されているとします。

```
BOOL GetBandInfo(
    UINT uBand,
    REBARBANDINFO* prbbi) const;
```

### <a name="parameters"></a>パラメーター

*uBand*<br/>
情報を取得するのバンドの 0 から始まるインデックス。

*prbbi*<br/>
ポインターを[REBARBANDINFO](/windows/desktop/api/commctrl/ns-commctrl-tagrebarbandinfoa)域外情報を受け取る構造体。 設定する必要があります、`cbSize`をこの構造体のメンバー`sizeof(REBARBANDINFO)`設定と、`fMask`メンバーにこのメッセージを送信する前に取得する項目。

### <a name="return-value"></a>戻り値

成功した場合は 0 以外を返します。それ以外の場合は 0 を返します。

##  <a name="getbandmargins"></a>  CReBarCtrl::GetBandMargins

バンドの余白を取得します。

```
void GetBandMargins(PMARGINS pMargins);
```

### <a name="parameters"></a>パラメーター

*pMargins*<br/>
ポインターを[余白](/windows/desktop/api/uxtheme/ns-uxtheme-_margins)情報を受け取る構造体。

### <a name="remarks"></a>Remarks

このメンバー関数の機能をエミュレートする、 [RB_GETBANDMARGINS](/windows/desktop/Controls/rb-getbandmargins)メッセージ、Windows SDK で説明されているとします。

##  <a name="getbarheight"></a>  CReBarCtrl::GetBarHeight

Rebar バーの高さを取得します。

```
UINT GetBarHeight() const;
```

### <a name="return-value"></a>戻り値

コントロールのピクセルの高さを表す値です。

##  <a name="getbarinfo"></a>  CReBarCtrl::GetBarInfo

Win32 メッセージの動作を実装[RB_GETBARINFO](/windows/desktop/Controls/rb-getbarinfo)」の説明に従って、Windows SDK。

```
BOOL GetBarInfo(REBARINFO* prbi) const;
```

### <a name="parameters"></a>パラメーター

*prbi*<br/>
ポインターを[REBARINFO](/windows/desktop/api/commctrl/ns-commctrl-tagrebarinfo) rebar コントロールの情報を受け取る構造体。 設定する必要があります、 *cbSize*をこの構造体のメンバー`sizeof(REBARINFO)`このメッセージを送信する前にします。

### <a name="return-value"></a>戻り値

成功した場合は 0 以外を返します。それ以外の場合は 0 を返します。

##  <a name="getbkcolor"></a>  CReBarCtrl::GetBkColor

Win32 メッセージの動作を実装[RB_GETBKCOLOR](/windows/desktop/Controls/rb-getbkcolor)」の説明に従って、Windows SDK。

```
COLORREF GetBkColor() const;
```

### <a name="return-value"></a>戻り値

現在の既定の背景色を表す COLORREF 値。

##  <a name="getcolorscheme"></a>  CReBarCtrl::GetColorScheme

取得、 [COLORSCHEME](/windows/desktop/api/commctrl/ns-commctrl-tagcolorscheme) rebar コントロールの構造体。

```
BOOL GetColorScheme(COLORSCHEME* lpcs);
```

### <a name="parameters"></a>パラメーター

*lpc*<br/>
ポインターを[COLORSCHEME](/windows/desktop/api/commctrl/ns-commctrl-tagcolorscheme) Windows SDK」の説明に従って、構造体します。

### <a name="return-value"></a>戻り値

成功した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>Remarks

`COLORSCHEME`構造には、ボタンの強調表示色とボタンの影の色が含まれています。

##  <a name="getdroptarget"></a>  CReBarCtrl::GetDropTarget

Win32 メッセージの動作を実装[RB_GETDROPTARGET](/windows/desktop/Controls/rb-getdroptarget)」の説明に従って、Windows SDK。

```
IDropTarget* GetDropTarget() const;
```

### <a name="return-value"></a>戻り値

ポインター、 [IDropTarget](/windows/desktop/api/oleidl/nn-oleidl-idroptarget)インターフェイス。

##  <a name="getextendedstyle"></a>  CReBarCtrl::GetExtendedStyle

現在の rebar コントロールの拡張スタイルを取得します。

```
DWORD GetExtendedStyle() const;
```

### <a name="return-value"></a>戻り値

拡張スタイルを示すフラグのビットごとの組み合わせ (OR)。 使用できるフラグには、RBS_EX_SPLITTER および RBS_EX_TRANSPARENT です。 詳細については、次を参照してください。、 *dwMask*のパラメーター、 [CReBarCtrl::SetExtendedStyle](#setextendedstyle)メソッド。

### <a name="remarks"></a>Remarks

このメソッドは、送信、 [RB_GETEXTENDEDSTYLE](/windows/desktop/Controls/rb-dragmove)メッセージは、Windows SDK で説明します。

##  <a name="getimagelist"></a>  CReBarCtrl::GetImageList

取得、 `CImageList` rebar コントロールに関連付けられているオブジェクト。

```
CImageList* GetImageList() const;
```

### <a name="return-value"></a>戻り値

ポインターを[CImageList](../../mfc/reference/cimagelist-class.md)オブジェクト。 コントロールのイメージ リストが設定されていない場合は、NULL を返します。

### <a name="remarks"></a>Remarks

このメンバー関数に格納されているサイズとマスクの情報を使用して、 [REBARINFO](/windows/desktop/api/commctrl/ns-commctrl-tagrebarinfo) Windows SDK」の説明に従って、構造体します。

##  <a name="getpalette"></a>  CReBarCtrl::GetPalette

Rebar コントロールの現在のパレットを取得します。

```
CPalette* GetPalette() const;
```

### <a name="return-value"></a>戻り値

ポインターを[CPalette](../../mfc/reference/cpalette-class.md) rebar コントロールの現在のパレットを指定するオブジェクト。

### <a name="remarks"></a>Remarks

このメンバー関数を使用するノートを`CPalette`HPALETTE ではなく、戻り値としてオブジェクト。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CReBarCtrl#5](../../mfc/reference/codesnippet/cpp/crebarctrl-class_3.cpp)]

##  <a name="getrect"></a>  CReBarCtrl::GetRect

Win32 メッセージの動作を実装[RB_GETRECT](/windows/desktop/Controls/rb-getrect)」の説明に従って、Windows SDK。

```
BOOL GetRect(
    UINT uBand,
    LPRECT prc) const;
```

### <a name="parameters"></a>パラメーター

*uBand*<br/>
Rebar コントロールのバンドの 0 から始まるインデックス。

*中華人民共和国*<br/>
ポインターを[RECT](https://msdn.microsoft.com/library/windows/desktop/dd162897) rebar バンドの境界を受信する構造体。

### <a name="return-value"></a>戻り値

成功した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CReBarCtrl#6](../../mfc/reference/codesnippet/cpp/crebarctrl-class_4.cpp)]

##  <a name="getrowcount"></a>  CReBarCtrl::GetRowCount

Win32 メッセージの動作を実装[RB_GETROWCOUNT](/windows/desktop/Controls/rb-getrowcount)」の説明に従って、Windows SDK。

```
UINT GetRowCount() const;
```

### <a name="return-value"></a>戻り値

コントロールのバンド行の数を表す UINT 値。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CReBarCtrl#7](../../mfc/reference/codesnippet/cpp/crebarctrl-class_5.cpp)]

##  <a name="getrowheight"></a>  CReBarCtrl::GetRowHeight

Win32 メッセージの動作を実装[RB_GETROWHEIGHT](/windows/desktop/Controls/rb-getrowheight)」の説明に従って、Windows SDK。

```
UINT GetRowHeight(UINT uRow) const;
```

### <a name="parameters"></a>パラメーター

*uRow*<br/>
高さを取得する必要がありますのバンドの 0 から始まるインデックス。

### <a name="return-value"></a>戻り値

行の高さ (ピクセル単位) を表す UINT 値。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CReBarCtrl#8](../../mfc/reference/codesnippet/cpp/crebarctrl-class_6.cpp)]

##  <a name="gettextcolor"></a>  CReBarCtrl::GetTextColor

Win32 メッセージの動作を実装[RB_GETTEXTCOLOR](/windows/desktop/Controls/rb-gettextcolor)」の説明に従って、Windows SDK。

```
COLORREF GetTextColor() const;
```

### <a name="return-value"></a>戻り値

現在の既定のテキストの色を表す COLORREF 値。

##  <a name="gettooltips"></a>  CReBarCtrl::GetToolTips

Win32 メッセージの動作を実装[RB_GETTOOLTIPS](/windows/desktop/Controls/rb-gettooltips)」の説明に従って、Windows SDK。

```
CToolTipCtrl* GetToolTips() const;
```

### <a name="return-value"></a>戻り値

ポインターを[CToolTipCtrl](../../mfc/reference/ctooltipctrl-class.md)オブジェクト。

### <a name="remarks"></a>Remarks

注意の MFC 実装`GetToolTips`へのポインターを返します、 `CToolTipCtrl`HWND ではなく。

##  <a name="hittest"></a>  CReBarCtrl::HitTest

Win32 メッセージの動作を実装[RB_HITTEST](/windows/desktop/Controls/rb-hittest)」の説明に従って、Windows SDK。

```
int HitTest(RBHITTESTINFO* prbht);
```

### <a name="parameters"></a>パラメーター

*prbht*<br/>
ポインターを[RBHITTESTINFO](/windows/desktop/api/commctrl/ns-commctrl-_rb_hittestinfo)構造体。 メッセージを送信する前に、`pt`クライアント座標で、テストされるポイントにこの構造体のメンバーを初期化する必要があります。

### <a name="return-value"></a>戻り値

指定したポイントまたは時点 rebar バンドがなかった場合は-1 で、バンドの 0 から始まるインデックス。

##  <a name="idtoindex"></a>  CReBarCtrl::IDToIndex

Win32 メッセージの動作を実装[RB_IDTOINDEX](https://msdn.microsoft.com/library/windows/desktop/bb774496)」の説明に従って、Windows SDK。

```
int IDToIndex(UINT uBandID) const;
```

### <a name="parameters"></a>パラメーター

*uBandID*<br/>
渡された指定のバンドのアプリケーション定義の識別子、`wID`のメンバー、 [REBARBANDINFO](/windows/desktop/api/commctrl/ns-commctrl-tagrebarbandinfoa)バンドが挿入されたときに構造体します。

### <a name="return-value"></a>戻り値

成功した場合は、バンドの 0 から始まるインデックス、またはそれ以外の場合は-1。 バンドが重複するインデックスが存在する場合は、1 つ目が返されます。

##  <a name="insertband"></a>  CReBarCtrl::InsertBand

Win32 メッセージの動作を実装[RB_INSERTBAND](/windows/desktop/Controls/rb-insertband)」の説明に従って、Windows SDK。

```
BOOL InsertBand(
    UINT uIndex,
    REBARBANDINFO* prbbi);
```

### <a name="parameters"></a>パラメーター

*uIndex*<br/>
バンドを挿入する位置の 0 から始まるインデックス。 このパラメーターを-1 に設定した場合、コントロールは最後の位置で新しいバンドを追加します。

*prbbi*<br/>
ポインターを[REBARBANDINFO](/windows/desktop/api/commctrl/ns-commctrl-tagrebarbandinfoa)を挿入するバンドを定義する構造体。 設定する必要があります、 *cbSize*をこの構造体のメンバー`sizeof(REBARBANDINFO)`この関数を呼び出す前にします。

### <a name="return-value"></a>戻り値

成功した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CReBarCtrl#9](../../mfc/reference/codesnippet/cpp/crebarctrl-class_7.cpp)]

##  <a name="maximizeband"></a>  CReBarCtrl::MaximizeBand

最大サイズに rebar コントロールのバンドのサイズを変更します。

```
void MaximizeBand(UINT uBand);
```

### <a name="parameters"></a>パラメーター

*uBand*<br/>
最大化するバンドの 0 から始まるインデックス。

### <a name="remarks"></a>Remarks

Win32 メッセージの動作を実装[RB_MAXIMIZEBAND](/windows/desktop/Controls/rb-maximizeband)で`fIdeal`Windows SDK」の説明に従って、0 に設定します。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CReBarCtrl#10](../../mfc/reference/codesnippet/cpp/crebarctrl-class_8.cpp)]

##  <a name="minimizeband"></a>  CReBarCtrl::MinimizeBand

最小サイズに rebar コントロールのバンドのサイズを変更します。

```
void MinimizeBand(UINT uBand);
```

### <a name="parameters"></a>パラメーター

*uBand*<br/>
最小化するバンドの 0 から始まるインデックス。

### <a name="remarks"></a>Remarks

Win32 メッセージの動作を実装[RB_MINIMIZEBAND](/windows/desktop/Controls/rb-minimizeband)」の説明に従って、Windows SDK。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CReBarCtrl#11](../../mfc/reference/codesnippet/cpp/crebarctrl-class_9.cpp)]

##  <a name="moveband"></a>  CReBarCtrl::MoveBand

Win32 メッセージの動作を実装[RB_MOVEBAND](/windows/desktop/Controls/rb-moveband)」の説明に従って、Windows SDK。

```
BOOL MoveBand(
    UINT uFrom,
    UINT uTo);
```

### <a name="parameters"></a>パラメーター

*uFrom*<br/>
移動するバンドの 0 から始まるインデックス。

*uTo*<br/>
バンドの新しい位置の 0 から始まるインデックス。 このパラメーターの値は、バンドから 1 を引いた数より大きいしない場合があります。 バンドの数を取得するには、呼び出す[GetBandCount](#getbandcount)します。

### <a name="return-value"></a>戻り値

成功した場合は 0 以外を返します。それ以外の場合は 0 を返します。

##  <a name="pushchevron"></a>  CReBarCtrl::PushChevron

Win32 メッセージの動作を実装[RB_PUSHCHEVRON](/windows/desktop/Controls/rb-pushchevron)」の説明に従って、Windows SDK。

```
void PushChevron(
    UINT uBand,
    LPARAM lAppValue);
```

### <a name="parameters"></a>パラメーター

*uBand*<br/>
シェブロンがプッシュされるバンドの 0 から始まるインデックス。

*lAppValue*<br/>
アプリケーションでは、32 ビット値を定義します。 参照してください*lAppValue*で[RB_PUSHCHEVRON](/windows/desktop/Controls/rb-pushchevron) Windows SDK に含まれています。

##  <a name="restoreband"></a>  CReBarCtrl::RestoreBand

理想的なサイズに rebar コントロールのバンドのサイズを変更します。

```
void RestoreBand(UINT uBand);
```

### <a name="parameters"></a>パラメーター

*uBand*<br/>
最大化するバンドの 0 から始まるインデックス。

### <a name="remarks"></a>Remarks

Win32 メッセージの動作を実装[RB_MAXIMIZEBAND](/windows/desktop/Controls/rb-maximizeband)で`fIdeal`Windows SDK」の説明に従って、1 に設定します。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CReBarCtrl#12](../../mfc/reference/codesnippet/cpp/crebarctrl-class_10.cpp)]

##  <a name="setbandinfo"></a>  CReBarCtrl::SetBandInfo

Win32 メッセージの動作を実装[RB_SETBANDINFO](/windows/desktop/Controls/rb-setbandinfo)」の説明に従って、Windows SDK。

```
BOOL SetBandInfo(
    UINT uBand,
    REBARBANDINFO* prbbi);
```

### <a name="parameters"></a>パラメーター

*uBand*<br/>
新しい設定を受信するバンドの 0 から始まるインデックス。

*prbbi*<br/>
ポインターを[REBARBANDINFO](/windows/desktop/api/commctrl/ns-commctrl-tagrebarbandinfoa)を挿入するバンドを定義する構造体。 設定する必要があります、`cbSize`をこの構造体のメンバー`sizeof(REBARBANDINFO)`このメッセージを送信する前にします。

### <a name="return-value"></a>戻り値

成功した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CReBarCtrl#13](../../mfc/reference/codesnippet/cpp/crebarctrl-class_11.cpp)]

##  <a name="setbandwidth"></a>  CReBarCtrl::SetBandWidth

現在の rebar コントロールでの指定されたドッキングされた帯域幅を設定します。

```
BOOL SetBandWidth(
    UINT uBand,
    int cxWidth);
```

### <a name="parameters"></a>パラメーター

|パラメーター|説明|
|---------------|-----------------|
|*uBand*|[in]Rebar バンドの 0 から始まるインデックス。|
|*cxWidth*|[in]Rebar バンドをピクセル単位での新しい幅。|

### <a name="return-value"></a>戻り値

メソッドが成功した場合は TRUE。それ以外の場合、FALSE です。

### <a name="remarks"></a>Remarks

このメソッドは、送信、 [RB_SETBANDWIDTH](/windows/desktop/Controls/rb-setbandwidth)メッセージは、Windows SDK で説明します。

### <a name="example"></a>例

次のコード例は、変数を定義します。 `m_rebar`、つまり現在 rebar コントロールにアクセスするために使用します。 この変数は次の例で使用されています。

[!code-cpp[NVC_MFC_CReBarCtrl_s1#1](../../mfc/reference/codesnippet/cpp/crebarctrl-class_12.h)]

### <a name="example"></a>例

次のコード例では、同じ幅にするには、各 rebar バンドを設定します。

[!code-cpp[NVC_MFC_CReBarCtrl_s1#2](../../mfc/reference/codesnippet/cpp/crebarctrl-class_13.cpp)]

##  <a name="setbarinfo"></a>  CReBarCtrl::SetBarInfo

Win32 メッセージの動作を実装[RB_SETBARINFO](/windows/desktop/Controls/rb-setbarinfo)」の説明に従って、Windows SDK。

```
BOOL SetBarInfo(REBARINFO* prbi);
```

### <a name="parameters"></a>パラメーター

*prbi*<br/>
ポインターを[REBARINFO](/windows/desktop/api/commctrl/ns-commctrl-tagrebarinfo)を設定する情報を含む構造体。 設定する必要があります、`cbSize`をこの構造体のメンバー`sizeof(REBARINFO)`このメッセージを送信する前に

### <a name="return-value"></a>戻り値

成功した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CReBarCtrl#14](../../mfc/reference/codesnippet/cpp/crebarctrl-class_14.cpp)]

##  <a name="setbkcolor"></a>  CReBarCtrl::SetBkColor

Win32 メッセージの動作を実装[RB_SETBKCOLOR](/windows/desktop/Controls/rb-setbkcolor)」の説明に従って、Windows SDK。

```
COLORREF SetBkColor(COLORREF clr);
```

### <a name="parameters"></a>パラメーター

*clr*<br/>
新しい既定の背景色を表す COLORREF 値。

### <a name="return-value"></a>戻り値

A [COLORREF](/windows/desktop/gdi/colorref)前の既定の背景色を表す値です。

### <a name="remarks"></a>Remarks

詳細については、背景色を設定して、既定値を設定する方法については、このトピックを参照してください。

##  <a name="setcolorscheme"></a>  CReBarCtrl::SetColorScheme

Rebar コントロールのボタンの配色を設定します。

```
void SetColorScheme(const COLORSCHEME* lpcs);
```

### <a name="parameters"></a>パラメーター

*lpc*<br/>
ポインターを[COLORSCHEME](/windows/desktop/api/commctrl/ns-commctrl-tagcolorscheme) Windows SDK」の説明に従って、構造体します。

### <a name="remarks"></a>Remarks

`COLORSCHEME`構造には、ボタンの強調表示色とボタンの影の色の両方が含まれています。

##  <a name="setextendedstyle"></a>  CReBarCtrl::SetExtendedStyle

現在の rebar コントロールの拡張スタイルを設定します。

```
DWORD SetExtendedStyle(
    DWORD dwMask,
    DWORD dwStyleEx);
```

### <a name="parameters"></a>パラメーター

|パラメーター|説明|
|---------------|-----------------|
|*dwMask*|[in]どのフラグを指定するフラグのビットごとの組み合わせ (OR)、 *dwStyleEx*パラメーターを適用します。 次の値の 1 つ以上を使用します。<br /><br /> RBS_EX_SPLITTER:既定で表示、スプリッター下部にある横モードで、右側に縦モードでします。<br /><br /> RBS_EX_TRANSPARENT:転送、 [WM_ERASEBKGND](/windows/desktop/winmsg/wm-erasebkgnd)メッセージを親ウィンドウ。|
|*dwStyleEx*|[in]適用するスタイルを指定するフラグのビットごとの組み合わせ (OR)。 スタイルを設定するで使用されている同じフラグを指定、 *dwMask*パラメーター。 スタイルをリセットするには、バイナリのゼロを指定します。|

### <a name="return-value"></a>戻り値

以前の拡張スタイル。

### <a name="remarks"></a>Remarks

このメソッドは、送信、 [RB_SETEXTENDEDSTYLE](/windows/desktop/Controls/rb-setextendedstyle)メッセージは、Windows SDK で説明します。

##  <a name="setimagelist"></a>  CReBarCtrl::SetImageList

Rebar コントロールには、イメージ リストを割り当てます。

```
BOOL SetImageList(CImageList* pImageList);
```

### <a name="parameters"></a>パラメーター

*pImageList*<br/>
ポインターを[CImageList](../../mfc/reference/cimagelist-class.md) rebar コントロールに割り当てられるイメージ リストを含むオブジェクト。

### <a name="return-value"></a>戻り値

成功した場合は 0 以外を返します。それ以外の場合は 0 を返します。

##  <a name="setowner"></a>  CReBarCtrl::SetOwner

Win32 メッセージの動作を実装[RB_SETPARENT](/windows/desktop/Controls/rb-setparent)」の説明に従って、Windows SDK。

```
CWnd* SetOwner(CWnd* pWnd);
```

### <a name="parameters"></a>パラメーター

*我が物*<br/>
ポインター、 `CWnd` rebar コントロールの所有者として設定するオブジェクト。

### <a name="return-value"></a>戻り値

ポインターを[CWnd](../../mfc/reference/cwnd-class.md) rebar コントロールの現在の所有者であるオブジェクト。

### <a name="remarks"></a>Remarks

このメンバー関数へのポインターを使用して`CWnd`ウィンドウへのハンドルではなく、rebar コントロールの現在および選択した所有者の両方のオブジェクトします。

> [!NOTE]
>  このメンバー関数は、コントロールが作成されたときに設定した実際の親を変更していません。はなく指定したウィンドウに通知メッセージを送信します。

##  <a name="setpalette"></a>  CReBarCtrl::SetPalette

Win32 メッセージの動作を実装[RB_SETPALETTE](/windows/desktop/Controls/rb-setpalette)」の説明に従って、Windows SDK。

```
CPalette* SetPalette(HPALETTE hPal);
```

### <a name="parameters"></a>パラメーター

*hPal*<br/>
Rebar コントロールで使用する新しいパレットを指定する HPALETTE します。

### <a name="return-value"></a>戻り値

ポインターを[CPalette](../../mfc/reference/cpalette-class.md) rebar コントロールの前のパレットを指定するオブジェクト。

### <a name="remarks"></a>Remarks

このメンバー関数を使用するノートを`CPalette`HPALETTE ではなく、戻り値としてオブジェクト。

##  <a name="settextcolor"></a>  CReBarCtrl::SetTextColor

Win32 メッセージの動作を実装[RB_SETTEXTCOLOR](/windows/desktop/Controls/rb-settextcolor)」の説明に従って、Windows SDK。

```
COLORREF SetTextColor(COLORREF clr);
```

### <a name="parameters"></a>パラメーター

*clr*<br/>
新しいテキストを表す COLORREF 値の色、`CReBarCtrl`オブジェクト。

### <a name="return-value"></a>戻り値

[COLORREF](/windows/desktop/gdi/colorref)前のテキストの色を表す値に関連付けられている、`CReBarCtrl`オブジェクト。

### <a name="remarks"></a>Remarks

Rebar コントロールでテキストの色の柔軟性をサポートするために提供されます。

##  <a name="settooltips"></a>  CReBarCtrl::SetToolTips

Rebar コントロールで、ツール ヒント コントロールに関連付けます。

```
void SetToolTips(CToolTipCtrl* pToolTip);
```

### <a name="parameters"></a>パラメーター

*pToolTip*<br/>
ポインターを[CToolTipCtrl](../../mfc/reference/ctooltipctrl-class.md)オブジェクト

### <a name="remarks"></a>Remarks

破棄する必要があります、`CToolTipCtrl`でそれが済んだらオブジェクトします。

##  <a name="setwindowtheme"></a>  CReBarCtrl::SetWindowTheme

Rebar コントロールの視覚スタイルを設定します。

```
HRESULT SetWindowTheme(LPCWSTR pszSubAppName);
```

### <a name="parameters"></a>パラメーター

*pszSubAppName*<br/>
設定する rebar の visual スタイルを含む Unicode 文字列へのポインター。

### <a name="return-value"></a>戻り値

戻り値は使用されません。

### <a name="remarks"></a>Remarks

このメンバー関数の機能をエミュレートする、 [RB_SETWINDOWTHEME](/windows/desktop/Controls/rb-setwindowtheme)メッセージ、Windows SDK で説明されているとします。

##  <a name="showband"></a>  CReBarCtrl::ShowBand

Win32 メッセージの動作を実装[RB_SHOWBAND](/windows/desktop/Controls/rb-showband)」の説明に従って、Windows SDK。

```
BOOL ShowBand(
    UINT uBand,
    BOOL fShow = TRUE);
```

### <a name="parameters"></a>パラメーター

*uBand*<br/>
Rebar コントロールのバンドの 0 から始まるインデックス。

*fShow*<br/>
バンドを表示するか非表示にすることを示します。 この値が TRUE の場合は、band が表示されます。 それ以外の場合、バンドは表示されません。

### <a name="return-value"></a>戻り値

成功した場合は 0 以外を返します。それ以外の場合は 0 を返します。

##  <a name="sizetorect"></a>  CReBarCtrl::SizeToRect

Win32 メッセージの動作を実装[RB_SIZETORECT](/windows/desktop/Controls/rb-sizetorect)」の説明に従って、Windows SDK。

```
BOOL SizeToRect(CRect& rect);
```

### <a name="parameters"></a>パラメーター

*rect*<br/>
参照を[CRect](../../atl-mfc-shared/reference/crect-class.md) rebar コントロールのサイズを示す四角形を指定するオブジェクト。

### <a name="return-value"></a>戻り値

成功した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>Remarks

このメンバー関数を使用するノートを`CRect`オブジェクトをパラメーターとしてではなく`RECT`構造体。

## <a name="see-also"></a>関連項目

[CWnd クラス](../../mfc/reference/cwnd-class.md)<br/>
[階層図](../../mfc/hierarchy-chart.md)

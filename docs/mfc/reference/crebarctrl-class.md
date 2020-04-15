---
title: クラス
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
ms.openlocfilehash: 776892d71e2cb0f5d57512754cd7fa12730eb044
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81367443"
---
# <a name="crebarctrl-class"></a>クラス

Rebar コントロールの機能がカプセル化されています。Rebar コントロールは、子ウィンドウを含むコンテナーです。

## <a name="syntax"></a>構文

```
class CReBarCtrl : public CWnd
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[クレバーCtrl::CReBarCtrl](#crebarctrl)|`CReBarCtrl` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CReBarCtrl::開始ドラッグ](#begindrag)|Rebar コントロールをドラッグ アンド ドロップ モードにします。|
|[CReBarCtrl::作成](#create)|Rebar コントロールを作成し、オブジェクトに`CReBarCtrl`アタッチします。|
|[CReBarCtrl::作成します。](#createex)|指定した Windows 拡張スタイルを使用して Rebar コントロールを作成`CReBarCtrl`し、オブジェクトにアタッチします。|
|[クレバーCtrl::Dエレテバンド](#deleteband)|Rebar コントロールからバンドを削除します。|
|[:Dラグムーブ](#dragmove)|を呼び出した後、Rebar コントロール内の`BeginDrag`ドラッグ位置を更新します。|
|[CReBarCtrl::エンドドラッグ](#enddrag)|Rebar コントロールのドラッグ アンド ドロップ操作を終了します。|
|[クレバーCtrl::ゲットバンドボーダーズ](#getbandborders)|バンドの境界線を取得します。|
|[を返します。](#getbandcount)|Rebar コントロール内のバンドの数を取得します。|
|[を返します。](#getbandinfo)|Rebar コントロール内の指定したバンドに関する情報を取得します。|
|[を返します。](#getbandmargins)|バンドの余白を取得します。|
|[を返します。](#getbarheight)|Rebar コントロールの高さを取得します。|
|[を返します。](#getbarinfo)|Rebar コントロールと、そのコントロールが使用するイメージ リストに関する情報を取得します。|
|[次の項目を使用します。](#getbkcolor)|Rebar コントロールの既定の背景色を取得します。|
|[をクリックします。](#getcolorscheme)|Rebar コントロールに関連付けられている[COLORSCHEME](/windows/win32/api/commctrl/ns-commctrl-colorscheme)構造体を取得します。|
|[を返します。](#getdroptarget)|Rebar コントロールのインターフェイス ポインター`IDropTarget`を取得します。|
|[を返します。](#getextendedstyle)|現在の Rebar コントロールの拡張スタイルを取得します。|
|[を返します。](#getimagelist)|Rebar コントロールに関連付けられているイメージ リストを取得します。|
|[コントロールバーCtrl::ゲットパレット](#getpalette)|Rebar コントロールの現在のパレットを取得します。|
|[クレバーCtrl::ゲットレック](#getrect)|Rebar コントロール内の特定のバンドに外接する四角形を取得します。|
|[を返します。](#getrowcount)|Rebar コントロール内のバンド行の数を取得します。|
|[を返します。](#getrowheight)|Rebar コントロール内の指定した行の高さを取得します。|
|[を返します。](#gettextcolor)|Rebar コントロールの既定のテキスト色を取得します。|
|[ヒントを取得します。](#gettooltips)|Rebar コントロールに関連付けられているツール ヒント コントロールのハンドルを取得します。|
|[ヒットテスト](#hittest)|Rebar バンドが画面上の特定のポイントにある場合、そのポイントに Rebar バンドが存在する場合に、その部分を決定します。|
|[を返します。](#idtoindex)|帯識別子 (ID) を Rebar コントロールのバンド インデックスに変換します。|
|[次の文字列を使用します。](#insertband)|Rebar コントロールに新しいバンドを挿入します。|
|[CReBarCtrl::最大化バンド](#maximizeband)|Rebar コントロールのバンドのサイズを最大サイズに変更します。|
|[を切り替える::バンドを最小化する](#minimizeband)|Rebar コントロールのバンドのサイズを最小サイズに変更します。|
|[CReBarCtrl::移動バンド](#moveband)|バンドをインデックス間で移動します。|
|[クレバーCtrl::Pシュシェブロン](#pushchevron)|プログラムによってシェブロンをプッシュします。|
|[次のコマンドを使用します。](#restoreband)|Rebar コントロールのバンドのサイズを、理想的なサイズに変更します。|
|[を設定します。](#setbandinfo)|Rebar コントロール内の既存のバンドの特性を設定します。|
|[を切り離して下さる](#setbandwidth)|現在の Rebar コントロール内の指定された固定バンドの幅を設定します。|
|[を返します。](#setbarinfo)|Rebar コントロールの特性を設定します。|
|[を返します。](#setbkcolor)|Rebar コントロールの既定の背景色を設定します。|
|[コントロールバーCtrl::セットカラースキーム](#setcolorscheme)|Rebar コントロールのボタンの配色を設定します。|
|[を使用します。](#setextendedstyle)|現在の Rebar コントロールの拡張スタイルを設定します。|
|[を返します。](#setimagelist)|Rebar コントロールのイメージ リストを設定します。|
|[クレバーCtrl::セットオーナー](#setowner)|Rebar コントロールのオーナー ウィンドウを設定します。|
|[コントロールCtrl::セットパレット](#setpalette)|Rebar コントロールの現在のパレットを設定します。|
|[をクリックします。](#settextcolor)|Rebar コントロールの既定のテキスト色を設定します。|
|[コントロールバーCtrl::ヒントの設定](#settooltips)|ツール ヒント コントロールを Rebar コントロールに関連付けます。|
|[コントロールバーCtrl::セットウィンドウテーマ](#setwindowtheme)|Rebar コントロールの表示スタイルを設定します。|
|[CReBarCtrl::ショーバンド](#showband)|Rebar コントロール内の特定のバンドを表示または非表示にします。|
|[クレバーCtrl::サイズトレクト](#sizetorect)|指定した四角形に Rebar コントロールを配置します。|

## <a name="remarks"></a>解説

Rebar コントロールが常駐するアプリケーションは、Rebar コントロールに含まれる子ウィンドウを Rebar バンドに割り当てます。 子ウィンドウは、通常は別のコモン コントロールです。

Rebar コントロールには、1 つまたは複数のバンドが含まれています。 各バンドには、グリッパー バー、ビットマップ、テキスト ラベル、および子ウィンドウの組み合わせを含めることができます。 バンドには、これらの項目の 1 つだけを含めることができます。

Rebar コントロールは、指定した背景ビットマップ上に子ウィンドウを表示できます。 RBBS_FIXEDSIZEスタイルを使用するバンドを除き、すべての Rebar コントロールバンドのサイズを変更できます。 Rebar コントロール バンドの位置を変更またはサイズ変更すると、Rebar コントロールはそのバンドに割り当てられた子ウィンドウのサイズと位置を管理します。 コントロール内のバンドのサイズを変更するには、バンドのグリッパー バーをクリックしてドラッグします。

次の図は、3 つのバンドを持つ Rebar コントロールを示しています。

- バンド 0 には、フラットで透明なツール バー コントロールが含まれています。

- バンド 1 には、透明な標準と透明の両方のドロップダウン ボタンが含まれています。

- バンド 2 には、コンボ ボックスと 4 つの標準ボタンが含まれています。

   ![Rebar メニューの例](../../mfc/reference/media/vc4scc1.gif "Rebar メニューの例")

## <a name="rebar-control"></a>リバー コントロール

Rebar コントロールのサポート:

- イメージ リスト。

- メッセージ処理。

- カスタム描画機能。

- 標準のウィンドウ スタイルに加えて、さまざまなコントロール スタイル。 これらのスタイルの一覧については、「Windows SDK の[Rebar コントロール スタイル](/windows/win32/Controls/rebar-control-styles)」を参照してください。

詳細については、「 [CReBarCtrl の使用](../../mfc/using-crebarctrl.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CReBarCtrl`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxcmn.h

## <a name="crebarctrlbegindrag"></a><a name="begindrag"></a>CReBarCtrl::開始ドラッグ

Windows SDK で説明されているように、Win32 メッセージ[RB_BEGINDRAG](/windows/win32/Controls/rb-begindrag)の動作を実装します。

```
void BeginDrag(
    UINT uBand,
    DWORD dwPos = (DWORD)-1);
```

### <a name="parameters"></a>パラメーター

*ユーバンド*<br/>
ドラッグ アンド ドロップ操作が影響を受けるバンドの 0 から始まるインデックス。

*ドウォポス*<br/>
マウスの開始座標を含む DWORD 値。 水平座標は LOWORD に含まれ、垂直座標は HIWORD に含まれています。 (DWORD)-1 を渡すと、Rebar コントロールは、コントロールのスレッドが最後に呼び出された時にマウス`GetMessage`の`PeekMessage`位置を使用します。

## <a name="crebarctrlcreate"></a><a name="create"></a>CReBarCtrl::作成

Rebar コントロールを作成し、オブジェクトに`CReBarCtrl`アタッチします。

```
virtual BOOL Create(
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>パラメーター

*Dwstyle*<br/>
コントロールに適用される Rebar コントロール スタイルの組み合わせを指定します。 サポートされているスタイルの一覧については、Windows SDK の[Rebar コントロール](/windows/win32/Controls/rebar-control-styles)スタイルを参照してください。

*Rect*<br/>
Rebar コントロールの位置とサイズを示す[CRect](../../atl-mfc-shared/reference/crect-class.md)オブジェクトまたは[RECT](/previous-versions/dd162897\(v=vs.85\))構造体への参照。

*pParentWnd*<br/>
Rebar コントロールの親ウィンドウである[CWnd](../../mfc/reference/cwnd-class.md)オブジェクトへのポインター。 NULL にすることはできません。

*nID*<br/>
Rebar コントロールのコントロール ID を指定します。

### <a name="return-value"></a>戻り値

オブジェクトが正常に作成された場合は 0 以外の値を返します。それ以外の場合は 0。

### <a name="remarks"></a>解説

Rebar コントロールを作成するには、次の 2 つの手順を実行します。

1. オブジェクトを構築する[CReBarCtrl](#crebarctrl)を`CReBarCtrl`呼び出します。

1. このメンバー関数を呼び出して、Windows Rebar コントロールを作成し`CReBarCtrl`、オブジェクトにアタッチします。

を呼び`Create`出すと、コモン コントロールが初期化されます。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CReBarCtrl#3](../../mfc/reference/codesnippet/cpp/crebarctrl-class_1.cpp)]

## <a name="crebarctrlcreateex"></a><a name="createex"></a>CReBarCtrl::作成します。

コントロール (子ウィンドウ) を作成し、オブジェクトに関連`CReBarCtrl`付けます。

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
コントロールに適用される Rebar コントロール スタイルの組み合わせを指定します。 サポートされているスタイルの一覧については、Windows SDK の[「Rebar コントロール スタイル](/windows/win32/Controls/rebar-control-styles)」を参照してください。

*Rect*<br/>
作成するウィンドウのサイズと位置を記述する[RECT](/previous-versions/dd162897\(v=vs.85\))構造体への参照を *、 pParentWnd*のクライアント座標で指定します。

*pParentWnd*<br/>
コントロールの親であるウィンドウへのポインター。

*nID*<br/>
コントロールの子ウィンドウ ID。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>解説

[`CreateEx`[作成]](#create)の代わりに、Windows 拡張スタイルの序文で指定された拡張 Windows スタイル**を適用WS_EX_。**

## <a name="crebarctrlcrebarctrl"></a><a name="crebarctrl"></a>クレバーCtrl::CReBarCtrl

`CReBarCtrl` オブジェクトを作成します。

```
CReBarCtrl();
```

### <a name="example"></a>例

  [「CReBarCtrl::作成](#create)」の例を参照してください。

## <a name="crebarctrldeleteband"></a><a name="deleteband"></a>クレバーCtrl::Dエレテバンド

Windows SDK で説明されているように、Win32 メッセージ[RB_DELETEBAND](/windows/win32/Controls/rb-deleteband)の動作を実装します。

```
BOOL DeleteBand(UINT uBand);
```

### <a name="parameters"></a>パラメーター

*ユーバンド*<br/>
削除するバンドの 0 から始まるインデックス。

### <a name="return-value"></a>戻り値

バンドが正常に削除された場合は 0 以外。それ以外の場合は 0。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CReBarCtrl#4](../../mfc/reference/codesnippet/cpp/crebarctrl-class_2.cpp)]

## <a name="crebarctrldragmove"></a><a name="dragmove"></a>:Dラグムーブ

Windows SDK で説明されているように、Win32 メッセージ[RB_DRAGMOVE](/windows/win32/Controls/rb-dragmove)の動作を実装します。

```
void DragMove(DWORD dwPos = (DWORD)-1);
```

### <a name="parameters"></a>パラメーター

*ドウォポス*<br/>
新しいマウス座標を含む DWORD 値。 水平座標は LOWORD に含まれ、垂直座標は HIWORD に含まれています。 (DWORD)-1 を渡すと、Rebar コントロールは、コントロールのスレッドが最後に呼び出された時にマウス`GetMessage`の`PeekMessage`位置を使用します。

## <a name="crebarctrlenddrag"></a><a name="enddrag"></a>CReBarCtrl::エンドドラッグ

Windows SDK で説明されているように、Win32 メッセージ[RB_ENDDRAG](/windows/win32/Controls/rb-enddrag)の動作を実装します。

```
void EndDrag();
```

## <a name="crebarctrlgetbandborders"></a><a name="getbandborders"></a>クレバーCtrl::ゲットバンドボーダーズ

Win32 メッセージ[RB_GETBANDBORDERS](/windows/win32/Controls/rb-getbandborders)の動作を実装します。

```
void GetBandBorders(
    UINT uBand,
    LPRECT prc) const;
```

### <a name="parameters"></a>パラメーター

*ユーバンド*<br/>
境界を取得するバンドの 0 から始まるインデックス。

*Prc*<br/>
帯の境界を受け取る[RECT](/previous-versions/dd162897\(v=vs.85\))構造体へのポインタ。 rebar コントロールにRBS_BANDBORDERSスタイルがある場合、この構造体の各メンバーは、境界を構成するバンドの対応する側のピクセル数を受け取ります。 rebar コントロールにRBS_BANDBORDERSスタイルがない場合、この構造体の左側のメンバーだけが有効な情報を受け取ります。 Rebar コントロールスタイルの詳細については、Windows SDK の[「Rebar コントロールスタイル](/windows/win32/Controls/rebar-control-styles)」を参照してください。

## <a name="crebarctrlgetbandcount"></a><a name="getbandcount"></a>を返します。

Windows SDK で説明されているように、Win32 メッセージ[RB_GETBANDCOUNT](/windows/win32/Controls/rb-getbandcount)の動作を実装します。

```
UINT GetBandCount() const;
```

### <a name="return-value"></a>戻り値

コントロールに割り当てられたバンドの数。

## <a name="crebarctrlgetbandinfo"></a><a name="getbandinfo"></a>を返します。

Windows SDK で説明されているように、Win32 メッセージ[RB_GETBANDINFO](/windows/win32/Controls/rb-getbandinfo)の動作を実装します。

```
BOOL GetBandInfo(
    UINT uBand,
    REBARBANDINFO* prbbi) const;
```

### <a name="parameters"></a>パラメーター

*ユーバンド*<br/>
情報を取得するバンドの 0 から始まるインデックス。

*プルビ*<br/>
バンド情報を受け取るための[REBARBANDINFO](/windows/win32/api/commctrl/ns-commctrl-rebarbandinfow)構造体へのポインター。 この構造体のメンバー`cbSize`を`sizeof(REBARBANDINFO)`設定し、このメッセージを`fMask`送信する前に、取得する項目にメンバーを設定する必要があります。

### <a name="return-value"></a>戻り値

成功した場合は 0 以外を返します。それ以外の場合は 0 を返します。

## <a name="crebarctrlgetbandmargins"></a><a name="getbandmargins"></a>を返します。

バンドの余白を取得します。

```
void GetBandMargins(PMARGINS pMargins);
```

### <a name="parameters"></a>パラメーター

*マージン*<br/>
情報を受け取る[MARGINS](/windows/win32/api/uxtheme/ns-uxtheme-margins)構造体へのポインター。

### <a name="remarks"></a>解説

このメンバー関数は、Windows SDK で説明されているように[、RB_GETBANDMARGINS](/windows/win32/Controls/rb-getbandmargins)メッセージの機能をエミュレートします。

## <a name="crebarctrlgetbarheight"></a><a name="getbarheight"></a>を返します。

Rebar バーの高さを取得します。

```
UINT GetBarHeight() const;
```

### <a name="return-value"></a>戻り値

コントロールの高さをピクセル単位で表す値。

## <a name="crebarctrlgetbarinfo"></a><a name="getbarinfo"></a>を返します。

Windows SDK で説明されているように、Win32 メッセージ[RB_GETBARINFO](/windows/win32/Controls/rb-getbarinfo)の動作を実装します。

```
BOOL GetBarInfo(REBARINFO* prbi) const;
```

### <a name="parameters"></a>パラメーター

*プルビ*<br/>
REBAR 制御情報を受け取る[REBARINFO](/windows/win32/api/commctrl/ns-commctrl-rebarinfo)構造体へのポインター。 このメッセージを送信する前に、この構造体の`sizeof(REBARINFO)` *cbSize*メンバーをに設定する必要があります。

### <a name="return-value"></a>戻り値

成功した場合は 0 以外を返します。それ以外の場合は 0 を返します。

## <a name="crebarctrlgetbkcolor"></a><a name="getbkcolor"></a>次の項目を使用します。

Windows SDK で説明されているように、Win32 メッセージ[RB_GETBKCOLOR](/windows/win32/Controls/rb-getbkcolor)の動作を実装します。

```
COLORREF GetBkColor() const;
```

### <a name="return-value"></a>戻り値

現在の既定の背景色を表す COLORREF 値。

## <a name="crebarctrlgetcolorscheme"></a><a name="getcolorscheme"></a>をクリックします。

REBAR コントロールの[COLORSCHEME](/windows/win32/api/commctrl/ns-commctrl-colorscheme)構造体を取得します。

```
BOOL GetColorScheme(COLORSCHEME* lpcs);
```

### <a name="parameters"></a>パラメーター

*lpcs*<br/>
Windows SDK で説明されているように、[カラースキーム](/windows/win32/api/commctrl/ns-commctrl-colorscheme)構造体へのポインター。

### <a name="return-value"></a>戻り値

成功した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>解説

構造`COLORSCHEME`には、ボタンのハイライトカラーとボタンの影の色が含まれます。

## <a name="crebarctrlgetdroptarget"></a><a name="getdroptarget"></a>を返します。

Windows SDK で説明されているように、Win32 メッセージ[RB_GETDROPTARGET](/windows/win32/Controls/rb-getdroptarget)の動作を実装します。

```
IDropTarget* GetDropTarget() const;
```

### <a name="return-value"></a>戻り値

[インターフェイス](/windows/win32/api/oleidl/nn-oleidl-idroptarget)へのポインター。

## <a name="crebarctrlgetextendedstyle"></a><a name="getextendedstyle"></a>を返します。

現在の Rebar コントロールの拡張スタイルを取得します。

```
DWORD GetExtendedStyle() const;
```

### <a name="return-value"></a>戻り値

拡張スタイルを示すフラグのビットごとの組み合わせ (OR)。 可能なフラグはRBS_EX_SPLITTERされ、RBS_EX_TRANSPARENT。 詳細については[、メソッドの](#setextendedstyle) *dwMask*パラメーターを参照してください。

### <a name="remarks"></a>解説

このメソッドは、Windows SDK で説明されている[RB_GETEXTENDEDSTYLE](/windows/win32/Controls/rb-dragmove)メッセージを送信します。

## <a name="crebarctrlgetimagelist"></a><a name="getimagelist"></a>を返します。

Rebar`CImageList`コントロールに関連付けられているオブジェクトを取得します。

```
CImageList* GetImageList() const;
```

### <a name="return-value"></a>戻り値

[オブジェクト](../../mfc/reference/cimagelist-class.md)へのポインター。 コントロールにイメージ リストが設定されていない場合は NULL を返します。

### <a name="remarks"></a>解説

このメンバー関数は、Windows SDK で説明されているように[、REBARINFO](/windows/win32/api/commctrl/ns-commctrl-rebarinfo)構造体に格納されているサイズとマスクの情報を使用します。

## <a name="crebarctrlgetpalette"></a><a name="getpalette"></a>コントロールバーCtrl::ゲットパレット

Rebar コントロールの現在のパレットを取得します。

```
CPalette* GetPalette() const;
```

### <a name="return-value"></a>戻り値

Rebar コントロールの現在のパレットを指定する[CPalette](../../mfc/reference/cpalette-class.md)オブジェクトへのポインター。

### <a name="remarks"></a>解説

このメンバー関数は、HPALETTE`CPalette`ではなく、戻り値としてオブジェクトを使用することに注意してください。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CReBarCtrl#5](../../mfc/reference/codesnippet/cpp/crebarctrl-class_3.cpp)]

## <a name="crebarctrlgetrect"></a><a name="getrect"></a>クレバーCtrl::ゲットレック

Windows SDK で説明されているように、Win32 メッセージ[RB_GETRECT](/windows/win32/Controls/rb-getrect)の動作を実装します。

```
BOOL GetRect(
    UINT uBand,
    LPRECT prc) const;
```

### <a name="parameters"></a>パラメーター

*ユーバンド*<br/>
Rebar コントロール内のバンドの 0 から始まるインデックス。

*Prc*<br/>
REBAR バンドの境界を受け取る[RECT](/previous-versions/dd162897\(v=vs.85\))構造体へのポインター。

### <a name="return-value"></a>戻り値

成功した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CReBarCtrl#6](../../mfc/reference/codesnippet/cpp/crebarctrl-class_4.cpp)]

## <a name="crebarctrlgetrowcount"></a><a name="getrowcount"></a>を返します。

Windows SDK で説明されているように、Win32 メッセージ[RB_GETROWCOUNT](/windows/win32/Controls/rb-getrowcount)の動作を実装します。

```
UINT GetRowCount() const;
```

### <a name="return-value"></a>戻り値

コントロール内のバンド行数を表す UINT 値。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CReBarCtrl#7](../../mfc/reference/codesnippet/cpp/crebarctrl-class_5.cpp)]

## <a name="crebarctrlgetrowheight"></a><a name="getrowheight"></a>を返します。

Windows SDK で説明されているように、Win32 メッセージ[RB_GETROWHEIGHT](/windows/win32/Controls/rb-getrowheight)の動作を実装します。

```
UINT GetRowHeight(UINT uRow) const;
```

### <a name="parameters"></a>パラメーター

*uRow*<br/>
高さを取得するバンドの 0 から始まるインデックス。

### <a name="return-value"></a>戻り値

行の高さをピクセル単位で表す UINT 値。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CReBarCtrl#8](../../mfc/reference/codesnippet/cpp/crebarctrl-class_6.cpp)]

## <a name="crebarctrlgettextcolor"></a><a name="gettextcolor"></a>を返します。

Windows SDK で説明されているように、Win32 メッセージ[RB_GETTEXTCOLOR](/windows/win32/Controls/rb-gettextcolor)の動作を実装します。

```
COLORREF GetTextColor() const;
```

### <a name="return-value"></a>戻り値

現在の既定のテキストの色を表す COLORREF 値。

## <a name="crebarctrlgettooltips"></a><a name="gettooltips"></a>ヒントを取得します。

Win32 メッセージ[RB_GETTOOLTIPS](/windows/win32/Controls/rb-gettooltips)の動作を実装します。

```
CToolTipCtrl* GetToolTips() const;
```

### <a name="return-value"></a>戻り値

[オブジェクトへの](../../mfc/reference/ctooltipctrl-class.md)ポインター。

### <a name="remarks"></a>解説

MFC の実装では、HWND ではなく`GetToolTips``CToolTipCtrl`、 へのポインターが返されることに注意してください。

## <a name="crebarctrlhittest"></a><a name="hittest"></a>ヒットテスト

Windows SDK で説明されているように、Win32 メッセージ[RB_HITTEST](/windows/win32/Controls/rb-hittest)の動作を実装します。

```
int HitTest(RBHITTESTINFO* prbht);
```

### <a name="parameters"></a>パラメーター

*プルブト*<br/>
[構造体](/windows/win32/api/commctrl/ns-commctrl-rbhittestinfo)へのポインター。 メッセージを送信する前に`pt`、この構造体のメンバーは、クライアント座標でテストされるポイントに初期化する必要があります。

### <a name="return-value"></a>戻り値

指定されたポイントでのバンドの 0 から始まるインデックス。または、そのポイントに Rebar バンドがない場合は -1。

## <a name="crebarctrlidtoindex"></a><a name="idtoindex"></a>を返します。

Windows SDK で説明されているように、Win32 メッセージ[RB_IDTOINDEX](/windows/win32/controls/rb-idtoindex)の動作を実装します。

```
int IDToIndex(UINT uBandID) const;
```

### <a name="parameters"></a>パラメーター

*ユーバンドID*<br/>
指定されたバンドのアプリケーション定義の ID で、バンド`wID`が挿入されるときに[REBARBANDINFO](/windows/win32/api/commctrl/ns-commctrl-rebarbandinfow)構造体のメンバーに渡されます。

### <a name="return-value"></a>戻り値

成功した場合は 0 から始まるバンド インデックス、それ以外の場合は -1。 重複するバンド インデックスが存在する場合は、最初のインデックスが返されます。

## <a name="crebarctrlinsertband"></a><a name="insertband"></a>次の文字列を使用します。

Windows SDK で説明されているように、Win32 メッセージ[RB_INSERTBAND](/windows/win32/Controls/rb-insertband)の動作を実装します。

```
BOOL InsertBand(
    UINT uIndex,
    REBARBANDINFO* prbbi);
```

### <a name="parameters"></a>パラメーター

*インデックス*<br/>
バンドが挿入される位置の 0 から始まるインデックス。 このパラメーターを -1 に設定すると、コントロールは最後の位置に新しいバンドを追加します。

*プルビ*<br/>
挿入するバンドを定義する[REBARBANDINFO](/windows/win32/api/commctrl/ns-commctrl-rebarbandinfow)構造体へのポインター。 この関数を呼び出す前に、この`sizeof(REBARBANDINFO)`構造体の*cbSize*メンバーをに設定する必要があります。

### <a name="return-value"></a>戻り値

成功した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CReBarCtrl#9](../../mfc/reference/codesnippet/cpp/crebarctrl-class_7.cpp)]

## <a name="crebarctrlmaximizeband"></a><a name="maximizeband"></a>CReBarCtrl::最大化バンド

Rebar コントロールのバンドのサイズを最大サイズに変更します。

```
void MaximizeBand(UINT uBand);
```

### <a name="parameters"></a>パラメーター

*ユーバンド*<br/>
最大にするバンドの 0 から始まるインデックス。

### <a name="remarks"></a>解説

Windows SDK で説明されているように、Win32`fIdeal`メッセージ[RB_MAXIMIZEBAND](/windows/win32/Controls/rb-maximizeband)の動作を 0 に設定して実装します。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CReBarCtrl#10](../../mfc/reference/codesnippet/cpp/crebarctrl-class_8.cpp)]

## <a name="crebarctrlminimizeband"></a><a name="minimizeband"></a>を切り替える::バンドを最小化する

Rebar コントロールのバンドのサイズを最小サイズに変更します。

```
void MinimizeBand(UINT uBand);
```

### <a name="parameters"></a>パラメーター

*ユーバンド*<br/>
最小化するバンドの 0 から始まるインデックス。

### <a name="remarks"></a>解説

Windows SDK で説明されているように、Win32 メッセージ[RB_MINIMIZEBAND](/windows/win32/Controls/rb-minimizeband)の動作を実装します。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CReBarCtrl#11](../../mfc/reference/codesnippet/cpp/crebarctrl-class_9.cpp)]

## <a name="crebarctrlmoveband"></a><a name="moveband"></a>CReBarCtrl::移動バンド

Win32 メッセージ[RB_MOVEBAND](/windows/win32/Controls/rb-moveband)の動作を実装します。

```
BOOL MoveBand(
    UINT uFrom,
    UINT uTo);
```

### <a name="parameters"></a>パラメーター

*から*<br/>
移動するバンドの 0 から始まるインデックス。

*宇土*<br/>
新しいバンド位置の 0 から始まるインデックス。 このパラメーター値は、バンド数から 1 を引いた値より大きくすることはできません。 バンドの数を取得するには[、GetBandCount](#getbandcount)を呼び出します。

### <a name="return-value"></a>戻り値

成功した場合は 0 以外を返します。それ以外の場合は 0 を返します。

## <a name="crebarctrlpushchevron"></a><a name="pushchevron"></a>クレバーCtrl::Pシュシェブロン

Windows SDK で説明されているように、Win32 メッセージ[RB_PUSHCHEVRON](/windows/win32/Controls/rb-pushchevron)の動作を実装します。

```
void PushChevron(
    UINT uBand,
    LPARAM lAppValue);
```

### <a name="parameters"></a>パラメーター

*ユーバンド*<br/>
シェブロンを押すバンドの 0 から始まるインデックス。

*値*<br/>
アプリケーション定義の 32 ビット値。 Windows SDK の[RB_PUSHCHEVRON](/windows/win32/Controls/rb-pushchevron)の*lAppValue*を参照してください。

## <a name="crebarctrlrestoreband"></a><a name="restoreband"></a>次のコマンドを使用します。

Rebar コントロールのバンドのサイズを、理想的なサイズに変更します。

```
void RestoreBand(UINT uBand);
```

### <a name="parameters"></a>パラメーター

*ユーバンド*<br/>
最大にするバンドの 0 から始まるインデックス。

### <a name="remarks"></a>解説

Win32 メッセージ[RB_MAXIMIZEBAND](/windows/win32/Controls/rb-maximizeband)の動作を実装し`fIdeal`、Windows SDK で説明されているように 1 に設定します。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CReBarCtrl#12](../../mfc/reference/codesnippet/cpp/crebarctrl-class_10.cpp)]

## <a name="crebarctrlsetbandinfo"></a><a name="setbandinfo"></a>を設定します。

Windows SDK で説明されているように、Win32 メッセージ[RB_SETBANDINFO](/windows/win32/Controls/rb-setbandinfo)の動作を実装します。

```
BOOL SetBandInfo(
    UINT uBand,
    REBARBANDINFO* prbbi);
```

### <a name="parameters"></a>パラメーター

*ユーバンド*<br/>
新しい設定を受け取るバンドの 0 から始まるインデックス。

*プルビ*<br/>
挿入するバンドを定義する[REBARBANDINFO](/windows/win32/api/commctrl/ns-commctrl-rebarbandinfow)構造体へのポインター。 このメッセージを送信`cbSize`する前に、この`sizeof(REBARBANDINFO)`構造体のメンバーを に設定する必要があります。

### <a name="return-value"></a>戻り値

成功した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CReBarCtrl#13](../../mfc/reference/codesnippet/cpp/crebarctrl-class_11.cpp)]

## <a name="crebarctrlsetbandwidth"></a><a name="setbandwidth"></a>を切り離して下さる

現在の Rebar コントロール内の指定された固定バンドの幅を設定します。

```
BOOL SetBandWidth(
    UINT uBand,
    int cxWidth);
```

### <a name="parameters"></a>パラメーター

|パラメーター|説明|
|---------------|-----------------|
|*ユーバンド*|[in]Rebar バンドの 0 から始まるインデックス。|
|*幅*|[in]リバーバンドの新しい幅(ピクセル単位)。|

### <a name="return-value"></a>戻り値

メソッドが成功した場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

このメソッドは、Windows SDK で説明されている[RB_SETBANDWIDTH](/windows/win32/Controls/rb-setbandwidth)メッセージを送信します。

### <a name="example"></a>例

次のコード例では、`m_rebar`現在の Rebar コントロールにアクセスするために使用される変数 を定義します。 この変数は次の例で使用されています。

[!code-cpp[NVC_MFC_CReBarCtrl_s1#1](../../mfc/reference/codesnippet/cpp/crebarctrl-class_12.h)]

### <a name="example"></a>例

各 Rebar バンドを同じ幅に設定するコード例を次に示します。

[!code-cpp[NVC_MFC_CReBarCtrl_s1#2](../../mfc/reference/codesnippet/cpp/crebarctrl-class_13.cpp)]

## <a name="crebarctrlsetbarinfo"></a><a name="setbarinfo"></a>を返します。

Windows SDK で説明されているように、Win32 メッセージ[RB_SETBARINFO](/windows/win32/Controls/rb-setbarinfo)の動作を実装します。

```
BOOL SetBarInfo(REBARINFO* prbi);
```

### <a name="parameters"></a>パラメーター

*プルビ*<br/>
設定する情報を含む[REBARINFO](/windows/win32/api/commctrl/ns-commctrl-rebarinfo)構造体へのポインター。 このメッセージを送信`cbSize`する前に、この`sizeof(REBARINFO)`構造体のメンバーをに設定する必要があります

### <a name="return-value"></a>戻り値

成功した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CReBarCtrl#14](../../mfc/reference/codesnippet/cpp/crebarctrl-class_14.cpp)]

## <a name="crebarctrlsetbkcolor"></a><a name="setbkcolor"></a>を返します。

Windows SDK で説明されているように、Win32 メッセージ[RB_SETBKCOLOR](/windows/win32/Controls/rb-setbkcolor)の動作を実装します。

```
COLORREF SetBkColor(COLORREF clr);
```

### <a name="parameters"></a>パラメーター

*Clr*<br/>
新しい既定の背景色を表す COLORREF 値。

### <a name="return-value"></a>戻り値

以前の既定の背景色を表す[COLORREF](/windows/win32/gdi/colorref)値。

### <a name="remarks"></a>解説

背景色を設定するタイミングと、既定値を設定する方法の詳細については、このトピックを参照してください。

## <a name="crebarctrlsetcolorscheme"></a><a name="setcolorscheme"></a>コントロールバーCtrl::セットカラースキーム

Rebar コントロールのボタンの配色を設定します。

```
void SetColorScheme(const COLORSCHEME* lpcs);
```

### <a name="parameters"></a>パラメーター

*lpcs*<br/>
Windows SDK で説明されているように、[カラースキーム](/windows/win32/api/commctrl/ns-commctrl-colorscheme)構造体へのポインター。

### <a name="remarks"></a>解説

構造`COLORSCHEME`には、ボタンのハイライトカラーとボタンの影の色の両方が含まれています。

## <a name="crebarctrlsetextendedstyle"></a><a name="setextendedstyle"></a>を使用します。

現在の Rebar コントロールの拡張スタイルを設定します。

```
DWORD SetExtendedStyle(
    DWORD dwMask,
    DWORD dwStyleEx);
```

### <a name="parameters"></a>パラメーター

|パラメーター|説明|
|---------------|-----------------|
|*Dwmask*|[in]*dwStyleEx*パラメーターでどのフラグを適用するかを指定するフラグのビットごとの組み合わせ (OR)。 次の値の 1 つ以上を使用します。<br /><br /> RBS_EX_SPLITTER: 既定では、水平モードでは下部にスプリッターを表示し、垂直モードでは右に分割線を表示します。<br /><br /> RBS_EX_TRANSPARENT: [WM_ERASEBKGND](/windows/win32/winmsg/wm-erasebkgnd)メッセージを親ウィンドウに転送します。|
|*ドウスタイルエックス*|[in]適用するスタイルを指定するフラグのビットごとの組み合わせ (OR)。 スタイルを設定するには *、dwMask*パラメーターで使用されているフラグと同じフラグを指定します。 スタイルをリセットするには、2 進ゼロを指定します。|

### <a name="return-value"></a>戻り値

以前の拡張スタイル。

### <a name="remarks"></a>解説

このメソッドは、Windows SDK で説明されている[RB_SETEXTENDEDSTYLE](/windows/win32/Controls/rb-setextendedstyle)メッセージを送信します。

## <a name="crebarctrlsetimagelist"></a><a name="setimagelist"></a>を返します。

イメージ リストを Rebar コントロールに割り当てます。

```
BOOL SetImageList(CImageList* pImageList);
```

### <a name="parameters"></a>パラメーター

*一覧*<br/>
Rebar コントロールに割り当てるイメージ リストを含む[CImageList](../../mfc/reference/cimagelist-class.md)オブジェクトへのポインター。

### <a name="return-value"></a>戻り値

成功した場合は 0 以外を返します。それ以外の場合は 0 を返します。

## <a name="crebarctrlsetowner"></a><a name="setowner"></a>クレバーCtrl::セットオーナー

Windows SDK で説明されているように、Win32 メッセージ[RB_SETPARENT](/windows/win32/Controls/rb-setparent)の動作を実装します。

```
CWnd* SetOwner(CWnd* pWnd);
```

### <a name="parameters"></a>パラメーター

*Pwnd*<br/>
Rebar コントロール`CWnd`の所有者として設定するオブジェクトへのポインター。

### <a name="return-value"></a>戻り値

Rebar コントロールの現在の所有者である[CWnd](../../mfc/reference/cwnd-class.md)オブジェクトへのポインター。

### <a name="remarks"></a>解説

このメンバー関数は、ウィンドウへの`CWnd`ハンドルではなく、Rebar コントロールの現在の所有者と選択された所有者の両方のオブジェクトへのポインターを使用することに注意してください。

> [!NOTE]
> このメンバー関数は、コントロールの作成時に設定された実際の親を変更しません。指定したウィンドウに通知メッセージを送信します。

## <a name="crebarctrlsetpalette"></a><a name="setpalette"></a>コントロールCtrl::セットパレット

Windows SDK で説明されているように、Win32 メッセージ[RB_SETPALETTE](/windows/win32/Controls/rb-setpalette)の動作を実装します。

```
CPalette* SetPalette(HPALETTE hPal);
```

### <a name="parameters"></a>パラメーター

*hパル*<br/>
Rebar コントロールで使用する新しいパレットを指定する HPALETTE です。

### <a name="return-value"></a>戻り値

Rebar コントロールの前のパレットを指定する[CPalette](../../mfc/reference/cpalette-class.md)オブジェクトへのポインター。

### <a name="remarks"></a>解説

このメンバー関数は、HPALETTE`CPalette`ではなく、戻り値としてオブジェクトを使用することに注意してください。

## <a name="crebarctrlsettextcolor"></a><a name="settextcolor"></a>をクリックします。

Windows SDK で説明されているように、Win32 メッセージ[RB_SETTEXTCOLOR](/windows/win32/Controls/rb-settextcolor)の動作を実装します。

```
COLORREF SetTextColor(COLORREF clr);
```

### <a name="parameters"></a>パラメーター

*Clr*<br/>
オブジェクトの新しいテキストの色を表す COLORREF 値。 `CReBarCtrl`

### <a name="return-value"></a>戻り値

オブジェクトに関連付けられている前のテキストの色を表す`CReBarCtrl` [COLORREF](/windows/win32/gdi/colorref)値。

### <a name="remarks"></a>解説

Rebar コントロールでテキストの色の柔軟性をサポートするために提供されます。

## <a name="crebarctrlsettooltips"></a><a name="settooltips"></a>コントロールバーCtrl::ヒントの設定

ツール ヒント コントロールを Rebar コントロールに関連付けます。

```
void SetToolTips(CToolTipCtrl* pToolTip);
```

### <a name="parameters"></a>パラメーター

*ツールチップ*<br/>
[オブジェクトへの](../../mfc/reference/ctooltipctrl-class.md)ポインター

### <a name="remarks"></a>解説

オブジェクトを`CToolTipCtrl`破棄する必要があります。

## <a name="crebarctrlsetwindowtheme"></a><a name="setwindowtheme"></a>コントロールバーCtrl::セットウィンドウテーマ

Rebar コントロールの表示スタイルを設定します。

```
HRESULT SetWindowTheme(LPCWSTR pszSubAppName);
```

### <a name="parameters"></a>パラメーター

*を使用します。*<br/>
設定する Rebar ビジュアル スタイルを含む Unicode 文字列へのポインター。

### <a name="return-value"></a>戻り値

戻り値は使用されません。

### <a name="remarks"></a>解説

このメンバー関数は、Windows SDK で説明されているように[、RB_SETWINDOWTHEME](/windows/win32/Controls/rb-setwindowtheme)メッセージの機能をエミュレートします。

## <a name="crebarctrlshowband"></a><a name="showband"></a>CReBarCtrl::ショーバンド

Windows SDK で説明されているように、Win32 メッセージ[RB_SHOWBAND](/windows/win32/Controls/rb-showband)の動作を実装します。

```
BOOL ShowBand(
    UINT uBand,
    BOOL fShow = TRUE);
```

### <a name="parameters"></a>パラメーター

*ユーバンド*<br/>
Rebar コントロール内のバンドの 0 から始まるインデックス。

*fショー*<br/>
バンドを表示するか非表示にするかを示します。 この値が TRUE の場合、バンドが表示されます。 それ以外の場合は、バンドが非表示になります。

### <a name="return-value"></a>戻り値

成功した場合は 0 以外を返します。それ以外の場合は 0 を返します。

## <a name="crebarctrlsizetorect"></a><a name="sizetorect"></a>クレバーCtrl::サイズトレクト

Windows SDK で説明されているように、Win32 メッセージ[RB_SIZETORECT](/windows/win32/Controls/rb-sizetorect)の動作を実装します。

```
BOOL SizeToRect(CRect& rect);
```

### <a name="parameters"></a>パラメーター

*Rect*<br/>
Rebar コントロールのサイズを変更する四角形を指定する[CRect](../../atl-mfc-shared/reference/crect-class.md)オブジェクトへの参照。

### <a name="return-value"></a>戻り値

成功した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>解説

このメンバー関数は、構造体ではなく`CRect`、パラメーターとしてオブジェクトを使用します`RECT`。

## <a name="see-also"></a>関連項目

[CWnd クラス](../../mfc/reference/cwnd-class.md)<br/>
[階層グラフ](../../mfc/hierarchy-chart.md)

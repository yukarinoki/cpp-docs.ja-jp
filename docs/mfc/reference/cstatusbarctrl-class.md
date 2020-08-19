---
title: CStatusBarCtrl クラス
ms.date: 11/04/2016
f1_keywords:
- CStatusBarCtrl
- AFXCMN/CStatusBarCtrl
- AFXCMN/CStatusBarCtrl::CStatusBarCtrl
- AFXCMN/CStatusBarCtrl::Create
- AFXCMN/CStatusBarCtrl::CreateEx
- AFXCMN/CStatusBarCtrl::DrawItem
- AFXCMN/CStatusBarCtrl::GetBorders
- AFXCMN/CStatusBarCtrl::GetIcon
- AFXCMN/CStatusBarCtrl::GetParts
- AFXCMN/CStatusBarCtrl::GetRect
- AFXCMN/CStatusBarCtrl::GetText
- AFXCMN/CStatusBarCtrl::GetTextLength
- AFXCMN/CStatusBarCtrl::GetTipText
- AFXCMN/CStatusBarCtrl::IsSimple
- AFXCMN/CStatusBarCtrl::SetBkColor
- AFXCMN/CStatusBarCtrl::SetIcon
- AFXCMN/CStatusBarCtrl::SetMinHeight
- AFXCMN/CStatusBarCtrl::SetParts
- AFXCMN/CStatusBarCtrl::SetSimple
- AFXCMN/CStatusBarCtrl::SetText
- AFXCMN/CStatusBarCtrl::SetTipText
helpviewer_keywords:
- CStatusBarCtrl [MFC], CStatusBarCtrl
- CStatusBarCtrl [MFC], Create
- CStatusBarCtrl [MFC], CreateEx
- CStatusBarCtrl [MFC], DrawItem
- CStatusBarCtrl [MFC], GetBorders
- CStatusBarCtrl [MFC], GetIcon
- CStatusBarCtrl [MFC], GetParts
- CStatusBarCtrl [MFC], GetRect
- CStatusBarCtrl [MFC], GetText
- CStatusBarCtrl [MFC], GetTextLength
- CStatusBarCtrl [MFC], GetTipText
- CStatusBarCtrl [MFC], IsSimple
- CStatusBarCtrl [MFC], SetBkColor
- CStatusBarCtrl [MFC], SetIcon
- CStatusBarCtrl [MFC], SetMinHeight
- CStatusBarCtrl [MFC], SetParts
- CStatusBarCtrl [MFC], SetSimple
- CStatusBarCtrl [MFC], SetText
- CStatusBarCtrl [MFC], SetTipText
ms.assetid: 8504ad38-7b91-4746-aede-ac98886eb47b
ms.openlocfilehash: d2440eb05a1367b7d4980494e3d7f5de646d5fd0
ms.sourcegitcommit: 1839405b97036891b6e4d37c99def044d6f37eff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/18/2020
ms.locfileid: "88562650"
---
# <a name="cstatusbarctrl-class"></a>CStatusBarCtrl クラス

Windows コモン ステータス バー コントロール の機能が用意されています。

## <a name="syntax"></a>構文

```
class CStatusBarCtrl : public CWnd
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CStatusBarCtrl:: CStatusBarCtrl](#cstatusbarctrl)|`CStatusBarCtrl` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CStatusBarCtrl:: Create](#create)|ステータスバーコントロールを作成し、オブジェクトにアタッチし `CStatusBarCtrl` ます。|
|[CStatusBarCtrl:: CreateEx](#createex)|指定された Windows 拡張スタイルを使用してステータスバーコントロールを作成し、オブジェクトにアタッチし `CStatusBarCtrl` ます。|
|[CStatusBarCtrl::D rawItem](#drawitem)|オーナー描画ステータスバーコントロールの外観が変化したときに呼び出されます。|
|[CStatusBarCtrl:: GetBorders](#getborders)|ステータスバーコントロールの水平方向と垂直方向の境界線の現在の幅を取得します。|
|[CStatusBarCtrl:: GetIcon](#geticon)|現在のステータスバーコントロールのパーツ (ウィンドウとも呼ばれます) のアイコンを取得します。|
|[CStatusBarCtrl:: GetParts](#getparts)|ステータスバーコントロール内のパーツの数を取得します。|
|[CStatusBarCtrl:: GetRect](#getrect)|ステータスバーコントロール内のパーツの外接する四角形を取得します。|
|[CStatusBarCtrl:: GetText](#gettext)|ステータスバーコントロールの指定した部分からテキストを取得します。|
|[CStatusBarCtrl:: GetTextLength](#gettextlength)|ステータスバーコントロールの特定の部分からのテキストの長さを文字数で取得します。|
|[CStatusBarCtrl:: GetTipText](#gettiptext)|ステータスバーのペインのツールヒントテキストを取得します。|
|[CStatusBarCtrl:: IsSimple](#issimple)|ステータスウィンドウコントロールが、単純モードであるかどうかを確認します。|
|[CStatusBarCtrl:: SetBkColor](#setbkcolor)|ステータスバーの背景色を設定します。|
|[CStatusBarCtrl:: SetIcon](#seticon)|ステータスバーのペインのアイコンを設定します。|
|[CStatusBarCtrl:: SetMinHeight](#setminheight)|ステータスバーコントロールの描画領域の最小の高さを設定します。|
|[CStatusBarCtrl:: SetParts](#setparts)|ステータスバーコントロール内のパーツの数と各部分の右端の座標を設定します。|
|[CStatusBarCtrl:: SetSimple](#setsimple)|ステータスバーコントロールで単純なテキストを表示するか、の前回の呼び出しで設定されたすべてのコントロールパーツを表示するかを指定し `SetParts` ます。|
|[CStatusBarCtrl:: SetText](#settext)|ステータス バー コントロールの特定の部分にテキストを設定します。|
|[CStatusBarCtrl:: SetTipText](#settiptext)|ステータスバーのペインのツールヒントテキストを設定します。|

## <a name="remarks"></a>解説

"ステータスバーコントロール" は、通常は親ウィンドウの下部に表示される水平方向のウィンドウであり、アプリケーションはさまざまな状態情報を表示できます。 ステータスバーコントロールは、複数の種類の情報を表示するために、複数の要素に分割できます。

このコントロール (および `CStatusBarCtrl` クラス) は、windows 95/98 および WINDOWS NT バージョン3.51 以降で実行されているプログラムに対してのみ使用できます。

の使用方法の詳細について `CStatusBarCtrl` は、「 [Controls](../../mfc/controls-mfc.md) and [using CStatusBarCtrl](../../mfc/using-cstatusbarctrl.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CStatusBarCtrl`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxcmn.h

## <a name="cstatusbarctrlcreate"></a><a name="create"></a> CStatusBarCtrl:: Create

ステータスバーコントロールを作成し、オブジェクトにアタッチし `CStatusBarCtrl` ます。

```
virtual BOOL Create(
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>パラメーター

*dwStyle*<br/>
ステータスバーコントロールのスタイルを指定します。 Windows SDK の [コモンコントロールスタイル](/windows/win32/Controls/common-control-styles) に一覧表示されているステータスバーコントロールスタイルの任意の組み合わせを適用します。 このパラメーターには WS_CHILD スタイルを含める必要があります。 また、WS_VISIBLE スタイルも含める必要があります。

*rect*<br/>
ステータスバーコントロールのサイズと位置を指定します。 これは、 [CRect](../../atl-mfc-shared/reference/crect-class.md) オブジェクトまたは [RECT](/windows/win32/api/windef/ns-windef-rect) 構造体のいずれかになります。

*pParentWnd*<br/>
ステータスバーコントロールの親ウィンドウ (通常は) を指定し `CDialog` ます。 NULL にすることはできません。

*nID*<br/>
ステータスバーコントロールの ID を指定します。

### <a name="return-value"></a>戻り値

成功した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>解説

を作成する `CStatusBarCtrl` には、2つの手順を実行します。 まず、コンストラクターを呼び出し、次に `Create` を呼び出します。これにより、ステータスバーコントロールが作成され、オブジェクトにアタッチさ `CStatusBarCtrl` れます。

ステータスウィンドウの既定の位置は、親ウィンドウの下部に表示されますが、親ウィンドウのクライアント領域の上部に表示されるように CCS_TOP スタイルを指定することもできます。 SBARS_SIZEGRIP スタイルを指定して、ステータスウィンドウの右端にサイズ変更グリップを含めることができます。 CCS_TOP スタイルと SBARS_SIZEGRIP スタイルを組み合わせることは推奨されません。これは、システムによって状態ウィンドウに描画される場合でも、結果のサイズ変更グリップが機能しないためです。

拡張ウィンドウスタイルを使用してステータスバーを作成するには、の代わりに [CStatusBarCtrl:: CreateEx](#createex) を呼び出し `Create` ます。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CStatusBarCtrl#1](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_1.cpp)]

## <a name="cstatusbarctrlcreateex"></a><a name="createex"></a> CStatusBarCtrl:: CreateEx

コントロール (子ウィンドウ) を作成し、オブジェクトに関連付け `CStatusBarCtrl` ます。

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
作成するコントロールの拡張スタイルを指定します。 拡張 Windows スタイルの一覧については、Windows SDK の[CreateWindowEx](/windows/win32/api/winuser/nf-winuser-createwindowexw)の*dwexstyle*パラメーターを参照してください。

*dwStyle*<br/>
ステータスバーコントロールのスタイルを指定します。 Windows SDK の [コモンコントロールスタイル](/windows/win32/Controls/common-control-styles) に一覧表示されているステータスバーコントロールスタイルの任意の組み合わせを適用します。 このパラメーターには WS_CHILD スタイルを含める必要があります。 また、WS_VISIBLE スタイルも含める必要があります。

*rect*<br/>
*PParentWnd*のクライアント座標で、作成されるウィンドウのサイズと位置を記述する[RECT](/windows/win32/api/windef/ns-windef-rect)構造体への参照。

*pParentWnd*<br/>
コントロールの親であるウィンドウへのポインター。

*nID*<br/>
コントロールの子ウィンドウ ID。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>解説

`CreateEx`Windows 拡張スタイルの先頭**WS_EX_** によって指定された拡張 windows スタイルを適用するには、[[作成](#create)] ではなくを使用します。

## <a name="cstatusbarctrlcstatusbarctrl"></a><a name="cstatusbarctrl"></a> CStatusBarCtrl:: CStatusBarCtrl

`CStatusBarCtrl` オブジェクトを構築します。

```
CStatusBarCtrl();
```

## <a name="cstatusbarctrldrawitem"></a><a name="drawitem"></a> CStatusBarCtrl::D rawItem

オーナー描画ステータスバーコントロールの外観が変化したときに、フレームワークによって呼び出されます。

```
virtual void DrawItem(LPDRAWITEMSTRUCT lpDrawItemStruct);
```

### <a name="parameters"></a>パラメーター

*lpDrawItemStruct*<br/>
必要な描画の種類に関する情報を格納している [DRAWITEMSTRUCT](/windows/win32/api/winuser/ns-winuser-drawitemstruct) 構造体への long ポインター。

### <a name="remarks"></a>解説

`itemAction`構造体のメンバーは、 `DRAWITEMSTRUCT` 実行する描画アクションを定義します。

既定では、このメンバー関数は何も行いません。 オーナー描画オブジェクトの描画を実装するには、このメンバー関数をオーバーライドし `CStatusBarCtrl` ます。

このメンバー関数が終了する前に、アプリケーションでは、 *lpDrawItemStruct* で指定された表示コンテキスト用に選択されたすべてのグラフィックスデバイスインターフェイス (GDI) オブジェクトを復元する必要があります。

## <a name="cstatusbarctrlgetborders"></a><a name="getborders"></a> CStatusBarCtrl:: GetBorders

ステータスバーコントロールの水平および垂直の境界線と、四角形の間のスペースの現在の幅を取得します。

```
BOOL GetBorders(int* pBorders) const;

BOOL GetBorders(
    int& nHorz,
    int& nVert,
    int& nSpacing) const;
```

### <a name="parameters"></a>パラメーター

*pBorders*<br/>
3つの要素を持つ整数配列のアドレス。 最初の要素は、水平方向の境界線の幅を受け取り、2番目の要素が垂直方向の境界線の幅を受け取り、3番目の要素が四角形の間の境界線の幅を受け取ります。

*nHorz*<br/>
水平方向の境界線の幅を受け取る整数への参照。

*N)*<br/>
垂直方向の境界線の幅を受け取る整数への参照。

*nSpacing*<br/>
四角形の間の境界線の幅を受け取る整数への参照。

### <a name="return-value"></a>戻り値

成功した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>解説

これらの境界線によって、コントロールの外側の端とテキストを含むコントロール内の四角形の間隔が決まります。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CStatusBarCtrl#2](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_2.cpp)]

## <a name="cstatusbarctrlgeticon"></a><a name="geticon"></a> CStatusBarCtrl:: GetIcon

現在のステータスバーコントロールのパーツ (ウィンドウとも呼ばれます) のアイコンを取得します。

```
HICON GetIcon(int iPart) const;
```

### <a name="parameters"></a>パラメーター

*iPart*\
から取得するアイコンを格納しているパーツの0から始まるインデックス。 このパラメーターが-1 の場合、ステータスバーは、簡易モードのステータスバーであると見なされます。

### <a name="return-value"></a>戻り値

メソッドが成功した場合は、アイコンを示すハンドル。それ以外の場合は NULL。

### <a name="remarks"></a>解説

このメソッドは、Windows SDK で説明されている [SB_GETICON](/windows/win32/Controls/sb-geticon) メッセージを送信します。

ステータスバーコントロールは、パーツとも呼ばれる、テキスト出力ペインの行で構成されます。 ステータスバーの詳細については、「 [MFC でのステータスバーの実装](../../mfc/status-bar-implementation-in-mfc.md) 」および「 [CStatusBarCtrl オブジェクトのモードの設定](../../mfc/setting-the-mode-of-a-cstatusbarctrl-object.md)」を参照してください。

### <a name="example"></a>例

`m_statusBar`現在のステータスバーコントロールにアクセスするために使用される変数を定義するコード例を次に示します。 この変数は次の例で使用されています。

[!code-cpp[NVC_MFC_CStatusBarCtrl_s1#1](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_3.h)]

### <a name="example"></a>例

次のコード例では、現在のステータスバーコントロールの2つのウィンドウにアイコンをコピーします。 コード例の前のセクションでは、3つのペインを含むステータスバーコントロールを作成し、最初のウィンドウにアイコンを追加しました。 この例では、最初のペインからアイコンを取得し、2番目と3番目のペインに追加します。

[!code-cpp[NVC_MFC_CStatusBarCtrl_s1#2](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_4.cpp)]

## <a name="cstatusbarctrlgetparts"></a><a name="getparts"></a> CStatusBarCtrl:: GetParts

ステータスバーコントロール内のパーツの数を取得します。

```
int GetParts(
    int nParts,
    int* pParts) const;
```

### <a name="parameters"></a>パラメーター

*nParts*<br/>
座標を取得する対象の部分の数。 このパラメーターがコントロール内のパーツの数よりも大きい場合、メッセージは既存のパーツの座標だけを取得します。

*pParts*<br/>
N 個の *部分*で指定された要素の数と同じ数の要素を持つ整数配列のアドレス。 配列の各要素は、対応する部分の右端のクライアント座標を受け取ります。 要素が-1 に設定されている場合は、その部分の右端の位置がステータスバーの右端になります。

### <a name="return-value"></a>戻り値

成功した場合はコントロール内のパーツの数。それ以外の場合は0。

### <a name="remarks"></a>解説

このメンバー関数は、指定された数のパーツの右端の座標も取得します。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CStatusBarCtrl#3](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_5.cpp)]

## <a name="cstatusbarctrlgetrect"></a><a name="getrect"></a> CStatusBarCtrl:: GetRect

ステータスバーコントロール内のパーツの外接する四角形を取得します。

```
BOOL GetRect(
    int nPane,
    LPRECT lpRect) const;
```

### <a name="parameters"></a>パラメーター

*n ペイン*<br/>
外接する四角形を取得する部分の0から始まるインデックス。

*lpRect*<br/>
外接する四角形を受け取る [RECT](/windows/win32/api/windef/ns-windef-rect) 構造体のアドレス。

### <a name="return-value"></a>戻り値

成功した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CStatusBarCtrl#4](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_6.cpp)]

## <a name="cstatusbarctrlgettext"></a><a name="gettext"></a> CStatusBarCtrl:: GetText

ステータスバーコントロールの指定した部分からテキストを取得します。

```
CString GetText(
    int nPane,
    int* pType = NULL) const;

int GetText(
    LPCTSTR lpszText,
    int nPane,
    int* pType = NULL) const;
```

### <a name="parameters"></a>パラメーター

*lpszText*<br/>
テキストを受け取るバッファーのアドレス。 このパラメーターは、null で終わる文字列です。

*n ペイン*<br/>
テキストの取得元となるパーツの0から始まるインデックス。

*pType*<br/>
型情報を受け取る整数へのポインター。 型には、次のいずれかの値を指定できます。

- **0** テキストは、ステータスバーの平面よりも低い境界線で描画されます。

- SBT_NOBORDERS テキストが罫線なしで描画されます。

- テキストが、ステータスバーの平面よりも上に表示される境界線を使用して描画さ SBT_POPOUT ます。

- SBT_OWNERDRAW テキストに SBT_OWNERDRAW の描画の種類がある場合、 *pType* はこのメッセージを受信し、長さと操作の種類ではなく、テキストに関連付けられている32ビットの値を返します。

### <a name="return-value"></a>戻り値

現在のテキストを含むテキストまたは [CString](../../atl-mfc-shared/reference/cstringt-class.md) の長さ (文字数)。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CStatusBarCtrl#5](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_7.cpp)]

## <a name="cstatusbarctrlgettextlength"></a><a name="gettextlength"></a> CStatusBarCtrl:: GetTextLength

ステータスバーコントロールの指定した部分からのテキストの長さを文字数で取得します。

```
int GetTextLength(
    int nPane,
    int* pType = NULL) const;
```

### <a name="parameters"></a>パラメーター

*n ペイン*<br/>
テキストの取得元となるパーツの0から始まるインデックス。

*pType*<br/>
型情報を受け取る整数へのポインター。 型には、次のいずれかの値を指定できます。

- **0** テキストは、ステータスバーの平面よりも低い境界線で描画されます。

- SBT_NOBORDERS テキストが罫線なしで描画されます。

- SBT_OWNERDRAW テキストが親ウィンドウによって描画されます。

- テキストが、ステータスバーの平面よりも上に表示される境界線を使用して描画さ SBT_POPOUT ます。

### <a name="return-value"></a>戻り値

テキストの長さ (文字数)。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CStatusBarCtrl#6](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_8.cpp)]

## <a name="cstatusbarctrlgettiptext"></a><a name="gettiptext"></a> CStatusBarCtrl:: GetTipText

ステータスバーのペインのツールヒントテキストを取得します。

```
CString GetTipText(int nPane) const;
```

### <a name="parameters"></a>パラメーター

*n ペイン*<br/>
ツールヒントテキストを受け取るステータスバーペインの0から始まるインデックス。

### <a name="return-value"></a>戻り値

ツールヒントで使用されるテキストを格納している [CString](../../atl-mfc-shared/reference/cstringt-class.md) オブジェクト。

### <a name="remarks"></a>解説

このメンバー関数は、Windows SDK で説明されているように、Win32 メッセージ [SB_GETTIPTEXT](/windows/win32/Controls/sb-gettiptext)の動作を実装します。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CStatusBarCtrl#7](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_9.cpp)]

## <a name="cstatusbarctrlissimple"></a><a name="issimple"></a> CStatusBarCtrl:: IsSimple

ステータスウィンドウコントロールが、単純モードであるかどうかを確認します。

```
BOOL IsSimple() const;
```

### <a name="return-value"></a>戻り値

ステータスウィンドウコントロールが簡易モードの場合は0以外の場合は。それ以外の場合は0。

### <a name="remarks"></a>解説

このメンバー関数は、Windows SDK で説明されているように、Win32 メッセージ [SB_ISSIMPLE](/windows/win32/Controls/sb-issimple)の動作を実装します。

## <a name="cstatusbarctrlsetbkcolor"></a><a name="setbkcolor"></a> CStatusBarCtrl:: SetBkColor

ステータスバーの背景色を設定します。

```
COLORREF SetBkColor(COLORREF cr);
```

### <a name="parameters"></a>パラメーター

*リターン*<br/>
新しい背景色を指定する COLORREF 値。 CLR_DEFAULT の値を指定して、ステータスバーが既定の背景色を使用するようにします。

### <a name="return-value"></a>戻り値

前の既定の背景色を表す [COLORREF](/windows/win32/gdi/colorref) 値。

### <a name="remarks"></a>解説

このメンバー関数は、Windows SDK で説明されているように、Win32 メッセージ [SB_SETBKCOLOR](/windows/win32/Controls/sb-setbkcolor)の動作を実装します。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CStatusBarCtrl#8](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_10.cpp)]

## <a name="cstatusbarctrlseticon"></a><a name="seticon"></a> CStatusBarCtrl:: SetIcon

ステータスバーのペインのアイコンを設定します。

```
BOOL SetIcon(
    int nPane,
    HICON hIcon);
```

### <a name="parameters"></a>パラメーター

*n ペイン*<br/>
アイコンを受け取るペインの0から始まるインデックス。 このパラメーターが-1 の場合、ステータスバーは単純なステータスバーであると見なされます。

*hIcon*<br/>
設定するアイコンへのハンドル。 この値が NULL の場合は、その部分からアイコンが削除されます。

### <a name="return-value"></a>戻り値

成功した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>解説

このメンバー関数は、Windows SDK で説明されているように、Win32 メッセージ [SB_SETICON](/windows/win32/Controls/sb-seticon)の動作を実装します。

### <a name="example"></a>例

  [CStatusBarCtrl:: SetBkColor](#setbkcolor)の例を参照してください。

## <a name="cstatusbarctrlsetminheight"></a><a name="setminheight"></a> CStatusBarCtrl:: SetMinHeight

ステータスバーコントロールの描画領域の最小の高さを設定します。

```cpp
void SetMinHeight(int nMin);
```

### <a name="parameters"></a>パラメーター

*N1 日*<br/>
コントロールの高さの最小値 (ピクセル単位)。

### <a name="remarks"></a>解説

高さの最小値は、ステータスバーコントロールの垂直方向の境界線の *Nmin* と幅の2倍 (ピクセル単位) の合計です。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CStatusBarCtrl#9](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_11.cpp)]

## <a name="cstatusbarctrlsetparts"></a><a name="setparts"></a> CStatusBarCtrl:: SetParts

ステータスバーコントロール内のパーツの数と各部分の右端の座標を設定します。

```
BOOL SetParts(
    int nParts,
    int* pWidths);
```

### <a name="parameters"></a>パラメーター

*nParts*<br/>
設定するパーツの数。 部分の数を255より大きくすることはできません。

*pWidths*<br/>
*Nparts*によって指定された部分と同じ数の要素を持つ整数配列のアドレス。 配列の各要素は、対応する部分の右端の位置をクライアント座標で指定します。 要素が-1 の場合、その部分の右端の位置は、コントロールの右端に向かって拡張されます。

### <a name="return-value"></a>戻り値

成功した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CStatusBarCtrl#10](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_12.cpp)]

## <a name="cstatusbarctrlsetsimple"></a><a name="setsimple"></a> CStatusBarCtrl:: SetSimple

ステータスバーコントロールで単純なテキストを表示するか、以前の [SetParts](#setparts)の呼び出しで設定されたすべてのコントロールパーツを表示するかを指定します。

```
BOOL SetSimple(BOOL bSimple = TRUE);
```

### <a name="parameters"></a>パラメーター

*bSimple*<br/>
から表示形式フラグ。 このパラメーターが TRUE の場合、コントロールには単純なテキストが表示されます。FALSE の場合は、複数の部分が表示されます。

### <a name="return-value"></a>戻り値

常に 0 を返します。

### <a name="remarks"></a>解説

アプリケーションがステータスバーコントロールを非単純から単純に、またはその逆に変更した場合、システムはすぐにコントロールを再描画します。

## <a name="cstatusbarctrlsettext"></a><a name="settext"></a> CStatusBarCtrl:: SetText

ステータス バー コントロールの特定の部分にテキストを設定します。

```
BOOL SetText(
    LPCTSTR lpszText,
    int nPane,
    int nType);
```

### <a name="parameters"></a>パラメーター

*lpszText*<br/>
設定されるテキストを指定する null で終わる文字列のアドレス。 *NType*が SBT_OWNERDRAW の場合、 *lpszText*は32ビットのデータを表します。

*n ペイン*<br/>
設定される部分の 0 から始まるインデックス。 この値が 255 の場合、ステータス バー コントロールは 1 つの部分のみで構成される単純なコントロールと見なされます。

*nType*<br/>
描画操作の種類。 使用可能な値の一覧については、 [SB_SETTEXT メッセージ](/windows/win32/Controls/sb-settext) を参照してください。

### <a name="return-value"></a>戻り値

成功した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>解説

このメッセージは、変更されたコントロールの一部を無効にし、コントロールが次に WM_PAINT メッセージを受信したときに新しいテキストを表示します。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CStatusBarCtrl#11](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_13.cpp)]

## <a name="cstatusbarctrlsettiptext"></a><a name="settiptext"></a> CStatusBarCtrl:: SetTipText

ステータスバーのペインのツールヒントテキストを設定します。

```cpp
void SetTipText(
    int nPane,
    LPCTSTR pszTipText);
```

### <a name="parameters"></a>パラメーター

*n ペイン*<br/>
ツールヒントテキストを受け取るステータスバーペインの0から始まるインデックス。

*pszTipText*<br/>
ツールヒントテキストを格納している文字列へのポインター。

### <a name="remarks"></a>解説

このメンバー関数は、Windows SDK で説明されているように、Win32 メッセージ [SB_SETTIPTEXT](/windows/win32/Controls/sb-settiptext)の動作を実装します。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CStatusBarCtrl#12](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_14.cpp)]

## <a name="see-also"></a>関連項目

[CWnd クラス](../../mfc/reference/cwnd-class.md)<br/>
[階層図](../../mfc/hierarchy-chart.md)<br/>
[CToolBarCtrl クラス](../../mfc/reference/ctoolbarctrl-class.md)

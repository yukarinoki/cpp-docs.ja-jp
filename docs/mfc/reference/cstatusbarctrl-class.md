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
ms.openlocfilehash: 57d040a7efd87d384e0aaa6275593bc91f38cc86
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "81753037"
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
|[を切り離します。](#cstatusbarctrl)|`CStatusBarCtrl` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[をクリックします。](#create)|ステータス バー コントロールを作成し、`CStatusBarCtrl`オブジェクトにアタッチします。|
|[をクリックします。](#createex)|指定した Windows 拡張スタイルを持つステータス バー コントロールを作成`CStatusBarCtrl`し、オブジェクトにアタッチします。|
|[を:D](#drawitem)|オーナー描画ステータス バー コントロールの視覚的な側面が変更されたときに呼び出されます。|
|[を取得します。](#getborders)|ステータス バー コントロールの水平および垂直境界線の現在の幅を取得します。|
|[をクリックします。](#geticon)|現在のステータス バー コントロールのパーツ (ペインとも呼ばれます) のアイコンを取得します。|
|[をクリックします。](#getparts)|ステータス バー コントロール内のパーツの数を取得します。|
|[をクリックします。](#getrect)|ステータス バー コントロール内のパーツの外接する四角形を取得します。|
|[をクリックします。](#gettext)|ステータス バー コントロールの指定した部分からテキストを取得します。|
|[を使用します。](#gettextlength)|ステータス バー コントロールの指定した部分からテキストの長さを文字数で取得します。|
|[テキストを取得します。](#gettiptext)|ステータス バーのペインのツールヒント テキストを取得します。|
|[をクリックします。](#issimple)|ステータス ウィンドウ コントロールを調べて、シンプル モードかどうかを確認します。|
|[をクリックします。](#setbkcolor)|ステータス バーの背景色を設定します。|
|[をクリックします。](#seticon)|ステータス バーのペインのアイコンを設定します。|
|[をクリックします。](#setminheight)|ステータス バー コントロールの作図領域の最小の高さを設定します。|
|[をクリックします。](#setparts)|ステータス バー コントロールのパーツ数と各パーツの右端の座標を設定します。|
|[をクリックします。](#setsimple)|ステータス バー コントロールに単純なテキストを表示するか、以前の呼び出しで`SetParts`設定したすべてのコントロール パーツを表示するかを指定します。|
|[をクリックします。](#settext)|ステータス バー コントロールの特定の部分にテキストを設定します。|
|[テキストを設定します。](#settiptext)|ステータス バーのペインのツールヒント テキストを設定します。|

## <a name="remarks"></a>解説

"ステータス バー コントロール" は、通常、アプリケーションがさまざまな種類のステータス情報を表示できる、親ウィンドウの下部に表示される水平ウィンドウです。 ステータス バー コントロールは、複数の種類の情報を表示するために、複数の部分に分割できます。

このコントロール (および`CStatusBarCtrl`クラス) は、Windows 95/98 および Windows NT バージョン 3.51 以降で実行されているプログラムでのみ使用できます。

の詳細`CStatusBarCtrl`については、「[コントロール](../../mfc/controls-mfc.md)と[CStatusBarCtrl を使用する](../../mfc/using-cstatusbarctrl.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CStatusBarCtrl`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxcmn.h

## <a name="cstatusbarctrlcreate"></a><a name="create"></a>をクリックします。

ステータス バー コントロールを作成し、`CStatusBarCtrl`オブジェクトにアタッチします。

```
virtual BOOL Create(
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>パラメーター

*Dwstyle*<br/>
ステータス バー コントロールのスタイルを指定します。 Windows SDK のコモン コントロール スタイルに表示されているステータス バー[コントロール スタイル](/windows/win32/Controls/common-control-styles)の任意の組み合わせを適用します。 このパラメーターには、WS_CHILDスタイルを含める必要があります。 また、WS_VISIBLEスタイルも含める必要があります。

*Rect*<br/>
ステータス バー コントロールのサイズと位置を指定します。 [CRect](../../atl-mfc-shared/reference/crect-class.md)オブジェクトまたは[RECT](/windows/win32/api/windef/ns-windef-rect)構造体を指定できます。

*pParentWnd*<br/>
ステータス バー コントロールの親ウィンドウを指定します`CDialog`。 NULL にすることはできません。

*nID*<br/>
ステータス バー コントロールの ID を指定します。

### <a name="return-value"></a>戻り値

成功した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>解説

を`CStatusBarCtrl`2 つの手順で作成します。 まず、コンストラクターを呼び出し、`Create`次に`CStatusBarCtrl`を呼び出します。

ステータス ウィンドウの既定の位置は親ウィンドウの下部に沿っていますが、CCS_TOPスタイルを指定して、親ウィンドウのクライアント領域の上部に表示されるようにすることができます。 ステータス ウィンドウの右端にサイズ変更グリップを含めるSBARS_SIZEGRIP スタイルを指定できます。 CCS_TOP スタイルとSBARS_SIZEGRIP スタイルを組み合わせることは、システムがステータス ウィンドウに描画しても、結果として得られるサイズ変更グリップが機能しないため、推奨されません。

拡張ウィンドウ スタイルを持つステータス バーを作成するには、代わりに[CStatusBarCtrl::CreateEx](#createex)を呼び出`Create`します。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CStatusBarCtrl#1](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_1.cpp)]

## <a name="cstatusbarctrlcreateex"></a><a name="createex"></a>をクリックします。

コントロール (子ウィンドウ) を作成し、オブジェクトに関連`CStatusBarCtrl`付けます。

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
ステータス バー コントロールのスタイルを指定します。 Windows SDK のコモン コントロール スタイルに表示されているステータス バー[コントロール スタイル](/windows/win32/Controls/common-control-styles)の任意の組み合わせを適用します。 このパラメーターには、WS_CHILDスタイルを含める必要があります。 また、WS_VISIBLEスタイルも含める必要があります。

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

## <a name="cstatusbarctrlcstatusbarctrl"></a><a name="cstatusbarctrl"></a>を切り離します。

`CStatusBarCtrl` オブジェクトを構築します。

```
CStatusBarCtrl();
```

## <a name="cstatusbarctrldrawitem"></a><a name="drawitem"></a>を:D

オーナー描画ステータス バー コントロールの視覚的な側面が変更されたときに、フレームワークによって呼び出されます。

```
virtual void DrawItem(LPDRAWITEMSTRUCT lpDrawItemStruct);
```

### <a name="parameters"></a>パラメーター

*構造体*<br/>
必要な描画の種類に関する情報を含む[DRAWITEMSTRUCT 構造体](/windows/win32/api/winuser/ns-winuser-drawitemstruct)への長いポインター。

### <a name="remarks"></a>解説

構造`itemAction`のメンバーは`DRAWITEMSTRUCT`、実行される描画アクションを定義します。

既定では、このメンバー関数は何も実行しません。 オーナー描画`CStatusBarCtrl`オブジェクトの描画を実装するには、このメンバー関数をオーバーライドします。

アプリケーションは、このメンバー関数が終了する前に *、lpDrawItemStruct*で提供される表示コンテキストに選択されているすべてのグラフィックス デバイス インターフェイス (GDI) オブジェクトを復元する必要があります。

## <a name="cstatusbarctrlgetborders"></a><a name="getborders"></a>を取得します。

ステータス バー コントロールの水平および垂直境界線の現在の幅、および四角形の間のスペースを取得します。

```
BOOL GetBorders(int* pBorders) const;

BOOL GetBorders(
    int& nHorz,
    int& nVert,
    int& nSpacing) const;
```

### <a name="parameters"></a>パラメーター

*pボーダーズ*<br/>
3 つの要素を持つ整数配列のアドレス。 最初の要素は水平境界線の幅を受け取り、2 番目の要素は垂直境界線の幅を受け取り、3 番目の要素は四角形の間の境界線の幅を受け取ります。

*nホルツ*<br/>
水平境界線の幅を受け取る整数への参照。

*nVert*<br/>
垂直境界線の幅を受け取る整数への参照。

*n間隔*<br/>
四角形の境界線の幅を受け取る整数への参照。

### <a name="return-value"></a>戻り値

成功した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>解説

これらの境界線は、コントロールの外側の端とテキストを含むコントロール内の四角形との間の間隔を決定します。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CStatusBarCtrl#2](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_2.cpp)]

## <a name="cstatusbarctrlgeticon"></a><a name="geticon"></a>をクリックします。

現在のステータス バー コントロールのパーツ (ペインとも呼ばれます) のアイコンを取得します。

```
HICON GetIcon(int iPart) const;
```

### <a name="parameters"></a>パラメーター

|パラメーター|説明|
|---------------|-----------------|
|*Ipart*|[in]取得するアイコンを含むパーツの 0 から始まるインデックス。 このパラメーターが -1 の場合、ステータス バーは簡易モードのステータス バーと見なされます。|

### <a name="return-value"></a>戻り値

メソッドが成功した場合はアイコンへのハンドル。それ以外の場合は NULL。

### <a name="remarks"></a>解説

このメソッドは、Windows SDK で説明されている[SB_GETICON](/windows/win32/Controls/sb-geticon)メッセージを送信します。

ステータス バー コントロールは、一部とも呼ばれるテキスト出力ペインの行で構成されます。 ステータス バーの詳細については[、「MFC でのステータス バーの実装](../../mfc/status-bar-implementation-in-mfc.md)」および[「CStatusBarCtrl オブジェクトのモードの設定](../../mfc/setting-the-mode-of-a-cstatusbarctrl-object.md)」を参照してください。

### <a name="example"></a>例

次のコード例では、`m_statusBar`現在のステータス バー コントロールにアクセスするために使用される変数 を定義します。 この変数は次の例で使用されています。

[!code-cpp[NVC_MFC_CStatusBarCtrl_s1#1](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_3.h)]

### <a name="example"></a>例

次のコード例では、現在のステータス バー コントロールの 2 つのペインにアイコンをコピーします。 コード例の前のセクションでは、3 つのペインを含むステータス バー コントロールを作成し、最初のペインにアイコンを追加しました。 次の使用例は、最初のペインからアイコンを取得し、2 番目と 3 番目のウィンドウに追加します。

[!code-cpp[NVC_MFC_CStatusBarCtrl_s1#2](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_4.cpp)]

## <a name="cstatusbarctrlgetparts"></a><a name="getparts"></a>をクリックします。

ステータス バー コントロール内のパーツの数を取得します。

```
int GetParts(
    int nParts,
    int* pParts) const;
```

### <a name="parameters"></a>パラメーター

*Nparts*<br/>
座標を取得するパーツの数。 このパラメーターがコントロール内の部品の数より大きい場合、メッセージは既存の部品のみの座標を取得します。

*pパーツ*<br/>
*nParts*で指定された部分の数と同じ数の要素を持つ整数配列のアドレス。 配列内の各要素は、対応するパーツの右端のクライアント座標を受け取ります。 要素が -1 に設定されている場合、その部分の右端の位置はステータス バーの右端まで延長されます。

### <a name="return-value"></a>戻り値

成功した場合はコントロール内のパーツの数、またはそうでない場合は 0。

### <a name="remarks"></a>解説

このメンバー関数は、指定された数の部分の右端の座標も取得します。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CStatusBarCtrl#3](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_5.cpp)]

## <a name="cstatusbarctrlgetrect"></a><a name="getrect"></a>をクリックします。

ステータス バー コントロール内のパーツの外接する四角形を取得します。

```
BOOL GetRect(
    int nPane,
    LPRECT lpRect) const;
```

### <a name="parameters"></a>パラメーター

*nペイン*<br/>
外接する四角形を取得するパーツの 0 から始まるインデックス。

*Lprect*<br/>
外接する四角形を受け取る[RECT](/windows/win32/api/windef/ns-windef-rect)構造体のアドレス。

### <a name="return-value"></a>戻り値

成功した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CStatusBarCtrl#4](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_6.cpp)]

## <a name="cstatusbarctrlgettext"></a><a name="gettext"></a>をクリックします。

ステータス バー コントロールの指定した部分からテキストを取得します。

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
テキストを受け取るバッファーのアドレス。 このパラメーターは、NULL で終わる文字列です。

*nペイン*<br/>
テキストの取得元となる部分の 0 から始まるインデックス。

*pタイプ*<br/>
型情報を受け取る整数へのポインター。 型は、次のいずれかの値を指定できます。

- **0**テキストは、ステータス バーの平面よりも低い枠線で描画されます。

- SBT_NOBORDERS テキストは枠線なしで描画されます。

- SBT_POPOUT テキストは、ステータス バーの平面よりも高い枠線で描画されます。

- SBT_OWNERDRAWテキストにSBT_OWNERDRAW描画タイプがある場合 *、pType*はこのメッセージを受け取り、長さと操作の種類ではなく、テキストに関連付けられた 32 ビット値を返します。

### <a name="return-value"></a>戻り値

現在のテキストを含むテキストまたは[CString](../../atl-mfc-shared/reference/cstringt-class.md)の長さ (文字数)。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CStatusBarCtrl#5](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_7.cpp)]

## <a name="cstatusbarctrlgettextlength"></a><a name="gettextlength"></a>を使用します。

ステータス バー コントロールの指定した部分からテキストの長さを文字数で取得します。

```
int GetTextLength(
    int nPane,
    int* pType = NULL) const;
```

### <a name="parameters"></a>パラメーター

*nペイン*<br/>
テキストの取得元となる部分の 0 から始まるインデックス。

*pタイプ*<br/>
型情報を受け取る整数へのポインター。 型は、次のいずれかの値を指定できます。

- **0**テキストは、ステータス バーの平面よりも低い枠線で描画されます。

- SBT_NOBORDERS テキストは枠線なしで描画されます。

- SBT_OWNERDRAW テキストは親ウィンドウによって描画されます。

- SBT_POPOUT テキストは、ステータス バーの平面よりも高い枠線で描画されます。

### <a name="return-value"></a>戻り値

テキストの長さ (文字数)。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CStatusBarCtrl#6](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_8.cpp)]

## <a name="cstatusbarctrlgettiptext"></a><a name="gettiptext"></a>テキストを取得します。

ステータス バーのペインのツールヒント テキストを取得します。

```
CString GetTipText(int nPane) const;
```

### <a name="parameters"></a>パラメーター

*nペイン*<br/>
ツールヒント テキストを受け取るステータス バー ペインの 0 から始まるインデックス。

### <a name="return-value"></a>戻り値

ツールヒントで使用するテキストを含む[CString](../../atl-mfc-shared/reference/cstringt-class.md)オブジェクト。

### <a name="remarks"></a>解説

このメンバー関数は、Windows SDK で説明されているように、Win32 メッセージ[SB_GETTIPTEXT](/windows/win32/Controls/sb-gettiptext)の動作を実装します。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CStatusBarCtrl#7](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_9.cpp)]

## <a name="cstatusbarctrlissimple"></a><a name="issimple"></a>をクリックします。

ステータス ウィンドウ コントロールを調べて、シンプル モードかどうかを確認します。

```
BOOL IsSimple() const;
```

### <a name="return-value"></a>戻り値

ステータス ウィンドウ コントロールが単純モードの場合は 0 以外。それ以外の場合は 0。

### <a name="remarks"></a>解説

このメンバー関数は、Windows SDK で説明されているように、Win32 メッセージ[SB_ISSIMPLE](/windows/win32/Controls/sb-issimple)の動作を実装します。

## <a name="cstatusbarctrlsetbkcolor"></a><a name="setbkcolor"></a>をクリックします。

ステータス バーの背景色を設定します。

```
COLORREF SetBkColor(COLORREF cr);
```

### <a name="parameters"></a>パラメーター

*Cr*<br/>
新しい背景色を指定する COLORREF 値。 ステータス バーが既定の背景色を使用するようにするには、CLR_DEFAULT値を指定します。

### <a name="return-value"></a>戻り値

以前の既定の背景色を表す[COLORREF](/windows/win32/gdi/colorref)値。

### <a name="remarks"></a>解説

このメンバー関数は、Windows SDK で説明されているように、Win32 メッセージ[SB_SETBKCOLOR](/windows/win32/Controls/sb-setbkcolor)の動作を実装します。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CStatusBarCtrl#8](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_10.cpp)]

## <a name="cstatusbarctrlseticon"></a><a name="seticon"></a>をクリックします。

ステータス バーのペインのアイコンを設定します。

```
BOOL SetIcon(
    int nPane,
    HICON hIcon);
```

### <a name="parameters"></a>パラメーター

*nペイン*<br/>
アイコンを受け取るペインの 0 から始まるインデックス。 このパラメーターが -1 の場合、ステータス バーは単純なステータス バーと見なされます。

*Hicon*<br/>
設定するアイコンへのハンドル。 この値が NULL の場合、アイコンは部品から削除されます。

### <a name="return-value"></a>戻り値

成功した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>解説

このメンバー関数は、Windows SDK で説明されているように、Win32 メッセージ[SB_SETICON](/windows/win32/Controls/sb-seticon)の動作を実装します。

### <a name="example"></a>例

  の[例を参照](#setbkcolor)してください。

## <a name="cstatusbarctrlsetminheight"></a><a name="setminheight"></a>をクリックします。

ステータス バー コントロールの作図領域の最小の高さを設定します。

```cpp
void SetMinHeight(int nMin);
```

### <a name="parameters"></a>パラメーター

*nMin*<br/>
コントロールの最小の高さ (ピクセル単位)。

### <a name="remarks"></a>解説

最小の高さは *、nMin*の合計と、ステータス バー コントロールの垂直境界線の幅の 2 倍のピクセル単位です。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CStatusBarCtrl#9](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_11.cpp)]

## <a name="cstatusbarctrlsetparts"></a><a name="setparts"></a>をクリックします。

ステータス バー コントロールのパーツ数と各パーツの右端の座標を設定します。

```
BOOL SetParts(
    int nParts,
    int* pWidths);
```

### <a name="parameters"></a>パラメーター

*Nparts*<br/>
設定するパーツの数。 パーツの数は 255 を超えることはできません。

*幅*<br/>
*nParts*で指定された部分と同じ数の要素を持つ整数配列のアドレス。 配列内の各要素は、対応するパーツの右端の位置をクライアント座標で指定します。 要素が -1 の場合、その部分の右端の位置はコントロールの右端まで拡張されます。

### <a name="return-value"></a>戻り値

成功した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CStatusBarCtrl#10](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_12.cpp)]

## <a name="cstatusbarctrlsetsimple"></a><a name="setsimple"></a>をクリックします。

ステータス バー コントロールに単純なテキストを表示するか[、SetParts](#setparts)への前回の呼び出しで設定したすべてのコントロール パーツを表示するかを指定します。

```
BOOL SetSimple(BOOL bSimple = TRUE);
```

### <a name="parameters"></a>パラメーター

*bシンプル*<br/>
[in]表示タイプのフラグ。 このパラメーターが TRUE の場合、コントロールは単純なテキストを表示します。FALSE の場合は、複数のパーツを表示します。

### <a name="return-value"></a>戻り値

常に 0 を返します。

### <a name="remarks"></a>解説

アプリケーションがステータス バー コントロールを単純でないコントロールから単純コントロールに変更した場合、またはその逆の場合、システムはコントロールを直ちに再描画します。

## <a name="cstatusbarctrlsettext"></a><a name="settext"></a>をクリックします。

ステータス バー コントロールの特定の部分にテキストを設定します。

```
BOOL SetText(
    LPCTSTR lpszText,
    int nPane,
    int nType);
```

### <a name="parameters"></a>パラメーター

*lpszText*<br/>
設定されるテキストを指定する null で終わる文字列のアドレス。 *nType*がSBT_OWNERDRAW場合 *、lpszText*は 32 ビットのデータを表します。

*nペイン*<br/>
設定される部分の 0 から始まるインデックス。 この値が 255 の場合、ステータス バー コントロールは 1 つの部分のみで構成される単純なコントロールと見なされます。

*nType*<br/>
描画操作の種類。 可能[な値のリストについては、SB_SETTEXTメッセージ](/windows/win32/Controls/sb-settext)を参照してください。

### <a name="return-value"></a>戻り値

成功した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>解説

このメッセージは、変更されたコントロールの部分を無効にし、コントロールが次にWM_PAINT メッセージを受信したときに新しいテキストを表示します。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CStatusBarCtrl#11](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_13.cpp)]

## <a name="cstatusbarctrlsettiptext"></a><a name="settiptext"></a>テキストを設定します。

ステータス バーのペインのツールヒント テキストを設定します。

```cpp
void SetTipText(
    int nPane,
    LPCTSTR pszTipText);
```

### <a name="parameters"></a>パラメーター

*nペイン*<br/>
ツールヒント テキストを受け取るステータス バー ペインの 0 から始まるインデックス。

*テキスト*<br/>
ツールヒント テキストを含む文字列へのポインター。

### <a name="remarks"></a>解説

このメンバー関数は、Windows SDK で説明されているように、Win32 メッセージ[SB_SETTIPTEXT](/windows/win32/Controls/sb-settiptext)の動作を実装します。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CStatusBarCtrl#12](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_14.cpp)]

## <a name="see-also"></a>関連項目

[CWnd クラス](../../mfc/reference/cwnd-class.md)<br/>
[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[CToolBarCtrl クラス](../../mfc/reference/ctoolbarctrl-class.md)

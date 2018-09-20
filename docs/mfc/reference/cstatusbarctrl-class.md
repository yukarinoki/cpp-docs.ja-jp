---
title: CStatusBarCtrl クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
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
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 0dc416c47634de522a20f81d7240cc1ea5797551
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46392061"
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
|[CStatusBarCtrl::CStatusBarCtrl](#cstatusbarctrl)|`CStatusBarCtrl` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CStatusBarCtrl::Create](#create)|ステータス バー コントロールを作成しにアタッチします、`CStatusBarCtrl`オブジェクト。|
|[CStatusBarCtrl::CreateEx](#createex)|指定した Windows の拡張スタイルを使用して、ステータス バー コントロールを作成しにアタッチします、`CStatusBarCtrl`オブジェクト。|
|[CStatusBarCtrl::DrawItem](#drawitem)|オーナー描画ステータス バー コントロールの変更のビジュアルな部分と呼び出されます。|
|[CStatusBarCtrl::GetBorders](#getborders)|現在のステータス バー コントロールの水平および垂直方向の境界線の幅を取得します。|
|[CStatusBarCtrl::GetIcon](#geticon)|現在のステータス バー コントロールのパーツ (ウィンドウとも呼ばれます) のアイコンを取得します。|
|[CStatusBarCtrl::GetParts](#getparts)|ステータス バー コントロールの部品の数を取得します。|
|[CStatusBarCtrl::GetRect](#getrect)|ステータス バー コントロールでの部分の外接する四角形を取得します。|
|[Cstatusbarctrl::gettext](#gettext)|ステータス バー コントロールの特定の部分からテキストを取得します。|
|[Cstatusbarctrl::gettextlength](#gettextlength)|ステータス バー コントロールの特定の部分からテキストの文字の長さを取得します。|
|[CStatusBarCtrl::GetTipText](#gettiptext)|ステータス バーで、ウィンドウのツールヒントのテキストを取得します。|
|[CStatusBarCtrl::IsSimple](#issimple)|簡易モードでは、ステータス ウィンドウ コントロールを確認します。|
|[CStatusBarCtrl::SetBkColor](#setbkcolor)|ステータス バーの背景色を設定します。|
|[CStatusBarCtrl::SetIcon](#seticon)|ステータス バー ペインのアイコンを設定します。|
|[CStatusBarCtrl::SetMinHeight](#setminheight)|バーのコントロールの描画領域の状態の最小の高さを設定します。|
|[CStatusBarCtrl::SetParts](#setparts)|ステータス バー コントロールと各部分の右端の座標で部分の数を設定します。|
|[CStatusBarCtrl::SetSimple](#setsimple)|ステータス バー コントロールが単純なテキストを表示します。 または以前の呼び出しで設定するすべてのコントロール パーツが表示されますかどうかを指定します`SetParts`します。|
|[CStatusBarCtrl::SetText](#settext)|ステータス バー コントロールの特定の部分にテキストを設定します。|
|[CStatusBarCtrl::SetTipText](#settiptext)|ステータス バーで、ウィンドウのツールヒントのテキストを設定します。|

## <a name="remarks"></a>Remarks

「ステータス バー コントロール」は、水平方向のウィンドウで、通常、アプリケーションがさまざまな種類のステータス情報を表示できます、親ウィンドウの下部に表示されます。 ステータス バー コントロールは、情報の 1 つ以上の種類を表示する部分に分割できます。

このコントロール (つまり、`CStatusBarCtrl`クラス) は以降、Windows 95/98 および Windows NT version 3.51 で実行するプログラムにのみ使用できます。

使用しての詳細については`CStatusBarCtrl`を参照してください[コントロール](../../mfc/controls-mfc.md)と[を使用して CStatusBarCtrl](../../mfc/using-cstatusbarctrl.md)します。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CStatusBarCtrl`

## <a name="requirements"></a>要件

**ヘッダー:** afxcmn.h

##  <a name="create"></a>  CStatusBarCtrl::Create

ステータス バー コントロールを作成しにアタッチします、`CStatusBarCtrl`オブジェクト。

```
virtual BOOL Create(
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>パラメーター

*dwStyle*<br/>
ステータス バー コントロールのスタイルを指定します。 ステータス バーのコントロールのスタイルで表示されている任意の組み合わせを適用[一般的なコントロールのスタイル](/windows/desktop/Controls/common-control-styles)Windows SDK に含まれています。 このパラメーターは、WS_CHILD スタイルを含める必要があります。 WS_VISIBLE スタイルする必要があります。

*rect*<br/>
ステータス バー コントロールのサイズと位置を指定します。 いずれかのことができます、 [CRect](../../atl-mfc-shared/reference/crect-class.md)オブジェクトまたは[RECT](https://msdn.microsoft.com/library/windows/desktop/dd162897)構造体。

*pParentWnd*<br/>
ステータス バー コントロールの親ウィンドウを通常を指定します、`CDialog`します。 NULL は指定できません。

*nID*<br/>
ステータス バー コントロールの ID を指定します

### <a name="return-value"></a>戻り値

成功した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>Remarks

構築する、`CStatusBarCtrl`で 2 つの手順。 最初に、コンス トラクターを呼び出してを呼び出して`Create`、ステータス バー コントロールを作成しにアタッチする`CStatusBarCtrl`オブジェクト。

ステータス ウィンドウの既定の位置は、親ウィンドウの下部にあるが、親ウィンドウのクライアント領域の上部に表示されるようにする CCS_TOP スタイルを指定することができます。 ステータス ウィンドウの右端にあるサイズ変更グリップを含める SBARS_SIZEGRIP スタイルを指定することができます。 結果のサイズ変更グリップが機能しない場合でも、システムは、ステータス ウィンドウに描画するため、CCS_TOP と SBARS_SIZEGRIP スタイルを組み合わせることはお勧めできません。

拡張ウィンドウ スタイルを使用して、ステータス バーを作成するには、呼び出す[CStatusBarCtrl::CreateEx](#createex)の代わりに`Create`します。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CStatusBarCtrl#1](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_1.cpp)]

##  <a name="createex"></a>  CStatusBarCtrl::CreateEx

コントロール (子ウィンドウ) を作成しに関連付けます、`CStatusBarCtrl`オブジェクト。

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
ステータス バー コントロールのスタイルを指定します。 ステータス バーのコントロールのスタイルで表示されている任意の組み合わせを適用[一般的なコントロールのスタイル](/windows/desktop/Controls/common-control-styles)Windows SDK に含まれています。 このパラメーターは、WS_CHILD スタイルを含める必要があります。 WS_VISIBLE スタイルする必要があります。

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

##  <a name="cstatusbarctrl"></a>  CStatusBarCtrl::CStatusBarCtrl

`CStatusBarCtrl` オブジェクトを構築します。

```
CStatusBarCtrl();
```

##  <a name="drawitem"></a>  CStatusBarCtrl::DrawItem

オーナー描画ステータス バー コントロールの変更のビジュアルな部分のときにフレームワークによって呼び出されます。

```
virtual void DrawItem(LPDRAWITEMSTRUCT lpDrawItemStruct);
```

### <a name="parameters"></a>パラメーター

*lpDrawItemStruct*<br/>
Long ポインター、 [DRAWITEMSTRUCT](/windows/desktop/api/winuser/ns-winuser-tagdrawitemstruct)のために必要な図面の種類に関する情報を含む構造体。

### <a name="remarks"></a>Remarks

`itemAction`のメンバー、`DRAWITEMSTRUCT`構造体を実行する描画の動作を定義します。

既定では、このメンバー関数は何もしません。 オーナー描画の描画を実装するには、このメンバー関数をオーバーライド`CStatusBarCtrl`オブジェクト。

アプリケーションで提供されるディスプレイ コンテキスト用に選択したすべてのグラフィックス デバイス インターフェイス (GDI) オブジェクトを復元する必要があります*lpDrawItemStruct*このメンバーの前に、関数が終了します。

##  <a name="getborders"></a>  CStatusBarCtrl::GetBorders

水平および垂直の罫線と四角形の間のスペースのステータス バー コントロールの現在の幅を取得します。

```
BOOL GetBorders(int* pBorders) const;

BOOL GetBorders(
    int& nHorz,
    int& nVert,
    int& nSpacing) const;
```

### <a name="parameters"></a>パラメーター

*pBorders*<br/>
3 つの要素を持つ整数配列のアドレス。 最初の要素が水平方向の境界線の幅を受け取る、2 つ目は、垂直方向の境界線の幅を受信し、3 番目が四角形の間の境界線の幅を受信します。

*nHorz*<br/>
水平方向の境界線の幅を受け取る整数への参照。

*nVert*<br/>
垂直方向の境界線の幅を受け取る整数への参照。

*nSpacing*<br/>
四角形の間の境界線の幅を受け取る整数への参照。

### <a name="return-value"></a>戻り値

成功した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>Remarks

これらの罫線は、コントロールの外側の端とテキストを含む、コントロール内の四角形の間隔を決定します。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CStatusBarCtrl#2](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_2.cpp)]

##  <a name="geticon"></a>  CStatusBarCtrl::GetIcon

現在のステータス バー コントロールのパーツ (ウィンドウとも呼ばれます) のアイコンを取得します。

```
HICON GetIcon(int iPart) const;
```

### <a name="parameters"></a>パラメーター

|パラメーター|説明|
|---------------|-----------------|
|*iPart*|[in]取得するアイコンを含む一部の 0 から始まるインデックス。 このパラメーターが-1 の場合、ステータス バーは簡易モードのステータス バーと見なされます。|

### <a name="return-value"></a>戻り値

アイコンへのハンドル場合メソッドが成功しました。それ以外の場合は NULL です。

### <a name="remarks"></a>Remarks

このメソッドは、送信、 [SB_GETICON](/windows/desktop/Controls/sb-geticon)メッセージは、Windows SDK で説明します。

ステータス バー コントロールとも呼ばれる部分には、テキスト出力ペインの行で構成されます。 ステータス バーの詳細については、次を参照してください。 [MFC でのステータス バーの実装](../../mfc/status-bar-implementation-in-mfc.md)と[CStatusBarCtrl オブジェクトのモードの設定](../../mfc/setting-the-mode-of-a-cstatusbarctrl-object.md)します。

### <a name="example"></a>例

次のコード例は、変数を定義`m_statusBar`、つまり現在のステータス バー コントロールにアクセスするために使用します。 この変数は次の例で使用されています。

[!code-cpp[NVC_MFC_CStatusBarCtrl_s1#1](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_3.h)]

### <a name="example"></a>例

次のコード例では、現在のステータス バー コントロールの 2 つのウィンドウにアイコンをコピーします。 前のセクションのコード例は、3 つのペインで、ステータス バー コントロールを作成し、最初のウィンドウにアイコンを追加します。 この例では、最初のウィンドウからアイコンを取得し、2 番目と 3 番目のウィンドウに追加されます。

[!code-cpp[NVC_MFC_CStatusBarCtrl_s1#2](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_4.cpp)]

##  <a name="getparts"></a>  CStatusBarCtrl::GetParts

ステータス バー コントロールの部品の数を取得します。

```
int GetParts(
    int nParts,
    int* pParts) const;
```

### <a name="parameters"></a>パラメーター

*nParts*<br/>
座標を取得する対象の部分の数。 このパラメーターがコントロール内の部分の数より大きい場合は、既存のパーツのみの座標を取得します。

*pParts*<br/>
指定された部分の数と同じ数の要素を持つ整数配列のアドレス*nParts*します。 配列内の各要素は、対応する部分の右端からのクライアント座標を受け取ります。 -要素が設定されている場合、1 の部分の右端の位置は、ステータス バーの右端に拡張します。

### <a name="return-value"></a>戻り値

成功した場合、コントロール内の部分の数。

### <a name="remarks"></a>Remarks

このメンバー関数は、部分の指定した数値の右端の座標も取得します。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CStatusBarCtrl#3](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_5.cpp)]

##  <a name="getrect"></a>  CStatusBarCtrl::GetRect

ステータス バー コントロールでの部分の外接する四角形を取得します。

```
BOOL GetRect(
    int nPane,
    LPRECT lpRect) const;
```

### <a name="parameters"></a>パラメーター

*nPane*<br/>
外接する四角形が取得される一部の 0 から始まるインデックス。

*lpRect*<br/>
アドレスを[RECT](https://msdn.microsoft.com/library/windows/desktop/dd162897)外接する四角形を受け取る。

### <a name="return-value"></a>戻り値

成功した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CStatusBarCtrl#4](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_6.cpp)]

##  <a name="gettext"></a>  Cstatusbarctrl::gettext

ステータス バー コントロールの特定の部分からテキストを取得します。

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

*nPane*<br/>
テキストの取得元となる部分の 0 から始まるインデックス。

*p 入力してください。*<br/>
型情報を受け取る整数へのポインター。 型には、これらの値のいずれかを指定できます。

- **0**ステータス バーの平面より低く見える境界線と共に、テキストを描画します。

- 国境なき SBT_NOBORDERS テキストが描画されます。

- ステータス バーの平面より上に表示する境界線付き SBT_POPOUT テキストが描画されます。

- SBT_OWNERDRAW 場合、テキストが図面の種類、SBT_OWNERDRAW *p 入力してください*はこのメッセージを受信し、長さと操作の種類ではなくテキストに関連付けられている 32 ビット値を返します。

### <a name="return-value"></a>戻り値

テキストの文字、長さ、または[CString](../../atl-mfc-shared/reference/cstringt-class.md)現在のテキストを格納しています。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CStatusBarCtrl#5](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_7.cpp)]

##  <a name="gettextlength"></a>  Cstatusbarctrl::gettextlength

ステータス バー コントロールの特定の部分からテキストの文字の長さを取得します。

```
int GetTextLength(
    int nPane,
    int* pType = NULL) const;
```

### <a name="parameters"></a>パラメーター

*nPane*<br/>
テキストの取得元となる部分の 0 から始まるインデックス。

*p 入力してください。*<br/>
型情報を受け取る整数へのポインター。 型には、これらの値のいずれかを指定できます。

- **0**ステータス バーの平面より低く見える境界線と共に、テキストを描画します。

- 国境なき SBT_NOBORDERS テキストが描画されます。

- SBT_OWNERDRAW 親ウィンドウで、テキストを描画します。

- ステータス バーの平面より上に表示する境界線付き SBT_POPOUT テキストが描画されます。

### <a name="return-value"></a>戻り値

テキストの文字の長さ。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CStatusBarCtrl#6](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_8.cpp)]

##  <a name="gettiptext"></a>  CStatusBarCtrl::GetTipText

ステータス バーで、ウィンドウのツールヒントのテキストを取得します。

```
CString GetTipText(int nPane) const;
```

### <a name="parameters"></a>パラメーター

*nPane*<br/>
ツールヒント テキストを受け取るステータス バー ペインの 0 から始まるインデックス。

### <a name="return-value"></a>戻り値

A [CString](../../atl-mfc-shared/reference/cstringt-class.md)ツールヒントで使用するテキストを含むオブジェクト。

### <a name="remarks"></a>Remarks

このメンバー関数は、Win32 メッセージの動作を実装[SB_GETTIPTEXT](/windows/desktop/Controls/sb-gettiptext)」の説明に従って、Windows SDK。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CStatusBarCtrl#7](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_9.cpp)]

##  <a name="issimple"></a>  CStatusBarCtrl::IsSimple

簡易モードでは、ステータス ウィンドウ コントロールを確認します。

```
BOOL IsSimple() const;
```

### <a name="return-value"></a>戻り値

ステータス ウィンドウのコントロールが簡易モードの場合、0 以外の場合それ以外の場合 0 を返します。

### <a name="remarks"></a>Remarks

このメンバー関数は、Win32 メッセージの動作を実装[SB_ISSIMPLE](/windows/desktop/Controls/sb-issimple)」の説明に従って、Windows SDK。

##  <a name="setbkcolor"></a>  CStatusBarCtrl::SetBkColor

ステータス バーの背景色を設定します。

```
COLORREF SetBkColor(COLORREF cr);
```

### <a name="parameters"></a>パラメーター

*cr*<br/>
新しい背景色を示す COLORREF 値です。 ステータス バーの既定の背景色を使用するときの値を指定します。

### <a name="return-value"></a>戻り値

A [COLORREF](/windows/desktop/gdi/colorref)前の既定の背景色を表す値です。

### <a name="remarks"></a>Remarks

このメンバー関数は、Win32 メッセージの動作を実装[SB_SETBKCOLOR](/windows/desktop/Controls/sb-setbkcolor)」の説明に従って、Windows SDK。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CStatusBarCtrl#8](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_10.cpp)]

##  <a name="seticon"></a>  CStatusBarCtrl::SetIcon

ステータス バー ペインのアイコンを設定します。

```
BOOL SetIcon(
    int nPane,
    HICON hIcon);
```

### <a name="parameters"></a>パラメーター

*nPane*<br/>
アイコンを受信するウィンドウの 0 から始まるインデックス。 このパラメーターが-1 の場合、ステータス バーは簡易ステータス バーと見なされます。

*hIcon*<br/>
設定するアイコンへのハンドルします。 この値が NULL の場合は、アイコンが、一部から削除されます。

### <a name="return-value"></a>戻り値

成功した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>Remarks

このメンバー関数は、Win32 メッセージの動作を実装[SB_SETICON](/windows/desktop/Controls/sb-seticon)」の説明に従って、Windows SDK。

### <a name="example"></a>例

  例をご覧ください[CStatusBarCtrl::SetBkColor](#setbkcolor)します。

##  <a name="setminheight"></a>  CStatusBarCtrl::SetMinHeight

バーのコントロールの描画領域の状態の最小の高さを設定します。

```
void SetMinHeight(int nMin);
```

### <a name="parameters"></a>パラメーター

*nMin*<br/>
最小の高さ、コントロールの (ピクセル単位)。

### <a name="remarks"></a>Remarks

最小の高さの合計は、 *nMin*と (ピクセル単位)、ステータス バー コントロールの垂直方向の境界線の幅 2 回クリックします。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CStatusBarCtrl#9](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_11.cpp)]

##  <a name="setparts"></a>  CStatusBarCtrl::SetParts

ステータス バー コントロールと各部分の右端の座標で部分の数を設定します。

```
BOOL SetParts(
    int nParts,
    int* pWidths);
```

### <a name="parameters"></a>パラメーター

*nParts*<br/>
設定する部分の数。 部分の数は 255 より大きい値にすることはできません。

*pWidths*<br/>
指定された部分と同じ数の要素を持つ整数配列のアドレス*nParts*します。 配列内の各要素には、クライアント座標での対応する部分の右端の位置を指定します。 要素が - 1 の場合、その部分の右端の位置は、コントロールの右端に拡張されます。

### <a name="return-value"></a>戻り値

成功した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CStatusBarCtrl#10](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_12.cpp)]

##  <a name="setsimple"></a>  CStatusBarCtrl::SetSimple

ステータス バー コントロールが単純なテキストを表示します。 または以前の呼び出しで設定するすべてのコントロール パーツが表示されますかどうかを指定します[呼び出した](#setparts)します。

```
BOOL SetSimple(BOOL bSimple = TRUE);
```

### <a name="parameters"></a>パラメーター

*bSimple*<br/>
[in]表示型のフラグ。 コントロールが単純なテキストを表示するこのパラメーターが TRUE の場合FALSE の場合は、複数の部分が表示されます。

### <a name="return-value"></a>戻り値

常に 0 を返します。

### <a name="remarks"></a>Remarks

アプリケーションでは、単純なまたはその逆に、単純ではないから、ステータス バー コントロールを変更、する場合、システムがすぐに、コントロールに再描画します。

##  <a name="settext"></a>  CStatusBarCtrl::SetText

ステータス バー コントロールの特定の部分にテキストを設定します。

```
BOOL SetText(
    LPCTSTR lpszText,
    int nPane,
    int nType);
```

### <a name="parameters"></a>パラメーター

*lpszText*<br/>
設定されるテキストを指定する null で終わる文字列のアドレス。 場合 *%n タイプ*は SBT_OWNERDRAW、 *lpszText* 32 ビットのデータを表します。

*nPane*<br/>
設定される部分の 0 から始まるインデックス。 この値が 255 の場合、ステータス バー コントロールは 1 つの部分のみで構成される単純なコントロールと見なされます。

*%n タイプ*<br/>
描画操作の種類。 参照してください[SB_SETTEXT メッセージ](/windows/desktop/Controls/sb-settext)使用可能な値の一覧についてはします。

### <a name="return-value"></a>戻り値

成功した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>Remarks

メッセージは、原因で、コントロールが次に WM_PAINT メッセージを受信すると、新しいテキストを表示するように、変更されたコントロールの部分を無効にします。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CStatusBarCtrl#11](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_13.cpp)]

##  <a name="settiptext"></a>  CStatusBarCtrl::SetTipText

ステータス バーで、ウィンドウのツールヒントのテキストを設定します。

```
void SetTipText(
    int nPane,
    LPCTSTR pszTipText);
```

### <a name="parameters"></a>パラメーター

*nPane*<br/>
ツールヒント テキストを受け取るステータス バー ペインの 0 から始まるインデックス。

*pszTipText*<br/>
ツールヒント テキストを含む文字列へのポインター。

### <a name="remarks"></a>Remarks

このメンバー関数は、Win32 メッセージの動作を実装[SB_SETTIPTEXT](/windows/desktop/Controls/sb-settiptext)」の説明に従って、Windows SDK。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CStatusBarCtrl#12](../../mfc/reference/codesnippet/cpp/cstatusbarctrl-class_14.cpp)]

## <a name="see-also"></a>関連項目

[CWnd クラス](../../mfc/reference/cwnd-class.md)<br/>
[階層図](../../mfc/hierarchy-chart.md)<br/>
[CToolBarCtrl クラス](../../mfc/reference/ctoolbarctrl-class.md)

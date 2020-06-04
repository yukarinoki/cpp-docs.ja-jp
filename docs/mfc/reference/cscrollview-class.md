---
title: CScrollView クラス
ms.date: 11/04/2016
f1_keywords:
- CScrollView
- AFXWIN/CScrollView
- AFXWIN/CScrollView::CScrollView
- AFXWIN/CScrollView::CheckScrollBars
- AFXWIN/CScrollView::FillOutsideRect
- AFXWIN/CScrollView::GetDeviceScrollPosition
- AFXWIN/CScrollView::GetDeviceScrollSizes
- AFXWIN/CScrollView::GetScrollPosition
- AFXWIN/CScrollView::GetTotalSize
- AFXWIN/CScrollView::ResizeParentToFit
- AFXWIN/CScrollView::ScrollToPosition
- AFXWIN/CScrollView::SetScaleToFitSize
- AFXWIN/CScrollView::SetScrollSizes
helpviewer_keywords:
- CScrollView [MFC], CScrollView
- CScrollView [MFC], CheckScrollBars
- CScrollView [MFC], FillOutsideRect
- CScrollView [MFC], GetDeviceScrollPosition
- CScrollView [MFC], GetDeviceScrollSizes
- CScrollView [MFC], GetScrollPosition
- CScrollView [MFC], GetTotalSize
- CScrollView [MFC], ResizeParentToFit
- CScrollView [MFC], ScrollToPosition
- CScrollView [MFC], SetScaleToFitSize
- CScrollView [MFC], SetScrollSizes
ms.assetid: 4ba16dac-1acb-4be0-bb55-5fb695b6948d
ms.openlocfilehash: 5d0eb163fae2aa5fc63470e1c499311ab1a402a6
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "81754420"
---
# <a name="cscrollview-class"></a>CScrollView クラス

スクロール機能を備えた[CView。](../../mfc/reference/cview-class.md)

## <a name="syntax"></a>構文

```
class CScrollView : public CView
```

## <a name="members"></a>メンバー

### <a name="protected-constructors"></a>プロテクト コンストラクター

|名前|説明|
|----------|-----------------|
|[スクロールビュー::スクロールビュー](#cscrollview)|`CScrollView` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[スクロールバーを見る](#checkscrollbars)|スクロール ビューに水平スクロール バーと垂直スクロール バーがあるかどうかを示します。|
|[スクロールビュー::フィルアウトサイドレクト](#filloutsiderect)|スクロール領域の外側のビューの領域を塗りつぶします。|
|[次の値を表示します。](#getdevicescrollposition)|デバイス単位の現在のスクロール位置を取得します。|
|[スクロールビュー::デバイススクロールのサイズ](#getdevicescrollsizes)|現在のマップ モード、合計サイズ、およびスクロール可能なビューの行とページ のサイズを取得します。 サイズはデバイス単位です。|
|[表示::取得スクロール位置](#getscrollposition)|現在のスクロール位置を論理単位で取得します。|
|[表示::合計サイズを取得します。](#gettotalsize)|スクロール ビューの合計サイズを論理単位で取得します。|
|[スクロールビュー::リサイズ親フィットフィット](#resizeparenttofit)|ビューのサイズによってフレームのサイズが決まります。|
|[スクロールビュー::スクロールの位置](#scrolltoposition)|論理単位で指定された特定のポイントまでビューをスクロールします。|
|[スクロールビュー::セットスケールフィットサイズ](#setscaletofitsize)|スクロール ビューを拡大縮小モードにします。|
|[スクロールビュー::セットスクロールサイズ](#setscrollsizes)|スクロール ビューのマッピング モード、合計サイズ、水平および垂直スクロール量を設定します。|

## <a name="remarks"></a>解説

メッセージ マップされた OnHScroll および`CView`[OnVScroll](../../mfc/reference/cwnd-class.md#onvscroll)メンバー関数をオーバーライドすることで、派生した任意のクラスで標準[スクロール](../../mfc/reference/cwnd-class.md#onhscroll)を処理できます。 ただし`CScrollView`、その機能に次の`CView`機能を追加します。

- ウィンドウとビューポートのサイズとマッピング モードを管理します。

- スクロール バー メッセージに応答して自動的にスクロールします。

- キーボード、スクロールしないマウス、または IntelliMouse ホイールからのメッセージに応答して自動的にスクロールします。

キーボードからのメッセージに応答して自動的にスクロールするには、WM_KEYDOWNメッセージを追加し、VK_DOWNをテストし、VK_PREVして[SetScrollPos](/windows/win32/api/winuser/nf-winuser-setscrollpos)を呼び出します。

マウス ホイールを自分でスクロールするには、メッセージ マップの[OnMouseWheel](../../mfc/reference/cwnd-class.md#onmousewheel)および[OnRegisteredMouseWheel](../../mfc/reference/cwnd-class.md#onregisteredmousewheel)メンバー関数をオーバーライドします。 これらのメンバー関数は`CScrollView`、ホイール回転メッセージ を[WM_MOUSEWHEEL](/windows/win32/inputdev/wm-mousewheel)に推奨される動作をサポートします。

自動スクロールを利用するには、 から`CScrollView`ではなくからビュー クラスを派生`CView`させます。 ビューが最初に作成されたとき、ドキュメントのサイズに基づいてスクロール可能なビューのサイズを計算する場合は[、CView::OnInitialUpdate](../../mfc/reference/cview-class.md#oninitialupdate)または[CView::OnUpdate](../../mfc/reference/cview-class.md#onupdate)のいずれかのオーバーライドから`SetScrollSizes`メンバー関数を呼び出します。 (ドキュメントのサイズをクエリする独自のコードを記述する必要があります。 例については、[落書きのサンプル](../../overview/visual-cpp-samples.md)を参照してください。

メンバー関数の`SetScrollSizes`呼び出しは、ビューのマッピング モード、スクロール ビューの合計サイズ、および水平方向と垂直方向にスクロールする量を設定します。 すべてのサイズは論理単位です。 ビューの論理サイズは、通常、ドキュメントに格納されているデータから計算されますが、場合によっては固定サイズを指定する必要があります。 両方のアプローチの例については[、「CScrollView::SetScrollSizes](#setscrollsizes)」を参照してください。

水平および垂直にスクロールする量を論理単位で指定します。 既定では、ユーザーがスクロール ボックスの外側にあるスクロール バーシャフトをクリックすると`CScrollView`、"ページ" がスクロールされます。 ユーザーがスクロール バーの両端にあるスクロール バーをクリックすると、"`CScrollView`行" がスクロールされます。 既定では、ページはビューの合計サイズの 1/10 です。行はページ サイズの 1/10 です。 メンバー関数でカスタム サイズを渡すことによって、これらの`SetScrollSizes`既定値をオーバーライドします。 たとえば、横のサイズを合計サイズの幅の一部に、縦サイズを現在のフォントの行の高さに設定できます。

スクロールの代わりに、`CScrollView`ビューを現在のウィンドウ サイズに自動的に拡大縮小できます。 このモードでは、ビューにスクロール バーがなく、論理ビューはウィンドウのクライアント領域に正確に収まるように拡大または縮小されます。 このスケール・ツー・フィット機能を使用するには[、CScrollView::SetScaleToFitSize](#setscaletofitsize)を呼び出します。 (いずれかまたは`SetScaleToFitSize``SetScrollSizes`を呼び出しますが、両方は呼び出しません)。

派生ビュー`OnDraw`クラスのメンバー関数が呼び出される`CScrollView`前に、そのクラスがに渡`CPaintDC`すデバイス コンテキスト オブジェクトのビューポートの`OnDraw`原点を自動的に調整します。

スクロール ウィンドウのビューポートの原点を調整するには`CScrollView`[、CView::OnPrepareDC](../../mfc/reference/cview-class.md#onpreparedc)をオーバーライドします。 この調整は、 に`CPaintDC`渡される`CScrollView`デバイス コンテキストに`OnDraw`対して自動的に行`CScrollView::OnPrepareDC`われますが、 など、使用するその他のデバイス`CClientDC`コンテキストについては自分自身を呼び出す必要があります。 ペン、背景色`CScrollView::OnPrepareDC`、およびその他の描画属性を設定するためにオーバーライドできますが、スケーリングを行うには基本クラスを呼び出します。

スクロール バーは、次の場合に示すように、ビューに対して相対的に 3 つの場所に表示されます。

- 標準のウィンドウ スタイルスクロール バーは、WS_HSCROLLおよび[Windows スタイル](../../mfc/reference/styles-used-by-mfc.md#window-styles)WS_VSCROLLを使用してビューに設定できます。

- スクロール バー コントロールは WM_VSCROLL WM_HSCROLLビューを含むフレームに追加することもできます。

- フレームワークは、ス`CSplitterWnd`プリッタ コントロールから現在アクティブな分割ペイン (ビュー) にスクロール メッセージも転送します。 共有スクロール バーを持つ[CSplitterWnd](../../mfc/reference/csplitterwnd-class.md)に`CScrollView`配置すると、オブジェクトは、独自のスクロール バーを作成するのではなく、共有オブジェクトを使用します。

の詳細`CScrollView`については、「 MFC で使用できる[ドキュメント/ビュー アーキテクチャ](../../mfc/document-view-architecture.md)クラスおよび[派生ビュー クラス](../../mfc/derived-view-classes-available-in-mfc.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CView](../../mfc/reference/cview-class.md)

`CScrollView`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxwin.h

## <a name="cscrollviewcheckscrollbars"></a><a name="checkscrollbars"></a>スクロールバーを見る

スクロール ビューに水平および垂直のバーがあるかどうかを調べます。

```cpp
void CheckScrollBars(
    BOOL& bHasHorzBar,
    BOOL& bHasVertBar) const;
```

### <a name="parameters"></a>パラメーター

*bHasHorzBar*<br/>
アプリケーションに水平スクロール バーが表示されていることを示します。

*bハスバートバー*<br/>
アプリケーションに垂直スクロール バーが表示されていることを示します。

## <a name="cscrollviewcscrollview"></a><a name="cscrollview"></a>スクロールビュー::スクロールビュー

`CScrollView` オブジェクトを構築します。

```
CScrollView();
```

### <a name="remarks"></a>解説

スクロール ビューを`SetScrollSizes`使用`SetScaleToFitSize`できるようにするには、いずれかまたは前に呼び出す必要があります。

## <a name="cscrollviewfilloutsiderect"></a><a name="filloutsiderect"></a>スクロールビュー::フィルアウトサイドレクト

スクロール`FillOutsideRect`領域の外側に表示されるビューの領域を埋めるために呼び出します。

```cpp
void FillOutsideRect(
    CDC* pDC,
    CBrush* pBrush);
```

### <a name="parameters"></a>パラメーター

*pDC*<br/>
埋め込みが行われるデバイス コンテキスト。

*pブラシ*<br/>
領域を塗りつぶすブラシ。

### <a name="remarks"></a>解説

スクロール`FillOutsideRect`ビューの`OnEraseBkgnd`ハンドラー関数で使用すると、バックグラウンドでの再描画が過剰に行えなくなります。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocView#164](../../mfc/codesnippet/cpp/cscrollview-class_1.cpp)]

## <a name="cscrollviewgetdevicescrollposition"></a><a name="getdevicescrollposition"></a>次の値を表示します。

スクロール`GetDeviceScrollPosition`バーのスクロール ボックスの現在の水平位置と垂直位置が必要な場合に呼び出します。

```
CPoint GetDeviceScrollPosition() const;
```

### <a name="return-value"></a>戻り値

スクロール ボックスの水平位置と垂直位置 (デバイス単位) を`CPoint`オブジェクトとして指定します。

### <a name="remarks"></a>解説

この座標ペアは、ビューの左上隅がスクロールされたドキュメント内の位置に対応します。 これは、マウス デバイスの位置をスクロール ビュー デバイスの位置にオフセットする場合に便利です。

`GetDeviceScrollPosition`は、値をデバイス単位で返します。 論理単位が必要な場合は`GetScrollPosition`、代わりに使用します。

## <a name="cscrollviewgetdevicescrollsizes"></a><a name="getdevicescrollsizes"></a>スクロールビュー::デバイススクロールのサイズ

`GetDeviceScrollSizes`現在のマッピング モード、合計サイズ、およびスクロール可能なビューの行とページ サイズを取得します。

```cpp
void GetDeviceScrollSizes(
    int& nMapMode,
    SIZE& sizeTotal,
    SIZE& sizePage,
    SIZE& sizeLine) const;
```

### <a name="parameters"></a>パラメーター

*マップモード*<br/>
このビューの現在のマッピング モードを返します。 有効な値の一覧については、「`SetScrollSizes`」を参照してください。

*サイズ合計*<br/>
スクロール ビューの現在の合計サイズをデバイス単位で返します。

*サイズページ*<br/>
スクロール バーシャフトのマウス クリックに応じて、各方向にスクロールする現在の水平および垂直の量を返します。 メンバ`cx`には水平方向の量が含まれています。 メンバ`cy`には、縦方向の金額が含まれています。

*サイズライン*<br/>
スクロール バーの矢印でマウスをクリックしたときに、各方向にスクロールする現在の水平および垂直の量を返します。 メンバ`cx`には水平方向の量が含まれています。 メンバ`cy`には、縦方向の金額が含まれています。

### <a name="remarks"></a>解説

サイズはデバイス単位です。 このメンバー関数はめったに呼び出されません。

## <a name="cscrollviewgetscrollposition"></a><a name="getscrollposition"></a>表示::取得スクロール位置

スクロール`GetScrollPosition`バーのスクロール ボックスの現在の水平位置と垂直位置が必要な場合に呼び出します。

```
CPoint GetScrollPosition() const;
```

### <a name="return-value"></a>戻り値

スクロール ボックスの水平位置と垂直位置 (論理単位) を`CPoint`オブジェクトとして指定します。

### <a name="remarks"></a>解説

この座標ペアは、ビューの左上隅がスクロールされたドキュメント内の位置に対応します。

`GetScrollPosition`は、論理単位で値を返します。 デバイスユニットが必要な場合は`GetDeviceScrollPosition`、代わりに使用してください。

## <a name="cscrollviewgettotalsize"></a><a name="gettotalsize"></a>表示::合計サイズを取得します。

スクロール`GetTotalSize`ビューの現在の水平サイズと垂直サイズを取得する呼び出し。

```
CSize GetTotalSize() const;
```

### <a name="return-value"></a>戻り値

スクロール ビューの合計サイズ (論理単位)。 水平方向のサイズは、戻`cx`り値の`CSize`メンバーにあります。 縦のサイズはメンバー内`cy`にあります。

## <a name="cscrollviewresizeparenttofit"></a><a name="resizeparenttofit"></a>スクロールビュー::リサイズ親フィットフィット

ビュー`ResizeParentToFit`のサイズがフレーム ウィンドウのサイズを決定するように呼び出します。

```cpp
void ResizeParentToFit(BOOL bShrinkOnly = TRUE);
```

### <a name="parameters"></a>パラメーター

*を縮小するのみ*<br/>
実行するサイズ変更の種類。 既定値 TRUE は、必要に応じてフレーム ウィンドウを縮小します。 大きなビューまたは小さなフレーム ウィンドウの場合も、スクロール バーは表示されます。 FALSE の値を指定すると、ビューは常にフレーム ウィンドウのサイズを正確に変更します。 フレーム ウィンドウが大きくなりすぎてマルチ ドキュメント インターフェイス (MDI) フレーム ウィンドウまたは画面に収まらない場合があるため、この方法は多少危険です。

### <a name="remarks"></a>解説

これは、MDI 子フレーム ウィンドウのビューにのみ使用することをお勧めします。 派生`ResizeParentToFit``CScrollView`クラスの`OnInitialUpdate`ハンドラー関数で使用します。 このメンバー関数の例については[、「CScrollView::SetScrollSizes](#setscrollsizes)」を参照してください。

`ResizeParentToFit`ビュー ウィンドウのサイズが設定されていることを前提にしています。 ビュー ウィンドウのサイズが呼び出されたときに`ResizeParentToFit`設定されていない場合は、アサーションが取得されます。 この問題が発生しないようにするには、呼び出す前に次`ResizeParentToFit`の呼び出しを行います。

[!code-cpp[NVC_MFCDocView#165](../../mfc/codesnippet/cpp/cscrollview-class_2.cpp)]

## <a name="cscrollviewscrolltoposition"></a><a name="scrolltoposition"></a>スクロールビュー::スクロールの位置

ビュー`ScrollToPosition`内の指定したポイントまでスクロールする呼び出し。

```cpp
void ScrollToPosition(POINT pt);
```

### <a name="parameters"></a>パラメーター

*Pt*<br/>
スクロールするポイント (論理単位)。 メンバー`x`は正の値 (ビューの合計サイズまで 0 以上) である必要があります。 マッピング モードがMM_TEXTの`y`場合も、メンバーについても同じことが言えます。 メンバー`y`は、MM_TEXT以外のマッピング モードでは負の値です。

### <a name="remarks"></a>解説

ビューは、このポイントがウィンドウの左上隅になるようにスクロールされます。 ビューが適切に拡大縮小されている場合は、このメンバー関数を呼び出してはなりません。

## <a name="cscrollviewsetscaletofitsize"></a><a name="setscaletofitsize"></a>スクロールビュー::セットスケールフィットサイズ

ビューポート`SetScaleToFitSize`のサイズを現在のウィンドウ サイズに自動的にスケールする場合に呼び出します。

```cpp
void SetScaleToFitSize(SIZE sizeTotal);
```

### <a name="parameters"></a>パラメーター

*サイズ合計*<br/>
ビューの拡大/縮小先の水平および垂直サイズ。 スクロール ビューのサイズは論理単位で測定されます。 水平方向のサイズは、メンバーに`cx`含まれています。 縦のサイズは、メンバーに`cy`含まれています。 両方`cx`とも`cy`0 以上である必要があります。

### <a name="remarks"></a>解説

スクロール バーでは、論理ビューの一部だけがいつでも表示できます。 ただし、拡大縮小機能では、ビューにスクロール バーがなく、論理ビューはウィンドウのクライアント領域に正確に合うように拡大または縮小されます。 ウィンドウのサイズを変更すると、ビューはウィンドウのサイズに基づいて新しいスケールでデータを描画します。

通常、ビューの`SetScaleToFitSize``OnInitialUpdate`メンバー関数のオーバーライドに呼び出しを配置します。 自動スケーリングを行わない場合は、代わりにメンバー`SetScrollSizes`関数を呼び出します。

`SetScaleToFitSize`「合わせてズーム」操作を実装するために使用できます。 スクロール`SetScrollSizes`を再初期化するために使用します。

`SetScaleToFitSize`ビュー ウィンドウのサイズが設定されていることを前提にしています。 ビュー ウィンドウのサイズが呼び出されたときに`SetScaleToFitSize`設定されていない場合は、アサーションが取得されます。 この問題が発生しないようにするには、呼び出す前に次`SetScaleToFitSize`の呼び出しを行います。

[!code-cpp[NVC_MFCDocView#165](../../mfc/codesnippet/cpp/cscrollview-class_2.cpp)]

## <a name="cscrollviewsetscrollsizes"></a><a name="setscrollsizes"></a>スクロールビュー::セットスクロールサイズ

ビュー`SetScrollSizes`が更新されるときに呼び出します。

```cpp
void SetScrollSizes(
    int nMapMode,
    SIZE sizeTotal,
    const SIZE& sizePage = sizeDefault,
    const SIZE& sizeLine = sizeDefault);
```

### <a name="parameters"></a>パラメーター

*マップモード*<br/>
このビューに設定するマッピング モード。 指定できる値は、次のとおりです。

|マッピングモード|論理ユニット|正の y 軸拡張.|
|------------------|------------------|---------------------------------|
|Mm_text|1 ピクセル|下方|
|MM_HIMETRIC|0.01 mm|上向き|
|MM_TWIPS|1/1440 in|上向き|
|MM_HIENGLISH|0.001 in|上向き|
|MM_LOMETRIC|0.1 mm|上向き|
|MM_LOENGLISH|0.01 in|上向き|

これらのモードはすべて Windows によって定義されます。 MM_ISOTROPICとMM_ANISOTROPICの 2 つの標準マッピング モードは`CScrollView`、 には使用されません。 クラス ライブラリは、`SetScaleToFitSize`ウィンドウ サイズにビューをスケーリングするためのメンバー関数を提供します。 上の表の 3 列目に、座標の方向を説明します。

*サイズ合計*<br/>
スクロール ビューの合計サイズ。 メンバ`cx`には水平方向の範囲が含まれています。 メンバー`cy`には、垂直方向の範囲が含まれています。 サイズは論理単位で表されます。 両方`cx`とも`cy`0 以上である必要があります。

*サイズページ*<br/>
スクロール バーシャフトでのマウスクリックに応じて、各方向にスクロールする水平方向と垂直方向の量。 メンバ`cx`には水平方向の量が含まれています。 メンバ`cy`には、縦方向の金額が含まれています。

*サイズライン*<br/>
スクロールバーの矢印でマウスをクリックしたときに、各方向にスクロールする水平方向と垂直方向の量。 メンバ`cx`には水平方向の量が含まれています。 メンバ`cy`には、縦方向の金額が含まれています。

### <a name="remarks"></a>解説

たとえば、ドキュメントが`OnUpdate`最初に表示されたときやサイズが変更されたときにスクロール特性を調整するために、メンバー関数のオーバーライドで呼び出します。

通常、派生ドキュメント クラスで提供するドキュメント メンバー関数 (たとえば " と呼ばれます`GetMyDocSize`) を呼び出すことによって、ビューの関連ドキュメントからサイズ情報を取得します。 次のコードは、この方法を示しています。

[!code-cpp[NVC_MFCDocView#166](../../mfc/codesnippet/cpp/cscrollview-class_3.cpp)]

または、次のコードのように固定サイズを設定する必要がある場合もあります。

[!code-cpp[NVC_MFCDocView#167](../../mfc/codesnippet/cpp/cscrollview-class_4.cpp)]

マッピング モードは、MM_ISOTROPICまたはMM_ANISOTROPIC以外の Windows マッピング モードのいずれかに設定する必要があります。 制約のないマッピング モードを使用する場合は、`SetScaleToFitSize``SetScrollSizes`の代わりにメンバー関数を呼び出します。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocView#168](../../mfc/codesnippet/cpp/cscrollview-class_5.cpp)]

[!code-cpp[NVC_MFCDocView#169](../../mfc/codesnippet/cpp/cscrollview-class_6.cpp)]

## <a name="see-also"></a>関連項目

[MFC サンプル ディブルック](../../overview/visual-cpp-samples.md)<br/>
[Cビュークラス](../../mfc/reference/cview-class.md)<br/>
[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[Cビュークラス](../../mfc/reference/cview-class.md)<br/>
[クラスを分割する](../../mfc/reference/csplitterwnd-class.md)

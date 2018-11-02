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
ms.openlocfilehash: 9ec6177b1f2cb071a6aa284c2936f3af4dbe4634
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50468277"
---
# <a name="cscrollview-class"></a>CScrollView クラス

A [CView](../../mfc/reference/cview-class.md)スクロール機能を持つ。

## <a name="syntax"></a>構文

```
class CScrollView : public CView
```

## <a name="members"></a>メンバー

### <a name="protected-constructors"></a>プロテクト コンストラクター

|名前|説明|
|----------|-----------------|
|[CScrollView::CScrollView](#cscrollview)|`CScrollView` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CScrollView::CheckScrollBars](#checkscrollbars)|スクロール ビューが水平方向と垂直スクロール バーを持つかどうかを示します。|
|[CScrollView::FillOutsideRect](#filloutsiderect)|スクロール領域の外側のビューの領域を塗りつぶします。|
|[CScrollView::GetDeviceScrollPosition](#getdevicescrollposition)|デバイス単位では、現在のスクロール位置を取得します。|
|[CScrollView::GetDeviceScrollSizes](#getdevicescrollsizes)|現在のマップ モード、合計のサイズおよびスクロール可能なビューの行とページのサイズを取得します。 サイズでは、デバイス単位です。|
|[CScrollView::GetScrollPosition](#getscrollposition)|論理ユニットでは、現在のスクロール位置を取得します。|
|[CScrollView::GetTotalSize](#gettotalsize)|論理ユニットで、スクロール ビューの合計サイズを取得します。|
|[CScrollView::ResizeParentToFit](#resizeparenttofit)|フレームのサイズに合うようにビューのサイズをによりします。|
|[CScrollView::ScrollToPosition](#scrolltoposition)|論理単位で指定された位置にビューをスクロールします。|
|[CScrollView::SetScaleToFitSize](#setscaletofitsize)|サイズに合わせて-スケール モードには、スクロール ビューを配置します。|
|[CScrollView::SetScrollSizes](#setscrollsizes)|スクロール ビューのマッピング モード、合計サイズ、および水平方向および垂直方向のスクロール量を設定します。|

## <a name="remarks"></a>Remarks

Standard から派生したクラスで自分でスクロールを処理できる`CView`メッセージ マップをオーバーライドして[OnHScroll](../../mfc/reference/cwnd-class.md#onhscroll)と[OnVScroll](../../mfc/reference/cwnd-class.md#onvscroll)メンバー関数。 `CScrollView`には、次の機能を追加します。 その`CView`機能。

- ウィンドウと、ビューポートのサイズとのマッピング モードを管理します。

- スクロール バーのメッセージに応答して自動的にスクロールします。

- キーボード、非スクロールのマウス、または IntelliMouse ホイールからのメッセージに応答して自動的にスクロールします。

キーボードからのメッセージに対して自動的にスクロールして、WM_KEYDOWN メッセージを追加し、VK_DOWN、VK_PREV と呼び出しをテスト[SetScrollPos](/windows/desktop/api/winuser/nf-winuser-setscrollpos)します。

マウス ホイールを自分でメッセージ マップをオーバーライドしてスクロールを処理できる[OnMouseWheel](../../mfc/reference/cwnd-class.md#onmousewheel)と[OnRegisteredMouseWheel](../../mfc/reference/cwnd-class.md#onregisteredmousewheel)メンバー関数。 `CScrollView`、これらのメンバー関数の推奨される動作をサポートする[WM_MOUSEWHEEL](/windows/desktop/inputdev/wm-mousewheel)ホイールの回転メッセージ。

自動スクロールを活用するからビュー クラスを派生`CScrollView`の代わりにから`CView`します。 ビューが初めて作成すると、呼び出し、ドキュメントのサイズに基づいて、スクロール可能なビューのサイズを計算する場合、`SetScrollSizes`メンバー関数は、いずれかのオーバーライドから[:oninitialupdate](../../mfc/reference/cview-class.md#oninitialupdate)または[CView::OnUpdate](../../mfc/reference/cview-class.md#onupdate)します。 (ドキュメントのサイズを照会する独自のコードを記述する必要があります。 例については、次を参照してください、 [Scribble サンプル](../../visual-cpp-samples.md)。)。

呼び出し、`SetScrollSizes`メンバー関数、ビューのマッピング モードでは、スクロール ビュー、および水平方向および垂直方向のスクロール量の合計サイズを設定します。 すべてのサイズでは、論理単位です。 ビューの論理サイズは通常、ドキュメントに格納されたデータから計算されます。 ただし、場合によっては、固定サイズを指定したい場合があります。 両方の方法の例については、次を参照してください。 [CScrollView::SetScrollSizes](#setscrollsizes)します。

論理単位で水平方向および垂直方向のスクロール量を指定します。 既定では、ユーザーがクリックすると、スクロール ボックスの外側のスクロール バー突き出し`CScrollView`「ページ」をスクロールします。 ユーザーがスクロール バーのいずれかの端にあるスクロール バーの矢印をクリックすると`CScrollView`"line"をスクロールします。 既定では、1 ページには、ビューの合計サイズの 1/10 です。線は、1/10 ページ サイズです。 カスタム サイズを渡すことによってこれらの既定値をオーバーライド、`SetScrollSizes`メンバー関数。 たとえば、現在のフォントで水平方向のサイズを合計サイズと行の高さを垂直方向のサイズの幅未満であるに設定する可能性があります。

スクロールではなく`CScrollView`ビューを現在のウィンドウ サイズを自動的にスケールできます。 このモードでは、ビューにスクロール バーがないと論理的なビューを拡大または縮小に合わせてウィンドウのクライアント領域。 このサイズに合わせて-スケール機能を使用するには、呼び出す[CScrollView::SetScaleToFitSize](#setscaletofitsize)します。 (いずれかを呼び出す`SetScaleToFitSize`または`SetScrollSizes`、両方ではなく)。

前に、`OnDraw`派生ビュー クラスのメンバー関数が呼び出されると、`CScrollView`のビューポートの原点を自動的に調整、`CPaintDC`デバイス コンテキスト オブジェクトに渡される`OnDraw`します。

スクロールのウィンドウのビューポートの原点を調整する`CScrollView`オーバーライド[付け](../../mfc/reference/cview-class.md#onpreparedc)します。 この調整が自動的に、`CPaintDC`デバイス コンテキストを`CScrollView`に渡す`OnDraw`、呼び出す必要がありますが、`CScrollView::OnPrepareDC`あなた自身の他の任意のデバイス コンテキストを使用するなど、`CClientDC`します。 オーバーライドできます`CScrollView::OnPrepareDC`ペン、背景色、およびその他の描画の属性がスケーリングを行う基本クラスを呼び出します。

スクロール バーは、次の場合のようにビューを基準とした 3 つの場所で表示できます。

- WS_HSCROLL と WS_VSCROLL を使用して、ビューのスクロール バーの標準のウィンドウ スタイルを設定できる[Windows スタイル](../../mfc/reference/styles-used-by-mfc.md#window-styles)します。

- ビューを含むフレームにスクロール バー コントロールを追加することも、この場合、framework から転送されますしおよび WM_VSCROLL メッセージ フレーム ウィンドウから現在アクティブなビューに。

- フレームワークはまた転送からのメッセージのスクロール、`CSplitterWnd`現在アクティブな分割ウィンドウ (ビュー) に分割線コントロール。 使用すると、 [CSplitterWnd](../../mfc/reference/csplitterwnd-class.md) 、共有のスクロール バーを`CScrollView`独自に作成するのではなく、共有のオブジェクトを使用します。

使用しての詳細については`CScrollView`を参照してください[ドキュメント/ビュー アーキテクチャ](../../mfc/document-view-architecture.md)と[派生ビュー クラスで使用できる MFC](../../mfc/derived-view-classes-available-in-mfc.md)します。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CView](../../mfc/reference/cview-class.md)

`CScrollView`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxwin.h

##  <a name="checkscrollbars"></a>  CScrollView::CheckScrollBars

スクロール ビューが水平方向および垂直のバーを確認するのには、このメンバー関数を呼び出します。

```
void CheckScrollBars(
    BOOL& bHasHorzBar,
    BOOL& bHasVertBar) const;
```

### <a name="parameters"></a>パラメーター

*bHasHorzBar*<br/>
アプリケーションを水平スクロール バーを持つことを示します。

*bHasVertBar*<br/>
アプリケーションが垂直スクロール バーを示します。

##  <a name="cscrollview"></a>  CScrollView::CScrollView

`CScrollView` オブジェクトを構築します。

```
CScrollView();
```

### <a name="remarks"></a>Remarks

いずれかを呼び出す必要があります`SetScrollSizes`または`SetScaleToFitSize`スクロールする前にビューが使用されます。

##  <a name="filloutsiderect"></a>  CScrollView::FillOutsideRect

呼び出す`FillOutsideRect`スクロール領域の外側に表示されるビューの領域を塗りつぶします。

```
void FillOutsideRect(
    CDC* pDC,
    CBrush* pBrush);
```

### <a name="parameters"></a>パラメーター

*pDC*<br/>
デバイス コンテキストがいっぱいになるが実行するのです。

*pBrush*<br/>
られている領域を格納するブラシ。

### <a name="remarks"></a>Remarks

使用`FillOutsideRect`、スクロール ビューの`OnEraseBkgnd`ハンドラー関数に過剰なバック グラウンドで再描画しないようにします。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocView#164](../../mfc/codesnippet/cpp/cscrollview-class_1.cpp)]

##  <a name="getdevicescrollposition"></a>  CScrollView::GetDeviceScrollPosition

呼び出す`GetDeviceScrollPosition`水平および垂直の現在の位置のスクロール ボックス、スクロール バーの必要があります。

```
CPoint GetDeviceScrollPosition() const;
```

### <a name="return-value"></a>戻り値

スクロール ボックスとしての (デバイス単位で) 水平および垂直位置を`CPoint`オブジェクト。

### <a name="remarks"></a>Remarks

この座標ペアは、ビューの左上隅のスクロール先のドキュメント内の場所に対応します。 これは、スクロール ビューのデバイスの位置をマウス デバイスの位置をオフセットするのに便利です。

`GetDeviceScrollPosition` デバイス単位で値を返します。 論理ユニットを実行する場合に、使用`GetScrollPosition`代わりにします。

##  <a name="getdevicescrollsizes"></a>  CScrollView::GetDeviceScrollSizes

`GetDeviceScrollSizes` 現在のマップ モード、合計のサイズおよびスクロール可能なビューの行とページのサイズを取得します。

```
void GetDeviceScrollSizes(
    int& nMapMode,
    SIZE& sizeTotal,
    SIZE& sizePage,
    SIZE& sizeLine) const;
```

### <a name="parameters"></a>パラメーター

*nMapMode*<br/>
このビューの現在のマッピング モードを返します。 使用可能な値の一覧は、次を参照してください。`SetScrollSizes`します。

*sizeTotal*<br/>
デバイス単位でスクロール ビューの現在の合計サイズを返します。

*サイズページ*<br/>
スクロール バーの軸でクリックしてマウスへの応答には、各方向にスクロールする現在の水平および垂直方向の量を返します。 `cx`メンバーには、水平方向の量が含まれています。 `cy`メンバーには、垂直方向の量が含まれています。

*sizeLine*<br/>
マウスへの応答には、各方向にスクロールする現在の水平および垂直の量は、スクロール バーの矢印のクリックを返します。 `cx`メンバーには、水平方向の量が含まれています。 `cy`メンバーには、垂直方向の量が含まれています。

### <a name="remarks"></a>Remarks

サイズでは、デバイス単位です。 このメンバー関数と呼ばれることはほとんどありません。

##  <a name="getscrollposition"></a>  CScrollView::GetScrollPosition

呼び出す`GetScrollPosition`水平および垂直の現在の位置のスクロール ボックス、スクロール バーの必要があります。

```
CPoint GetScrollPosition() const;
```

### <a name="return-value"></a>戻り値

スクロール ボックスとしての (論理単位) で水平および垂直位置を`CPoint`オブジェクト。

### <a name="remarks"></a>Remarks

この座標ペアは、ビューの左上隅のスクロール先のドキュメント内の場所に対応します。

`GetScrollPosition` 論理ユニットの値を返します。 デバイス単位にする場合は、使用`GetDeviceScrollPosition`代わりにします。

##  <a name="gettotalsize"></a>  CScrollView::GetTotalSize

呼び出す`GetTotalSize`スクロール ビューの現在の水平および垂直方向のサイズを取得します。

```
CSize GetTotalSize() const;
```

### <a name="return-value"></a>戻り値

論理ユニットで、スクロール ビューの合計サイズ。 は、水平方向のサイズ、`cx`のメンバー、`CSize`値を返します。 垂直方向のサイズは、`cy`メンバー。

##  <a name="resizeparenttofit"></a>  CScrollView::ResizeParentToFit

呼び出す`ResizeParentToFit`そのフレーム ウィンドウのサイズに合う、ビューのサイズをできるようにします。

```
void ResizeParentToFit(BOOL bShrinkOnly = TRUE);
```

### <a name="parameters"></a>パラメーター

*bShrinkOnly*<br/>
実行するサイズ変更の種類。 True の場合、既定値は、該当する場合、フレーム ウィンドウを縮小します。 ビューが大きいまたは小さいフレーム ウィンドウのスクロール バーが表示されます。 値 FALSE の場合、正確にフレーム ウィンドウのサイズを変更するには、常に表示します。 これは、フレーム ウィンドウが大きすぎてマルチ ドキュメント インターフェイス (MDI) のフレーム ウィンドウまたは画面内に収まるように取得でしたので少し危険です。

### <a name="remarks"></a>Remarks

これは、MDI 子フレーム ウィンドウのビューに対してのみ推奨されます。 使用`ResizeParentToFit`で、`OnInitialUpdate`ハンドラー関数、派生の`CScrollView`クラス。 このメンバー関数の例は、次を参照してください。 [CScrollView::SetScrollSizes](#setscrollsizes)します。

`ResizeParentToFit` [ビュー] ウィンドウのサイズが設定されていることを想定しています。 かどうか、ビュー ウィンドウのサイズが設定されていない場合に`ResizeParentToFit`が呼び出されると、アサーションが取得されます。 そうでないことを確認するには、呼び出す前に次の呼び出しを行う`ResizeParentToFit`:

[!code-cpp[NVC_MFCDocView#165](../../mfc/codesnippet/cpp/cscrollview-class_2.cpp)]

##  <a name="scrolltoposition"></a>  CScrollView::ScrollToPosition

呼び出す`ScrollToPosition`ビューの特定の時点までスクロールします。

```
void ScrollToPosition(POINT pt);
```

### <a name="parameters"></a>パラメーター

*pt*<br/>
論理ユニットでのスクロールをポイントします。 `x`メンバーは、正の値を使用している (より大きいまたは 0 で、ビューの合計サイズの最大) を指定する必要があります。 場合も同様、`y`マッピング モードが MM_TEXT メンバー。 `y`メンバーがマップ モードで負の値。

### <a name="remarks"></a>Remarks

このポイントがウィンドウの左上隅にあるように、ビューにスクロールされます。 ビューのサイズに合わせてスケールする場合、このメンバー関数は呼び出されませんする必要があります。

##  <a name="setscaletofitsize"></a>  CScrollView::SetScaleToFitSize

呼び出す`SetScaleToFitSize`ビューポートのサイズを現在のウィンドウ サイズを自動的にスケールしたい場合。

```
void SetScaleToFitSize(SIZE sizeTotal);
```

### <a name="parameters"></a>パラメーター

*sizeTotal*<br/>
ビューがスケールを水平および垂直方向サイズ。 スクロール ビューのサイズは、論理単位で測定されます。 水平方向のサイズが含まれている、`cx`メンバー。 垂直方向のサイズが含まれている、`cy`メンバー。 両方`cx`と`cy`0 以上にする必要があります。

### <a name="remarks"></a>Remarks

スクロール バーを持つ論理ビューの一部だけ表示あります、いつでも。 サイズに合わせて-スケール機能により、ビューにスクロール バーがないと論理的なビューを拡大または縮小に合わせてウィンドウのクライアント領域。 ウィンドウのサイズは、ビューは、ウィンドウのサイズに基づく新しいスケールにそのデータを描画します。

通常の呼び出しを配置する`SetScaleToFitSize`のビューのオーバーライドで`OnInitialUpdate`メンバー関数。 自動スケールしたくない場合、`SetScrollSizes`メンバー関数を使用します。

`SetScaleToFitSize` 「拡大に合わせて」操作を実装するために使用できます。 使用`SetScrollSizes`スクロールを再初期化します。

`SetScaleToFitSize` [ビュー] ウィンドウのサイズが設定されていることを想定しています。 かどうか、ビュー ウィンドウのサイズが設定されていない場合に`SetScaleToFitSize`が呼び出されると、アサーションが取得されます。 そうでないことを確認するには、呼び出す前に次の呼び出しを行う`SetScaleToFitSize`:

[!code-cpp[NVC_MFCDocView#165](../../mfc/codesnippet/cpp/cscrollview-class_2.cpp)]

##  <a name="setscrollsizes"></a>  CScrollView::SetScrollSizes

呼び出す`SetScrollSizes`ときに、ビューが更新しようとしています。

```
void SetScrollSizes(
    int nMapMode,
    SIZE sizeTotal,
    const SIZE& sizePage = sizeDefault,
    const SIZE& sizeLine = sizeDefault);
```

### <a name="parameters"></a>パラメーター

*nMapMode*<br/>
このビューを設定するマッピング モード。 次の値を使用できます。

|マップ モード|論理ユニット|Y 軸の正の拡張しています.|
|------------------|------------------|---------------------------------|
|MM_TEXT|1 ピクセル|下方向|
|MM_HIMETRIC|0.01 mm|上方向|
|MM_TWIPS|1/1440 で|上方向|
|MM_HIENGLISH|0.001 インチ|上方向|
|MM_LOMETRIC|0.1 mm|上方向|
|MM_LOENGLISH|0.01 インチ|上方向|

すべてのこれらのモードは、Windows によって定義されます。 MM_ISOTROPIC と MM_ANISOTROPIC、2 つの標準のマッピング モードは使用されません`CScrollView`します。 クラス ライブラリには、`SetScaleToFitSize`枠のサイズに拡大または縮小のメンバー関数。 上記の表に 3 番目の列には、座標の方向がについて説明します。

*sizeTotal*<br/>
スクロール ビューの合計サイズ。 `cx`メンバーには、水平方向のエクステントが含まれています。 `cy`メンバーには、垂直方向のエクステントが含まれています。 サイズでは、論理単位です。 両方`cx`と`cy`0 以上にする必要があります。

*サイズページ*<br/>
マウスへの応答には、各方向にスクロールする水平および垂直の量は、スクロール バーの軸をクリックします。 `cx`メンバーには、水平方向の量が含まれています。 `cy`メンバーには、垂直方向の量が含まれています。

*sizeLine*<br/>
マウスへの応答には、各方向にスクロールする水平および垂直の量は、スクロール バーの矢印をクリックします。 `cx`メンバーには、水平方向の量が含まれています。 `cy`メンバーには、垂直方向の量が含まれています。

### <a name="remarks"></a>Remarks

オーバーライドで呼び出す、`OnUpdate`メンバー関数は、ドキュメントが最初に表示されるなどのとき、またはサイズを変更するときは、スクロールの特性を調整します。

おそらくと呼ばれる、ドキュメントのメンバー関数を呼び出すことによって、ビューの関連付けられているドキュメントからサイズ情報を取得するが通常`GetMyDocSize`、派生したドキュメント クラスを使用して、提供します。 次のコードは、この方法を示しています。

[!code-cpp[NVC_MFCDocView#166](../../mfc/codesnippet/cpp/cscrollview-class_3.cpp)]

または、次のコードのように、固定サイズを設定する必要がある場合があります。

[!code-cpp[NVC_MFCDocView#167](../../mfc/codesnippet/cpp/cscrollview-class_4.cpp)]

マッピング モードは、MM_ISOTROPIC または MM_ANISOTROPIC を除く、Windows のマッピング モードのいずれかに設定する必要があります。 制約のないマッピング モードを使用する場合は、呼び出し、`SetScaleToFitSize`メンバー関数の代わりに`SetScrollSizes`します。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocView#168](../../mfc/codesnippet/cpp/cscrollview-class_5.cpp)]

[!code-cpp[NVC_MFCDocView#169](../../mfc/codesnippet/cpp/cscrollview-class_6.cpp)]

## <a name="see-also"></a>関連項目

[MFC サンプル DIBLOOK](../../visual-cpp-samples.md)<br/>
[CView クラス](../../mfc/reference/cview-class.md)<br/>
[階層図](../../mfc/hierarchy-chart.md)<br/>
[CView クラス](../../mfc/reference/cview-class.md)<br/>
[CSplitterWnd クラス](../../mfc/reference/csplitterwnd-class.md)

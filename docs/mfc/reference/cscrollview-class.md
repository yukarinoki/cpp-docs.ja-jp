---
description: '詳細情報: CScrollView クラス'
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
ms.openlocfilehash: 76045f640cf74b650fbbf48dead7ee44c57fbd87
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97342905"
---
# <a name="cscrollview-class"></a>CScrollView クラス

スクロール機能を持つ [CView](../../mfc/reference/cview-class.md) 。

## <a name="syntax"></a>構文

```
class CScrollView : public CView
```

## <a name="members"></a>メンバー

### <a name="protected-constructors"></a>プロテクト コンストラクター

|名前|説明|
|----------|-----------------|
|[CScrollView:: CScrollView](#cscrollview)|`CScrollView` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CScrollView:: CheckScrollBars](#checkscrollbars)|スクロールビューに水平スクロールバーと垂直スクロールバーがあるかどうかを示します。|
|[CScrollView:: FillOutsideRect](#filloutsiderect)|ビューの領域をスクロール領域の外側に塗りつぶします。|
|[CScrollView:: GetDeviceScrollPosition](#getdevicescrollposition)|デバイスユニット内の現在のスクロール位置を取得します。|
|[CScrollView:: GetDeviceScrollSizes](#getdevicescrollsizes)|スクロール可能なビューの現在のマッピングモード、合計サイズ、および行とページのサイズを取得します。 サイズはデバイス単位です。|
|[CScrollView:: GetScrollPosition](#getscrollposition)|現在のスクロール位置を論理単位で取得します。|
|[CScrollView:: GetTotalSize](#gettotalsize)|スクロールビューの論理単位の合計サイズを取得します。|
|[CScrollView:: ResizeParentToFit](#resizeparenttofit)|ビューのサイズによって、フレームのサイズが決まります。|
|[CScrollView:: ScrollToPosition](#scrolltoposition)|ビューを論理単位で指定された特定のポイントまでスクロールします。|
|[CScrollView:: SetScaleToFitSize](#setscaletofitsize)|スクロールビューをスケールインフィットモードにします。|
|[CScrollView:: SetScrollSizes](#setscrollsizes)|スクロールビューのマッピングモード、合計サイズ、および水平および垂直方向のスクロールの量を設定します。|

## <a name="remarks"></a>解説

から派生した任意のクラスで標準スクロールを処理でき `CView` ます。そのためには、メッセージマップされた [OnHScroll](../../mfc/reference/cwnd-class.md#onhscroll) および [onvscroll](../../mfc/reference/cwnd-class.md#onvscroll) メンバー関数をオーバーライドします。 ただし、 `CScrollView` 機能には次の機能が追加されてい `CView` ます。

- ウィンドウおよびビューポートのサイズとマッピングモードを管理します。

- スクロールバーのメッセージに応じて自動的にスクロールします。

- キーボード、スクロール不可のマウス、または IntelliMouse ホイールからのメッセージに応じて自動的にスクロールされます。

キーボードからのメッセージに応答して自動的にスクロールするには、WM_KEYDOWN メッセージを追加し、VK_DOWN をテストして、VK_PREV [SetScrollPos](/windows/win32/api/winuser/nf-winuser-setscrollpos)を呼び出します。

[OnMouseWheel](../../mfc/reference/cwnd-class.md#onmousewheel)および[OnRegisteredMouseWheel](../../mfc/reference/cwnd-class.md#onregisteredmousewheel)の各メンバー関数をオーバーライドすることにより、マウスホイールのスクロールを自分で処理できます。 これらのメンバー関数は、の場合と同様に、 `CScrollView` ホイール回転メッセージの [WM_MOUSEWHEEL](/windows/win32/inputdev/wm-mousewheel)に対して推奨される動作をサポートします。

自動スクロールを利用するには、からではなく、からビュークラスを派生させ `CScrollView` `CView` ます。 ビューを最初に作成するときに、ドキュメントのサイズに基づいてスクロール可能なビューのサイズを計算する場合は、 `SetScrollSizes` [cview:: OnInitialUpdate](../../mfc/reference/cview-class.md#oninitialupdate) または [cview:: OnUpdate](../../mfc/reference/cview-class.md#onupdate)のいずれかのオーバーライドからメンバー関数を呼び出します。 (ドキュメントのサイズに対してクエリを実行するには、独自のコードを記述する必要があります。 例については、 [Scribble サンプル](../../overview/visual-cpp-samples.md)を参照してください)。

このメンバー関数を呼び出すと、 `SetScrollSizes` ビューのマッピングモード、スクロールビューの合計サイズ、水平および垂直方向にスクロールする量が設定されます。 すべてのサイズは論理単位になります。 ビューの論理サイズは、通常、ドキュメントに格納されているデータから計算されますが、場合によっては、固定サイズを指定する必要があります。 両方の方法の例については、「 [CScrollView:: SetScrollSizes](#setscrollsizes)」を参照してください。

論理単位で水平方向および垂直方向にスクロールする量を指定します。 既定では、スクロールボックスの外側でスクロールバーのシャフトをクリックすると、 `CScrollView` "ページ" がスクロールされます。 スクロールバーのいずれかの端のスクロールバーの矢印ボタンをクリックすると、 `CScrollView` "線" がスクロールされます。 既定では、ページはビューの合計サイズの1/10 です。行はページサイズの1/10 です。 メンバー関数でカスタムサイズを渡すことによって、これらの既定値をオーバーライドし `SetScrollSizes` ます。 たとえば、水平方向のサイズを、合計サイズの幅の一部に設定し、垂直方向のサイズを現在のフォントの行の高さに設定できます。

スクロールではなく、では、 `CScrollView` 現在のウィンドウサイズに合わせてビューを自動的に拡大縮小できます。 このモードでは、ビューにスクロールバーは表示されず、ウィンドウのクライアント領域にぴったり合うように論理ビューが拡大または縮小されます。 このスケールインフィット機能を使用するには、 [CScrollView:: SetScaleToFitSize](#setscaletofitsize)を呼び出します。 ( `SetScaleToFitSize` またはのいずれか `SetScrollSizes` を呼び出しますが、両方は呼び出さないでください)。

`OnDraw`派生ビュークラスのメンバー関数が呼び出される前に、によっ `CScrollView` `CPaintDC` て渡されるデバイスコンテキストオブジェクトのビューポートの原点が自動的に調整され `OnDraw` ます。

スクロールウィンドウのビューポートの原点を調整するには、は `CScrollView` [CView:: OnPrepareDC](../../mfc/reference/cview-class.md#onpreparedc)をオーバーライドします。 この調整は、に渡されるデバイスコンテキストに対して自動的に行うことができますが、など、 `CPaintDC` `CScrollView` `OnDraw` `CScrollView::OnPrepareDC` 使用するその他のデバイスコンテキストに対しては、を呼び出す必要があり `CClientDC` ます。 をオーバーライドすると、 `CScrollView::OnPrepareDC` ペン、背景色、およびその他の描画属性を設定できますが、基本クラスを呼び出してスケーリングを行うことができます。

スクロールバーは、次の場合に示すように、ビューに対して相対的に3か所に表示されます。

- 標準のウィンドウスタイルのスクロールバーは、WS_HSCROLL および WS_VSCROLL[Windows スタイル](../../mfc/reference/styles-used-by-mfc.md#window-styles)を使用して、ビューに対して設定できます。

- また、スクロールバーコントロールをビューが含まれているフレームに追加することもできます。この場合、フレームワークは、フレームウィンドウから現在アクティブなビューに WM_HSCROLL および WM_VSCROLL メッセージを転送します。

- また、フレームワークは、 `CSplitterWnd` スプリッターコントロールから現在アクティブなスプリッターペイン (ビュー) にスクロールメッセージを転送します。 共有されたスクロールバーを使用して [CSplitterWnd](../../mfc/reference/csplitterwnd-class.md) に配置すると、オブジェクトは独自のを `CScrollView` 作成するのではなく、共有されたものを使用します。

の使用方法の詳細につい `CScrollView` ては、「 [MFC で使用できる](../../mfc/derived-view-classes-available-in-mfc.md)[ドキュメント/ビューアーキテクチャ](../../mfc/document-view-architecture.md)および派生ビュークラス」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CView](../../mfc/reference/cview-class.md)

`CScrollView`

## <a name="requirements"></a>要件

**ヘッダー:** afxwin.h

## <a name="cscrollviewcheckscrollbars"></a><a name="checkscrollbars"></a> CScrollView:: CheckScrollBars

スクロールビューに水平と垂直のバーがあるかどうかを判断するには、このメンバー関数を呼び出します。

```cpp
void CheckScrollBars(
    BOOL& bHasHorzBar,
    BOOL& bHasVertBar) const;
```

### <a name="parameters"></a>パラメーター

*bHasHorzBar*<br/>
アプリケーションに水平スクロールバーがあることを示します。

*bHasVertBar*<br/>
アプリケーションに垂直スクロールバーがあることを示します。

## <a name="cscrollviewcscrollview"></a><a name="cscrollview"></a> CScrollView:: CScrollView

`CScrollView` オブジェクトを構築します。

```
CScrollView();
```

### <a name="remarks"></a>解説

`SetScrollSizes`スクロールビューが使用できるようにするには、またはのいずれかを呼び出す必要があり `SetScaleToFitSize` ます。

## <a name="cscrollviewfilloutsiderect"></a><a name="filloutsiderect"></a> CScrollView:: FillOutsideRect

を呼び出して、 `FillOutsideRect` スクロール領域の外側に表示されるビューの領域を塗りつぶします。

```cpp
void FillOutsideRect(
    CDC* pDC,
    CBrush* pBrush);
```

### <a name="parameters"></a>パラメーター

*pDC*<br/>
塗りつぶしを行うデバイスコンテキスト。

*pBrush*<br/>
領域の塗りつぶしに使用するブラシ。

### <a name="remarks"></a>解説

`FillOutsideRect`バックグラウンドで過度に再描画されるのを防ぐために、スクロールビューのハンドラー関数でを使用し `OnEraseBkgnd` ます。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocView#164](../../mfc/codesnippet/cpp/cscrollview-class_1.cpp)]

## <a name="cscrollviewgetdevicescrollposition"></a><a name="getdevicescrollposition"></a> CScrollView:: GetDeviceScrollPosition

`GetDeviceScrollPosition`スクロールバーのスクロールボックスの現在の水平方向および垂直位置が必要な場合に、を呼び出します。

```
CPoint GetDeviceScrollPosition() const;
```

### <a name="return-value"></a>戻り値

オブジェクトとしてのスクロールボックスの水平方向および垂直方向の位置 (デバイス単位) `CPoint` 。

### <a name="remarks"></a>解説

この座標ペアは、ビューの左上隅がスクロールされたドキュメント内の位置に対応します。 これは、マウスデバイスの位置をスクロールビューのデバイスの位置にずらす場合に便利です。

`GetDeviceScrollPosition` デバイス単位で値を返します。 論理ユニットが必要な場合は、代わりにを使用 `GetScrollPosition` します。

## <a name="cscrollviewgetdevicescrollsizes"></a><a name="getdevicescrollsizes"></a> CScrollView:: GetDeviceScrollSizes

`GetDeviceScrollSizes` スクロール可能なビューの現在のマッピングモード、合計サイズ、および行とページのサイズを取得します。

```cpp
void GetDeviceScrollSizes(
    int& nMapMode,
    SIZE& sizeTotal,
    SIZE& sizePage,
    SIZE& sizeLine) const;
```

### <a name="parameters"></a>パラメーター

*nMapMode*<br/>
このビューの現在のマッピングモードを返します。 有効な値の一覧については、「`SetScrollSizes`」を参照してください。

*sizeTotal*<br/>
デバイス単位でのスクロールビューの現在の合計サイズを返します。

*sizePage*<br/>
スクロールバーのシャフトでのマウスクリックに応じて、各方向にスクロールする現在の水平および垂直の量を返します。 この `cx` メンバーには、水平方向の金額が含まれています。 この `cy` メンバーには、垂直方向の金額が含まれています。

*siz*<br/>
スクロールボタンのマウスクリックに応じて、各方向にスクロールする現在の水平および垂直の量を返します。 この `cx` メンバーには、水平方向の金額が含まれています。 この `cy` メンバーには、垂直方向の金額が含まれています。

### <a name="remarks"></a>解説

サイズはデバイス単位です。 このメンバー関数は、と呼ばれることはほとんどありません。

## <a name="cscrollviewgetscrollposition"></a><a name="getscrollposition"></a> CScrollView:: GetScrollPosition

`GetScrollPosition`スクロールバーのスクロールボックスの現在の水平方向および垂直位置が必要な場合に、を呼び出します。

```
CPoint GetScrollPosition() const;
```

### <a name="return-value"></a>戻り値

オブジェクトとしてのスクロールボックスの水平方向と垂直位置 (論理単位) `CPoint` 。

### <a name="remarks"></a>解説

この座標ペアは、ビューの左上隅がスクロールされたドキュメント内の位置に対応します。

`GetScrollPosition` 論理単位で値を返します。 デバイスユニットが必要な場合は、代わりにを使用 `GetDeviceScrollPosition` します。

## <a name="cscrollviewgettotalsize"></a><a name="gettotalsize"></a> CScrollView:: GetTotalSize

を呼び出して、 `GetTotalSize` スクロールビューの現在の水平方向と垂直方向のサイズを取得します。

```
CSize GetTotalSize() const;
```

### <a name="return-value"></a>戻り値

スクロールビューの論理単位の合計サイズ。 水平方向のサイズは、 `cx` 戻り値のメンバーに含まれてい `CSize` ます。 垂直方向のサイズは、メンバーに含まれてい `cy` ます。

## <a name="cscrollviewresizeparenttofit"></a><a name="resizeparenttofit"></a> CScrollView:: ResizeParentToFit

`ResizeParentToFit`を呼び出して、ビューのサイズによってフレームウィンドウのサイズを決定します。

```cpp
void ResizeParentToFit(BOOL bShrinkOnly = TRUE);
```

### <a name="parameters"></a>パラメーター

*bShrinkOnly*<br/>
実行するサイズ変更の種類。 既定値は TRUE で、必要に応じてフレームウィンドウが縮小されます。 大きいビューや小さいフレームウィンドウでは、スクロールバーが表示されます。 FALSE の値を指定すると、ビューは常にフレームウィンドウのサイズを正確に変更します。 フレームウィンドウが大きすぎてマルチドキュメントインターフェイス (MDI) フレームウィンドウまたは画面に収まりきらない可能性があるため、これは多少危険になることがあります。

### <a name="remarks"></a>解説

これは、MDI 子フレームウィンドウのビューに対してのみ推奨されます。 `ResizeParentToFit` `OnInitialUpdate` 派生クラスのハンドラー関数でを使用し `CScrollView` ます。 このメンバー関数の例については、「 [CScrollView:: SetScrollSizes](#setscrollsizes)」を参照してください。

`ResizeParentToFit` ビューウィンドウのサイズが設定されていることを前提としています。 が呼び出されたときにビューウィンドウのサイズが設定されていない場合は `ResizeParentToFit` 、アサーションが発生します。 これが行われないようにするには、を呼び出す前に、次の呼び出しを行い `ResizeParentToFit` ます。

[!code-cpp[NVC_MFCDocView#165](../../mfc/codesnippet/cpp/cscrollview-class_2.cpp)]

## <a name="cscrollviewscrolltoposition"></a><a name="scrolltoposition"></a> CScrollView:: ScrollToPosition

`ScrollToPosition`を呼び出して、ビュー内の特定のポイントまでスクロールします。

```cpp
void ScrollToPosition(POINT pt);
```

### <a name="parameters"></a>パラメーター

*pt*<br/>
論理単位でスクロールするポイント。 メンバーは、 `x` 正の値 (0 以上、ビューの合計サイズまで) である必要があります。 マッピングモードが MM_TEXT 場合も、メンバーに対して同じことが当てはまり `y` ます。 `y`MM_TEXT 以外のマッピングモードでは、メンバーは負の値です。

### <a name="remarks"></a>解説

このポイントがウィンドウの左上隅になるように、ビューがスクロールされます。 ビューが合わせて拡大縮小されている場合は、このメンバー関数を呼び出さないでください。

## <a name="cscrollviewsetscaletofitsize"></a><a name="setscaletofitsize"></a> CScrollView:: SetScaleToFitSize

`SetScaleToFitSize`ビューポートのサイズを現在のウィンドウサイズに自動的にスケーリングする場合は、を呼び出します。

```cpp
void SetScaleToFitSize(SIZE sizeTotal);
```

### <a name="parameters"></a>パラメーター

*sizeTotal*<br/>
ビューをスケーリングする水平方向および垂直方向のサイズ。 スクロールビューのサイズは、論理単位で測定されます。 水平方向のサイズは、メンバーに含まれてい `cx` ます。 垂直方向のサイズは、メンバーに含まれてい `cy` ます。 とはどちらも `cx` `cy` 0 以上である必要があります。

### <a name="remarks"></a>解説

スクロールバーでは、論理ビューの一部だけがいつでも表示される場合があります。 ただし、スケールツーフィット機能を使用すると、ビューにはスクロールバーがなく、ウィンドウのクライアント領域に合わせて論理ビューが拡大または縮小されます。 ウィンドウのサイズを変更すると、ウィンドウのサイズに基づいて新しいスケールでデータが描画されます。

通常、 `SetScaleToFitSize` ビューのメンバー関数のオーバーライドでは、への呼び出しを配置し `OnInitialUpdate` ます。 自動スケーリングを使用しない場合は、 `SetScrollSizes` 代わりにメンバー関数を呼び出します。

`SetScaleToFitSize` "最適なサイズに拡大" 操作を実装するために使用できます。 `SetScrollSizes`スクロールを再初期化するために使用します。

`SetScaleToFitSize` ビューウィンドウのサイズが設定されていることを前提としています。 が呼び出されたときにビューウィンドウのサイズが設定されていない場合は `SetScaleToFitSize` 、アサーションが発生します。 これが行われないようにするには、を呼び出す前に、次の呼び出しを行い `SetScaleToFitSize` ます。

[!code-cpp[NVC_MFCDocView#165](../../mfc/codesnippet/cpp/cscrollview-class_2.cpp)]

## <a name="cscrollviewsetscrollsizes"></a><a name="setscrollsizes"></a> CScrollView:: SetScrollSizes

`SetScrollSizes`ビューを更新しようとしているときに、を呼び出します。

```cpp
void SetScrollSizes(
    int nMapMode,
    SIZE sizeTotal,
    const SIZE& sizePage = sizeDefault,
    const SIZE& sizeLine = sizeDefault);
```

### <a name="parameters"></a>パラメーター

*nMapMode*<br/>
このビューに設定するマッピングモード。 次の値を指定できます。

|マッピングモード|論理ユニット|正の y 軸の拡張...|
|------------------|------------------|---------------------------------|
|MM_TEXT|1 ピクセル|下向き|
|MM_HIMETRIC|0.01 mm|上向き|
|MM_TWIPS|1/1440|上向き|
|MM_HIENGLISH|0.001|上向き|
|MM_LOMETRIC|0.1 mm|上向き|
|MM_LOENGLISH|0.01|上向き|

これらのモードはすべて、Windows で定義されています。 MM_ISOTROPIC と MM_ANISOTROPIC の2つの標準マッピングモードは、では使用されません `CScrollView` 。 クラスライブラリには、 `SetScaleToFitSize` ビューをウィンドウサイズにスケーリングするためのメンバー関数が用意されています。 上の表の3列目は、座標の向きを示しています。

*sizeTotal*<br/>
スクロールビューの合計サイズ。 メンバーには `cx` 、水平方向のエクステントが含まれます。 この `cy` メンバーには、垂直方向のエクステントが含まれます。 サイズは論理単位です。 とはどちらも `cx` `cy` 0 以上である必要があります。

*sizePage*<br/>
スクロールバーのシャフトでのマウスクリックに応じて、各方向にスクロールする水平および垂直の量。 この `cx` メンバーには、水平方向の金額が含まれています。 この `cy` メンバーには、垂直方向の金額が含まれています。

*siz*<br/>
スクロールバーの矢印の中でマウスクリックに応答して、各方向にスクロールする水平および垂直の量。 この `cx` メンバーには、水平方向の金額が含まれています。 この `cy` メンバーには、垂直方向の金額が含まれています。

### <a name="remarks"></a>解説

`OnUpdate`たとえば、ドキュメントが最初に表示されたときや、サイズが変更されたときに、スクロールの特性を調整するために、メンバー関数のオーバーライドで呼び出します。

通常、派生した `GetMyDocSize` ドキュメントクラスで提供するドキュメントメンバー関数 (など) を呼び出すことによって、ビューに関連付けられたドキュメントからサイズ情報を取得します。 次のコードは、この方法を示しています。

[!code-cpp[NVC_MFCDocView#166](../../mfc/codesnippet/cpp/cscrollview-class_3.cpp)]

また、次のコードのように、固定サイズの設定が必要になる場合もあります。

[!code-cpp[NVC_MFCDocView#167](../../mfc/codesnippet/cpp/cscrollview-class_4.cpp)]

マッピングモードは、MM_ISOTROPIC または MM_ANISOTROPIC を除くすべての Windows マッピングモードに設定する必要があります。 制約のないマッピングモードを使用する場合は、では `SetScaleToFitSize` なくメンバー関数を呼び出し `SetScrollSizes` ます。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocView#168](../../mfc/codesnippet/cpp/cscrollview-class_5.cpp)]

[!code-cpp[NVC_MFCDocView#169](../../mfc/codesnippet/cpp/cscrollview-class_6.cpp)]

## <a name="see-also"></a>関連項目

[MFC のサンプル DIBLOOK](../../overview/visual-cpp-samples.md)<br/>
[CView クラス](../../mfc/reference/cview-class.md)<br/>
[階層図](../../mfc/hierarchy-chart.md)<br/>
[CView クラス](../../mfc/reference/cview-class.md)<br/>
[CSplitterWnd クラス](../../mfc/reference/csplitterwnd-class.md)

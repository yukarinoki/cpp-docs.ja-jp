---
title: CScrollView クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
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
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 82ffdb26c5766a0ff7cbada511c9bc9c82ebfd93
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33375543"
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
|[CScrollView::CheckScrollBars](#checkscrollbars)|スクロール ビューが水平方向および垂直のスクロール バーを持つかどうかを示します。|  
|[CScrollView::FillOutsideRect](#filloutsiderect)|スクロール領域の外側のビューの領域を塗りつぶします。|  
|[CScrollView::GetDeviceScrollPosition](#getdevicescrollposition)|デバイス単位の現在のスクロール位置を取得します。|  
|[CScrollView::GetDeviceScrollSizes](#getdevicescrollsizes)|現在のマップ モード、合計サイズは、スクロール可能なビューの行とページのサイズを取得します。 デバイス単位のサイズです。|  
|[CScrollView::GetScrollPosition](#getscrollposition)|論理ユニットでは、現在のスクロール位置を取得します。|  
|[CScrollView::GetTotalSize](#gettotalsize)|論理ユニットでスクロール ビューの合計サイズを取得します。|  
|[CScrollView::ResizeParentToFit](#resizeparenttofit)|フレームのサイズに合うようにビューのサイズが発生します。|  
|[CScrollView::ScrollToPosition](#scrolltoposition)|論理単位で指定された位置にビューをスクロールします。|  
|[CScrollView::SetScaleToFitSize](#setscaletofitsize)|スクロール ビューを実行すると、スケールの調整モードにします。|  
|[CScrollView::SetScrollSizes](#setscrollsizes)|スクロール ビューのマッピング モード、合計サイズは、および水平方向および垂直のスクロール量を設定します。|  
  
## <a name="remarks"></a>コメント  
 Standard から派生したクラスで自分のスクロールを処理できる`CView`メッセージ マップをオーバーライドすることで[OnHScroll](../../mfc/reference/cwnd-class.md#onhscroll)と[OnVScroll](../../mfc/reference/cwnd-class.md#onvscroll)メンバー関数。 `CScrollView`には、次の機能を追加、`CView`機能。  
  
-   ウィンドウとビューポートのサイズとのマッピング モードを管理します。  
  
-   スクロール バーのメッセージに応答して自動的にスクロールします。  
  
-   キーボード、非スクロールのマウス、または IntelliMouse ホイールからのメッセージに応答して自動的にスクロールします。  
  
 メッセージに応答をキーボードから自動的にスクロールするに WM_KEYDOWN メッセージを追加し、VK_DOWN、VK_PREV と呼び出しをテスト[SetScrollPos](http://msdn.microsoft.com/library/windows/desktop/bb787597)です。  
  
 マウス ホイールを自分でメッセージ マップをオーバーライドしてスクロールを処理できる[OnMouseWheel](../../mfc/reference/cwnd-class.md#onmousewheel)と[OnRegisteredMouseWheel](../../mfc/reference/cwnd-class.md#onregisteredmousewheel)メンバー関数。 場合と`CScrollView`、これらのメンバー関数の推奨される動作をサポートする[WM_MOUSEWHEEL](http://msdn.microsoft.com/library/windows/desktop/ms645617)ホイールを回転メッセージ。  
  
 自動スクロールを利用するからビュー クラスを派生`CScrollView`の代わりにから`CView`です。 ビューが初めて作成すると、呼び出し、ドキュメントのサイズに基づいて、スクロール可能なビューのサイズを計算する場合、`SetScrollSizes`メンバー関数のいずれかのオーバーライドから[:oninitialupdate](../../mfc/reference/cview-class.md#oninitialupdate)または[CView::OnUpdate](../../mfc/reference/cview-class.md#onupdate)です。 (ドキュメントのサイズを照会するコードを記述する必要があります。 例については、次を参照してください、 [Scribble サンプル](../../visual-cpp-samples.md)。)。  
  
 呼び出し、`SetScrollSizes`メンバー関数は、ビューのマッピング モードでは、スクロール ビューと横方向および垂直方向にスクロール金額の合計サイズを設定します。 すべてのサイズは、論理ユニットでです。 ビューの論理サイズが、ドキュメントに格納されたデータから計算された通常が、場合によっては固定サイズを指定することがあります。 両方のアプローチの例については、次を参照してください。 [CScrollView::SetScrollSizes](#setscrollsizes)です。  
  
 論理ユニットに水平方向および垂直方向をスクロールする量を指定します。 既定では、ユーザーが、スクロール バーの軸スクロール ボックスの外側をクリックすると`CScrollView`「ページ」をスクロール ユーザーがスクロール バーの端にあるスクロール矢印をクリックすると`CScrollView`「行」をスクロール 既定では、ページは、ビューの合計サイズの 1/10 です。線は、1/10 ページ サイズです。 カスタム サイズを渡すことによってこれらの既定値を上書き、`SetScrollSizes`メンバー関数。 たとえば、現在のフォントで合計サイズと、行の高さを垂直方向のサイズの幅を一定の割合を水平方向のサイズを設定する可能性があります。  
  
 スクロールではなく`CScrollView`ビューを現在のウィンドウ サイズを自動的にスケールできます。 このモードでは、ビューにスクロール バーがないと論理ビューを拡大またはウィンドウのクライアント領域を正確に合わせて縮小します。 このスケールの調整機能を使用して、呼び出す[CScrollView::SetScaleToFitSize](#setscaletofitsize)です。 (いずれかを呼び出す`SetScaleToFitSize`または`SetScrollSizes`が、両方は使用できません)。  
  
 前に、`OnDraw`派生ビュー クラスのメンバー関数が呼び出されると、`CScrollView`のビューポートの原点が自動的に調整、`CPaintDC`に渡されるデバイス コンテキスト オブジェクト`OnDraw`です。  
  
 スクロールのウィンドウのビューポートの原点を調整する`CScrollView`オーバーライド[付け](../../mfc/reference/cview-class.md#onpreparedc)です。 この調整が自動的に、`CPaintDC`デバイス コンテキストを`CScrollView`に渡す`OnDraw`、呼び出す必要がありますが、 **CScrollView::OnPrepareDC**自分で他のデバイス コンテキストを使用するなど、 `CClientDC`. オーバーライドできます**CScrollView::OnPrepareDC**をスケーリングを行うには、基本クラスを呼び出すことは、ペン、背景色、およびその他の描画属性を設定します。  
  
 スクロール バーは、次の場合のように、ビューを基準とした 3 つの場所で表示できます。  
  
-   使用してビューの標準のウィンドウ スタイルのスクロール バーを設定することができます、 **WS_HSCROLL**と**WS_VSCROLL**[Windows スタイル](../../mfc/reference/styles-used-by-mfc.md#window-styles)です。  
  
-   フレームワークのケースを転送するビューを含むフレームにスクロール バー コントロールを追加することも`WM_HSCROLL`と`WM_VSCROLL`フレーム ウィンドウから現在アクティブなビューへのメッセージ。  
  
-   また、フレームワークに転送からのメッセージをスクロール、 `CSplitterWnd` splitter コントロールの現在アクティブな分割ウィンドウ (ビュー) にします。 配置すると、 [CSplitterWnd](../../mfc/reference/csplitterwnd-class.md)共有のスクロール バーを持つ、`CScrollView`独自に作成するのではなく、共有のオブジェクトで使用されます。  
  
 使用する方法についての`CScrollView`を参照してください[ドキュメント/ビュー アーキテクチャ](../../mfc/document-view-architecture.md)と[派生ビュー クラスで使用できる MFC](../../mfc/derived-view-classes-available-in-mfc.md)です。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CView](../../mfc/reference/cview-class.md)  
  
 `CScrollView`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxwin.h  
  
##  <a name="checkscrollbars"></a>  CScrollView::CheckScrollBars  
 スクロール ビューが水平方向および垂直のバーを持つかどうかを決定するには、このメンバー関数を呼び出します。  
  
```  
void CheckScrollBars(
    BOOL& bHasHorzBar,  
    BOOL& bHasVertBar) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 *bHasHorzBar*  
 アプリケーション、水平スクロール バーを持つことを示します。  
  
 *bHasVertBar*  
 アプリケーションが垂直スクロール バーを持つことを示します。  
  
##  <a name="cscrollview"></a>  CScrollView::CScrollView  
 `CScrollView` オブジェクトを構築します。  
  
```  
CScrollView();
```  
  
### <a name="remarks"></a>コメント  
 いずれかを呼び出す必要があります`SetScrollSizes`または`SetScaleToFitSize`スクロールする前にビューが使用できるようにします。  
  
##  <a name="filloutsiderect"></a>  CScrollView::FillOutsideRect  
 呼び出す`FillOutsideRect`スクロール領域の外側に表示されるビューの領域を塗りつぶします。  
  
```  
void FillOutsideRect(
    CDC* pDC,  
    CBrush* pBrush);
```  
  
### <a name="parameters"></a>パラメーター  
 `pDC`  
 デバイスがコンテキストで、読み込みを行います。  
  
 `pBrush`  
 領域が格納されるが使用するブラシ。  
  
### <a name="remarks"></a>コメント  
 使用して`FillOutsideRect`スクロール ビューの `OnEraseBkgnd`過剰なバック グラウンドで再描画するようにハンドラー関数。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView#164](../../mfc/codesnippet/cpp/cscrollview-class_1.cpp)]  
  
##  <a name="getdevicescrollposition"></a>  CScrollView::GetDeviceScrollPosition  
 呼び出す`GetDeviceScrollPosition`水平および垂直方向の現在の位置のスクロール ボックス、スクロール バーの必要があります。  
  
```  
CPoint GetDeviceScrollPosition() const;  
```  
  
### <a name="return-value"></a>戻り値  
 水平および垂直方向の位置 (デバイス単位) としてスクロール ボックス、`CPoint`オブジェクト。  
  
### <a name="remarks"></a>コメント  
 この座標ペアでは、ビューの左上隅のスクロール先のドキュメント内の場所に対応しています。 これは、マウス デバイスの位置をスクロール表示デバイスの位置をオフセットするのに役立ちます。  
  
 `GetDeviceScrollPosition` デバイス単位の値を返します。 論理ユニットを実行する場合に、使用`GetScrollPosition`代わりにします。  
  
##  <a name="getdevicescrollsizes"></a>  CScrollView::GetDeviceScrollSizes  
 `GetDeviceScrollSizes` 現在のマップ モード、合計サイズは、スクロール可能なビューの行とページのサイズを取得します。  
  
```  
void GetDeviceScrollSizes(
    int& nMapMode,  
    SIZE& sizeTotal,  
    SIZE& sizePage,  
    SIZE& sizeLine) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `nMapMode`  
 このビューの現在のマップ モードを返します。 使用可能な値の一覧は、次を参照してください。`SetScrollSizes`です。  
  
 `sizeTotal`  
 デバイス単位でスクロール ビューの現在の合計サイズを返します。  
  
 `sizePage`  
 スクロール バーの軸でクリックしてマウスへの応答には、各方向にスクロールする現在の水平および垂直方向の量を返します。 **Cx**メンバーには、水平方向のサイズが含まれています。 **Cy**メンバーには、垂直方向のサイズが含まれています。  
  
 `sizeLine`  
 スクロール バーの矢印でクリックしてマウスへの応答には、各方向にスクロールする現在の水平および垂直方向の量を返します。 **Cx**メンバーには、水平方向のサイズが含まれています。 **Cy**メンバーには、垂直方向のサイズが含まれています。  
  
### <a name="remarks"></a>コメント  
 デバイス単位のサイズです。 このメンバー関数が呼び出されますことはほとんどありません。  
  
##  <a name="getscrollposition"></a>  CScrollView::GetScrollPosition  
 呼び出す`GetScrollPosition`水平および垂直方向の現在の位置のスクロール ボックス、スクロール バーの必要があります。  
  
```  
CPoint GetScrollPosition() const;  
```  
  
### <a name="return-value"></a>戻り値  
 水平および垂直方向の位置 (論理単位で) に応じて、スクロール ボックス、`CPoint`オブジェクト。  
  
### <a name="remarks"></a>コメント  
 この座標ペアでは、ビューの左上隅のスクロール先のドキュメント内の場所に対応しています。  
  
 `GetScrollPosition` 論理ユニットの値を返します。 デバイス単位にする場合は、使用`GetDeviceScrollPosition`代わりにします。  
  
##  <a name="gettotalsize"></a>  CScrollView::GetTotalSize  
 呼び出す`GetTotalSize`スクロール ビューの現在の水平方向および垂直方向のサイズを取得します。  
  
```  
CSize GetTotalSize() const;  
```  
  
### <a name="return-value"></a>戻り値  
 論理ユニットでスクロール ビューの合計サイズ。 水平方向のサイズは、 **cx**のメンバー、`CSize`値を返します。 垂直方向のサイズは、 **cy**メンバー。  
  
##  <a name="resizeparenttofit"></a>  CScrollView::ResizeParentToFit  
 呼び出す`ResizeParentToFit`フレーム ウィンドウのサイズに合う、ビューのサイズをできるようにします。  
  
```  
void ResizeParentToFit(BOOL bShrinkOnly = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 *bShrinkOnly*  
 実行するサイズ変更の種類。 既定値は**TRUE**、該当する場合は、フレーム ウィンドウを縮小します。 スクロール バーは、ビューが大きいまたは小さいフレーム ウィンドウも表示されます。 値**FALSE**と正確にフレーム ウィンドウのサイズを変更するには、常に表示します。 これは、フレーム ウィンドウは、マルチ ドキュメント インターフェイス (MDI) のフレーム ウィンドウまたは画面に収まるが大きすぎて取得でしたので多少危険です。  
  
### <a name="remarks"></a>コメント  
 MDI 子フレーム ウィンドウのビューにのみお勧めします。 使用して`ResizeParentToFit`で、`OnInitialUpdate`ハンドラー関数、派生の`CScrollView`クラスです。 このメンバー関数の例は、次を参照してください。 [CScrollView::SetScrollSizes](#setscrollsizes)です。  
  
 `ResizeParentToFit` [ビュー] ウィンドウのサイズが設定されていると仮定します。 かどうか、表示ウィンドウのサイズが設定されていない場合に`ResizeParentToFit`が呼び出されると、アサーションが取得されます。 そうでないことを確認してくださいを呼び出す前に、次の呼び出しを行う`ResizeParentToFit`:  
  
 [!code-cpp[NVC_MFCDocView#165](../../mfc/codesnippet/cpp/cscrollview-class_2.cpp)]  
  
##  <a name="scrolltoposition"></a>  CScrollView::ScrollToPosition  
 呼び出す`ScrollToPosition`ビューの特定の時点にスクロールします。  
  
```  
void ScrollToPosition(POINT pt);
```  
  
### <a name="parameters"></a>パラメーター  
 `pt`  
 論理ユニットでのスクロールをポイントします。 **X**メンバーは (より大きいまたは 0 で、ビューの合計サイズの最大) の正の値である必要があります。 場合も同様、 **y**マッピング モードの場合、メンバー`MM_TEXT`です。 **Y**メンバーは負の値以外のモードのマッピングで`MM_TEXT`です。  
  
### <a name="remarks"></a>コメント  
 このポイントがウィンドウの左上隅にあるように、ビューにスクロールされます。 ビューに合わせてスケーリングされる場合、このメンバー関数は呼び出されません必要があります。  
  
##  <a name="setscaletofitsize"></a>  CScrollView::SetScaleToFitSize  
 呼び出す`SetScaleToFitSize`ビューポートのサイズを現在のウィンドウ サイズを自動的にスケールする場合。  
  
```  
void SetScaleToFitSize(SIZE sizeTotal);
```  
  
### <a name="parameters"></a>パラメーター  
 `sizeTotal`  
 水平および垂直方向のサイズをビューが拡大縮小します。 スクロール ビューのサイズは、論理単位で測定されます。 水平方向のサイズに含まれている、 **cx**メンバー。 垂直方向のサイズに含まれている、 **cy**メンバー。 両方**cx**と**cy** 0 以上にする必要があります。  
  
### <a name="remarks"></a>コメント  
 スクロール バーを持つ論理ビューの一部にのみ表示される可能性がいつでもできます。 スケールの調整機能を持つビューにスクロール バーがないと論理ビューを拡大またはウィンドウのクライアント領域を正確に合わせて縮小します。 ウィンドウのサイズを変更、ビューは、ウィンドウのサイズに基づく新しいスケールにそのデータを描画します。  
  
 呼び出しを配置する通常`SetScaleToFitSize`のビューのオーバーライドで`OnInitialUpdate`メンバー関数。 自動スケーリングしたくない場合、`SetScrollSizes`メンバー関数を使用します。  
  
 `SetScaleToFitSize` "ズームに Fit"操作を実装するために使用します。 使用して`SetScrollSizes`スクロールを再初期化します。  
  
 `SetScaleToFitSize` [ビュー] ウィンドウのサイズが設定されていると仮定します。 かどうか、表示ウィンドウのサイズが設定されていない場合に`SetScaleToFitSize`が呼び出されると、アサーションが取得されます。 そうでないことを確認してくださいを呼び出す前に、次の呼び出しを行う`SetScaleToFitSize`:  
  
 [!code-cpp[NVC_MFCDocView#165](../../mfc/codesnippet/cpp/cscrollview-class_2.cpp)]  
  
##  <a name="setscrollsizes"></a>  CScrollView::SetScrollSizes  
 呼び出す`SetScrollSizes`とビューが更新しようとしています。  
  
```  
void SetScrollSizes(
    int nMapMode,  
    SIZE sizeTotal,  
    const SIZE& sizePage = sizeDefault,  
    const SIZE& sizeLine = sizeDefault);
```  
  
### <a name="parameters"></a>パラメーター  
 `nMapMode`  
 このビューに設定するマッピング モードです。 次の値を使用できます。  
  
|マップ モード|論理ユニット|正の y 軸拡張しています.|  
|------------------|------------------|---------------------------------|  
|`MM_TEXT`|1 ピクセル|下降傾向|  
|`MM_HIMETRIC`|0.01 mm|上方向へ|  
|`MM_TWIPS`|1/1440|上方向へ|  
|`MM_HIENGLISH`|0.001 で|上方向へ|  
|`MM_LOMETRIC`|0.1 mm|上方向へ|  
|`MM_LOENGLISH`|0.01 インチ|上方向へ|  
  
 これらのモードのすべては、Windows によって定義されます。 2 つの標準マッピング モード`MM_ISOTROPIC`と`MM_ANISOTROPIC`、使用されない`CScrollView`です。 クラス ライブラリには、`SetScaleToFitSize`ウィンドウ サイズに拡大または縮小のメンバー関数。 上記の表に 3 番目の列には、座標の方向がについて説明します。  
  
 `sizeTotal`  
 スクロール ビューの合計サイズ。 **Cx**メンバーには、水平方向のエクステントが含まれています。 **Cy**メンバーには、垂直方向のエクステントが含まれています。 論理ユニットのサイズです。 両方**cx**と**cy** 0 以上にする必要があります。  
  
 `sizePage`  
 マウスへの応答には、各方向にスクロールする水平および垂直の量は、スクロール バーの軸をクリックします。 **Cx**メンバーには、水平方向のサイズが含まれています。 **Cy**メンバーには、垂直方向のサイズが含まれています。  
  
 `sizeLine`  
 マウスへの応答には、各方向にスクロールする水平および垂直の量は、スクロール バーの矢印をクリックします。 **Cx**メンバーには、水平方向のサイズが含まれています。 **Cy**メンバーには、垂直方向のサイズが含まれています。  
  
### <a name="remarks"></a>コメント  
 オーバーライドで呼び出して、`OnUpdate`ドキュメントが最初に表示されるなどのとき、またはサイズを変更するときに、スクロールの特性を調整するメンバー関数。  
  
 おそらくと呼ばれる、ドキュメントのメンバー関数を呼び出すことによって、ビューの関連するドキュメントからサイズ情報を取得するは通常`GetMyDocSize`、派生したドキュメント クラスを提供します。 次のコードは、この方法を示しています。  
  
 [!code-cpp[NVC_MFCDocView#166](../../mfc/codesnippet/cpp/cscrollview-class_3.cpp)]  
  
 代わりに、次のコードのように、固定サイズを設定する必要がある場合があります。  
  
 [!code-cpp[NVC_MFCDocView#167](../../mfc/codesnippet/cpp/cscrollview-class_4.cpp)]  
  
 除く Windows マッピング モードのいずれかのマッピング モードを設定する必要があります`MM_ISOTROPIC`または`MM_ANISOTROPIC`です。 制約なしのマッピング モードを使用する場合は、呼び出し、`SetScaleToFitSize`メンバー関数の代わりに`SetScrollSizes`です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView#168](../../mfc/codesnippet/cpp/cscrollview-class_5.cpp)]  
  
 [!code-cpp[NVC_MFCDocView#169](../../mfc/codesnippet/cpp/cscrollview-class_6.cpp)]  
  
## <a name="see-also"></a>関連項目  
 [MFC サンプル DIBLOOK](../../visual-cpp-samples.md)   
 [CView クラス](../../mfc/reference/cview-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CView クラス](../../mfc/reference/cview-class.md)   
 [CSplitterWnd クラス](../../mfc/reference/csplitterwnd-class.md)

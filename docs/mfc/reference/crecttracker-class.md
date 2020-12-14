---
description: '詳細情報: CRectTracker クラス'
title: CRectTracker クラス
ms.date: 11/19/2018
f1_keywords:
- CRectTracker
- AFXEXT/CRectTracker
- AFXEXT/CRectTracker::CRectTracker
- AFXEXT/CRectTracker::AdjustRect
- AFXEXT/CRectTracker::Draw
- AFXEXT/CRectTracker::DrawTrackerRect
- AFXEXT/CRectTracker::GetHandleMask
- AFXEXT/CRectTracker::GetTrueRect
- AFXEXT/CRectTracker::HitTest
- AFXEXT/CRectTracker::NormalizeHit
- AFXEXT/CRectTracker::OnChangedRect
- AFXEXT/CRectTracker::SetCursor
- AFXEXT/CRectTracker::Track
- AFXEXT/CRectTracker::TrackRubberBand
- AFXEXT/CRectTracker::m_nHandleSize
- AFXEXT/CRectTracker::m_nStyle
- AFXEXT/CRectTracker::m_rect
- AFXEXT/CRectTracker::m_sizeMin
helpviewer_keywords:
- CRectTracker [MFC], CRectTracker
- CRectTracker [MFC], AdjustRect
- CRectTracker [MFC], Draw
- CRectTracker [MFC], DrawTrackerRect
- CRectTracker [MFC], GetHandleMask
- CRectTracker [MFC], GetTrueRect
- CRectTracker [MFC], HitTest
- CRectTracker [MFC], NormalizeHit
- CRectTracker [MFC], OnChangedRect
- CRectTracker [MFC], SetCursor
- CRectTracker [MFC], Track
- CRectTracker [MFC], TrackRubberBand
- CRectTracker [MFC], m_nHandleSize
- CRectTracker [MFC], m_nStyle
- CRectTracker [MFC], m_rect
- CRectTracker [MFC], m_sizeMin
ms.assetid: 99caa7f2-3c0d-4a42-bbee-e5d1d342d4ee
ms.openlocfilehash: 8406b6b45a99ca2e1816cb650f243fcea2db8ddc
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97343021"
---
# <a name="crecttracker-class"></a>CRectTracker クラス

異なる fashions で項目を表示、移動、およびサイズ変更できるようにします。

## <a name="syntax"></a>構文

```
class CRectTracker
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CRectTracker:: CRectTracker](#crecttracker)|`CRectTracker` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CRectTracker:: AdjustRect](#adjustrect)|四角形のサイズが変更されると呼び出されます。|
|[CRectTracker::D raw](#draw)|四角形を描画します。|
|[CRectTracker::D rawTrackerRect](#drawtrackerrect)|オブジェクトの境界線を描画するときに呼び出され `CRectTracker` ます。|
|[CRectTracker:: GetHandleMask](#gethandlemask)|項目のサイズ変更ハンドルのマスクを取得するために呼び出され `CRectTracker` ます。|
|[CRectTracker:: GetTrueRect](#gettruerect)|サイズ変更ハンドルを含む、四角形の幅と高さを返します。|
|[CRectTracker:: System.windows.media.visualtreehelper.hittest](#hittest)|オブジェクトに関連付けられているカーソルの現在位置を返し `CRectTracker` ます。|
|[CRectTracker:: NormalizeHit](#normalizehit)|ヒットテストコードを正規化します。|
|[CRectTracker:: On Rect](#onchangedrect)|四角形のサイズ変更または移動が行われたときに呼び出されます。|
|[CRectTracker:: SetCursor](#setcursor)|四角形上の位置に応じてカーソルを設定します。|
|[CRectTracker:: Track](#track)|ユーザーが四角形を操作できるようにします。|
|[CRectTracker:: TrackRubberBand](#trackrubberband)|ユーザーが選択範囲を "ラバーバンド" できるようにします。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[CRectTracker:: m_nHandleSize](#m_nhandlesize)|サイズ変更ハンドルのサイズを決定します。|
|[CRectTracker:: m_nStyle](#m_nstyle)|トラッカーの現在のスタイル。|
|[CRectTracker:: m_rect](#m_rect)|四角形の現在の位置 (ピクセル単位)。|
|[CRectTracker:: m_sizeMin](#m_sizemin)|最小の四角形の幅と高さを決定します。|

## <a name="remarks"></a>解説

`CRectTracker` に基底クラスがありません。

クラスは、 `CRectTracker` ユーザーがグラフィカルインターフェイスを使用して ole 項目を操作できるように設計されていますが、その使用は ole 対応アプリケーションに限定されません。 ユーザーインターフェイスが必要な場所であればどこでも使用できます。

`CRectTracker` 枠線は実線または点線にすることができます。 項目には、斜線の境界線を付けたり、項目の異なる状態を示すためにハッチパターンで重ねたりすることができます。 項目の外側または内側の境界線のいずれかに、8つのサイズ変更ハンドルを配置できます。 (サイズ変更ハンドルの詳細については、「 [GetHandleMask](#gethandlemask)」を参照してください)。最後に、を使用すると、 `CRectTracker` サイズ変更中に項目の向きを変更できます。

を使用するには `CRectTracker` 、オブジェクトを構築 `CRectTracker` し、初期化される表示状態を指定します。 その後、このインターフェイスを使用して、オブジェクトに関連付けられている OLE 項目の現在の状態に関する視覚的なフィードバックをユーザーに与えることができ `CRectTracker` ます。

の使用方法の詳細については `CRectTracker` 、「 [トラッカー](../../mfc/trackers.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

`CRectTracker`

## <a name="requirements"></a>要件

**ヘッダー:** afxext.h

## <a name="crecttrackeradjustrect"></a><a name="adjustrect"></a> CRectTracker:: AdjustRect

サイズ変更ハンドルを使用して追跡四角形のサイズを変更するときに、フレームワークによって呼び出されます。

```
virtual void AdjustRect(
    int nHandle,
    LPRECT lpRect);
```

### <a name="parameters"></a>パラメーター

*nHandle*<br/>
使用されるハンドルのインデックス。

*lpRect*<br/>
四角形の現在のサイズへのポインター。 (四角形のサイズは、その高さと幅によって指定されます)。

### <a name="remarks"></a>解説

この関数の既定の動作では、 `Track` 反転を許可してを呼び出した場合にのみ、四角形の向きを変更でき `TrackRubberBand` ます。

この関数をオーバーライドして、ドラッグ操作中の追跡四角形の調整を制御します。 1つの方法は、を返す前に、 *lpRect* によって指定された座標を調整することです。

によって直接サポートされていない特殊な機能 `CRectTracker` (スナップツーグリッドや、縦横比など) は、この関数をオーバーライドすることによって実装できます。

## <a name="crecttrackercrecttracker"></a><a name="crecttracker"></a> CRectTracker:: CRectTracker

`CRectTracker` オブジェクトを構築して、初期化します。

```
CRectTracker();

CRectTracker(
    LPCRECT lpSrcRect,
    UINT nStyle);
```

### <a name="parameters"></a>パラメーター

*lpSrcRect*<br/>
四角形オブジェクトの座標。

*nStyle*<br/>
オブジェクトのスタイルを指定し `CRectTracker` ます。 次のスタイルがサポートされています。

- `CRectTracker::solidLine` 四角形の境界線には実線を使用します。

- `CRectTracker::dottedLine` 四角形の境界線に点線を使用します。

- `CRectTracker::hatchedBorder` 四角形の境界線には、ハッチパターンを使用します。

- `CRectTracker::resizeInside` 四角形内にあるハンドルのサイズを変更します。

- `CRectTracker::resizeOutside` 四角形の外側にあるハンドルのサイズを変更します。

- `CRectTracker::hatchInside` ハッチパターンは、四角形全体をカバーします。

### <a name="remarks"></a>解説

既定のコンストラクターは、 `CRectTracker` *Lpsrcrect* の値を使用してオブジェクトを初期化し、その他のサイズをシステムの既定値に初期化します。 オブジェクトがパラメーターなしで作成された場合、 `m_rect` および `m_nStyle` データメンバーは初期化されません。

## <a name="crecttrackerdraw"></a><a name="draw"></a> CRectTracker::D raw

四角形の外側の線と内部領域を描画するには、この関数を呼び出します。

```cpp
void Draw(CDC* pDC) const;
```

### <a name="parameters"></a>パラメーター

*pDC*<br/>
描画するデバイスコンテキストへのポインター。

### <a name="remarks"></a>解説

トラッカーのスタイルによって、描画の実行方法が決まります。 使用できるスタイルの詳細については、のコンストラクターを参照してください `CRectTracker` 。

## <a name="crecttrackerdrawtrackerrect"></a><a name="drawtrackerrect"></a> CRectTracker::D rawTrackerRect

またはメンバー関数の内部でトラッカーの位置が変更されるたびに、フレームワークによって呼び出され `Track` `TrackRubberBand` ます。

```
virtual void DrawTrackerRect(
    LPCRECT lpRect,
    CWnd* pWndClipTo,
    CDC* pDC,
    CWnd* pWnd);
```

### <a name="parameters"></a>パラメーター

*lpRect*<br/>
描画する四角形を格納しているへのポインター `RECT` 。

*pWndClipTo*<br/>
四角形のクリッピングに使用するウィンドウへのポインター。

*pDC*<br/>
描画するデバイスコンテキストへのポインター。

*pWnd*<br/>
描画が発生するウィンドウへのポインター。

### <a name="remarks"></a>解説

既定の実装では、の呼び出しが行われ `CDC::DrawFocusRect` 、点線の四角形が描画されます。

追跡操作中に別のフィードバックを提供するには、この関数をオーバーライドします。

## <a name="crecttrackergethandlemask"></a><a name="gethandlemask"></a> CRectTracker:: GetHandleMask

フレームワークは、このメンバー関数を呼び出して、四角形のサイズ変更ハンドルのマスクを取得します。

```
virtual UINT GetHandleMask() const;
```

### <a name="return-value"></a>戻り値

`CRectTracker`項目のサイズ変更ハンドルのマスク。

### <a name="remarks"></a>解説

サイズ変更ハンドルは、四角形の辺と隅に表示され、ユーザーが四角形の形状とサイズを制御できるようにします。

四角形には、8個のサイズ変更ハンドルが付いています (0-7)。 各サイズ変更ハンドルはマスクのビットで表されます。そのビットの値は 2 ^ *n* です。ここで、 *n* はサイズ変更ハンドル番号です。 ビット0-3 は、左上に向かって左に回転する、コーナーのサイズ変更ハンドルに対応します。 ビット4-7 は、上部の移動を開始する側のサイズ変更ハンドルに対応します。 次の図は、四角形のサイズ変更ハンドルと、それに対応するサイズ変更ハンドルの番号と値を示しています。

![ハンドル番号のサイズ変更](../../mfc/reference/media/vc35dp1.gif "ハンドル番号のサイズ変更")

の既定の実装では、 `GetHandleMask` サイズ変更ハンドルが表示されるように、ビットのマスクが返されます。 シングルビットがオンの場合は、対応するサイズ変更ハンドルが描画されます。

このメンバー関数をオーバーライドして、指定されたサイズ変更ハンドルを表示または非表示にします。

## <a name="crecttrackergettruerect"></a><a name="gettruerect"></a> CRectTracker:: GetTrueRect

四角形の座標を取得するには、この関数を呼び出します。

```cpp
void GetTrueRect(LPRECT lpTrueRect) const;
```

### <a name="parameters"></a>パラメーター

*lpTrueRect*<br/>
`RECT`オブジェクトのデバイス座標を格納する構造体へのポインター `CRectTracker` 。

### <a name="remarks"></a>解説

四角形の大きさには、外側の境界線にあるサイズ変更ハンドルの高さと幅が含まれます。 返されると、 *lpTrueRect* は常にデバイス座標で正規化された四角形になります。

## <a name="crecttrackerhittest"></a><a name="hittest"></a> CRectTracker:: System.windows.media.visualtreehelper.hittest

ユーザーがサイズ変更ハンドルを取得したかどうかを調べるには、この関数を呼び出します。

```
int HitTest(CPoint point) const;
```

### <a name="parameters"></a>パラメーター

*視点*<br/>
テストするポイント (デバイス座標)。

### <a name="return-value"></a>戻り値

返される値は列挙型に基づい `CRectTracker::TrackerHit` ており、次のいずれかの値を持つことができます。

- `CRectTracker::hitNothing` -1

- `CRectTracker::hitTopLeft` 0

- `CRectTracker::hitTopRight` 1

- `CRectTracker::hitBottomRight` 3

- `CRectTracker::hitBottomLeft` 番

- `CRectTracker::hitTop` 4

- `CRectTracker::hitRight` 5/5

- `CRectTracker::hitBottom` 4/6

- `CRectTracker::hitLeft` 7

- `CRectTracker::hitMiddle` 8

## <a name="crecttrackerm_nhandlesize"></a><a name="m_nhandlesize"></a> CRectTracker:: m_nHandleSize

サイズ変更ハンドルのサイズ (ピクセル単位) `CRectTracker` 。

```
int m_nHandleSize;
```

### <a name="remarks"></a>解説

既定のシステム値で初期化されます。

## <a name="crecttrackerm_rect"></a><a name="m_rect"></a> CRectTracker:: m_rect

クライアント座標の四角形の現在位置 (ピクセル単位)。

```
CRect m_rect;
```

## <a name="crecttrackerm_sizemin"></a><a name="m_sizemin"></a> CRectTracker:: m_sizeMin

四角形の最小サイズ。

```
CSize m_sizeMin;
```

### <a name="remarks"></a>解説

既定値は、 `cx` との両方 `cy` が、境界線の幅の既定のシステム値から計算されます。 このデータメンバーは、メンバー関数によってのみ使用され `AdjustRect` ます。

## <a name="crecttrackerm_nstyle"></a><a name="m_nstyle"></a> CRectTracker:: m_nStyle

四角形の現在のスタイル。

```
UINT m_nStyle;
```

### <a name="remarks"></a>解説

使用可能なスタイルの一覧については、「 [CRectTracker:: CRectTracker](#crecttracker) 」を参照してください。

## <a name="crecttrackernormalizehit"></a><a name="normalizehit"></a> CRectTracker:: NormalizeHit

この関数を呼び出して、逆になる可能性のあるハンドルを変換します。

```
int NormalizeHit(int nHandle) const;
```

### <a name="parameters"></a>パラメーター

*nHandle*<br/>
ユーザーによって選択されたハンドル。

### <a name="return-value"></a>戻り値

正規化されたハンドルのインデックス。

### <a name="remarks"></a>解説

`CRectTracker::Track`または `CRectTracker::TrackRubberBand` が反転を使用して呼び出された場合、x 軸、y 軸、またはその両方で四角形を反転させることができます。 この場合、 `HitTest` は、四角形に対しても反転されるハンドルを返します。 これは、変更される四角形のデータ構造の一部ではなく、四角形の画面位置に依存するため、カーソルのフィードバックの描画には適していません。

## <a name="crecttrackeronchangedrect"></a><a name="onchangedrect"></a> CRectTracker:: On Rect

の呼び出し中にトラッカー四角形が変更されたときに、フレームワークによって呼び出され `Track` ます。

```
virtual void OnChangedRect(const CRect& rectOld);
```

### <a name="parameters"></a>パラメーター

*rectOld*<br/>
オブジェクトの古いデバイス座標を格納し `CRectTracker` ます。

### <a name="remarks"></a>解説

この関数が呼び出された時点で、で描画されたすべてのフィードバック `DrawTrackerRect` が削除されました。 この関数の既定の実装は、何も行いません。

四角形のサイズを変更した後にアクションを実行する場合は、この関数をオーバーライドします。

## <a name="crecttrackersetcursor"></a><a name="setcursor"></a> CRectTracker:: SetCursor

オブジェクトの領域上でカーソルの形状を変更するには、この関数を呼び出し `CRectTracker` ます。

```
BOOL SetCursor(
    CWnd* pWnd,
    UINT nHitTest) const;
```

### <a name="parameters"></a>パラメーター

*pWnd*<br/>
カーソルが現在格納されているウィンドウを指します。

*nHitTest*<br/>
WM_SETCURSOR メッセージからの前のヒットテストの結果。

### <a name="return-value"></a>戻り値

前のヒットがトラッカーの四角形の上にある場合は0以外の。それ以外の場合は0です。

### <a name="remarks"></a>解説

WM_SETCURSOR メッセージ (通常は) を処理するウィンドウの関数内から、この関数を呼び出し `OnSetCursor` ます。

## <a name="crecttrackertrack"></a><a name="track"></a> CRectTracker:: Track

四角形のサイズを変更するためのユーザーインターフェイスを表示するには、この関数を呼び出します。

```
BOOL Track(
    CWnd* pWnd,
    CPoint point,
    BOOL bAllowInvert = FALSE,
    CWnd* pWndClipTo = NULL);
```

### <a name="parameters"></a>パラメーター

*pWnd*<br/>
四角形を格納しているウィンドウオブジェクト。

*視点*<br/>
クライアント領域を基準とした、現在のマウス位置のデバイス座標。

*bAllowInvert*<br/>
TRUE の場合、四角形を x 軸または y 軸に沿って反転させることができます。それ以外の場合は FALSE。

*pWndClipTo*<br/>
描画操作がクリップされるウィンドウ。 NULL の場合、 *pWnd* はクリッピング四角形として使用されます。

### <a name="return-value"></a>戻り値

ESC キーが押されている場合、追跡プロセスは停止され、トラッカーに格納されている四角形は変更されず、0が返されます。 マウスを動かしてマウスの左ボタンを放すことで変更がコミットされた場合は、新しい位置またはサイズがトラッカーの四角形に記録され、0以外の値が返されます。

### <a name="remarks"></a>解説

通常、これはメッセージを処理するアプリケーションの関数の内部から呼び出され `WM_LBUTTONDOWN` ます (通常は `OnLButtonDown` )。

この関数は、ユーザーがマウスの左ボタンを離すか、ESC キーを押すか、マウスの右ボタンを押すまでマウスをキャプチャします。 ユーザーがマウスカーソルを移動すると、とを呼び出すことによってフィードバックが更新され `DrawTrackerRect` `OnChangedRect` ます。

*Ballowinvert* が TRUE の場合は、追跡四角形を x 軸または y 軸のいずれかで反転させることができます。

## <a name="crecttrackertrackrubberband"></a><a name="trackrubberband"></a> CRectTracker:: TrackRubberBand

ラバーバンドの選択を行うには、この関数を呼び出します。

```
BOOL TrackRubberBand(
    CWnd* pWnd,
    CPoint point,
    BOOL bAllowInvert = TRUE);
```

### <a name="parameters"></a>パラメーター

*pWnd*<br/>
四角形を格納しているウィンドウオブジェクト。

*視点*<br/>
クライアント領域を基準とした、現在のマウス位置のデバイス座標。

*bAllowInvert*<br/>
TRUE の場合、四角形を x 軸または y 軸に沿って反転させることができます。それ以外の場合は FALSE。

### <a name="return-value"></a>戻り値

マウスが移動し、四角形が空でない場合は0以外の。それ以外の場合は0です。

### <a name="remarks"></a>解説

通常は、WM_LBUTTONDOWN メッセージ (通常は) を処理するアプリケーションの関数の内部から呼び出され `OnLButtonDown` ます。

この関数は、ユーザーがマウスの左ボタンを離すか、ESC キーを押すか、マウスの右ボタンを押すまでマウスをキャプチャします。 ユーザーがマウスカーソルを移動すると、とを呼び出すことによってフィードバックが更新され `DrawTrackerRect` `OnChangedRect` ます。

追跡は、右下のハンドルからラバーバンド型の選択を使用して実行されます。 反転が許可されている場合、四角形を上下左右にドラッグしてサイズを変更できます。

## <a name="see-also"></a>関連項目

[MFC サンプルトラッカー](../../overview/visual-cpp-samples.md)<br/>
[MFC のサンプル DRAWCLI](../../overview/visual-cpp-samples.md)<br/>
[階層図](../../mfc/hierarchy-chart.md)<br/>
[COleResizeBar クラス](../../mfc/reference/coleresizebar-class.md)<br/>
[CRect クラス](../../atl-mfc-shared/reference/crect-class.md)

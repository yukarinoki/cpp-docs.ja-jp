---
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
ms.openlocfilehash: 4d262ab5f88481d56de1c236effb66fcbf6a706a
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81368374"
---
# <a name="crecttracker-class"></a>CRectTracker クラス

アイテムをさまざまな方法で表示、移動、およびサイズ変更できます。

## <a name="syntax"></a>構文

```
class CRectTracker
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[クレストトラッカー::CRectトラッカー](#crecttracker)|`CRectTracker` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[クレストトラッカー::アジャストレック](#adjustrect)|四角形のサイズが変更されたときに呼び出されます。|
|[クレストトラッカー::Dロー](#draw)|四角形をレンダリングします。|
|[クレストトラッカー::Dロートラッカーレック](#drawtrackerrect)|オブジェクトの境界線を描画するときに呼`CRectTracker`び出されます。|
|[クレストトラッカー::ゲットハンドルマスク](#gethandlemask)|項目のサイズ変更ハンドルのマスク`CRectTracker`を取得するために呼び出されます。|
|[クレストトラッカー::ゲットトゥルーレック](#gettruerect)|サイズ変更ハンドルを含む四角形の幅と高さを返します。|
|[クレストトラッカー::ヒットテスト](#hittest)|オブジェクトに関連するカーソルの現在位置を`CRectTracker`返します。|
|[クレストトラッカー::ノーマライズヒット](#normalizehit)|ヒット テスト コードを正規化します。|
|[クレストトラッカー::オン変更レック](#onchangedrect)|四角形のサイズ変更または移動が行われたときに呼び出されます。|
|[クレットトラッカー::セットカーソル](#setcursor)|四角形上のカーソルの位置に応じて、カーソルを設定します。|
|[クレストトラッカー::トラック](#track)|ユーザーが四角形を操作できるようにします。|
|[クレストトラッカー::トラックラバーバンド](#trackrubberband)|ユーザーが選択範囲を「ゴムバンド」できるようにします。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[クレストトラッカー::m_nHandleSize](#m_nhandlesize)|サイズ変更ハンドルのサイズを指定します。|
|[クレストトラッカー::m_nStyle](#m_nstyle)|トラッカーの現在のスタイルです。|
|[クレストトラッカー::m_rect](#m_rect)|四角形の現在位置 (ピクセル単位)。|
|[クレストトラッカー::m_sizeMin](#m_sizemin)|長方形の幅と高さの最小値を指定します。|

## <a name="remarks"></a>解説

`CRectTracker`は基本クラスを持っていません。

この`CRectTracker`クラスは、ユーザーがグラフィカル インターフェイスを使用して OLE アイテムを操作できるように設計されていますが、OLE 対応アプリケーションに限定されません。 このようなユーザーインターフェイスが必要な場所であればどこでも使用できます。

`CRectTracker`境界線は、実線または点線にすることができます。 アイテムは、ハッチングされた境界線を与えたり、ハッチング パターンでオーバーレイして、項目のさまざまな状態を示すことができます。 アイテムの外側または内側の境界線に、8 つのサイズ変更ハンドルを配置できます。 (サイズ変更ハンドルの説明については、 [GetHandleMask](#gethandlemask)を参照してください。最後に、`CRectTracker`サイズ変更中にアイテムの方向を変更できます。

を使用`CRectTracker`するには、オブジェクト`CRectTracker`を構築し、初期化する表示状態を指定します。 このインターフェイスを使用して、オブジェクトに関連付けられた OLE アイテムの現在の状態について、ユーザーに`CRectTracker`視覚的なフィードバックを提供できます。

の使用方法`CRectTracker`の詳細については、[記事のトラッカーを](../../mfc/trackers.md)参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

`CRectTracker`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxext.h

## <a name="crecttrackeradjustrect"></a><a name="adjustrect"></a>クレストトラッカー::アジャストレック

サイズ変更ハンドルを使用して追跡四角形のサイズを変更するときに、フレームワークによって呼び出されます。

```
virtual void AdjustRect(
    int nHandle,
    LPRECT lpRect);
```

### <a name="parameters"></a>パラメーター

*nハンドル*<br/>
使用されるハンドルのインデックス。

*Lprect*<br/>
四角形の現在のサイズへのポインター。 (四角形のサイズは、その高さと幅で指定されます)。

### <a name="remarks"></a>解説

この関数の既定の動作では、反転が許可されている状態で呼び`Track`出`TrackRubberBand`された場合にのみ、四角形の方向を変更できます。

ドラッグ操作中のトラッキング四角形の調整を制御するには、この関数をオーバーライドします。 1 つの方法は、戻る前に*lpRect*で指定された座標を調整することです。

グリッドへのスナップや横方向の比率`CRectTracker`の維持など、直接サポートされていない特殊機能は、この関数をオーバーライドすることによって実装できます。

## <a name="crecttrackercrecttracker"></a><a name="crecttracker"></a>クレストトラッカー::CRectトラッカー

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
オブジェクトのスタイルを`CRectTracker`指定します。 次のスタイルがサポートされています。

- `CRectTracker::solidLine`四角形の境界線には実線を使用します。

- `CRectTracker::dottedLine`四角形の境界線には点線を使用します。

- `CRectTracker::hatchedBorder`四角形の境界線にはハッチング パターンを使用します。

- `CRectTracker::resizeInside`四角形の内側にあるハンドルのサイズを変更します。

- `CRectTracker::resizeOutside`四角形の外側にあるハンドルのサイズを変更します。

- `CRectTracker::hatchInside`ハッチングパターンは矩形全体を覆います。

### <a name="remarks"></a>解説

既定のコンストラクターは`CRectTracker`*、lpSrcRect*の値を使用してオブジェクトを初期化し、他のサイズをシステムの既定値に初期化します。 オブジェクトがパラメータなしで作成された場合、`m_rect`および`m_nStyle`データ メンバーは初期化されません。

## <a name="crecttrackerdraw"></a><a name="draw"></a>クレストトラッカー::Dロー

四角形の外側の線と内側の領域を描画します。

```
void Draw(CDC* pDC) const;
```

### <a name="parameters"></a>パラメーター

*pDC*<br/>
描画するデバイス コンテキストへのポインター。

### <a name="remarks"></a>解説

トラッカーのスタイルによって、図面の実行方法が決まります。 使用可能なスタイルの`CRectTracker`詳細については、コンストラクターを参照してください。

## <a name="crecttrackerdrawtrackerrect"></a><a name="drawtrackerrect"></a>クレストトラッカー::Dロートラッカーレック

または`Track``TrackRubberBand`メンバー関数内でトラッカーの位置が変更されるたびに、フレームワークによって呼び出されます。

```
virtual void DrawTrackerRect(
    LPCRECT lpRect,
    CWnd* pWndClipTo,
    CDC* pDC,
    CWnd* pWnd);
```

### <a name="parameters"></a>パラメーター

*Lprect*<br/>
描画`RECT`する四角形を含む を指すポインター。

*クリップ*<br/>
四角形のクリッピングに使用するウィンドウへのポインター。

*pDC*<br/>
描画するデバイス コンテキストへのポインター。

*Pwnd*<br/>
図面が表示されるウィンドウへのポインター。

### <a name="remarks"></a>解説

既定の実装では、 を`CDC::DrawFocusRect`呼び出し、点線の四角形を描画します。

この関数をオーバーライドして、追跡操作中に異なるフィードバックを提供します。

## <a name="crecttrackergethandlemask"></a><a name="gethandlemask"></a>クレストトラッカー::ゲットハンドルマスク

フレームワークは、このメンバー関数を呼び出して、四角形のサイズ変更ハンドルのマスクを取得します。

```
virtual UINT GetHandleMask() const;
```

### <a name="return-value"></a>戻り値

`CRectTracker`項目のサイズ変更ハンドルのマスク。

### <a name="remarks"></a>解説

サイズ変更ハンドルは四角形の辺と角に表示され、ユーザーは四角形の形状とサイズを制御できます。

長方形には、0 から 7 の番号が付けられた 8 つのサイズ変更ハンドルがあります。 各サイズ変更ハンドルは、マスク内のビットで表されます。そのビットの値は 2^ *n*で *、n*はサイズ変更ハンドル番号です。 ビット 0 から 3 は、左上から時計回りに移動して、コーナーのサイズ変更ハンドルに対応します。 ビット 4 から 7 は、時計回りに移動する上部から始まるサイド サイズ変更ハンドルに対応します。 次の図は、四角形のサイズ変更ハンドルとそれに対応するサイズ変更ハンドルの数値と値を示しています。

![ハンドル番号のサイズを変更する](../../mfc/reference/media/vc35dp1.gif "ハンドル番号のサイズ変更")

デフォルトの実装では`GetHandleMask`、サイズ変更ハンドルが表示されるようにビットのマスクを返します。 単一ビットがオンの場合、対応するサイズ変更ハンドルが描画されます。

指定したサイズ変更ハンドルの表示/非表示を切り替える場合は、このメンバー関数をオーバーライドします。

## <a name="crecttrackergettruerect"></a><a name="gettruerect"></a>クレストトラッカー::ゲットトゥルーレック

四角形の座標を取得します。

```
void GetTrueRect(LPRECT lpTrueRect) const;
```

### <a name="parameters"></a>パラメーター

*ルトレクト*<br/>
オブジェクトの`RECT`デバイス座標を格納する構造体への`CRectTracker`ポインター。

### <a name="remarks"></a>解説

四角形の寸法には、外側の境界線上にあるサイズ変更ハンドルの高さと幅が含まれます。 *戻ると、lpTrueRect*は常にデバイス座標で正規化された四角形です。

## <a name="crecttrackerhittest"></a><a name="hittest"></a>クレストトラッカー::ヒットテスト

ユーザーがサイズ変更ハンドルをつかんだかどうかを調べます。

```
int HitTest(CPoint point) const;
```

### <a name="parameters"></a>パラメーター

*ポイント*<br/>
テストするポイント (デバイス座標)。

### <a name="return-value"></a>戻り値

返される値は列挙型`CRectTracker::TrackerHit`に基づいており、次のいずれかの値を持つことができます。

- `CRectTracker::hitNothing` -1

- `CRectTracker::hitTopLeft` 0

- `CRectTracker::hitTopRight`1

- `CRectTracker::hitBottomRight`2

- `CRectTracker::hitBottomLeft`3

- `CRectTracker::hitTop`4

- `CRectTracker::hitRight`5

- `CRectTracker::hitBottom`6

- `CRectTracker::hitLeft`7

- `CRectTracker::hitMiddle`8

## <a name="crecttrackerm_nhandlesize"></a><a name="m_nhandlesize"></a>クレストトラッカー::m_nHandleSize

サイズ変更ハンドルのサイズ (`CRectTracker`ピクセル単位)。

```
int m_nHandleSize;
```

### <a name="remarks"></a>解説

既定のシステム値で初期化されます。

## <a name="crecttrackerm_rect"></a><a name="m_rect"></a>クレストトラッカー::m_rect

クライアント座標 (ピクセル単位) での四角形の現在位置。

```
CRect m_rect;
```

## <a name="crecttrackerm_sizemin"></a><a name="m_sizemin"></a>クレストトラッカー::m_sizeMin

四角形の最小サイズ。

```
CSize m_sizeMin;
```

### <a name="remarks"></a>解説

既定値と は`cx``cy`どちらも、境界幅のシステムの既定値から計算されます。 このデータ メンバーは、メンバー関数`AdjustRect`でのみ使用されます。

## <a name="crecttrackerm_nstyle"></a><a name="m_nstyle"></a>クレストトラッカー::m_nStyle

四角形の現在のスタイル。

```
UINT m_nStyle;
```

### <a name="remarks"></a>解説

可能なスタイルのリストについては[、CRectTracker::CRectTracker](#crecttracker)を参照してください。

## <a name="crecttrackernormalizehit"></a><a name="normalizehit"></a>クレストトラッカー::ノーマライズヒット

反転する可能性のあるハンドルを変換します。

```
int NormalizeHit(int nHandle) const;
```

### <a name="parameters"></a>パラメーター

*nハンドル*<br/>
ユーザーが選択したハンドル。

### <a name="return-value"></a>戻り値

正規化されたハンドルのインデックス。

### <a name="remarks"></a>解説

反転`CRectTracker::Track`を`CRectTracker::TrackRubberBand`許可して呼び出したり呼び出したりすると、X 軸、y 軸、またはその両方で長方形を反転できます。 この場合、`HitTest`四角形に対しても反転したハンドルを返します。 フィードバックは四角形の画面位置に依存するため、変更される四角形のデータ構造の一部ではないため、カーソルのフィードバックを描画する場合には不適切です。

## <a name="crecttrackeronchangedrect"></a><a name="onchangedrect"></a>クレストトラッカー::オン変更レック

トラッカーの四角形が 呼び出し中に変更されるたびに`Track`、フレームワークによって呼び出されます。

```
virtual void OnChangedRect(const CRect& rectOld);
```

### <a name="parameters"></a>パラメーター

*直腸古い*<br/>
オブジェクトの古いデバイス座標を`CRectTracker`格納します。

### <a name="remarks"></a>解説

この関数が呼び出された時点で`DrawTrackerRect`、描画されたすべてのフィードバックは削除されています。 この関数の既定の実装は、何も行いません。

四角形のサイズを変更した後にアクションを実行する場合は、この関数をオーバーライドします。

## <a name="crecttrackersetcursor"></a><a name="setcursor"></a>クレットトラッカー::セットカーソル

オブジェクトの領域上にあるカーソルの形状を`CRectTracker`変更します。

```
BOOL SetCursor(
    CWnd* pWnd,
    UINT nHitTest) const;
```

### <a name="parameters"></a>パラメーター

*Pwnd*<br/>
現在カーソルが含まれているウィンドウへのポインタ。

*ヒットテスト*<br/>
WM_SETCURSOR メッセージからの前回のヒット テストの結果。

### <a name="return-value"></a>戻り値

前回のヒットがトラッカーの四角形を超えていた場合は 0 以外。それ以外の場合は 0。

### <a name="remarks"></a>解説

WM_SETCURSORメッセージを処理するウィンドウの関数の内部からこの関数を呼び出`OnSetCursor`します (通常は )。

## <a name="crecttrackertrack"></a><a name="track"></a>クレストトラッカー::トラック

四角形のサイズを変更するためのユーザー インターフェイスを表示します。

```
BOOL Track(
    CWnd* pWnd,
    CPoint point,
    BOOL bAllowInvert = FALSE,
    CWnd* pWndClipTo = NULL);
```

### <a name="parameters"></a>パラメーター

*Pwnd*<br/>
四角形を含むウィンドウ オブジェクト。

*ポイント*<br/>
クライアント領域を基準とした現在のマウス位置のデバイス座標。

*を許可する*<br/>
TRUE の場合、四角形は X 軸または y 軸に沿って反転できます。それ以外の場合は FALSE。

*クリップ*<br/>
描画操作がクリップされるウィンドウ。 NULL の場合 *、pWnd*はクリッピング四角形として使用されます。

### <a name="return-value"></a>戻り値

Esc キーを押すと、追跡プロセスが停止し、トラッカーに格納されている四角形は変更されず、0 が返されます。 変更がコミットされると、マウスを動かしてマウスの左ボタンを放すと、新しい位置やサイズがトラッカーの長方形に記録され、ゼロ以外が返されます。

### <a name="remarks"></a>解説

通常、このメソッドは`WM_LBUTTONDOWN`、メッセージを処理するアプリケーションの関数 (通常`OnLButtonDown`は ) から呼び出されます。

この関数は、ユーザーがマウスの左ボタンを離すか、Esc キーを押すか、マウスの右ボタンを押すまでマウスをキャプチャします。 ユーザーがマウス カーソルを移動すると、フィードバックは 呼び`DrawTrackerRect`出`OnChangedRect`しと で更新されます。

*bAllowInvert*が TRUE の場合、トラッキング四角形は X 軸または y 軸で反転できます。

## <a name="crecttrackertrackrubberband"></a><a name="trackrubberband"></a>クレストトラッカー::トラックラバーバンド

この関数を呼び出して、ラバーバンド選択を行います。

```
BOOL TrackRubberBand(
    CWnd* pWnd,
    CPoint point,
    BOOL bAllowInvert = TRUE);
```

### <a name="parameters"></a>パラメーター

*Pwnd*<br/>
四角形を含むウィンドウ オブジェクト。

*ポイント*<br/>
クライアント領域を基準とした現在のマウス位置のデバイス座標。

*を許可する*<br/>
TRUE の場合、四角形は X 軸または y 軸に沿って反転できます。それ以外の場合は FALSE。

### <a name="return-value"></a>戻り値

マウスが移動し、四角形が空でない場合は 0 以外の値を返します。それ以外の場合は 0。

### <a name="remarks"></a>解説

通常、WM_LBUTTONDOWNメッセージを処理するアプリケーションの関数 (通常`OnLButtonDown`は ) から呼び出されます。

この関数は、ユーザーがマウスの左ボタンを離すか、Esc キーを押すか、マウスの右ボタンを押すまでマウスをキャプチャします。 ユーザーがマウス カーソルを移動すると、フィードバックは 呼び`DrawTrackerRect`出`OnChangedRect`しと で更新されます。

追跡は右下ハンドルからゴムバンドタイプの選択で行われます。 反転が許可されている場合、矩形のサイズは、上下左右にドラッグしてサイズ変更できます。

## <a name="see-also"></a>関連項目

[MFC サンプル トラッカー](../../overview/visual-cpp-samples.md)<br/>
[MFC サンプル ドローCLI](../../overview/visual-cpp-samples.md)<br/>
[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[クラスを変更します。](../../mfc/reference/coleresizebar-class.md)<br/>
[CRect クラス](../../atl-mfc-shared/reference/crect-class.md)

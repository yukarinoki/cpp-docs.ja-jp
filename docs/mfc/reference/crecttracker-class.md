---
title: CRectTracker クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
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
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: eff57e1fde0af6e794c2c47db7d1e31daf545715
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="crecttracker-class"></a>CRectTracker クラス
項目を表示、移動、または異なる方法でサイズ変更を許可します。  
  
## <a name="syntax"></a>構文  
  
```  
class CRectTracker  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[利用](#crecttracker)|`CRectTracker` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CRectTracker::AdjustRect](#adjustrect)|四角形のサイズが変更されるときに呼び出されます。|  
|[CRectTracker::Draw](#draw)|四角形を表示します。|  
|[CRectTracker::DrawTrackerRect](#drawtrackerrect)|境界線を描画するときに呼び出されます、`CRectTracker`オブジェクト。|  
|[CRectTracker::GetHandleMask](#gethandlemask)|マスクを取得すると呼ばれる、`CRectTracker`アイテムのサイズ変更ハンドル。|  
|[CRectTracker::GetTrueRect](#gettruerect)|サイズ変更ハンドルを含む四角形の幅と高さを返します。|  
|[CRectTracker::HitTest](#hittest)|関連する、カーソルの現在位置を返します、`CRectTracker`オブジェクト。|  
|[CRectTracker::NormalizeHit](#normalizehit)|ヒット テストのコードを正規化します。|  
|[CRectTracker::OnChangedRect](#onchangedrect)|四角形のサイズを変更または移動されたときに呼び出されます。|  
|[CRectTracker::SetCursor](#setcursor)|四角形の上の位置によって、カーソル位置を設定します。|  
|[反転](#track)|四角形を操作することができます。|  
|[CRectTracker::TrackRubberBand](#trackrubberband)|ユーザーが「ラバー バンド」を選択できるようにします。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CRectTracker::m_nHandleSize](#m_nhandlesize)|サイズ変更ハンドルのサイズを決定します。|  
|[CRectTracker::m_nStyle](#m_nstyle)|トラッカーの現在のスタイル。|  
|[裏返し](#m_rect)|内の現在位置 (ピクセル単位) の四角形。|  
|[CRectTracker::m_sizeMin](#m_sizemin)|最小の四角形の幅と高さを決定します。|  
  
## <a name="remarks"></a>コメント  
 `CRectTracker` 基本クラスはありません。  
  
 ただし、`CRectTracker`クラスがグラフィカル インターフェイスを使用して OLE アイテムと対話するユーザーを許可するように設計、使用することは OLE 対応のアプリケーションに限定されません。 使用できる任意の場所、このようなユーザー インターフェイスが必要です。  
  
 `CRectTracker` 純色、罫線または点線。 アイテムの破線の境界線または斜線パターン、アイテムのさまざまな状態を示すために重なって表示できます。 8 つのサイズ変更ハンドルを配置するには、外側または内側のいずれかのアイテムの罫線。 (サイズ変更ハンドルの詳細については、次を参照してください[GetHandleMask](#gethandlemask)。)。最後に、`CRectTracker`方向を変更する項目のサイズ変更中にすることができます。  
  
 使用する`CRectTracker`、構築、`CRectTracker`オブジェクトを指定する表示状態が初期化されます。 関連付けられている OLE 項目の現在の状態のユーザーの視覚的フィードバックを提供する、このインターフェイスを使用することができますし、`CRectTracker`オブジェクト。  
  
 使用する方法について`CRectTracker`、記事を参照して[トラッカー](../../mfc/trackers.md)です。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `CRectTracker`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxext.h  
  
##  <a name="adjustrect"></a>  CRectTracker::AdjustRect  
 サイズ変更ハンドルを使用して追跡四角形のサイズが変更されるときに、フレームワークによって呼び出されます。  
  
```  
virtual void AdjustRect(
    int nHandle,  
    LPRECT lpRect);
```  
  
### <a name="parameters"></a>パラメーター  
 `nHandle`  
 使用されるハンドルのインデックス。  
  
 `lpRect`  
 四角形の現在のサイズへのポインター。 (四角形のサイズは、その高さと幅によって得られます)。  
  
### <a name="remarks"></a>コメント  
 この関数の既定の動作により、変更される場合にのみ、四角形の向き`Track`と`TrackRubberBand`許可と呼ばれます。  
  
 ドラッグ操作中に追跡四角形の調整を制御するには、この関数をオーバーライドします。 1 つの方法は、によって指定された座標を調整する`lpRect`を返す前にします。  
  
 特別な機能によって直接サポートされていない`CRectTracker`など、グリッドにスナップまたは縦横比の保持は、この関数をオーバーライドすることで実装できます。  
  
##  <a name="crecttracker"></a>  利用  
 作成して初期化、`CRectTracker`オブジェクト。  
  
```  
CRectTracker();

 
CRectTracker(
    LPCRECT lpSrcRect,  
    UINT nStyle);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpSrcRect`  
 Rectangle オブジェクトの座標。  
  
 `nStyle`  
 スタイルを指定します、`CRectTracker`オブジェクト。 次のスタイルがサポートされています。  
  
- **CRectTracker::solidLine**四角形の境界線の実線を使用します。  
  
- **CRectTracker::dottedLine**の四角形の枠線、点線を使用します。  
  
- **CRectTracker::hatchedBorder**四角形の境界線を斜線パターンを使用します。  
  
- **CRectTracker::resizeInside**四角形の内側にあるハンドルのサイズを変更します。  
  
- **CRectTracker::resizeOutside**四角形の外部にあるハンドルのサイズを変更します。  
  
- **CRectTracker::hatchInside** Hatched パターンは、四角形全体をカバーします。  
  
### <a name="remarks"></a>コメント  
 既定のコンス トラクター、`CRectTracker`から値を持つオブジェクト`lpSrcRect`し、その他のサイズをシステムの既定値を初期化します。 パラメーターなしで、オブジェクトが作成された場合、`m_rect`と`m_nStyle`データ メンバーは初期化されていません。  
  
##  <a name="draw"></a>  CRectTracker::Draw  
 四角形の外枠と内部の領域を描画するには、この関数を呼び出します。  
  
```  
void Draw(CDC* pDC) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `pDC`  
 描画するデバイス コンテキストへのポインター。  
  
### <a name="remarks"></a>コメント  
 トラッカーのスタイルは、描画を実行する方法を決定します。 コンス トラクターを参照してください`CRectTracker`詳細については、使用可能なスタイル。  
  
##  <a name="drawtrackerrect"></a>  CRectTracker::DrawTrackerRect  
 トラッカーの位置が変更されるたびに、フレームワークによって呼び出さ内中に、`Track`または`TrackRubberBand`メンバー関数。  
  
```  
virtual void DrawTrackerRect(
    LPCRECT lpRect,  
    CWnd* pWndClipTo,  
    CDC* pDC,  
    CWnd* pWnd);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpRect`  
 ポインター、`RECT`描画する四角形を格納しています。  
  
 `pWndClipTo`  
 クリッピング四角形で使用するウィンドウへのポインター。  
  
 `pDC`  
 描画するデバイス コンテキストへのポインター。  
  
 `pWnd`  
 ウィンドウの描画が発生する可能性へのポインター。  
  
### <a name="remarks"></a>コメント  
 既定の実装への呼び出しは、 `CDC::DrawFocusRect`、ピリオドで区切られた四角形を描画します。  
  
 フィードバックを提供するさまざまな追跡操作中にこの関数をオーバーライドします。  
  
##  <a name="gethandlemask"></a>  CRectTracker::GetHandleMask  
 フレームワークは、四角形のサイズ変更ハンドルをマスクを取得するには、このメンバー関数を呼び出します。  
  
```  
virtual UINT GetHandleMask() const;  
```  
  
### <a name="return-value"></a>戻り値  
 マスクは、`CRectTracker`アイテムのハンドルのサイズを変更します。  
  
### <a name="remarks"></a>コメント  
 サイズ変更ハンドルは、両側または四角形の角に表示され、図形や四角形のサイズを制御するアクセス許可。  
  
 四角形には、8 のサイズ変更ハンドルが 0 ~ 7 の番号があります。 各サイズ変更ハンドルによってを表されるビット マスクです。そのビットの値は 2 ^ *n*ここで、 *n*サイズ変更ハンドル数です。 ビット 0-3 は、角の開始位置として、左時計回りにサイズ変更ハンドルに対応します。 Bits 4 ~ 7 の側面に対応しているにサイズ変更ハンドル時計回り上部で開始を指定します。 次の図は、四角形のサイズ変更を処理し、それに対応するハンドル番号と値のサイズを変更します。  
  
 ![ハンドル番号のサイズを変更する](../../mfc/reference/media/vc35dp1.gif "vc35dp1")  
  
 既定の実装**GetHandleMask**サイズ変更ハンドルが表示されるようにビットのマスクを返します。 1 つのビットがオンの場合は、対応するサイズ変更ハンドルが描画されます。  
  
 指定したサイズ変更ハンドルを表示または非表示には、このメンバー関数をオーバーライドします。  
  
##  <a name="gettruerect"></a>  CRectTracker::GetTrueRect  
 四角形の座標を取得するには、この関数を呼び出します。  
  
```  
void GetTrueRect(LPRECT lpTrueRect) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `lpTrueRect`  
 ポインター、`RECT`座標と、デバイスを含む構造体、`CRectTracker`オブジェクト。  
  
### <a name="remarks"></a>コメント  
 四角形の寸法には、外側の境界線上にある任意のサイズ変更ハンドルの幅と高さが含まれます。 `lpTrueRect`は常に正規化されたデバイス座標の四角形。  
  
##  <a name="hittest"></a>  CRectTracker::HitTest  
 この関数では、ユーザーがサイズ変更ハンドルを取得するかどうかを確認します。  
  
```  
int HitTest(CPoint point) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `point`  
 テストする、デバイスの座標でのポイント。  
  
### <a name="return-value"></a>戻り値  
 返される値は列挙型に基づいて**CRectTracker::TrackerHit**値は次のいずれかを持つことができます。  
  
- **CRectTracker::hitNothing** -1  
  
- **CRectTracker::hitTopLeft** 0  
  
- **CRectTracker::hitTopRight** 1  
  
- **CRectTracker::hitBottomRight** 2  
  
- **CRectTracker::hitBottomLeft** 3  
  
- **CRectTracker::hitTop** 4  
  
- **CRectTracker::hitRight** 5  
  
- **CRectTracker::hitBottom** 6  
  
- **CRectTracker::hitLeft** 7  
  
- **CRectTracker::hitMiddle** 8  
  
##  <a name="m_nhandlesize"></a>  CRectTracker::m_nHandleSize  
 サイズをピクセル単位での`CRectTracker`ハンドルのサイズを変更します。  
  
```  
int m_nHandleSize;  
```  
  
### <a name="remarks"></a>コメント  
 システムの既定値で初期化します。  
  
##  <a name="m_rect"></a>  裏返し  
 四角形の現在の位置をクライアント座標 (ピクセル単位)。  
  
```  
CRect m_rect;  
```  
  
##  <a name="m_sizemin"></a>  CRectTracker::m_sizeMin  
 四角形の最小サイズ。  
  
```  
CSize m_sizeMin;  
```  
  
### <a name="remarks"></a>コメント  
 両方の既定値**cx**と**cy**罫線の幅に関する既定のシステム値から計算されます。 このデータ メンバーのみが使用、`AdjustRect`メンバー関数。  
  
##  <a name="m_nstyle"></a>  CRectTracker::m_nStyle  
 四角形の現在のスタイルです。  
  
```  
UINT m_nStyle;  
```  
  
### <a name="remarks"></a>コメント  
 参照してください[利用](#crecttracker)可能なスタイルの一覧についてはします。  
  
##  <a name="normalizehit"></a>  CRectTracker::NormalizeHit  
 反転された可能性があるハンドルを変換するには、この関数を呼び出します。  
  
```  
int NormalizeHit(int nHandle) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `nHandle`  
 ユーザーが選択されているハンドルです。  
  
### <a name="return-value"></a>戻り値  
 正規化されたハンドルのインデックス。  
  
### <a name="remarks"></a>コメント  
 ときに`CRectTracker::Track`または`CRectTracker::TrackRubberBand`が呼び出された許可を反転するには、使用可能であれば、x 軸と y 軸のどちらか一方または両方に反転される四角形のです。 この場合、`HitTest`は四角形反転がハンドルを返します。 これはカーソルのフィードバックの描画の適切なフィードバックが変更される四角形のデータ構造の部分ではなく、四角形の画面位置に依存するためです。  
  
##  <a name="onchangedrect"></a>  CRectTracker::OnChangedRect  
 トラッカー四角形の呼び出し中に変更されるたびに、フレームワークによって呼び出さ`Track`です。  
  
```  
virtual void OnChangedRect(const CRect& rectOld);
```  
  
### <a name="parameters"></a>パラメーター  
 *rectOld*  
 古いデバイス座標が含まれています、`CRectTracker`オブジェクト。  
  
### <a name="remarks"></a>コメント  
 時、この関数が呼び出されで描画されたすべてのフィードバック`DrawTrackerRect`は削除されました。 この関数の既定の実装は、何も行いません。  
  
 四角形のサイズが変更された後、すべてのアクションを実行する場合は、この関数をオーバーライドします。  
  
##  <a name="setcursor"></a>  CRectTracker::SetCursor  
 上では、カーソルの形状を変更するには、この関数を呼び出して、`CRectTracker`のオブジェクトの領域。  
  
```  
BOOL SetCursor(
    CWnd* pWnd,  
    UINT nHitTest) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `pWnd`  
 現在カーソルが含まれるウィンドウへのポインター。  
  
 `nHitTest`  
 前のヒット テストの結果から、`WM_SETCURSOR`メッセージ。  
  
### <a name="return-value"></a>戻り値  
 前の検索結果がトラッカー四角形の; 経由の場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 この関数は、処理するウィンドウの関数の内部から呼び出す、`WM_SETCURSOR`メッセージ (通常`OnSetCursor`)。  
  
##  <a name="track"></a>  反転  
 四角形のサイズ変更用ユーザー インターフェイスを表示するには、この関数を呼び出します。  
  
```  
BOOL Track(
    CWnd* pWnd,  
    CPoint point,  
    BOOL bAllowInvert = FALSE,  
    CWnd* pWndClipTo = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 `pWnd`  
 四角形を含むウィンドウのオブジェクト。  
  
 `point`  
 クライアント領域と相対的現在、マウスの位置のデバイスの座標。  
  
 `bAllowInvert`  
 場合**TRUE**、四角形は、それ以外の x 軸または y 軸に沿って反転**FALSE**です。  
  
 `pWndClipTo`  
 このウィンドウは、描画操作は、クリップされます。 場合**NULL**、`pWnd`クリッピング四角形として使用されます。  
  
### <a name="return-value"></a>戻り値  
 ESC キーが押された場合は、追跡プロセスが中止し、トラッカーに格納されている四角形は変更されません 0 が返されます。 変更がコミットされた場合は、マウスを移動し、マウスの左ボタンを解放する、新しい位置とサイズがトラッカーの四角形に記録され、0 以外の値が返されます。  
  
### <a name="remarks"></a>コメント  
 通常、処理するアプリケーションの関数の内部から呼び出されます、`WM_LBUTTONDOWN`メッセージ (通常`OnLButtonDown`)。  
  
 この関数は、ユーザーがマウスの左ボタンを離す、ESC キーを押すかマウスの右ボタンを押すまでに、マウスをキャプチャします。 フィードバックが呼び出すことによって更新されたユーザーがマウス カーソルを移動した`DrawTrackerRect`と`OnChangedRect`です。  
  
 場合`bAllowInvert`は**TRUE**、x 軸または y 軸のいずれかで追跡四角形を反転することができます。  
  
##  <a name="trackrubberband"></a>  CRectTracker::TrackRubberBand  
 ラバー バンドの選択を行うには、この関数を呼び出します。  
  
```  
BOOL TrackRubberBand(
    CWnd* pWnd,  
    CPoint point,  
    BOOL bAllowInvert = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 `pWnd`  
 四角形を含むウィンドウのオブジェクト。  
  
 `point`  
 クライアント領域と相対的現在、マウスの位置のデバイスの座標。  
  
 `bAllowInvert`  
 場合**true の場合、**四角形は、それ以外の x 軸または y 軸に沿って反転**FALSE**です。  
  
### <a name="return-value"></a>戻り値  
 マウスが移動、および四角形は空以外ではない場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 通常、処理するアプリケーションの関数の内部から呼び出された、`WM_LBUTTONDOWN`メッセージ (通常`OnLButtonDown`)。  
  
 この関数は、ユーザーがマウスの左ボタンを離す、ESC キーを押すかマウスの右ボタンを押すまでに、マウスをキャプチャします。 フィードバックが呼び出すことによって更新されたユーザーがマウス カーソルを移動した`DrawTrackerRect`と`OnChangedRect`です。  
  
 右下隅のハンドルからラバー バンド タイプの選択内容の追跡が実行されます。 反転が許可された場合、四角形がいずれかを左またはダウンおよび右側にドラッグしてサイズことができます。  
  
## <a name="see-also"></a>関連項目  
 [MFC サンプルの追跡ツール](../../visual-cpp-samples.md)   
 [MFC サンプル DRAWCLI](../../visual-cpp-samples.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [COleResizeBar クラス](../../mfc/reference/coleresizebar-class.md)   
 [CRect クラス](../../atl-mfc-shared/reference/crect-class.md)

---
title: CRenderTarget クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CRenderTarget
- AFXRENDERTARGET/CRenderTarget
- AFXRENDERTARGET/CRenderTarget::CRenderTarget
- AFXRENDERTARGET/CRenderTarget::Attach
- AFXRENDERTARGET/CRenderTarget::BeginDraw
- AFXRENDERTARGET/CRenderTarget::Clear
- AFXRENDERTARGET/CRenderTarget::COLORREF_TO_D2DCOLOR
- AFXRENDERTARGET/CRenderTarget::CreateCompatibleRenderTarget
- AFXRENDERTARGET/CRenderTarget::Destroy
- AFXRENDERTARGET/CRenderTarget::Detach
- AFXRENDERTARGET/CRenderTarget::DrawBitmap
- AFXRENDERTARGET/CRenderTarget::DrawEllipse
- AFXRENDERTARGET/CRenderTarget::DrawGeometry
- AFXRENDERTARGET/CRenderTarget::DrawGlyphRun
- AFXRENDERTARGET/CRenderTarget::DrawLine
- AFXRENDERTARGET/CRenderTarget::DrawRectangle
- AFXRENDERTARGET/CRenderTarget::DrawRoundedRectangle
- AFXRENDERTARGET/CRenderTarget::DrawText
- AFXRENDERTARGET/CRenderTarget::DrawTextLayout
- AFXRENDERTARGET/CRenderTarget::EndDraw
- AFXRENDERTARGET/CRenderTarget::FillEllipse
- AFXRENDERTARGET/CRenderTarget::FillGeometry
- AFXRENDERTARGET/CRenderTarget::FillMesh
- AFXRENDERTARGET/CRenderTarget::FillOpacityMask
- AFXRENDERTARGET/CRenderTarget::FillRectangle
- AFXRENDERTARGET/CRenderTarget::FillRoundedRectangle
- AFXRENDERTARGET/CRenderTarget::Flush
- AFXRENDERTARGET/CRenderTarget::GetAntialiasMode
- AFXRENDERTARGET/CRenderTarget::GetDpi
- AFXRENDERTARGET/CRenderTarget::GetMaximumBitmapSize
- AFXRENDERTARGET/CRenderTarget::GetPixelFormat
- AFXRENDERTARGET/CRenderTarget::GetPixelSize
- AFXRENDERTARGET/CRenderTarget::GetRenderTarget
- AFXRENDERTARGET/CRenderTarget::GetSize
- AFXRENDERTARGET/CRenderTarget::GetTags
- AFXRENDERTARGET/CRenderTarget::GetTextAntialiasMode
- AFXRENDERTARGET/CRenderTarget::GetTextRenderingParams
- AFXRENDERTARGET/CRenderTarget::GetTransform
- AFXRENDERTARGET/CRenderTarget::IsSupported
- AFXRENDERTARGET/CRenderTarget::IsValid
- AFXRENDERTARGET/CRenderTarget::PopAxisAlignedClip
- AFXRENDERTARGET/CRenderTarget::PopLayer
- AFXRENDERTARGET/CRenderTarget::PushAxisAlignedClip
- AFXRENDERTARGET/CRenderTarget::PushLayer
- AFXRENDERTARGET/CRenderTarget::RestoreDrawingState
- AFXRENDERTARGET/CRenderTarget::SaveDrawingState
- AFXRENDERTARGET/CRenderTarget::SetAntialiasMode
- AFXRENDERTARGET/CRenderTarget::SetDpi
- AFXRENDERTARGET/CRenderTarget::SetTags
- AFXRENDERTARGET/CRenderTarget::SetTextAntialiasMode
- AFXRENDERTARGET/CRenderTarget::SetTextRenderingParams
- AFXRENDERTARGET/CRenderTarget::SetTransform
- AFXRENDERTARGET/CRenderTarget::VerifyResource
- AFXRENDERTARGET/CRenderTarget::m_lstResources
- AFXRENDERTARGET/CRenderTarget::m_pRenderTarget
- AFXRENDERTARGET/CRenderTarget::m_pTextFormatDefault
dev_langs:
- C++
helpviewer_keywords:
- CRenderTarget [MFC], CRenderTarget
- CRenderTarget [MFC], Attach
- CRenderTarget [MFC], BeginDraw
- CRenderTarget [MFC], Clear
- CRenderTarget [MFC], COLORREF_TO_D2DCOLOR
- CRenderTarget [MFC], CreateCompatibleRenderTarget
- CRenderTarget [MFC], Destroy
- CRenderTarget [MFC], Detach
- CRenderTarget [MFC], DrawBitmap
- CRenderTarget [MFC], DrawEllipse
- CRenderTarget [MFC], DrawGeometry
- CRenderTarget [MFC], DrawGlyphRun
- CRenderTarget [MFC], DrawLine
- CRenderTarget [MFC], DrawRectangle
- CRenderTarget [MFC], DrawRoundedRectangle
- CRenderTarget [MFC], DrawText
- CRenderTarget [MFC], DrawTextLayout
- CRenderTarget [MFC], EndDraw
- CRenderTarget [MFC], FillEllipse
- CRenderTarget [MFC], FillGeometry
- CRenderTarget [MFC], FillMesh
- CRenderTarget [MFC], FillOpacityMask
- CRenderTarget [MFC], FillRectangle
- CRenderTarget [MFC], FillRoundedRectangle
- CRenderTarget [MFC], Flush
- CRenderTarget [MFC], GetAntialiasMode
- CRenderTarget [MFC], GetDpi
- CRenderTarget [MFC], GetMaximumBitmapSize
- CRenderTarget [MFC], GetPixelFormat
- CRenderTarget [MFC], GetPixelSize
- CRenderTarget [MFC], GetRenderTarget
- CRenderTarget [MFC], GetSize
- CRenderTarget [MFC], GetTags
- CRenderTarget [MFC], GetTextAntialiasMode
- CRenderTarget [MFC], GetTextRenderingParams
- CRenderTarget [MFC], GetTransform
- CRenderTarget [MFC], IsSupported
- CRenderTarget [MFC], IsValid
- CRenderTarget [MFC], PopAxisAlignedClip
- CRenderTarget [MFC], PopLayer
- CRenderTarget [MFC], PushAxisAlignedClip
- CRenderTarget [MFC], PushLayer
- CRenderTarget [MFC], RestoreDrawingState
- CRenderTarget [MFC], SaveDrawingState
- CRenderTarget [MFC], SetAntialiasMode
- CRenderTarget [MFC], SetDpi
- CRenderTarget [MFC], SetTags
- CRenderTarget [MFC], SetTextAntialiasMode
- CRenderTarget [MFC], SetTextRenderingParams
- CRenderTarget [MFC], SetTransform
- CRenderTarget [MFC], VerifyResource
- CRenderTarget [MFC], m_lstResources
- CRenderTarget [MFC], m_pRenderTarget
- CRenderTarget [MFC], m_pTextFormatDefault
ms.assetid: 30d1607d-68d3-4d14-ac36-fdbd0ef903a1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 6ab1f4a056e1a65475a71ede0b51db45189d2dd9
ms.sourcegitcommit: be0e3457f2884551f18e183ef0ea65c3ded7f689
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/28/2018
ms.locfileid: "37079761"
---
# <a name="crendertarget-class"></a>CRenderTarget クラス
ID2D1RenderTarget のラッパーです。  
  
## <a name="syntax"></a>構文  
  
```  
class CRenderTarget : public CObject;  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CRenderTarget::CRenderTarget](#crendertarget)|CRenderTarget オブジェクトを構築します。|  
|[CRenderTarget:: ~ CRenderTarget](#crendertarget__~crendertarget)|デストラクターです。 レンダー ターゲット オブジェクトが破棄されるときに呼び出されます。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CRenderTarget::Attach](#attach)|既存の接続オブジェクトを対象のインターフェイスを表示します。|  
|[CRenderTarget::BeginDraw](#begindraw)|このレンダー ターゲット上に描画を開始します。|  
|[CRenderTarget::Clear](#clear)|指定された色を描画領域をクリアします。|  
|[CRenderTarget::COLORREF_TO_D2DCOLOR](#colorref_to_d2dcolor)|GDI の色とアルファ値を D2D1_COLOR_F オブジェクトに変換します。|  
|[CRenderTarget::CreateCompatibleRenderTarget](#createcompatiblerendertarget)|現在のレンダー ターゲットと互換性がある中間スクリーン描画時に使用するための新しいビットマップ レンダー ターゲットを作成します。|  
|[CRenderTarget::Destroy](#destroy)|1 つまたは複数のリソースを削除します。|  
|[CRenderTarget::Detach](#detach)|レンダー ターゲット インターフェイス オブジェクトからのデタッチします。|  
|[CRenderTarget::DrawBitmap](#drawbitmap)|指定した IDWriteTextLayout オブジェクトによって記述されたフォーマットされたテキストを描画します。|  
|[CRenderTarget::DrawEllipse](#drawellipse)|指定した線のスタイルを使用して、指定された楕円のアウトラインを描画します。|  
|[CRenderTarget::DrawGeometry](#drawgeometry)|指定した線のスタイルを使用して指定した形状のアウトラインを描画します。|  
|[CRenderTarget::DrawGlyphRun](#drawglyphrun)|指定したグリフを描画します。|  
|[CRenderTarget::DrawLine](#drawline)|指定した線のスタイルを使用して指定した点の間の線を描画します。|  
|[CRenderTarget::DrawRectangle](#drawrectangle)|指定した寸法と線のスタイルを持つ四角形のアウトラインを描画します。|  
|[CRenderTarget::DrawRoundedRectangle](#drawroundedrectangle)|指定した線のスタイルを使用して、指定した丸みのある四角形のアウトラインを描画します。|  
|[CRenderTarget::DrawText](#drawtext)|IDWriteTextFormat オブジェクトによって提供される形式の情報を使用して、指定したテキストを描画します。|  
|[CRenderTarget::DrawTextLayout](#drawtextlayout)|指定した IDWriteTextLayout オブジェクトによって記述されたフォーマットされたテキストを描画します。|  
|[CRenderTarget::EndDraw](#enddraw)|レンダー ターゲット上で描画操作を終了し、現在のエラー状態と関連付けられているタグを示します。|  
|[CRenderTarget::FillEllipse](#fillellipse)|指定された楕円の内部を描画します。|  
|[CRenderTarget::FillGeometry](#fillgeometry)|指定した形状の内部を描画します。|  
|[CRenderTarget::FillMesh](#fillmesh)|指定したメッシュの内部を描画します。|  
|[CRenderTarget::FillOpacityMask](#fillopacitymask)|ブラシを指定したビットマップが示す不透明マスクを適用し、レンダー ターゲットの領域を塗りつぶすそのブラシを使用します。|  
|[CRenderTarget::FillRectangle](#fillrectangle)|指定した四角形の内部を描画します。|  
|[CRenderTarget::FillRoundedRectangle](#fillroundedrectangle)|指定した丸みのある四角形の内部を描画します。|  
|[CRenderTarget::Flush](#flush)|保留中のすべての描画コマンドを実行します。|  
|[CRenderTarget::GetAntialiasMode](#getantialiasmode)|テキスト以外の描画操作の現在の (アンチエイリアシング) モードを取得します。|  
|[CRenderTarget::GetDpi](#getdpi)|レンダリング ターゲットのドット/インチ (DPI) を返します|  
|[CRenderTarget::GetMaximumBitmapSize](#getmaximumbitmapsize)|レンダー ターゲットでサポートされている任意の 1 つのビットマップ ディメンションのデバイスに依存する単位 (ピクセル単位) で最大のサイズを取得します。|  
|[CRenderTarget::GetPixelFormat](#getpixelformat)|レンダー ターゲットのピクセル形式とアルファ モードを取得します。|  
|[CRenderTarget::GetPixelSize](#getpixelsize)|デバイス ピクセル単位で、レンダー ターゲットのサイズを返します|  
|[CRenderTarget::GetRenderTarget](#getrendertarget)|返します ID2D1RenderTarget インターフェイス|  
|[CRenderTarget::GetSize](#getsize)|デバイスに依存しないピクセル単位で、レンダー ターゲットのサイズを返します|  
|[CRenderTarget::GetTags](#gettags)|後続の描画操作のラベルを取得します。|  
|[CRenderTarget::GetTextAntialiasMode](#gettextantialiasmode)|テキストとグリフが描画操作の現在の (アンチエイリアシング) モードを取得します。|  
|[CRenderTarget::GetTextRenderingParams](#gettextrenderingparams)|レンダー ターゲットの現在のテキスト レンダリング オプションを取得します。|  
|[CRenderTarget::GetTransform](#gettransform)|既存の変換を置き換える、レンダー ターゲットを指定した変換を適用します。 後続のすべての描画操作は、変換後のスペースで発生します。|  
|[CRenderTarget::IsSupported](#issupported)|レンダー ターゲットが、指定されたプロパティをサポートするかどうかを示します|  
|[CRenderTarget::IsValid](#isvalid)|リソースの有効性のチェック|  
|[CRenderTarget::PopAxisAlignedClip](#popaxisalignedclip)|レンダー ターゲットから最後の軸に沿ったクリップを削除します。 このメソッドが呼び出されると、クリップは不要になった後続の描画操作に適用されます。|  
|[CRenderTarget::PopLayer](#poplayer)|最後の PushLayer で指定されているレイヤーの描画操作のリダイレクトを停止を呼び出します。|  
|[CRenderTarget::PushAxisAlignedClip](#pushaxisalignedclip)|レンダー ターゲットから最後の軸に沿ったクリップを削除します。 このメソッドが呼び出されると、クリップは不要になった後続の描画操作に適用されます。|  
|[CRenderTarget::PushLayer](#pushlayer)|PopLayer が呼び出されるまでは、後続のすべての描画操作を受信できるように、レンダー ターゲットに指定したレイヤーを追加します。|  
|[CRenderTarget::RestoreDrawingState](#restoredrawingstate)|指定した ID2D1DrawingStateBlock のレンダー ターゲットの描画状態を設定します。|  
|[CRenderTarget::SaveDrawingState](#savedrawingstate)|指定した ID2D1DrawingStateBlock に現在の描画状態を保存します。|  
|[CRenderTarget::SetAntialiasMode](#setantialiasmode)|レンダー ターゲットの (アンチエイリアシング) モードを設定します。 (アンチエイリアシング) モードは、テキストとグリフが描画操作を除く、すべての後続描画操作に適用されます。|  
|[CRenderTarget::SetDpi](#setdpi)|ドット/インチ (DPI) のレンダー ターゲットを設定します。|  
|[CRenderTarget::SetTags](#settags)|後続の描画操作のラベルを指定します。|  
|[CRenderTarget::SetTextAntialiasMode](#settextantialiasmode)|後続のテキストとグリフの描画操作に使用する (アンチエイリアシング) モードを指定します。|  
|[CRenderTarget::SetTextRenderingParams](#settextrenderingparams)|すべての後続のテキストとグリフが描画操作に適用するテキストのレンダリング オプションを指定します。|  
|[CRenderTarget::SetTransform](#settransform)|オーバーロードされます。 既存の変換を置き換える、レンダー ターゲットを指定した変換を適用します。 後続のすべての描画操作は、変換後のスペースで発生します。|  
  
### <a name="protected-methods"></a>プロテクト メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CRenderTarget::VerifyResource](#verifyresource)|CD2DResource オブジェクトの有効性; を検証します。存在しない場合は、オブジェクトを作成します。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[CRenderTarget::operator ID2D1RenderTarget *](#operator_id2d1rendertarget_star)|返します ID2D1RenderTarget インターフェイス|  
  
### <a name="protected-data-members"></a>プロテクト データ メンバー  
  
|name|説明|  
|----------|-----------------|  
|[CRenderTarget::m_lstResources](#m_lstresources)|CD2DResource オブジェクトへのポインターのリスト。|  
|[CRenderTarget::m_pRenderTarget](#m_prendertarget)|ID2D1RenderTarget オブジェクトへのポインター。|  
|[CRenderTarget::m_pTextFormatDefault](#m_ptextformatdefault)|既定のテキスト形式を格納している CD2DTextFormat オブジェクトへのポインター。|  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CRenderTarget](../../mfc/reference/crendertarget-class.md)  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** afxrendertarget.h  
  
##  <a name="_dtorcrendertarget"></a>  CRenderTarget:: ~ CRenderTarget  
 デストラクターです。 レンダー ターゲット オブジェクトが破棄されるときに呼び出されます。  
  
```  
virtual ~CRenderTarget();
```  
  
##  <a name="attach"></a>  CRenderTarget::Attach  
 既存の接続オブジェクトを対象のインターフェイスを表示します。  
  
```  
void Attach(ID2D1RenderTarget* pRenderTarget);
```  
  
### <a name="parameters"></a>パラメーター  
 *pRenderTarget*  
 既存のレンダー ターゲット インターフェイスです。 NULL をすることはできません。  
  
##  <a name="begindraw"></a>  CRenderTarget::BeginDraw  
 このレンダー ターゲット上に描画を開始します。  
  
```  
void BeginDraw();
```  
  
##  <a name="clear"></a>  CRenderTarget::Clear  
 指定された色を描画領域をクリアします。  
  
```  
void Clear(D2D1_COLOR_F color);
```  
  
### <a name="parameters"></a>パラメーター  
 *色*  
 描画領域をクリアする色です。  
  
##  <a name="colorref_to_d2dcolor"></a>  CRenderTarget::COLORREF_TO_D2DCOLOR  
 GDI の色とアルファ値を D2D1_COLOR_F オブジェクトに変換します。  
  
```  
static D2D1_COLOR_F COLORREF_TO_D2DCOLOR(
    COLORREF color,  
    int nAlpha = 255);
```  
  
### <a name="parameters"></a>パラメーター  
 *色*  
 RGB 値。  
  
 *nAlpha*  
  
### <a name="return-value"></a>戻り値  
 D2D1_COLOR_F 値です。  
  
##  <a name="createcompatiblerendertarget"></a>  CRenderTarget::CreateCompatibleRenderTarget  
 現在のレンダー ターゲットと互換性がある中間スクリーン描画時に使用するための新しいビットマップ レンダー ターゲットを作成します。  
  
```  
BOOL CreateCompatibleRenderTarget(
    CBitmapRenderTarget& bitmapTarget,  
    CD2DSizeF sizeDesired = CD2DSizeF(0., 0.), 
    CD2DSizeU sizePixelDesired = CD2DSizeU(0, 0), 
    D2D1_PIXEL_FORMAT* desiredFormat = NULL,  
    D2D1_COMPATIBLE_RENDER_TARGET_OPTIONS options = D2D1_COMPATIBLE_RENDER_TARGET_OPTIONS_NONE);
```  
  
### <a name="parameters"></a>パラメーター  
 *bitmapTarget*  
 このメソッドが戻るときに、新しいビットマップ レンダー ターゲットへのポインターのアドレスを格納します。 このパラメーターは初期化せずに渡されます。  
  
 *sizeDesired*  
 元と異なることがある場合、デバイスに依存しないピクセル単位で新しいレンダー ターゲットの目的のサイズは、レンダー ターゲット、または NULL。 詳細については、「解説」を参照してください。  
  
 *sizePixelDesired*  
 元と異なることが場合のピクセル単位で新しいレンダー ターゲットの目的のサイズは、レンダー ターゲット、または NULL。 詳細については、「解説」を参照してください。  
  
 *desiredFormat*  
 目的のピクセル形式と新しいアルファのモードは、レンダー ターゲット、または NULL。 DXGI_FORMAT_UNKNOWN するピクセル形式が設定されている場合、またはこのパラメーターが null の場合は、新しいレンダリング ターゲットは、元のレンダー ターゲットとして同じピクセル形式を使用します。 アルファ モードは D2D1_ALPHA_MODE_UNKNOWN またはこのパラメーターが NULL、D2D1_ALPHA_MODE_PREMULTIPLIED に新しいレンダー ターゲットのアルファ モードが既定値です。 サポートされているピクセル形式については、ピクセル形式のサポートとアルファ モードを参照してください。  
  
 *options*  
 新しいレンダリング ターゲットは、GDI と互換性があるかどうかを指定する値。  
  
### <a name="return-value"></a>戻り値  
 メソッドが成功した場合は TRUE を返します。 それ以外の場合、FALSE を返します。  
  
##  <a name="crendertarget"></a>  CRenderTarget::CRenderTarget  
 CRenderTarget オブジェクトを構築します。  
  
```  
CRenderTarget();
```  
  
##  <a name="destroy"></a>  CRenderTarget::Destroy  
 1 つまたは複数のリソースを削除します。  
  
```  
BOOL Destroy(BOOL bDeleteResources = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 *bDeleteResources*  
 BDeleteResources が TRUE の場合は、m_lstResources にあるすべてのリソースを自動的に破棄されます。  
  
### <a name="return-value"></a>戻り値  
 メソッドが成功した場合は TRUE を返します。 それ以外の場合は FALSE を返します  
  
##  <a name="detach"></a>  CRenderTarget::Detach  
 レンダー ターゲット インターフェイス オブジェクトからのデタッチします。  
  
```  
ID2D1RenderTarget* Detach ();
```  
  
### <a name="return-value"></a>戻り値  
 デタッチされたへのポインターは、対象のインターフェイスをレンダリングします。  
  
##  <a name="drawbitmap"></a>  CRenderTarget::DrawBitmap  
 指定した IDWriteTextLayout オブジェクトによって記述されたフォーマットされたテキストを描画します。  
  
```  
void DrawBitmap(
    CD2DBitmap* pBitmap,  
    const CD2DRectF& rectDest,  
    float fOpacity = 1.0,  
    D2D1_BITMAP_INTERPOLATION_MODE interpolationMode = D2D1_BITMAP_INTERPOLATION_MODE_LINEAR,  
    const CD2DRectF* pRectSrc = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 *pBitmap*  
 表示するためにビットマップです。  
  
 *rectDest*  
 サイズと、ビットマップが描画される領域のレンダー ターゲットの座標空間にデバイスに依存しないピクセル単位での位置。 かどうかは、四角形は適切な順序付けできませんが、何も描画されると、レンダー ターゲットがエラー状態を入力しません。  
  
 *fOpacity*  
 ビットマップに適用する不透明度の値を指定する 0.0f から 1.0f、両端を含む値この値は、ビットマップのコンテンツのアルファ値に対して乗算されます。  
  
 *interpolationMode*  
 ビットマップを拡大縮小または描画操作で回転場合に使用する補間モードです。  
  
 *pRectSrc*  
 サイズと、領域を描画するビットマップ内のビットマップの座標空間にデバイスに依存しないピクセル単位での位置。  
  
##  <a name="drawellipse"></a>  CRenderTarget::DrawEllipse  
 指定した線のスタイルを使用して、指定された楕円のアウトラインを描画します。  
  
```  
void DrawEllipse(
    const CD2DEllipse& ellipse,  
    CD2DBrush* pBrush,  
    FLOAT fStrokeWidth = 1.0,  
    ID2D1StrokeStyle* strokeStyle = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 *楕円*  
 位置と描くには、デバイスに依存しないピクセル単位で楕円の半径。  
  
 *pBrush*  
 楕円のアウトラインを描画するブラシ。  
  
 *fStrokeWidth*  
 楕円のストロークの太さ。 ストロークは、楕円のアウトラインで中央揃えされます。  
  
 *strokeStyle*  
 楕円のアウトライン表示、または線の描画に NULL を適用する線のスタイルです。  
  
##  <a name="drawgeometry"></a>  CRenderTarget::DrawGeometry  
 指定した線のスタイルを使用して指定した形状のアウトラインを描画します。  
  
```  
void DrawGeometry(
    CD2DGeometry* pGeometry,  
    CD2DBrush* pBrush,  
    FLOAT fStrokeWidth = 1.0,  
    ID2D1StrokeStyle* strokeStyle = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 *pGeometry*  
 描画するジオメトリ。  
  
 *pBrush*  
 ジオメトリのストロークを描画するブラシ。  
  
 *fStrokeWidth*  
 ジオメトリのストロークの太さ。 ストロークは、ジオメトリのアウトラインで中央揃えされます。  
  
 *strokeStyle*  
 ジオメトリのアウトライン表示、または線の描画に NULL を適用する線のスタイルです。  
  
##  <a name="drawglyphrun"></a>  CRenderTarget::DrawGlyphRun  
 指定したグリフを描画します。  
  
```  
void DrawGlyphRun(
    const CD2DPointF& ptBaseLineOrigin,  
    const DWRITE_GLYPH_RUN& glyphRun,  
    CD2DBrush* pForegroundBrush,  
    DWRITE_MEASURING_MODE measuringMode = DWRITE_MEASURING_MODE_NATURAL);
```  
  
### <a name="parameters"></a>パラメーター  
 *ptBaseLineOrigin*  
 グリフの基準のデバイスに依存しないピクセル単位での原点です。  
  
 *glyphRun*  
 表示するグリフします。  
  
 *pForegroundBrush*  
 指定したグリフを描画するブラシ。  
  
 *measuringMode*  
 書式設定時にテキストを測定するグリフのメトリックを使用する方法を示す値。 既定値は、DWRITE_MEASURING_MODE_NATURAL です。  
  
##  <a name="drawline"></a>  CRenderTarget::DrawLine  
 指定した線のスタイルを使用して指定した点の間の線を描画します。  
  
```  
void DrawLine(
    const CD2DPointF& ptFrom,  
    const CD2DPointF& ptTo,  
    CD2DBrush* pBrush,  
    FLOAT fStrokeWidth = 1.0,  
    ID2D1StrokeStyle* strokeStyle = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 *ptFrom*  
 デバイス非依存ピクセルで、行の開始点。  
  
 *ptTo*  
 デバイス非依存ピクセルで、直線の終点。  
  
 *pBrush*  
 線の線の描画に使用するブラシ。  
  
 *fStrokeWidth*  
 ストロークの幅を指定する 0.0 f 以上の値です。 このパラメーターが指定されていない場合の既定値は 1.0f までの値です。 ストロークは、線上の中央揃えされます。  
  
 *strokeStyle*  
 ペイント、または NULL 実線を描画する線のスタイルです。  
  
##  <a name="drawrectangle"></a>  CRenderTarget::DrawRectangle  
 指定した寸法と線のスタイルを持つ四角形のアウトラインを描画します。  
  
```  
void DrawRectangle(
    const CD2DRectF& rect,  
    CD2DBrush* pBrush,  
    FLOAT fStrokeWidth = 1.0,  
    ID2D1StrokeStyle* strokeStyle = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 *rect*  
 デバイス非依存ピクセルで、描画する四角形の寸法  
  
 *pBrush*  
 四角形のストロークを描画するブラシ  
  
 *fStrokeWidth*  
 四角形のストロークの幅を指定する 0.0 f 以上の値です。 ストロークは、四角形のアウトラインで中央揃えされます。  
  
 *strokeStyle*  
 ペイント、または線を描画する NULL に線のスタイルです。  
  
##  <a name="drawroundedrectangle"></a>  CRenderTarget::DrawRoundedRectangle  
 指定した線のスタイルを使用して、指定した丸みのある四角形のアウトラインを描画します。  
  
```  
void DrawRoundedRectangle(
    const CD2DRoundedRect& rectRounded,  
    CD2DBrush* pBrush,  
    FLOAT fStrokeWidth = 1.0,  
    ID2D1StrokeStyle* strokeStyle = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 *rectRounded*  
 デバイスに依存しないピクセル単位で、描画する角の丸い四角形の寸法。  
  
 *pBrush*  
 角の丸い四角形のアウトラインを描画するブラシ。  
  
 *fStrokeWidth*  
 角の丸い四角形のストロークの幅。 ストロークは、角の丸い四角形のアウトラインで中央揃えされます。 既定値は 1.0f になります。  
  
 *strokeStyle*  
 角の丸い四角形の線、または線の描画に NULL のスタイルです。 既定値は NULL です。  
  
##  <a name="drawtext"></a>  CRenderTarget::DrawText  
 IDWriteTextFormat オブジェクトによって提供される形式の情報を使用して、指定したテキストを描画します。  
  
```  
void DrawText(
    const CString& strText,  
    const CD2DRectF& rect,  
    CD2DBrush* pForegroundBrush,  
    CD2DTextFormat* textFormat = NULL,  
    D2D1_DRAW_TEXT_OPTIONS options = D2D1_DRAW_TEXT_OPTIONS_NONE,  
    DWRITE_MEASURING_MODE measuringMode = DWRITE_MEASURING_MODE_NATURAL);
```  
  
### <a name="parameters"></a>パラメーター  
 *strText*  
 描画する Unicode 文字の配列へのポインター。  
  
 *rect*  
 サイズと、テキストが描画される領域の位置。  
  
 *pForegroundBrush*  
 テキストの描画に使用するブラシ。  
  
 *textFormat*  
 書式設定、描画するテキストのフォント、フォント サイズ、およびフローの方向などの詳細を説明するオブジェクト。  
  
 *options*  
 ピクセルの境界にテキストをスナップするかどうかと、レイアウト四角形にテキストをクリップするかどうかを示す値。 既定値は、ピクセルの境界にテキストをスナップするかし、レイアウト四角形にクリップする必要がありますいないことを示す D2D1_DRAW_TEXT_OPTIONS_NONE です。  
  
 *measuringMode*  
 書式設定時にテキストを測定するグリフのメトリックを使用する方法を示す値。 既定値は、DWRITE_MEASURING_MODE_NATURAL です。  
  
##  <a name="drawtextlayout"></a>  CRenderTarget::DrawTextLayout  
 指定した IDWriteTextLayout オブジェクトによって記述されたフォーマットされたテキストを描画します。  
  
```  
void DrawTextLayout(
    const CD2DPointF& ptOrigin,  
    CD2DTextLayout* textLayout,  
    CD2DBrush* pBrushForeground,  
    D2D1_DRAW_TEXT_OPTIONS options = D2D1_DRAW_TEXT_OPTIONS_NONE);
```  
  
### <a name="parameters"></a>パラメーター  
 *ptOrigin*  
 TextLayout によって記述されたテキストの左上隅が描画されるデバイスに依存しないピクセル単位で説明されている点です。  
  
 *textLayout*  
 フォーマットされたテキストを描画します。 ID2D1Resource から継承していないすべての描画効果は無視されます。 描画の効果 ID2D1Resource から継承されるブラシではない場合は、このメソッドは失敗をレンダー ターゲットがエラー状態に格納されます。  
  
 *pBrushForeground*  
 既に (IDWriteTextLayout::SetDrawingEffect メソッドによって指定された) 描画効果と関連付けられているブラシを持たない textLayout 内のテキストの描画に使用するブラシ。  
  
 *options*  
 ピクセルの境界にテキストをスナップするかどうかと、レイアウト四角形にテキストをクリップするかどうかを示す値。 既定値は、ピクセルの境界にテキストをスナップするかし、レイアウト四角形にクリップする必要がありますいないことを示す D2D1_DRAW_TEXT_OPTIONS_NONE です。  
  
##  <a name="enddraw"></a>  CRenderTarget::EndDraw  
 レンダー ターゲット上で描画操作を終了し、現在のエラー状態と関連付けられているタグを示します。  
  
```  
HRESULT EndDraw();
```  
  
### <a name="return-value"></a>戻り値  
 メソッドが成功した場合は S_OK を返します。 それ以外の場合、HRESULT エラー コードを返します。  
  
##  <a name="fillellipse"></a>  CRenderTarget::FillEllipse  
 指定された楕円の内部を描画します。  
  
```  
void FillEllipse(
    const CD2DEllipse& ellipse,  
    CD2DBrush* pBrush);
```  
  
### <a name="parameters"></a>パラメーター  
 *楕円*  
 位置とデバイスに依存しないピクセル単位の楕円を描画するので、radius。  
  
 *pBrush*  
 楕円の内部を描画するために使用するブラシ。  
  
##  <a name="fillgeometry"></a>  CRenderTarget::FillGeometry  
 指定した形状の内部を描画します。  
  
```  
void FillGeometry(
    CD2DGeometry* pGeometry,  
    CD2DBrush* pBrush,  
    CD2DBrush* pOpacityBrush = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 *pGeometry*  
 描画するジオメトリ。  
  
 *pBrush*  
 ジオメトリの描画に使用するブラシの内部をします。  
  
 *pOpacityBrush*  
 Geometry; に適用する不透明度マスクありません不透明度マスクの場合は NULL です。 不透明度マスク (opacityBrush パラメーター) が指定されている場合、ブラシを D2D1_EXTEND_MODE_CLAMP に設定されているその x と y 拡張モードを持つ ID2D1BitmapBrush をする必要があります。 詳細については、「解説」を参照してください。  
  
##  <a name="fillmesh"></a>  CRenderTarget::FillMesh  
 指定したメッシュの内部を描画します。  
  
```  
void FillMesh(
    CD2DMesh* pMesh,  
    CD2DBrush* pBrush);
```  
  
### <a name="parameters"></a>パラメーター  
 *pMesh*  
 描画するメッシュです。  
  
 *pBrush*  
 メッシュの描画に使用するブラシ。  
  
##  <a name="fillopacitymask"></a>  CRenderTarget::FillOpacityMask  
 ブラシを指定したビットマップが示す不透明マスクを適用し、レンダー ターゲットの領域を塗りつぶすそのブラシを使用します。  
  
```  
void FillOpacityMask(
    CD2DBitmap* pOpacityMask,  
    CD2DBrush* pBrush,  
    D2D1_OPACITY_MASK_CONTENT content,  
    const CD2DRectF& rectDest,  
    const CD2DRectF& rectSrc);
```  
  
### <a name="parameters"></a>パラメーター  
 *pOpacityMask*  
 位置とデバイスに依存しないピクセル単位の楕円を描画するので、radius。  
  
 *pBrush*  
 DestinationRectangle で指定されたレンダー ターゲットの地域の描画に使用するブラシ。  
  
 *content*  
 コンテンツの不透明度マスクの種類が含まれています。 値は不透明マスクがブレンドされます色領域を判断するのに使用されます。  
  
 *rectDest*  
 描くには、デバイスに依存しないピクセル単位で、レンダー ターゲットの地域です。  
  
 *rectSrc*  
 デバイス非依存ピクセルで、不透明度マスクとして使用するビットマップの領域。  
  
##  <a name="fillrectangle"></a>  CRenderTarget::FillRectangle  
 指定した四角形の内部を描画します。  
  
```  
void FillRectangle(
    const CD2DRectF& rect,  
    CD2DBrush* pBrush);
```  
  
### <a name="parameters"></a>パラメーター  
 *rect*  
 デバイス非依存ピクセルで、描画する四角形のディメンションです。  
  
 *pBrush*  
 四角形を描画するブラシの内部をします。  
  
##  <a name="fillroundedrectangle"></a>  CRenderTarget::FillRoundedRectangle  
 指定した丸みのある四角形の内部を描画します。  
  
```  
void FillRoundedRectangle(
    const CD2DRoundedRect& rectRounded,  
    CD2DBrush* pBrush);
```  
  
### <a name="parameters"></a>パラメーター  
 *rectRounded*  
 デバイス非依存ピクセルで、ペイントする角の丸い四角形の寸法。  
  
 *pBrush*  
 角の丸い四角形の内部を描画するために使用するブラシ。  
  
##  <a name="flush"></a>  CRenderTarget::Flush  
 保留中のすべての描画コマンドを実行します。  
  
```  
void Flush(
    D2D1_TAG* tag1 = NULL,  
    D2D1_TAG* tag2 = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 *tag1*  
 エラーがない場合は、エラーまたは 0 を原因となった操作を描画するためのタグが含まれています。 このパラメーターは初期化せずに渡されます。  
  
 *tag2*  
 エラーがない場合は、エラーまたは 0 を原因となった操作を描画するためのタグが含まれています。 このパラメーターは初期化せずに渡されます。  
  
##  <a name="getantialiasmode"></a>  CRenderTarget::GetAntialiasMode  
 テキスト以外の描画操作の現在の (アンチエイリアシング) モードを取得します。  
  
```  
D2D1_ANTIALIAS_MODE GetAntialiasMode() const;  
```  
  
### <a name="return-value"></a>戻り値  
 テキスト以外の描画操作の現在の (アンチエイリアシング) モード。  
  
##  <a name="getdpi"></a>  CRenderTarget::GetDpi  
 レンダリング ターゲットのドット/インチ (DPI) を返します  
  
```  
CD2DSizeF GetDpi() const;  
```  
  
### <a name="return-value"></a>戻り値  
 レンダー ターゲットのドット/インチ (DPI)。  
  
##  <a name="getmaximumbitmapsize"></a>  CRenderTarget::GetMaximumBitmapSize  
 レンダー ターゲットでサポートされている任意の 1 つのビットマップ ディメンションのデバイスに依存する単位 (ピクセル単位) で最大のサイズを取得します。  
  
```  
UINT32 GetMaximumBitmapSize() const;  
```  
  
### <a name="return-value"></a>戻り値  
 レンダー ターゲットでサポートされている任意の 1 つのビットマップ ディメンションのピクセル単位の最大サイズ  
  
##  <a name="getpixelformat"></a>  CRenderTarget::GetPixelFormat  
 レンダー ターゲットのピクセル形式とアルファ モードを取得します。  
  
```  
D2D1_PIXEL_FORMAT GetPixelFormat() const;  
```  
  
### <a name="return-value"></a>戻り値  
 レンダー ターゲットのピクセル形式とアルファ モード  
  
##  <a name="getpixelsize"></a>  CRenderTarget::GetPixelSize  
 デバイス ピクセル単位で、レンダー ターゲットのサイズを返します  
  
```  
CD2DSizeU GetPixelSize() const;  
```  
  
### <a name="return-value"></a>戻り値  
 デバイス ピクセル単位で、レンダー ターゲットのサイズ  
  
##  <a name="getrendertarget"></a>  CRenderTarget::GetRenderTarget  
 返します ID2D1RenderTarget インターフェイス  
  
```  
ID2D1RenderTarget* GetRenderTarget();
```  
  
### <a name="return-value"></a>戻り値  
 ID2D1RenderTarget インターフェイスまたはオブジェクトがまだ初期化されていない場合は、NULL へのポインター。  
  
##  <a name="getsize"></a>  CRenderTarget::GetSize  
 デバイスに依存しないピクセル単位で、レンダー ターゲットのサイズを返します  
  
```  
CD2DSizeF GetSize() const;  
```  
  
### <a name="return-value"></a>戻り値  
 デバイス非依存ピクセルで、レンダー ターゲットの現在のサイズ  
  
##  <a name="gettags"></a>  CRenderTarget::GetTags  
 後続の描画操作のラベルを取得します。  
  
```  
void GetTags(
    D2D1_TAG* tag1 = NULL,  
    D2D1_TAG* tag2 = NULL) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 *tag1*  
 後続の描画操作の最初のラベルが含まれています。 このパラメーターは初期化せずに渡されます。 NULL が指定されている場合、このパラメーターの値は取得できません。  
  
 *tag2*  
 後続の描画操作の 2 番目のラベルが含まれています。 このパラメーターは初期化せずに渡されます。 NULL が指定されている場合、このパラメーターの値は取得できません。  
  
##  <a name="gettextantialiasmode"></a>  CRenderTarget::GetTextAntialiasMode  
 テキストとグリフが描画操作の現在の (アンチエイリアシング) モードを取得します。  
  
```  
D2D1_TEXT_ANTIALIAS_MODE GetTextAntialiasMode() const;  
```  
  
### <a name="return-value"></a>戻り値  
 テキストとグリフが描画操作の現在の (アンチエイリアシング) モード。  
  
##  <a name="gettextrenderingparams"></a>  CRenderTarget::GetTextRenderingParams  
 レンダー ターゲットの現在のテキスト レンダリング オプションを取得します。  
  
```  
void GetTextRenderingParams(IDWriteRenderingParams** textRenderingParams);
```  
  
### <a name="parameters"></a>パラメーター  
 *textRenderingParams*  
 TextRenderingParamscontains レンダー ターゲットへのポインターのアドレスが現在のこのメソッドが戻るときにテキストのレンダリング オプション。  
  
##  <a name="gettransform"></a>  CRenderTarget::GetTransform  
 既存の変換を置き換える、レンダー ターゲットを指定した変換を適用します。 後続のすべての描画操作は、変換後のスペースで発生します。  
  
```  
void GetTransform(D2D1_MATRIX_3X2_F* transform);
```  
  
### <a name="parameters"></a>パラメーター  
 *transform*  
 レンダー ターゲットに適用する変換です。  
  
##  <a name="issupported"></a>  CRenderTarget::IsSupported  
 レンダー ターゲットが、指定されたプロパティをサポートするかどうかを示します  
  
```  
BOOL IsSupported(const D2D1_RENDER_TARGET_PROPERTIES& renderTargetProperties) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 *renderTargetProperties*  
 レンダー ターゲットのプロパティをテストするには  
  
### <a name="return-value"></a>戻り値  
 指定したレンダー ターゲットのプロパティがこのレンダー ターゲットでサポートされている場合は TRUE。それ以外の場合は FALSE  
  
##  <a name="isvalid"></a>  CRenderTarget::IsValid  
 リソースの有効性のチェック  
  
```  
BOOL IsValid() const;  
```  
  
### <a name="return-value"></a>戻り値  
 リソースが無効である場合は TRUE。それ以外の場合は FALSE。  
  
##  <a name="m_lstresources"></a>  CRenderTarget::m_lstResources  
 CD2DResource オブジェクトへのポインターのリスト。  
  
```  
CObList m_lstResources;  
```  
  
##  <a name="m_prendertarget"></a>  CRenderTarget::m_pRenderTarget  
 ID2D1RenderTarget オブジェクトへのポインター。  
  
```  
ID2D1RenderTarget* m_pRenderTarget;  
```  
  
##  <a name="m_ptextformatdefault"></a>  CRenderTarget::m_pTextFormatDefault  
 既定のテキスト形式を格納している CD2DTextFormat オブジェクトへのポインター。  
  
```  
CD2DTextFormat* m_pTextFormatDefault;  
```  
  
##  <a name="operator_id2d1rendertarget_star"></a>  CRenderTarget::operator ID2D1RenderTarget *  
 返します ID2D1RenderTarget インターフェイス  
  
```  
operator ID2D1RenderTarget*();
```   
  
### <a name="return-value"></a>戻り値  
 ID2D1RenderTarget インターフェイスまたはオブジェクトがまだ初期化されていない場合は、NULL へのポインター。  
  
##  <a name="popaxisalignedclip"></a>  CRenderTarget::PopAxisAlignedClip  
 レンダー ターゲットから最後の軸に沿ったクリップを削除します。 このメソッドが呼び出されると、クリップは不要になった後続の描画操作に適用されます。  
  
```  
void PopAxisAlignedClip();
```  
  
##  <a name="poplayer"></a>  CRenderTarget::PopLayer  
 最後の PushLayer で指定されているレイヤーの描画操作のリダイレクトを停止を呼び出します。  
  
```  
void PopLayer();
```  
  
##  <a name="pushaxisalignedclip"></a>  CRenderTarget::PushAxisAlignedClip  
 レンダー ターゲットから最後の軸に沿ったクリップを削除します。 このメソッドが呼び出されると、クリップは不要になった後続の描画操作に適用されます。  
  
```  
void PushAxisAlignedClip(
    const CD2DRectF& rectClip,  
    D2D1_ANTIALIAS_MODE mode = D2D1_ANTIALIAS_MODE_PER_PRIMITIVE);
```  
  
### <a name="parameters"></a>パラメーター  
 *rectClip*  
 サイズとデバイスに依存しないピクセル単位でクリッピング領域の位置。  
  
 *モード*  
 (アンチエイリアシング) モードを使用してサブピクセル境界があるクリップ四角形のエッジを描画し、blend のシーン内容でクリップです。 ブレンド PopAxisAlignedClip メソッドが呼び出され、レイヤー内の各プリミティブには適用されませんが実行されます。  
  
##  <a name="pushlayer"></a>  CRenderTarget::PushLayer  
 PopLayer が呼び出されるまでは、後続のすべての描画操作を受信できるように、レンダー ターゲットに指定したレイヤーを追加します。  
  
```  
void PushLayer(
    const D2D1_LAYER_PARAMETERS& layerParameters,  
    CD2DLayer& layer);
```  
  
### <a name="parameters"></a>パラメーター  
 *layerParameters*  
 コンテンツの境界、幾何学的マスク、不透明度、不透明度マスク、およびアンチエイリアシング レイヤーのオプションです。  
  
 *レイヤー*  
 後続の描画操作を受信するレイヤー。  
  
##  <a name="restoredrawingstate"></a>  CRenderTarget::RestoreDrawingState  
 指定した ID2D1DrawingStateBlock のレンダー ターゲットの描画状態を設定します。  
  
```  
void RestoreDrawingState(ID2D1DrawingStateBlock& drawingStateBlock);
```  
  
### <a name="parameters"></a>パラメーター  
 *drawingStateBlock*  
 レンダー ターゲットの新しい状態を描画します。  
  
##  <a name="savedrawingstate"></a>  CRenderTarget::SaveDrawingState  
 指定した ID2D1DrawingStateBlock に現在の描画状態を保存します。  
  
```  
void SaveDrawingState(ID2D1DrawingStateBlock& drawingStateBlock) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 *drawingStateBlock*  
 このメソッドが戻るとき、レンダー ターゲットの現在の描画状態を格納します。 このパラメーターは、メソッドに渡す前に初期化する必要があります。  
  
##  <a name="setantialiasmode"></a>  CRenderTarget::SetAntialiasMode  
 レンダー ターゲットの (アンチエイリアシング) モードを設定します。 (アンチエイリアシング) モードは、テキストとグリフが描画操作を除く、すべての後続描画操作に適用されます。  
  
```  
void SetAntialiasMode(D2D1_ANTIALIAS_MODE antialiasMode);
```  
  
### <a name="parameters"></a>パラメーター  
 *antialiasMode*  
 将来の描画操作 (アンチエイリアシング) モード。  
  
##  <a name="setdpi"></a>  CRenderTarget::SetDpi  
 ドット/インチ (DPI) のレンダー ターゲットを設定します。  
  
```  
void SetDpi(const CD2DSizeF& sizeDPI);
```  
  
### <a name="parameters"></a>パラメーター  
 *sizeDPI*  
 大きいか、レンダー ターゲットの水平/verticalDPI を指定する 0 に等しい値です。  
  
##  <a name="settags"></a>  CRenderTarget::SetTags  
 後続の描画操作のラベルを指定します。  
  
```  
void SetTags(
    D2D1_TAG tag1,  
    D2D1_TAG tag2);
```  
  
### <a name="parameters"></a>パラメーター  
 *tag1*  
 後続の描画操作に適用するラベルです。  
  
 *tag2*  
 後続の描画操作に適用するラベルです。  
  
##  <a name="settextantialiasmode"></a>  CRenderTarget::SetTextAntialiasMode  
 後続のテキストとグリフの描画操作に使用する (アンチエイリアシング) モードを指定します。  
  
```  
void SetTextAntialiasMode(D2D1_TEXT_ANTIALIAS_MODE textAntialiasMode);
```  
  
### <a name="parameters"></a>パラメーター  
 *textAntialiasMode*  
 後続のテキストとグリフが描画操作に使用する (アンチエイリアシング) モード。  
  
##  <a name="settextrenderingparams"></a>  CRenderTarget::SetTextRenderingParams  
 すべての後続のテキストとグリフが描画操作に適用するテキストのレンダリング オプションを指定します。  
  
```  
void SetTextRenderingParams(IDWriteRenderingParams* textRenderingParams = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 *textRenderingParams*  
 すべての後続のテキストとグリフが描画操作に適用するテキストのレンダリング オプション現在のテキスト レンダリング オプションをオフにする場合は NULL です。  
  
##  <a name="settransform"></a>  CRenderTarget::SetTransform  
 既存の変換を置き換える、レンダー ターゲットを指定した変換を適用します。 後続のすべての描画操作は、変換後のスペースで発生します。  
  
```  
void SetTransform(const D2D1_MATRIX_3X2_F* transform);  
void SetTransform(const D2D1_MATRIX_3X2_F& transform);
```  
  
### <a name="parameters"></a>パラメーター  
 *transform*  
 レンダー ターゲットに適用する変換です。  
  
##  <a name="verifyresource"></a>  CRenderTarget::VerifyResource  
 CD2DResource オブジェクトの有効性; を検証します。存在しない場合は、オブジェクトを作成します。  
  
```  
BOOL VerifyResource(CD2DResource* pResource);
```  
  
### <a name="parameters"></a>パラメーター  
 *pResource*  
 CD2DResource オブジェクトへのポインター。  
  
### <a name="return-value"></a>戻り値  
 有効である場合は、オブジェクトの場合は TRUEそれ以外の場合は FALSE。  
  
## <a name="see-also"></a>関連項目  
 [クラス](../../mfc/reference/mfc-classes.md)

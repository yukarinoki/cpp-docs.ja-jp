---
title: CRenderTarget クラス
ms.date: 03/27/2019
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
ms.openlocfilehash: 1b165b485e067120477de560d2091c448e02fe44
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81368346"
---
# <a name="crendertarget-class"></a>CRenderTarget クラス

ID2D1RenderTarget のラッパー。

## <a name="syntax"></a>構文

```
class CRenderTarget : public CObject;
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[をクリックします。](#crendertarget)|オブジェクトを構築します。|
|[をクリックします。](#_dtorcrendertarget)|デストラクターです。 レンダー ターゲット オブジェクトが破棄されるときに呼び出されます。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[クレンダターゲット::アタッチ](#attach)|既存のレンダー ターゲット インターフェイスをオブジェクトにアタッチします。|
|[レンダリングターゲット::ドローを開始](#begindraw)|このレンダー ターゲットで描画を開始します。|
|[クレンダターゲット::クリア](#clear)|作図領域を指定した色にクリアします。|
|[クレンダターゲット::COLORREF_TO_D2DCOLOR](#colorref_to_d2dcolor)|GDI の色とアルファ値をD2D1_COLOR_Fオブジェクトに変換します。|
|[をクリックします。](#createcompatiblerendertarget)|現在のレンダー ターゲットと互換性のある中間のオフスクリーン描画中に使用する新しいビットマップ レンダー ターゲットを作成します。|
|[クレンデターゲット::Dエストロイ](#destroy)|1 つ以上のリソースを削除します。|
|[クレンダターゲット::Dエタッハ](#detach)|オブジェクトからレンダー ターゲット インターフェイスをデタッチします。|
|[オブジェクトを表示します。::Dロービットマップ](#drawbitmap)|指定した IDWriteTextLayout オブジェクトによって記述された書式設定されたテキストを描画します。|
|[:Dロー楕円](#drawellipse)|指定したストローク スタイルを使用して、指定した楕円のアウトラインを描画します。|
|[オブジェクトを作成する:Dロージオメトリ](#drawgeometry)|指定したストローク スタイルを使用して、指定したジオメトリのアウトラインを描画します。|
|[をクリックします。:Dローグリフラン](#drawglyphrun)|指定したグリフを描画します。|
|[クレンダターゲット::Dローライン](#drawline)|指定したストローク スタイルを使用して、指定したポイント間に線を描画します。|
|[オブジェクトを描画します。:Dロー長方形](#drawrectangle)|指定した寸法とストローク スタイルを持つ四角形のアウトラインを描画します。|
|[オブジェクトを表示します。:D丸めた長方形](#drawroundedrectangle)|指定したストローク スタイルを使用して、指定した角丸四角形のアウトラインを描画します。|
|[オブジェクトを:Dします。](#drawtext)|オブジェクトによって提供される書式情報を使用して、指定されたテキストを描画します。|
|[:Dテキストレイアウト](#drawtextlayout)|指定した IDWriteTextLayout オブジェクトによって記述された書式設定されたテキストを描画します。|
|[レンダリングターゲット::エンドドロー](#enddraw)|レンダー ターゲットの描画操作を終了し、現在のエラー状態と関連付けられたタグを示します。|
|[クレンダターゲット::フィル楕円](#fillellipse)|指定した楕円の内部を描画します。|
|[をクリックします。](#fillgeometry)|指定したジオメトリの内部を描画します。|
|[クレンダターゲット::フィルメッシュ](#fillmesh)|指定したメッシュの内部を描画します。|
|[クレンダターゲット::フィルオパシティマスク](#fillopacitymask)|指定したビットマップで記述された不透明マスクをブラシに適用し、そのブラシを使用してレンダー ターゲットの領域をペイントします。|
|[をクリックします。](#fillrectangle)|指定した四角形の内部を描画します。|
|[クレンダターゲット::フィルラウンド長方形](#fillroundedrectangle)|指定した角丸四角形の内部を描画します。|
|[クレンダターゲット::フラッシュ](#flush)|保留中のすべての描画コマンドを実行します。|
|[クレンダターゲット::アンチエイリアスモード](#getantialiasmode)|テキスト以外の描画操作の現在のアンチエイリアス モードを取得します。|
|[クレンドターゲット::ゲットドピ](#getdpi)|レンダー ターゲットの 1 インチあたりのドット数 (DPI) を返します。|
|[をクリックします。](#getmaximumbitmapsize)|レンダー ターゲットでサポートされている任意の 1 つのビットマップ ディメンションのデバイス依存単位 (ピクセル単位) の最大サイズを取得します。|
|[をクリックします。](#getpixelformat)|レンダー ターゲットのピクセル形式とアルファ モードを取得します。|
|[ターゲット::ピクセルサイズを取得します。](#getpixelsize)|レンダー ターゲットのサイズをデバイス ピクセル単位で返します。|
|[をクリックします。](#getrendertarget)|インターフェイスを返します。|
|[ターゲット::ゲットサイズ](#getsize)|レンダー ターゲットのサイズをデバイスに依存しないピクセル単位で返します。|
|[をクリックします。](#gettags)|後続の描画操作のラベルを取得します。|
|[をクリックします。](#gettextantialiasmode)|テキストおよびグリフ描画操作の現在のアンチエイリアシング モードを取得します。|
|[をクリックします。](#gettextrenderingparams)|レンダー ターゲットの現在のテキスト レンダリング オプションを取得します。|
|[ソースソース::変換を取得します。](#gettransform)|指定した変換をレンダー ターゲットに適用し、既存の変換を置き換えます。 それ以降の描画操作はすべて、変換された空間で行われます。|
|[をクリックします。](#issupported)|レンダー ターゲットが指定されたプロパティをサポートするかどうかを示します。|
|[クレンダターゲット::イズバリ](#isvalid)|リソースの有効性を確認します|
|[クレンダターゲット::Pソップアクシスアライメントクリップ](#popaxisalignedclip)|最後の軸に位置合わせされたクリップをレンダー ターゲットから削除します。 このメソッドが呼び出されると、クリップは以降の描画操作に適用されなくなります。|
|[クレンダターゲット::Pソップレイヤー](#poplayer)|最後の PushLayer 呼び出しで指定されたレイヤーへの描画操作のリダイレクトを停止します。|
|[クレンダターゲット::Pウシュアクシスアライメントクリップ](#pushaxisalignedclip)|最後の軸に位置合わせされたクリップをレンダー ターゲットから削除します。 このメソッドが呼び出されると、クリップは以降の描画操作に適用されなくなります。|
|[クレンジターゲット::Pウシュレイヤー](#pushlayer)|指定したレイヤーをレンダー ターゲットに追加し、PopLayer が呼び出されるまで以降のすべての描画操作を受け取ります。|
|[ステートターゲット::リストアドローイングステート](#restoredrawingstate)|レンダー ターゲットの描画状態を、指定した ID2D1DrawingStateBlock の描画状態に設定します。|
|[をクリックします。](#savedrawingstate)|現在の描画状態を指定した ID2D1DrawingStateBlock に保存します。|
|[クレンダターゲット::アンチエイリアスモード](#setantialiasmode)|レンダー ターゲットのアンチエイリアシング モードを設定します。 アンチエイリアシング モードは、テキストおよびグリフ描画操作を除く、後続のすべての描画操作に適用されます。|
|[クレンドターゲット::セットドピ](#setdpi)|レンダー ターゲットのドット/インチ (DPI) を設定します。|
|[クレンダターゲット::セットタグ](#settags)|後続の図面操作のラベルを指定します。|
|[をクリックします。](#settextantialiasmode)|後続のテキストおよびグリフ描画操作に使用するアンチエイリアシング モードを指定します。|
|[クレンダターゲット::セットテキストレンダリングパラム](#settextrenderingparams)|後続のすべてのテキストおよびグリフ描画操作に適用するテキスト レンダリング オプションを指定します。|
|[ソースソース::変換を設定します。](#settransform)|オーバーロードされます。 指定した変換をレンダー ターゲットに適用し、既存の変換を置き換えます。 それ以降の描画操作はすべて、変換された空間で行われます。|

### <a name="protected-methods"></a>プロテクト メソッド

|名前|説明|
|----------|-----------------|
|[リソースを確認します。](#verifyresource)|CD2D リソース オブジェクトの有効性を確認します。オブジェクトが存在しない場合は、オブジェクトを作成します。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[ソースターゲット::オペレーター ID2D1 レンダーターゲット*](#operator_id2d1rendertarget_star)|インターフェイスを返します。|

### <a name="protected-data-members"></a>プロテクト データ メンバー

|名前|説明|
|----------|-----------------|
|[クレンダターゲット::m_lstResources](#m_lstresources)|CD2DResource オブジェクトへのポインターのリスト。|
|[クレンダターゲット::m_pRenderTarget](#m_prendertarget)|オブジェクトへのポインター。|
|[クレンダターゲット::m_pTextFormatDefault](#m_ptextformatdefault)|既定のテキスト形式を含む CD2DTextFormat オブジェクトへのポインター。|

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[クレンダターゲット](../../mfc/reference/crendertarget-class.md)

## <a name="requirements"></a>必要条件

**ヘッダー:** afxrendertarget.h

## <a name="crendertargetcrendertarget"></a><a name="_dtorcrendertarget"></a>をクリックします。

デストラクターです。 レンダー ターゲット オブジェクトが破棄されるときに呼び出されます。

```
virtual ~CRenderTarget();
```

## <a name="crendertargetattach"></a><a name="attach"></a>クレンダターゲット::アタッチ

既存のレンダー ターゲット インターフェイスをオブジェクトにアタッチします。

```
void Attach(ID2D1RenderTarget* pRenderTarget);
```

### <a name="parameters"></a>パラメーター

*ターゲットをレンダリングします。*<br/>
既存のレンダー ターゲット インターフェイス。 NULL にすることはできません。

## <a name="crendertargetbegindraw"></a><a name="begindraw"></a>レンダリングターゲット::ドローを開始

このレンダー ターゲットで描画を開始します。

```
void BeginDraw();
```

## <a name="crendertargetclear"></a><a name="clear"></a>クレンダターゲット::クリア

作図領域を指定した色にクリアします。

```
void Clear(D2D1_COLOR_F color);
```

### <a name="parameters"></a>パラメーター

*色*<br/>
作図領域をクリアする色。

## <a name="crendertargetcolorref_to_d2dcolor"></a><a name="colorref_to_d2dcolor"></a>クレンダターゲット::COLORREF_TO_D2DCOLOR

GDI の色とアルファ値をD2D1_COLOR_Fオブジェクトに変換します。

```
static D2D1_COLOR_F COLORREF_TO_D2DCOLOR(
    COLORREF color,
    int nAlpha = 255);
```

### <a name="parameters"></a>パラメーター

*色*<br/>
RGB 値。

*nアルファ*

### <a name="return-value"></a>戻り値

D2D1_COLOR_F値。

## <a name="crendertargetcreatecompatiblerendertarget"></a><a name="createcompatiblerendertarget"></a>をクリックします。

現在のレンダー ターゲットと互換性のある中間のオフスクリーン描画中に使用する新しいビットマップ レンダー ターゲットを作成します。

```
BOOL CreateCompatibleRenderTarget(
    CBitmapRenderTarget& bitmapTarget,
    CD2DSizeF sizeDesired = CD2DSizeF(0., 0.),
    CD2DSizeU sizePixelDesired = CD2DSizeU(0, 0),
    D2D1_PIXEL_FORMAT* desiredFormat = NULL,
    D2D1_COMPATIBLE_RENDER_TARGET_OPTIONS options = D2D1_COMPATIBLE_RENDER_TARGET_OPTIONS_NONE);
```

### <a name="parameters"></a>パラメーター

*ビットマップターゲット*<br/>
このメソッドが返されるときに、新しいビットマップ レンダー ターゲットへのポインターのアドレスを格納します。 このパラメーターは初期化せずに渡されます。

*サイズ必要な*<br/>
元のレンダー ターゲットと異なる必要がある場合は、デバイスに依存しないピクセル単位での新しいレンダー ターゲットの必要なサイズ、または NULL。 詳細については、「解説」を参照してください。

*サイズピクセル必要な*<br/>
元のレンダー ターゲットと異なる必要がある場合は、新しいレンダー ターゲットの必要なサイズ (ピクセル単位)。 詳細については、「解説」を参照してください。

*目的のフォーマット*<br/>
新しいレンダー ターゲットの目的のピクセル形式とアルファ モード、または NULL。 ピクセル形式がDXGI_FORMAT_UNKNOWNに設定されている場合、またはこのパラメータが null の場合、新しいレンダー ターゲットは元のレンダー ターゲットと同じピクセル形式を使用します。 アルファ モードがD2D1_ALPHA_MODE_UNKNOWNまたは NULL の場合、新しいレンダー ターゲットのアルファ モードは既定でD2D1_ALPHA_MODE_PREMULTIPLIED。 サポートされるピクセル形式については、「サポートされるピクセル形式とアルファモード」を参照してください。

*オプション*<br/>
新しいレンダー ターゲットが GDI と互換性を持つ必要があるかどうかを指定する値。

### <a name="return-value"></a>戻り値

メソッドが成功すると、TRUE が返されます。 それ以外の場合は FALSE を返します。

## <a name="crendertargetcrendertarget"></a><a name="crendertarget"></a>をクリックします。

オブジェクトを構築します。

```
CRenderTarget();
```

## <a name="crendertargetdestroy"></a><a name="destroy"></a>クレンデターゲット::Dエストロイ

1 つ以上のリソースを削除します。

```
BOOL Destroy(BOOL bDeleteResources = TRUE);
```

### <a name="parameters"></a>パラメーター

*リソースを削除する*<br/>
bDeleteResources が TRUE の場合、m_lstResourcesに配置されているすべてのリソースは自動的に破棄されます。

### <a name="return-value"></a>戻り値

メソッドが成功すると、TRUE が返されます。 それ以外の場合は FALSE を返します。

## <a name="crendertargetdetach"></a><a name="detach"></a>クレンダターゲット::Dエタッハ

オブジェクトからレンダー ターゲット インターフェイスをデタッチします。

```
ID2D1RenderTarget* Detach ();
```

### <a name="return-value"></a>戻り値

デタッチされたレンダー ターゲット インターフェイスへのポインター。

## <a name="crendertargetdrawbitmap"></a><a name="drawbitmap"></a>オブジェクトを表示します。::Dロービットマップ

指定した IDWriteTextLayout オブジェクトによって記述された書式設定されたテキストを描画します。

```
void DrawBitmap(
    CD2DBitmap* pBitmap,
    const CD2DRectF& rectDest,
    float fOpacity = 1.0,
    D2D1_BITMAP_INTERPOLATION_MODE interpolationMode = D2D1_BITMAP_INTERPOLATION_MODE_LINEAR,
    const CD2DRectF* pRectSrc = NULL);
```

### <a name="parameters"></a>パラメーター

*ビットマップ*<br/>
レンダリングするビットマップ。

*レクトデスト*<br/>
ビットマップが描画される領域の、レンダー ターゲットの座標空間内のデバイスに依存しないピクセル単位のサイズと位置。 四角形が整順でない場合は何も描画されませんが、レンダー ターゲットはエラー状態に入りません。

*フォパシティ*<br/>
0.0f から 1.0f までの値で、ビットマップに適用する不透明度を指定します。この値は、ビットマップの内容のアルファ値に乗算されます。

*補間モード*<br/>
ビットマップが図面操作によって拡大または縮小される場合に使用する補間モード。

*プレックスル*<br/>
ビットマップの座標空間内のデバイスに依存しないピクセル単位で、描画するビットマップ内の領域のサイズと位置。

## <a name="crendertargetdrawellipse"></a><a name="drawellipse"></a>:Dロー楕円

指定したストローク スタイルを使用して、指定した楕円のアウトラインを描画します。

```
void DrawEllipse(
    const CD2DEllipse& ellipse,
    CD2DBrush* pBrush,
    FLOAT fStrokeWidth = 1.0,
    ID2D1StrokeStyle* strokeStyle = NULL);
```

### <a name="parameters"></a>パラメーター

*ellipse*<br/>
描画する楕円の位置と半径を、デバイスに依存しないピクセル単位で指定します。

*pブラシ*<br/>
楕円の輪郭を描画するために使用するブラシ。

*幅*<br/>
楕円のストロークの太さ。 ストロークは楕円のアウトラインの中央に配置されます。

*ストロークスタイル*<br/>
楕円のアウトラインに適用するストロークのスタイルを指定します。

## <a name="crendertargetdrawgeometry"></a><a name="drawgeometry"></a>オブジェクトを作成する:Dロージオメトリ

指定したストローク スタイルを使用して、指定したジオメトリのアウトラインを描画します。

```
void DrawGeometry(
    CD2DGeometry* pGeometry,
    CD2DBrush* pBrush,
    FLOAT fStrokeWidth = 1.0,
    ID2D1StrokeStyle* strokeStyle = NULL);
```

### <a name="parameters"></a>パラメーター

*ジオメトリ*<br/>
描画するジオメトリ。

*pブラシ*<br/>
ジオメトリのストロークをペイントするために使用するブラシ。

*幅*<br/>
ジオメトリのストロークの太さ。 ストロークは、ジオメトリのアウトラインの中央に配置されます。

*ストロークスタイル*<br/>
ジオメトリのアウトラインに適用するストロークのスタイルを指定します。

## <a name="crendertargetdrawglyphrun"></a><a name="drawglyphrun"></a>をクリックします。:Dローグリフラン

指定したグリフを描画します。

```
void DrawGlyphRun(
    const CD2DPointF& ptBaseLineOrigin,
    const DWRITE_GLYPH_RUN& glyphRun,
    CD2DBrush* pForegroundBrush,
    DWRITE_MEASURING_MODE measuringMode = DWRITE_MEASURING_MODE_NATURAL);
```

### <a name="parameters"></a>パラメーター

*ポイントベースラインオリジン*<br/>
グリフのベースラインの原点 (デバイスに依存しないピクセル単位)。

*Glyphrun*<br/>
表示するグリフ。

*前景ブラシ*<br/>
指定したグリフの描画に使用するブラシ。

*測定モード*<br/>
書式指定時にグリフ メトリックを使用してテキストを測定する方法を示す値。 既定値は DWRITE_MEASURING_MODE_NATURAL です。

## <a name="crendertargetdrawline"></a><a name="drawline"></a>クレンダターゲット::Dローライン

指定したストローク スタイルを使用して、指定したポイント間に線を描画します。

```
void DrawLine(
    const CD2DPointF& ptFrom,
    const CD2DPointF& ptTo,
    CD2DBrush* pBrush,
    FLOAT fStrokeWidth = 1.0,
    ID2D1StrokeStyle* strokeStyle = NULL);
```

### <a name="parameters"></a>パラメーター

*pt から*<br/>
ラインの始点 (デバイスに依存しないピクセル単位)。

*ptTo*<br/>
ラインの終点 (デバイスに依存しないピクセル単位)。

*pブラシ*<br/>
線のストロークをペイントするために使用するブラシ。

*幅*<br/>
ストロークの幅を指定する 0.0f 以上の値。 このパラメーターが指定されていない場合、デフォルトは 1.0f です。 線の中央にストロークが配置されます。

*ストロークスタイル*<br/>
描画するストロークのスタイル、または実線を描画する場合は NULL。

## <a name="crendertargetdrawrectangle"></a><a name="drawrectangle"></a>オブジェクトを描画します。:Dロー長方形

指定した寸法とストローク スタイルを持つ四角形のアウトラインを描画します。

```
void DrawRectangle(
    const CD2DRectF& rectangle,
    CD2DBrush* pBrush,
    FLOAT fStrokeWidth = 1.0,
    ID2D1StrokeStyle* strokeStyle = NULL);
```

### <a name="parameters"></a>パラメーター

*四角 形*<br/>
デバイスに依存しないピクセル単位で描画する四角形のサイズ

*pブラシ*<br/>
四角形のストロークをペイントするために使用するブラシ

*幅*<br/>
四角形のストロークの幅を指定する 0.0f 以上の値。 ストロークは、四角形のアウトラインの中央に配置されます。

*ストロークスタイル*<br/>
描画するストロークのスタイル、または、実線を描画する場合は NULL。

## <a name="crendertargetdrawroundedrectangle"></a><a name="drawroundedrectangle"></a>オブジェクトを表示します。:D丸めた長方形

指定したストローク スタイルを使用して、指定した角丸四角形のアウトラインを描画します。

```
void DrawRoundedRectangle(
    const CD2DRoundedRect& rectRounded,
    CD2DBrush* pBrush,
    FLOAT fStrokeWidth = 1.0,
    ID2D1StrokeStyle* strokeStyle = NULL);
```

### <a name="parameters"></a>パラメーター

*直角丸*<br/>
デバイスに依存しないピクセル単位で描画する丸い四角形のサイズ。

*pブラシ*<br/>
角丸長方形の輪郭を塗りつぶすために使用するブラシ。

*幅*<br/>
角丸長方形のストロークの幅。 ストロークは、丸い四角形のアウトラインの中央に配置されます。 デフォルト値は 1.0f です。

*ストロークスタイル*<br/>
角丸長方形のストロークのスタイルを指定するか、または NULL を指定して実線を描画します。 既定値は NULL です。

## <a name="crendertargetdrawtext"></a><a name="drawtext"></a>オブジェクトを:Dします。

オブジェクトによって提供される書式情報を使用して、指定されたテキストを描画します。

```
void DrawText(
    const CString& strText,
    const CD2DRectF& rectangle,
    CD2DBrush* pForegroundBrush,
    CD2DTextFormat* textFormat = NULL,
    D2D1_DRAW_TEXT_OPTIONS options = D2D1_DRAW_TEXT_OPTIONS_NONE,
    DWRITE_MEASURING_MODE measuringMode = DWRITE_MEASURING_MODE_NATURAL);
```

### <a name="parameters"></a>パラメーター

*str テキスト*<br/>
描画する Unicode 文字の配列へのポインター。

*四角 形*<br/>
テキストが描画される領域のサイズと位置。

*前景ブラシ*<br/>
テキストの塗りつぶしに使用するブラシ。

*textFormat*<br/>
フォント、フォント サイズ、フロー方向など、描画するテキストの書式の詳細を記述するオブジェクト。

*オプション*<br/>
テキストをピクセル境界にスナップするかどうか、およびテキストをレイアウト四角形にクリップするかどうかを示す値。 既定値は D2D1_DRAW_TEXT_OPTIONS_NONE で、テキストをピクセル境界にスナップし、レイアウト四角形にクリップしないことを示します。

*測定モード*<br/>
書式指定時にグリフ メトリックを使用してテキストを測定する方法を示す値。 既定値は DWRITE_MEASURING_MODE_NATURAL です。

## <a name="crendertargetdrawtextlayout"></a><a name="drawtextlayout"></a>:Dテキストレイアウト

指定した IDWriteTextLayout オブジェクトによって記述された書式設定されたテキストを描画します。

```
void DrawTextLayout(
    const CD2DPointF& ptOrigin,
    CD2DTextLayout* textLayout,
    CD2DBrush* pBrushForeground,
    D2D1_DRAW_TEXT_OPTIONS options = D2D1_DRAW_TEXT_OPTIONS_NONE);
```

### <a name="parameters"></a>パラメーター

*ptオリジン*<br/>
textLayout で記述されたテキストの左上隅が描画される、デバイスに依存しないピクセルで記述される点。

*テキストレイアウト*<br/>
描画する書式設定されたテキスト。 ID2D1Resource から継承しない描画効果は無視されます。 ブラシではない ID2D1Resource から継承する描画効果がある場合、このメソッドは失敗し、レンダー ターゲットはエラー状態になります。

*前景*<br/>
テキスト内のテキストを描画するために使用されるブラシレイアウトに、描画効果として関連付けられているブラシがないレイアウトです (IDWriteTextLayout::SetDrawingEffect メソッドで指定)。

*オプション*<br/>
テキストをピクセル境界にスナップするかどうか、およびテキストをレイアウト四角形にクリップするかどうかを示す値。 既定値は D2D1_DRAW_TEXT_OPTIONS_NONE で、テキストをピクセル境界にスナップし、レイアウト四角形にクリップしないことを示します。

## <a name="crendertargetenddraw"></a><a name="enddraw"></a>レンダリングターゲット::エンドドロー

レンダー ターゲットの描画操作を終了し、現在のエラー状態と関連付けられたタグを示します。

```
HRESULT EndDraw();
```

### <a name="return-value"></a>戻り値

メソッドが成功した場合は、S_OK を返します。 それ以外の場合は、HRESULT エラー コードを返します。

## <a name="crendertargetfillellipse"></a><a name="fillellipse"></a>クレンダターゲット::フィル楕円

指定した楕円の内部を描画します。

```
void FillEllipse(
    const CD2DEllipse& ellipse,
    CD2DBrush* pBrush);
```

### <a name="parameters"></a>パラメーター

*ellipse*<br/>
ペイントする楕円の位置と半径 (デバイスに依存しないピクセル単位)。

*pブラシ*<br/>
楕円の内部を塗るのに使用するブラシ。

## <a name="crendertargetfillgeometry"></a><a name="fillgeometry"></a>をクリックします。

指定したジオメトリの内部を描画します。

```
void FillGeometry(
    CD2DGeometry* pGeometry,
    CD2DBrush* pBrush,
    CD2DBrush* pOpacityBrush = NULL);
```

### <a name="parameters"></a>パラメーター

*ジオメトリ*<br/>
ペイントするジオメトリ。

*pブラシ*<br/>
ジオメトリの内部をペイントするために使用されるブラシ。

*ポパシティブラシ*<br/>
ジオメトリに適用する不透明マスク。不透明マスクなしの場合は NULL。 不透明マスク (不透明ブラシ パラメーター) を指定する場合、ブラシは、その x および y 拡張モードがD2D1_EXTEND_MODE_CLAMPに設定されている ID2D1BitmapBrush である必要があります。 詳細については、「解説」を参照してください。

## <a name="crendertargetfillmesh"></a><a name="fillmesh"></a>クレンダターゲット::フィルメッシュ

指定したメッシュの内部を描画します。

```
void FillMesh(
    CD2DMesh* pMesh,
    CD2DBrush* pBrush);
```

### <a name="parameters"></a>パラメーター

*pメッシュ*<br/>
ペイントするメッシュ。

*pブラシ*<br/>
メッシュをペイントするために使用するブラシ。

## <a name="crendertargetfillopacitymask"></a><a name="fillopacitymask"></a>クレンダターゲット::フィルオパシティマスク

指定したビットマップで記述された不透明マスクをブラシに適用し、そのブラシを使用してレンダー ターゲットの領域をペイントします。

```
void FillOpacityMask(
    CD2DBitmap* pOpacityMask,
    CD2DBrush* pBrush,
    D2D1_OPACITY_MASK_CONTENT content,
    const CD2DRectF& rectDest,
    const CD2DRectF& rectSrc);
```

### <a name="parameters"></a>パラメーター

*ポパシティマスク*<br/>
ペイントする楕円の位置と半径 (デバイスに依存しないピクセル単位)。

*pブラシ*<br/>
destinationRectangle で指定されたレンダー ターゲットの領域を描画するために使用するブラシ。

*content*<br/>
不透明マスクに含まれるコンテンツのタイプ。 この値は、不透明マスクをブレンドするカラースペースを決定するために使用されます。

*レクトデスト*<br/>
デバイスに依存しないピクセル単位でペイントするレンダー ターゲットの領域。

*レクトスrc*<br/>
不透明度マスクとして使用するビットマップの領域 (デバイスに依存しないピクセル単位)。

## <a name="crendertargetfillrectangle"></a><a name="fillrectangle"></a>をクリックします。

指定した四角形の内部を描画します。

```
void FillRectangle(
    const CD2DRectF& rectangle,
    CD2DBrush* pBrush);
```

### <a name="parameters"></a>パラメーター

*四角 形*<br/>
デバイスに依存しないピクセル単位で描画する四角形の寸法。

*pブラシ*<br/>
長方形の内部を塗るのに使用されるブラシ。

## <a name="crendertargetfillroundedrectangle"></a><a name="fillroundedrectangle"></a>クレンダターゲット::フィルラウンド長方形

指定した角丸四角形の内部を描画します。

```
void FillRoundedRectangle(
    const CD2DRoundedRect& rectRounded,
    CD2DBrush* pBrush);
```

### <a name="parameters"></a>パラメーター

*直角丸*<br/>
デバイスに依存しないピクセル単位で、描画する丸みを帯びた四角形のサイズ。

*pブラシ*<br/>
角丸長方形の内部を塗りつぶすために使用するブラシ。

## <a name="crendertargetflush"></a><a name="flush"></a>クレンダターゲット::フラッシュ

保留中のすべての描画コマンドを実行します。

```
void Flush(
    D2D1_TAG* tag1 = NULL,
    D2D1_TAG* tag2 = NULL);
```

### <a name="parameters"></a>パラメーター

*タグ1*<br/>
エラーが発生した描画操作のタグが含まれています。 このパラメーターは初期化せずに渡されます。

*タグ2*<br/>
エラーが発生した描画操作のタグが含まれています。 このパラメーターは初期化せずに渡されます。

## <a name="crendertargetgetantialiasmode"></a><a name="getantialiasmode"></a>クレンダターゲット::アンチエイリアスモード

テキスト以外の描画操作の現在のアンチエイリアス モードを取得します。

```
D2D1_ANTIALIAS_MODE GetAntialiasMode() const;
```

### <a name="return-value"></a>戻り値

テキスト以外の描画操作の現在のアンチエイリアシング モード。

## <a name="crendertargetgetdpi"></a><a name="getdpi"></a>クレンドターゲット::ゲットドピ

レンダー ターゲットの 1 インチあたりのドット数 (DPI) を返します。

```
CD2DSizeF GetDpi() const;
```

### <a name="return-value"></a>戻り値

レンダー ターゲットの 1 インチあたりのドット数 (DPI)。

## <a name="crendertargetgetmaximumbitmapsize"></a><a name="getmaximumbitmapsize"></a>をクリックします。

レンダー ターゲットでサポートされている任意の 1 つのビットマップ ディメンションのデバイス依存単位 (ピクセル単位) の最大サイズを取得します。

```
UINT32 GetMaximumBitmapSize() const;
```

### <a name="return-value"></a>戻り値

レンダー ターゲットでサポートされている任意の 1 つのビットマップ ディメンションの最大サイズ (ピクセル単位)

## <a name="crendertargetgetpixelformat"></a><a name="getpixelformat"></a>をクリックします。

レンダー ターゲットのピクセル形式とアルファ モードを取得します。

```
D2D1_PIXEL_FORMAT GetPixelFormat() const;
```

### <a name="return-value"></a>戻り値

レンダー ターゲットのピクセル形式とアルファ モード

## <a name="crendertargetgetpixelsize"></a><a name="getpixelsize"></a>ターゲット::ピクセルサイズを取得します。

レンダー ターゲットのサイズをデバイス ピクセル単位で返します。

```
CD2DSizeU GetPixelSize() const;
```

### <a name="return-value"></a>戻り値

レンダー ターゲットのサイズ (デバイス ピクセル単位)

## <a name="crendertargetgetrendertarget"></a><a name="getrendertarget"></a>をクリックします。

インターフェイスを返します。

```
ID2D1RenderTarget* GetRenderTarget();
```

### <a name="return-value"></a>戻り値

ID2D1RenderTarget インターフェイスへのポインターまたは NULL オブジェクトがまだ初期化されていない場合。

## <a name="crendertargetgetsize"></a><a name="getsize"></a>ターゲット::ゲットサイズ

レンダー ターゲットのサイズをデバイスに依存しないピクセル単位で返します。

```
CD2DSizeF GetSize() const;
```

### <a name="return-value"></a>戻り値

デバイスに依存しないピクセル単位のレンダー ターゲットの現在のサイズ

## <a name="crendertargetgettags"></a><a name="gettags"></a>をクリックします。

後続の描画操作のラベルを取得します。

```
void GetTags(
    D2D1_TAG* tag1 = NULL,
    D2D1_TAG* tag2 = NULL) const;
```

### <a name="parameters"></a>パラメーター

*タグ1*<br/>
以降の描画操作の最初のラベルが含まれます。 このパラメーターは初期化せずに渡されます。 NULL を指定した場合、このパラメーターの値は取得されません。

*タグ2*<br/>
後続の描画操作の 2 番目のラベルが含まれます。 このパラメーターは初期化せずに渡されます。 NULL を指定した場合、このパラメーターの値は取得されません。

## <a name="crendertargetgettextantialiasmode"></a><a name="gettextantialiasmode"></a>をクリックします。

テキストおよびグリフ描画操作の現在のアンチエイリアシング モードを取得します。

```
D2D1_TEXT_ANTIALIAS_MODE GetTextAntialiasMode() const;
```

### <a name="return-value"></a>戻り値

テキストおよびグリフ描画操作の現在のアンチエイリアシング モード。

## <a name="crendertargetgettextrenderingparams"></a><a name="gettextrenderingparams"></a>をクリックします。

レンダー ターゲットの現在のテキスト レンダリング オプションを取得します。

```
void GetTextRenderingParams(IDWriteRenderingParams** textRenderingParams);
```

### <a name="parameters"></a>パラメーター

*テキストレンダリングパラム*<br/>
このメソッドが返されるときに、textRenderingParams には、レンダー ターゲットの現在のテキスト レンダリング オプションへのポインターのアドレスが格納されます。

## <a name="crendertargetgettransform"></a><a name="gettransform"></a>ソースソース::変換を取得します。

レンダリング ターゲットの現在の変換を取得します。

```
void GetTransform(D2D1_MATRIX_3X2_F* transform);
```

### <a name="parameters"></a>パラメーター

*transform*<br/>
これが返されるときに、レンダー ターゲットの現在の変換を格納します。 このパラメーターは初期化せずに渡されます。

## <a name="crendertargetissupported"></a><a name="issupported"></a>をクリックします。

レンダー ターゲットが指定されたプロパティをサポートするかどうかを示します。

```
BOOL IsSupported(const D2D1_RENDER_TARGET_PROPERTIES& renderTargetProperties) const;
```

### <a name="parameters"></a>パラメーター

*レンダーターゲットプロパティ*<br/>
テストするレンダー ターゲット プロパティ

### <a name="return-value"></a>戻り値

指定されたレンダー ターゲット プロパティがこのレンダー ターゲットでサポートされている場合は TRUE。それ以外の場合は FALSE

## <a name="crendertargetisvalid"></a><a name="isvalid"></a>クレンダターゲット::イズバリ

リソースの有効性を確認します

```
BOOL IsValid() const;
```

### <a name="return-value"></a>戻り値

リソースが有効な場合は TRUE。それ以外の場合は FALSE。

## <a name="crendertargetm_lstresources"></a><a name="m_lstresources"></a>クレンダターゲット::m_lstResources

CD2DResource オブジェクトへのポインターのリスト。

```
CObList m_lstResources;
```

## <a name="crendertargetm_prendertarget"></a><a name="m_prendertarget"></a>クレンダターゲット::m_pRenderTarget

オブジェクトへのポインター。

```
ID2D1RenderTarget* m_pRenderTarget;
```

## <a name="crendertargetm_ptextformatdefault"></a><a name="m_ptextformatdefault"></a>クレンダターゲット::m_pTextFormatDefault

既定のテキスト形式を含む CD2DTextFormat オブジェクトへのポインター。

```
CD2DTextFormat* m_pTextFormatDefault;
```

## <a name="crendertargetoperator-id2d1rendertarget"></a><a name="operator_id2d1rendertarget_star"></a>ソースターゲット::オペレーター ID2D1 レンダーターゲット*

インターフェイスを返します。

```
operator ID2D1RenderTarget*();
```

### <a name="return-value"></a>戻り値

ID2D1RenderTarget インターフェイスへのポインターまたは NULL オブジェクトがまだ初期化されていない場合。

## <a name="crendertargetpopaxisalignedclip"></a><a name="popaxisalignedclip"></a>クレンダターゲット::Pソップアクシスアライメントクリップ

最後の軸に位置合わせされたクリップをレンダー ターゲットから削除します。 このメソッドが呼び出されると、クリップは以降の描画操作に適用されなくなります。

```
void PopAxisAlignedClip();
```

## <a name="crendertargetpoplayer"></a><a name="poplayer"></a>クレンダターゲット::Pソップレイヤー

最後の PushLayer 呼び出しで指定されたレイヤーへの描画操作のリダイレクトを停止します。

```
void PopLayer();
```

## <a name="crendertargetpushaxisalignedclip"></a><a name="pushaxisalignedclip"></a>クレンダターゲット::Pウシュアクシスアライメントクリップ

最後の軸に位置合わせされたクリップをレンダー ターゲットから削除します。 このメソッドが呼び出されると、クリップは以降の描画操作に適用されなくなります。

```
void PushAxisAlignedClip(
    const CD2DRectF& rectClip,
    D2D1_ANTIALIAS_MODE mode = D2D1_ANTIALIAS_MODE_PER_PRIMITIVE);
```

### <a name="parameters"></a>パラメーター

*レクトクリップ*<br/>
クリップ領域のサイズと位置 (デバイスに依存しないピクセル単位)。

*モード*<br/>
サブピクセル境界を持つクリップ矩形のエッジを描画し、クリップをシーンの内容とブレンドするために使用されるアンチエイリアシングモード。 ブレンドは、PopAxisAlignedClip メソッドが呼び出されたときに 1 回実行され、レイヤー内の各プリミティブには適用されません。

## <a name="crendertargetpushlayer"></a><a name="pushlayer"></a>クレンジターゲット::Pウシュレイヤー

指定したレイヤーをレンダー ターゲットに追加し、PopLayer が呼び出されるまで以降のすべての描画操作を受け取ります。

```
void PushLayer(
    const D2D1_LAYER_PARAMETERS& layerParameters,
    CD2DLayer& layer);
```

### <a name="parameters"></a>パラメーター

*レイヤーパラメーター*<br/>
レイヤーのコンテンツ境界、ジオメトリマスク、不透明度、不透明マスク、アンチエイリアシングオプション。

*層*<br/>
後続の描画操作を受け取るレイヤー。

## <a name="crendertargetrestoredrawingstate"></a><a name="restoredrawingstate"></a>ステートターゲット::リストアドローイングステート

レンダー ターゲットの描画状態を、指定した ID2D1DrawingStateBlock の描画状態に設定します。

```
void RestoreDrawingState(ID2D1DrawingStateBlock& drawingStateBlock);
```

### <a name="parameters"></a>パラメーター

*図面ステートブロック*<br/>
レンダー ターゲットの新しい描画状態。

## <a name="crendertargetsavedrawingstate"></a><a name="savedrawingstate"></a>をクリックします。

現在の描画状態を指定した ID2D1DrawingStateBlock に保存します。

```
void SaveDrawingState(ID2D1DrawingStateBlock& drawingStateBlock) const;
```

### <a name="parameters"></a>パラメーター

*図面ステートブロック*<br/>
このメソッドが返されるときに、レンダー ターゲットの現在の描画状態を格納します。 このパラメーターは、メソッドに渡す前に初期化する必要があります。

## <a name="crendertargetsetantialiasmode"></a><a name="setantialiasmode"></a>クレンダターゲット::アンチエイリアスモード

レンダー ターゲットのアンチエイリアシング モードを設定します。 アンチエイリアシング モードは、テキストおよびグリフ描画操作を除く、後続のすべての描画操作に適用されます。

```
void SetAntialiasMode(D2D1_ANTIALIAS_MODE antialiasMode);
```

### <a name="parameters"></a>パラメーター

*アンチエイリアスモード*<br/>
将来の描画操作のためのアンチエイリアシング モード。

## <a name="crendertargetsetdpi"></a><a name="setdpi"></a>クレンドターゲット::セットドピ

レンダー ターゲットのドット/インチ (DPI) を設定します。

```
void SetDpi(const CD2DSizeF& sizeDPI);
```

### <a name="parameters"></a>パラメーター

*サイズ DPI*<br/>
レンダー ターゲットの水平/垂直 DPI を指定する 0 以上の値。

## <a name="crendertargetsettags"></a><a name="settags"></a>クレンダターゲット::セットタグ

後続の図面操作のラベルを指定します。

```
void SetTags(
    D2D1_TAG tag1,
    D2D1_TAG tag2);
```

### <a name="parameters"></a>パラメーター

*タグ1*<br/>
後続の描画操作に適用するラベル。

*タグ2*<br/>
後続の描画操作に適用するラベル。

## <a name="crendertargetsettextantialiasmode"></a><a name="settextantialiasmode"></a>をクリックします。

後続のテキストおよびグリフ描画操作に使用するアンチエイリアシング モードを指定します。

```
void SetTextAntialiasMode(D2D1_TEXT_ANTIALIAS_MODE textAntialiasMode);
```

### <a name="parameters"></a>パラメーター

*テキスト アンチエイリアスモード*<br/>
後続のテキストおよびグリフ描画操作に使用するアンチエイリアシング モード。

## <a name="crendertargetsettextrenderingparams"></a><a name="settextrenderingparams"></a>クレンダターゲット::セットテキストレンダリングパラム

後続のすべてのテキストおよびグリフ描画操作に適用するテキスト レンダリング オプションを指定します。

```
void SetTextRenderingParams(IDWriteRenderingParams* textRenderingParams = NULL);
```

### <a name="parameters"></a>パラメーター

*テキストレンダリングパラム*<br/>
後続のすべてのテキストおよびグリフ描画操作に適用するテキスト レンダリング オプション。現在のテキストレンダリング オプションをクリアするには、NULL を指定します。

## <a name="crendertargetsettransform"></a><a name="settransform"></a>ソースソース::変換を設定します。

指定した変換をレンダー ターゲットに適用し、既存の変換を置き換えます。 それ以降の描画操作はすべて、変換された空間で行われます。

```
void SetTransform(const D2D1_MATRIX_3X2_F* transform);
void SetTransform(const D2D1_MATRIX_3X2_F& transform);
```

### <a name="parameters"></a>パラメーター

*transform*<br/>
レンダー ターゲットに適用する変換。

## <a name="crendertargetverifyresource"></a><a name="verifyresource"></a>リソースを確認します。

CD2D リソース オブジェクトの有効性を確認します。オブジェクトが存在しない場合は、オブジェクトを作成します。

```
BOOL VerifyResource(CD2DResource* pResource);
```

### <a name="parameters"></a>パラメーター

*リソース*<br/>
オブジェクトへのポインター。

### <a name="return-value"></a>戻り値

TRUE は有効な場合はオブジェクトです。それ以外の場合は FALSE。

## <a name="see-also"></a>関連項目

[クラス](../../mfc/reference/mfc-classes.md)

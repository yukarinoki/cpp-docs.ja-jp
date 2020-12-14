---
description: '詳細情報: CD2DGeometry クラス'
title: CD2DGeometry クラス
ms.date: 11/04/2016
f1_keywords:
- CD2DGeometry
- AFXRENDERTARGET/CD2DGeometry
- AFXRENDERTARGET/CD2DGeometry::CD2DGeometry
- AFXRENDERTARGET/CD2DGeometry::Attach
- AFXRENDERTARGET/CD2DGeometry::CombineWithGeometry
- AFXRENDERTARGET/CD2DGeometry::CompareWithGeometry
- AFXRENDERTARGET/CD2DGeometry::ComputeArea
- AFXRENDERTARGET/CD2DGeometry::ComputeLength
- AFXRENDERTARGET/CD2DGeometry::ComputePointAtLength
- AFXRENDERTARGET/CD2DGeometry::Destroy
- AFXRENDERTARGET/CD2DGeometry::Detach
- AFXRENDERTARGET/CD2DGeometry::FillContainsPoint
- AFXRENDERTARGET/CD2DGeometry::Get
- AFXRENDERTARGET/CD2DGeometry::GetBounds
- AFXRENDERTARGET/CD2DGeometry::GetWidenedBounds
- AFXRENDERTARGET/CD2DGeometry::IsValid
- AFXRENDERTARGET/CD2DGeometry::Outline
- AFXRENDERTARGET/CD2DGeometry::Simplify
- AFXRENDERTARGET/CD2DGeometry::StrokeContainsPoint
- AFXRENDERTARGET/CD2DGeometry::Tessellate
- AFXRENDERTARGET/CD2DGeometry::Widen
- AFXRENDERTARGET/CD2DGeometry::m_pGeometry
helpviewer_keywords:
- CD2DGeometry [MFC], CD2DGeometry
- CD2DGeometry [MFC], Attach
- CD2DGeometry [MFC], CombineWithGeometry
- CD2DGeometry [MFC], CompareWithGeometry
- CD2DGeometry [MFC], ComputeArea
- CD2DGeometry [MFC], ComputeLength
- CD2DGeometry [MFC], ComputePointAtLength
- CD2DGeometry [MFC], Destroy
- CD2DGeometry [MFC], Detach
- CD2DGeometry [MFC], FillContainsPoint
- CD2DGeometry [MFC], Get
- CD2DGeometry [MFC], GetBounds
- CD2DGeometry [MFC], GetWidenedBounds
- CD2DGeometry [MFC], IsValid
- CD2DGeometry [MFC], Outline
- CD2DGeometry [MFC], Simplify
- CD2DGeometry [MFC], StrokeContainsPoint
- CD2DGeometry [MFC], Tessellate
- CD2DGeometry [MFC], Widen
- CD2DGeometry [MFC], m_pGeometry
ms.assetid: 3f95054b-fdb8-4e87-87f2-9fc3df7279ec
ms.openlocfilehash: 2c902554ba5377ce9f7a4a481d4001a9ef7a47f9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97193449"
---
# <a name="cd2dgeometry-class"></a>CD2DGeometry クラス

ID2D1Geometry のラッパー。

## <a name="syntax"></a>構文

```
class CD2DGeometry : public CD2DResource;
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CD2DGeometry:: CD2DGeometry](#cd2dgeometry)|CD2DGeometry オブジェクトを構築します。|
|[CD2DGeometry:: ~ CD2DGeometry](#_dtorcd2dgeometry)|デストラクターです。 D2D geometry オブジェクトが破棄されるときに呼び出されます。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CD2DGeometry:: Attach](#attach)|既存のリソースインターフェイスをオブジェクトにアタッチします。|
|[CD2DGeometry:: 連結 Ewithgeometry](#combinewithgeometry)|指定したジオメトリとこのジオメトリを結合し、結果を ID2D1SimplifiedGeometrySink に格納します。|
|[CD2DGeometry:: CompareWithGeometry](#comparewithgeometry)|このジオメトリと指定したジオメトリの交差部分について説明します。 比較は、指定されたフラット化許容範囲を使用して実行されます。|
|[CD2DGeometry:: ComputeArea](#computearea)|指定された行列によって変換され、指定された許容範囲を使用してフラット化された後に、ジオメトリの面積を計算します。|
|[CD2DGeometry:: ComputeLength](#computelength)|各セグメントが線に重ねられていない場合と同じように、ジオメトリの長さを計算します。|
|[CD2DGeometry:: ComputePointAtLength](#computepointatlength)|指定した行列によって変換され、指定された許容範囲を使用してフラット化された後の、指定した距離におけるポイントおよびタンジェントベクターを計算します。|
|[CD2DGeometry::D estroy](#destroy)|CD2DGeometry オブジェクトを破棄します。 ( [CD2DResource::D estroy](../../mfc/reference/cd2dresource-class.md#destroy)をオーバーライドします。)|
|[CD2DGeometry::D etach](#detach)|オブジェクトからリソースインターフェイスをデタッチします。|
|[CD2DGeometry:: FillContainsPoint](#fillcontainspoint)|指定された平坦化の許容範囲を指定して、ジオメトリによって塗りつぶされる領域に指定された点が含まれるかどうかを示します。|
|[CD2DGeometry:: Get](#get)|ID2D1Geometry インターフェイスを返します。|
|[CD2DGeometry:: GetBounds](#getbounds)||
|[CD2DGeometry:: GetWidenedBounds](#getwidenedbounds)|指定したストロークの幅とスタイルによって拡張され、指定した行列によって変換された後のジオメトリの境界を取得します。|
|[CD2DGeometry:: IsValid](#isvalid)|リソースの有効性を確認します ( [CD2DResource:: IsValid](../../mfc/reference/cd2dresource-class.md#isvalid)をオーバーライドします)。|
|[CD2DGeometry:: アウトライン](#outline)|ジオメトリの輪郭を計算し、結果を ID2D1SimplifiedGeometrySink に書き込みます。|
|[CD2DGeometry:: 単純化](#simplify)|直線と (必要に応じて) 3 次ベジエ曲線だけを含み、結果を ID2D1SimplifiedGeometrySink に書き込む geometry の簡略化されたバージョンを作成します。|
|[CD2DGeometry:: StrokeContainsPoint](#strokecontainspoint)|指定したストロークの太さ、スタイル、および変換を指定して、ジオメトリのストロークに指定した点が含まれているかどうかを判断します。|
|[CD2DGeometry:: テセレーション](#tessellate)|指定したマトリックスを使用して変換され、指定した許容範囲を使用してフラット化された後で、geometry をカバーする時計回りの三角形のセットを作成します。|
|[CD2DGeometry:: 広げ](#widen)|指定したストロークでジオメトリを拡大し、指定した行列によって変換され、指定された許容範囲を使用してフラット化された後に、結果を ID2D1SimplifiedGeometrySink に書き込みます。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[CD2DGeometry:: operator ID2D1Geometry *](#operator_id2d1geometry_star)|ID2D1Geometry インターフェイスを返します。|

### <a name="protected-data-members"></a>プロテクト データ メンバー

|名前|説明|
|----------|-----------------|
|[CD2DGeometry:: m_pGeometry](#m_pgeometry)|ID2D1Geometry へのポインター。|

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CD2DResource](../../mfc/reference/cd2dresource-class.md)

`CD2DGeometry`

## <a name="requirements"></a>要件

**ヘッダー:** afxrendertarget

## <a name="cd2dgeometrycd2dgeometry"></a><a name="_dtorcd2dgeometry"></a> CD2DGeometry:: ~ CD2DGeometry

デストラクターです。 D2D geometry オブジェクトが破棄されるときに呼び出されます。

```
virtual ~CD2DGeometry();
```

## <a name="cd2dgeometryattach"></a><a name="attach"></a> CD2DGeometry:: Attach

既存のリソースインターフェイスをオブジェクトにアタッチします。

```cpp
void Attach(ID2D1Geometry* pResource);
```

### <a name="parameters"></a>パラメーター

*pResource*<br/>
既存のリソースインターフェイス。 NULL にすることはできません

## <a name="cd2dgeometrycd2dgeometry"></a><a name="cd2dgeometry"></a> CD2DGeometry:: CD2DGeometry

CD2DGeometry オブジェクトを構築します。

```
CD2DGeometry(
    CRenderTarget* pParentTarget,
    BOOL bAutoDestroy = TRUE);
```

### <a name="parameters"></a>パラメーター

*pParentTarget*<br/>
レンダーターゲットへのポインター。

*bAutoDestroy*<br/>
オブジェクトが所有者 (pParentTarget) によって破棄されることを示します。

## <a name="cd2dgeometrycombinewithgeometry"></a><a name="combinewithgeometry"></a> CD2DGeometry:: 連結 Ewithgeometry

指定したジオメトリとこのジオメトリを結合し、結果を ID2D1SimplifiedGeometrySink に格納します。

```
BOOL CombineWithGeometry(
    CD2DGeometry& inputGeometry,
    D2D1_COMBINE_MODE combineMode,
    const D2D1_MATRIX_3X2_F& inputGeometryTransform,
    ID2D1SimplifiedGeometrySink* geometrySink,
    FLOAT flatteningTolerance = D2D1_DEFAULT_FLATTENING_TOLERANCE) const;
```

### <a name="parameters"></a>パラメーター

*inputGeometry*<br/>
このインスタンスと結合するジオメトリ。

*combineMode*<br/>
実行する結合操作の種類。

*inputGeometryTransform*<br/>
結合する前に inputGeometry に適用する変換。

*geometrySink*<br/>
結合演算の結果。

*flatteningTolerance*<br/>
ジオメトリの多角形近似における点と点の間の距離の上限。 値が小さいほど、生成される結果の精度は高まりますが、実行速度が低下します。

### <a name="return-value"></a>戻り値

メソッドが成功した場合、TRUE を返します。 それ以外の場合は FALSE を返します。

## <a name="cd2dgeometrycomparewithgeometry"></a><a name="comparewithgeometry"></a> CD2DGeometry:: CompareWithGeometry

このジオメトリと指定したジオメトリの交差部分について説明します。 比較は、指定されたフラット化許容範囲を使用して実行されます。

```
D2D1_GEOMETRY_RELATION CompareWithGeometry(
    CD2DGeometry& inputGeometry,
    const D2D1_MATRIX_3X2_F& inputGeometryTransform,
    FLOAT flatteningTolerance = D2D1_DEFAULT_FLATTENING_TOLERANCE) const;
```

### <a name="parameters"></a>パラメーター

*inputGeometry*<br/>
テストするジオメトリ。

*inputGeometryTransform*<br/>
InputGeometry に適用する変換。

*flatteningTolerance*<br/>
ジオメトリの多角形近似における点と点の間の距離の上限。 値が小さいほど、生成される結果の精度は高まりますが、実行速度が低下します。

### <a name="return-value"></a>戻り値

メソッドが成功した場合、TRUE を返します。 それ以外の場合は FALSE を返します。

## <a name="cd2dgeometrycomputearea"></a><a name="computearea"></a> CD2DGeometry:: ComputeArea

指定された行列によって変換され、指定された許容範囲を使用してフラット化された後に、ジオメトリの面積を計算します。

```
BOOL ComputeArea(
    const D2D1_MATRIX_3X2_F& worldTransform,
    FLOAT& area,
    FLOAT flatteningTolerance = D2D1_DEFAULT_FLATTENING_TOLERANCE) const;
```

### <a name="parameters"></a>パラメーター

*worldTransform*<br/>
領域を計算する前にこのジオメトリに適用する変換。

*領域*<br/>
このメソッドから制御が戻るときに、このジオメトリの変換されたフラット化されたバージョンの領域へのポインターを格納します。 このパラメーターにはストレージを割り当てる必要があります。

*flatteningTolerance*<br/>
ジオメトリの多角形近似における点と点の間の距離の上限。 値が小さいほど、生成される結果の精度は高まりますが、実行速度が低下します。

### <a name="return-value"></a>戻り値

メソッドが成功した場合、TRUE を返します。 それ以外の場合は FALSE を返します。

## <a name="cd2dgeometrycomputelength"></a><a name="computelength"></a> CD2DGeometry:: ComputeLength

各セグメントが線に重ねられていない場合と同じように、ジオメトリの長さを計算します。

```
BOOL ComputeLength(
    const D2D1_MATRIX_3X2_F& worldTransform,
    FLOAT& length,
    FLOAT flatteningTolerance = D2D1_DEFAULT_FLATTENING_TOLERANCE) const;
```

### <a name="parameters"></a>パラメーター

*worldTransform*<br/>
長さを計算する前にジオメトリに適用する変換。

*length*<br/>
このメソッドから制御が戻るときに、ジオメトリの長さへのポインターを格納します。 閉じたジオメトリの場合、長さには暗黙的な終了セグメントが含まれます。 このパラメーターにはストレージを割り当てる必要があります。

*flatteningTolerance*<br/>
ジオメトリの多角形近似における点と点の間の距離の上限。 値が小さいほど、生成される結果の精度は高まりますが、実行速度が低下します。

### <a name="return-value"></a>戻り値

メソッドが成功した場合、TRUE を返します。 それ以外の場合は FALSE を返します。

## <a name="cd2dgeometrycomputepointatlength"></a><a name="computepointatlength"></a> CD2DGeometry:: ComputePointAtLength

指定した行列によって変換され、指定された許容範囲を使用してフラット化された後の、指定した距離におけるポイントおよびタンジェントベクターを計算します。

```
BOOL ComputePointAtLength(
    FLOAT length,
    const D2D1_MATRIX_3X2_F& worldTransform,
    CD2DPointF& point,
    CD2DPointF& unitTangentVector,
    FLOAT flatteningTolerance = D2D1_DEFAULT_FLATTENING_TOLERANCE) const;
```

### <a name="parameters"></a>パラメーター

*length*<br/>
検索するポイントとタンジェントのジオメトリに沿った距離。 この距離が0より小さい場合、このメソッドはジオメトリ内の最初の点を計算します。 この距離が geometry の長さよりも大きい場合、このメソッドはジオメトリの最後の点を計算します。

*worldTransform*<br/>
指定した点とタンジェントを計算する前にジオメトリに適用する変換。

*視点*<br/>
ジオメトリに沿って指定した距離にある位置。 ジオメトリが空の場合、このポイントは x および y 値として NaN を含みます。

*unitTangentVector*<br/>
このメソッドから制御が戻るときに、指定した距離にある接線ベクトルへのポインターを、ジオメトリに沿って格納します。 ジオメトリが空の場合、このベクターには、x 値と y 値として NaN が含まれます。 このパラメーターにはストレージを割り当てる必要があります。

*flatteningTolerance*<br/>
ジオメトリの多角形近似における点と点の間の距離の上限。 値が小さいほど、生成される結果の精度は高まりますが、実行速度が低下します。

### <a name="return-value"></a>戻り値

メソッドが成功した場合、TRUE を返します。 それ以外の場合は FALSE を返します。

## <a name="cd2dgeometrydestroy"></a><a name="destroy"></a> CD2DGeometry::D estroy

CD2DGeometry オブジェクトを破棄します。

```
virtual void Destroy();
```

## <a name="cd2dgeometrydetach"></a><a name="detach"></a> CD2DGeometry::D etach

オブジェクトからリソースインターフェイスをデタッチします。

```
ID2D1Geometry* Detach();
```

### <a name="return-value"></a>戻り値

デタッチされたリソースインターフェイスへのポインター。

## <a name="cd2dgeometryfillcontainspoint"></a><a name="fillcontainspoint"></a> CD2DGeometry:: FillContainsPoint

指定された平坦化の許容範囲を指定して、ジオメトリによって塗りつぶされる領域に指定された点が含まれるかどうかを示します。

```
BOOL FillContainsPoint(
    CD2DPointF point,
    const D2D1_MATRIX_3X2_F& worldTransform,
    BOOL* contains,
    FLOAT flatteningTolerance = D2D1_DEFAULT_FLATTENING_TOLERANCE) const;
```

### <a name="parameters"></a>パラメーター

*視点*<br/>
テストするポイント。

*worldTransform*<br/>
コンテインメントのテストの前にジオメトリに適用する変換。

*contains*<br/>
このメソッドから制御が戻るときに、ジオメトリによって塗りつぶされた領域に point が含まれている場合は、ブール値が格納されます。それ以外の場合は FALSE。 このパラメーターにはストレージを割り当てる必要があります。

*flatteningTolerance*<br/>
正確なジオメトリックパスとパスの積集合を計算するために使用する数値精度。 Fill が不足している点は、許容範囲内であると見なされます。 値が小さいほど、生成される結果の精度は高まりますが、実行速度が低下します。

### <a name="return-value"></a>戻り値

メソッドが成功した場合、TRUE を返します。 それ以外の場合は FALSE を返します。

## <a name="cd2dgeometryget"></a><a name="get"></a> CD2DGeometry:: Get

ID2D1Geometry インターフェイスを返します。

```
ID2D1Geometry* Get();
```

### <a name="return-value"></a>戻り値

ID2D1Geometry インターフェイスへのポインター。オブジェクトがまだ初期化されていない場合は NULL。

## <a name="cd2dgeometrygetbounds"></a><a name="getbounds"></a> CD2DGeometry:: GetBounds

```
BOOL GetBounds(
const D2D1_MATRIX_3X2_F& worldTransform,
CD2DRectF& bounds) const;
```

### <a name="parameters"></a>パラメーター

*worldTransform*<br/>
*線*

### <a name="return-value"></a>戻り値

## <a name="cd2dgeometrygetwidenedbounds"></a><a name="getwidenedbounds"></a> CD2DGeometry:: GetWidenedBounds

指定したストロークの幅とスタイルによって拡張され、指定した行列によって変換された後のジオメトリの境界を取得します。

```
BOOL GetWidenedBounds(
    FLOAT strokeWidth,
    ID2D1StrokeStyle* strokeStyle,
    const D2D1_MATRIX_3X2_F& worldTransform,
    CD2DRectF& bounds,
    FLOAT flatteningTolerance = D2D1_DEFAULT_FLATTENING_TOLERANCE) const;
```

### <a name="parameters"></a>パラメーター

*strokeWidth*<br/>
その輪郭を描画して、ジオメトリを拡大する量。

*strokeStyle*<br/>
ジオメトリを拡大するストロークのスタイル。

*worldTransform*<br/>
ジオメトリを変換した後、ジオメトリにストロークを適用した後に、ジオメトリに適用する変換。

*線*<br/>
このメソッドから制御が戻るときに、拡張されたジオメトリの境界を格納します。 このパラメーターにはストレージを割り当てる必要があります。

*flatteningTolerance*<br/>
ジオメトリの多角形近似における点と点の間の距離の上限。 値が小さいほど、生成される結果の精度は高まりますが、実行速度が低下します。

### <a name="return-value"></a>戻り値

メソッドが成功した場合、TRUE を返します。 それ以外の場合は FALSE を返します。

## <a name="cd2dgeometryisvalid"></a><a name="isvalid"></a> CD2DGeometry:: IsValid

リソースの有効性を確認します

```
virtual BOOL IsValid() const;
```

### <a name="return-value"></a>戻り値

リソースが有効な場合は TRUE。それ以外の場合は FALSE。

## <a name="cd2dgeometrym_pgeometry"></a><a name="m_pgeometry"></a> CD2DGeometry:: m_pGeometry

ID2D1Geometry へのポインター。

```
ID2D1Geometry* m_pGeometry;
```

## <a name="cd2dgeometryoperator-id2d1geometry"></a><a name="operator_id2d1geometry_star"></a> CD2DGeometry:: operator ID2D1Geometry *

ID2D1Geometry インターフェイスを返します。

```
operator ID2D1Geometry*();
```

### <a name="return-value"></a>戻り値

ID2D1Geometry インターフェイスへのポインター。オブジェクトがまだ初期化されていない場合は NULL。

## <a name="cd2dgeometryoutline"></a><a name="outline"></a> CD2DGeometry:: アウトライン

ジオメトリの輪郭を計算し、結果を ID2D1SimplifiedGeometrySink に書き込みます。

```
BOOL Outline(
    const D2D1_MATRIX_3X2_F& worldTransform,
    ID2D1SimplifiedGeometrySink* geometrySink,
    FLOAT flatteningTolerance = D2D1_DEFAULT_FLATTENING_TOLERANCE) const;
```

### <a name="parameters"></a>パラメーター

*worldTransform*<br/>
ジオメトリアウトラインに適用する変換。

*geometrySink*<br/>
ジオメトリが変換されたアウトラインの追加先となる ID2D1SimplifiedGeometrySink。

*flatteningTolerance*<br/>
ジオメトリの多角形近似における点と点の間の距離の上限。 値が小さいほど、生成される結果の精度は高まりますが、実行速度が低下します。

### <a name="return-value"></a>戻り値

メソッドが成功した場合、TRUE を返します。 それ以外の場合は FALSE を返します。

## <a name="cd2dgeometrysimplify"></a><a name="simplify"></a> CD2DGeometry:: 単純化

直線と (必要に応じて) 3 次ベジエ曲線だけを含み、結果を ID2D1SimplifiedGeometrySink に書き込む geometry の簡略化されたバージョンを作成します。

```
BOOL Simplify(
    D2D1_GEOMETRY_SIMPLIFICATION_OPTION simplificationOption,
    const D2D1_MATRIX_3X2_F& worldTransform,
    ID2D1SimplifiedGeometrySink* geometrySink,
    FLOAT flatteningTolerance = D2D1_DEFAULT_FLATTENING_TOLERANCE) const;
```

### <a name="parameters"></a>パラメーター

*simplificationOption*<br/>
簡略化されたジオメトリに曲線を含めるかどうかを指定する値。

*worldTransform*<br/>
簡略化されたジオメトリに適用する変換。

*geometrySink*<br/>
簡略化されたジオメトリの追加先となる ID2D1SimplifiedGeometrySink。

*flatteningTolerance*<br/>
ジオメトリの多角形近似における点と点の間の距離の上限。 値が小さいほど、生成される結果の精度は高まりますが、実行速度が低下します。

### <a name="return-value"></a>戻り値

メソッドが成功した場合、TRUE を返します。 それ以外の場合は FALSE を返します。

## <a name="cd2dgeometrystrokecontainspoint"></a><a name="strokecontainspoint"></a> CD2DGeometry:: StrokeContainsPoint

指定したストロークの太さ、スタイル、および変換を指定して、ジオメトリのストロークに指定した点が含まれているかどうかを判断します。

```
BOOL StrokeContainsPoint(
    CD2DPointF point,
    FLOAT strokeWidth,
    ID2D1StrokeStyle* strokeStyle,
    const D2D1_MATRIX_3X2_F& worldTransform,
    BOOL* contains,
    FLOAT flatteningTolerance = D2D1_DEFAULT_FLATTENING_TOLERANCE) const;
```

### <a name="parameters"></a>パラメーター

*視点*<br/>
コンテインメントのテスト対象の点。

*strokeWidth*<br/>
適用するストロークの太さ。

*strokeStyle*<br/>
適用するストロークのスタイル。

*worldTransform*<br/>
ストロークジオメトリに適用する変換。

*contains*<br/>
このメソッドから制御が戻るときに、ジオメトリのストロークに指定した点が含まれている場合は TRUE に設定されたブール値を格納します。それ以外の場合は FALSE。 このパラメーターにはストレージを割り当てる必要があります。

*flatteningTolerance*<br/>
正確なジオメトリックパスとパスの積集合を計算するために使用する数値精度。 ストロークが不足している点は、許容範囲内であると見なされます。 値が小さいほど、生成される結果の精度は高まりますが、実行速度が低下します。

### <a name="return-value"></a>戻り値

メソッドが成功した場合、TRUE を返します。 それ以外の場合は FALSE を返します。

## <a name="cd2dgeometrytessellate"></a><a name="tessellate"></a> CD2DGeometry:: テセレーション

指定したマトリックスを使用して変換され、指定した許容範囲を使用してフラット化された後で、geometry をカバーする時計回りの三角形のセットを作成します。

```
BOOL Tessellate(
    const D2D1_MATRIX_3X2_F& worldTransform,
    ID2D1TessellationSink* tessellationSink,
    FLOAT flatteningTolerance = D2D1_DEFAULT_FLATTENING_TOLERANCE) const;
```

### <a name="parameters"></a>パラメーター

*worldTransform*<br/>
このジオメトリに適用する変換、または NULL。

*tessellationSink*<br/>
テセレーションが追加される ID2D1TessellationSink。

*flatteningTolerance*<br/>
ジオメトリの多角形近似における点と点の間の距離の上限。 値が小さいほど、生成される結果の精度は高まりますが、実行速度が低下します。

### <a name="return-value"></a>戻り値

メソッドが成功した場合、TRUE を返します。 それ以外の場合は FALSE を返します。

## <a name="cd2dgeometrywiden"></a><a name="widen"></a> CD2DGeometry:: 広げ

指定したストロークでジオメトリを拡大し、指定した行列によって変換され、指定された許容範囲を使用してフラット化された後に、結果を ID2D1SimplifiedGeometrySink に書き込みます。

```
BOOL Widen(
    FLOAT strokeWidth,
    ID2D1StrokeStyle* strokeStyle,
    const D2D1_MATRIX_3X2_F& worldTransform,
    ID2D1SimplifiedGeometrySink* geometrySink,
    FLOAT flatteningTolerance = D2D1_DEFAULT_FLATTENING_TOLERANCE) const;
```

### <a name="parameters"></a>パラメーター

*strokeWidth*<br/>
ジオメトリを拡大する量。

*strokeStyle*<br/>
ジオメトリに適用するストロークのスタイル、または NULL。

*worldTransform*<br/>
拡大後にジオメトリに適用する変換。

*geometrySink*<br/>
拡張されたジオメトリの追加先となる ID2D1SimplifiedGeometrySink。

*flatteningTolerance*<br/>
ジオメトリの多角形近似における点と点の間の距離の上限。 値が小さいほど、生成される結果の精度は高まりますが、実行速度が低下します。

### <a name="return-value"></a>戻り値

メソッドが成功した場合、TRUE を返します。 それ以外の場合は FALSE を返します。

## <a name="see-also"></a>関連項目

[クラス](../../mfc/reference/mfc-classes.md)

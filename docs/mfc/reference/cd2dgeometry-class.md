---
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
ms.openlocfilehash: 4727f7b1799604001134ee2f4d2d2e1ce6db87fa
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "81754788"
---
# <a name="cd2dgeometry-class"></a>CD2DGeometry クラス

ID2D1 ジオメトリのラッパー。

## <a name="syntax"></a>構文

```
class CD2DGeometry : public CD2DResource;
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CD2Dジオメトリ::CD2Dジオメトリ](#cd2dgeometry)|オブジェクトを作成します。|
|[CD2D ジオメトリ::~CD2D ジオメトリ](#_dtorcd2dgeometry)|デストラクターです。 D2D ジオメトリ オブジェクトが破棄されるときに呼び出されます。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CD2Dジオメトリ::アタッチ](#attach)|既存のリソース インターフェイスをオブジェクトにアタッチします。|
|[CD2Dジオメトリ::結合ジオメトリ](#combinewithgeometry)|指定したジオメトリとこのジオメトリを結合し、その結果を ID2D1 簡略ジオメトリ シンクに格納します。|
|[ジオメトリを比較します。](#comparewithgeometry)|このジオメトリと指定したジオメトリの間の交差部分を記述します。 比較は、指定されたフラット化許容値を使用して実行されます。|
|[CD2Dジオメトリ::コンピューティングエリア](#computearea)|指定した行列によって変換され、指定された許容値を使用してフラット化された後のジオメトリの領域を計算します。|
|[CD2Dジオメトリ::コンピュートレンス](#computelength)|各セグメントがラインに展開されたかのように、ジオメトリの長さを計算します。|
|[CD2Dジオメトリ::コンピューティングポイントアットレングス](#computepointatlength)|指定した行列によって変換され、指定された許容差を使用してフラット化された後、ジオメトリに沿って指定した距離でポイントおよびタンジェント ベクトルを計算します。|
|[CD2Dジオメトリ::Dエストロイ](#destroy)|CD2DGeometry オブジェクトを破棄します。 [(CD2D リソース::Dエストロイ](../../mfc/reference/cd2dresource-class.md#destroy)をオーバーライドします。|
|[CD2Dジオメトリ::Dエタッハ](#detach)|オブジェクトからリソース インターフェイスを切り離します。|
|[CD2Dジオメトリ::フィルインスイ](#fillcontainspoint)|指定したフラット化許容値に応じて、ジオメトリによって塗りつぶされた領域に指定された点が含まれるかどうかを示します。|
|[CD2Dジオメトリ::取得](#get)|ID2D1 ジオメトリ インターフェイスを返します。|
|[CD2Dジオメトリ::ゲットバウンド](#getbounds)||
|[CD2Dジオメトリ::幅広い境界を取得します。](#getwidenedbounds)|指定したストローク幅とスタイルによって広げられ、指定した行列によって変換された後のジオメトリの境界を取得します。|
|[CD2Dジオメトリ::IsValid](#isvalid)|リソースの妥当性を確認します[(CD2D リソースをオーバーライドします::IsValid](../../mfc/reference/cd2dresource-class.md#isvalid).)|
|[CD2Dジオメトリ::アウトライン](#outline)|ジオメトリのアウトラインを計算し、その結果を ID2D1 簡略ジオメトリ シンクに書き込みます。|
|[CD2Dジオメトリ::単純化](#simplify)|線のみを含むジオメトリの簡略化されたバージョンを作成し、(オプションで)3 次ベジエ曲線を含み、その結果を ID2D1簡体字ジオメトリシンクに書き込みます。|
|[CD2Dジオメトリ::ストロークContainsPoint](#strokecontainspoint)|指定したストロークの太さ、スタイル、および変換を指定した点がジオメトリのストロークに含まれているかどうかを判断します。|
|[CD2Dジオメトリ::テッセレート](#tessellate)|指定したマトリックスを使用して変換され、指定した許容範囲を使用してフラット化された後で、geometry をカバーする時計回りの三角形のセットを作成します。|
|[CD2Dジオメトリ::幅広く](#widen)|指定したストロークによってジオメトリを拡大し、指定した行列によって変換され、指定された許容値を使用してフラット化された後、その結果を ID2D1簡体字ジオメトリ シンクに書き込みます。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[CD2D ジオメトリ::演算子 ID2D1 ジオメトリ*](#operator_id2d1geometry_star)|ID2D1 ジオメトリ インターフェイスを返します。|

### <a name="protected-data-members"></a>プロテクト データ メンバー

|名前|説明|
|----------|-----------------|
|[CD2Dジオメトリ::m_pGeometry](#m_pgeometry)|ID2D1 ジオメトリへのポインター。|

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[リソース](../../mfc/reference/cd2dresource-class.md)

`CD2DGeometry`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxrendertarget.h

## <a name="cd2dgeometrycd2dgeometry"></a><a name="_dtorcd2dgeometry"></a>CD2D ジオメトリ::~CD2D ジオメトリ

デストラクターです。 D2D ジオメトリ オブジェクトが破棄されるときに呼び出されます。

```
virtual ~CD2DGeometry();
```

## <a name="cd2dgeometryattach"></a><a name="attach"></a>CD2Dジオメトリ::アタッチ

既存のリソース インターフェイスをオブジェクトにアタッチします。

```cpp
void Attach(ID2D1Geometry* pResource);
```

### <a name="parameters"></a>パラメーター

*リソース*<br/>
既存のリソース インターフェイス。 NULL にすることはできません。

## <a name="cd2dgeometrycd2dgeometry"></a><a name="cd2dgeometry"></a>CD2Dジオメトリ::CD2Dジオメトリ

オブジェクトを作成します。

```
CD2DGeometry(
    CRenderTarget* pParentTarget,
    BOOL bAutoDestroy = TRUE);
```

### <a name="parameters"></a>パラメーター

*ターゲット*<br/>
レンダー ターゲットへのポインター。

*b自動破壊*<br/>
オブジェクトが所有者 (pParentTarget) によって破棄されることを示します。

## <a name="cd2dgeometrycombinewithgeometry"></a><a name="combinewithgeometry"></a>CD2Dジオメトリ::結合ジオメトリ

指定したジオメトリとこのジオメトリを結合し、その結果を ID2D1 簡略ジオメトリ シンクに格納します。

```
BOOL CombineWithGeometry(
    CD2DGeometry& inputGeometry,
    D2D1_COMBINE_MODE combineMode,
    const D2D1_MATRIX_3X2_F& inputGeometryTransform,
    ID2D1SimplifiedGeometrySink* geometrySink,
    FLOAT flatteningTolerance = D2D1_DEFAULT_FLATTENING_TOLERANCE) const;
```

### <a name="parameters"></a>パラメーター

*入力ジオメトリ*<br/>
このインスタンスと結合するジオメトリ。

*コンバインモード*<br/>
実行する結合操作の種類。

*変換を入力します。*<br/>
結合する前に入力ジオメトリに適用する変換。

*ジオメトリシンク*<br/>
結合操作の結果。

*フラット化許容範囲*<br/>
ジオメトリの多角形近似における点と点の間の距離の上限。 値が小さいほど、生成される結果の精度は高まりますが、実行速度が低下します。

### <a name="return-value"></a>戻り値

メソッドが成功すると、TRUE が返されます。 それ以外の場合は FALSE を返します。

## <a name="cd2dgeometrycomparewithgeometry"></a><a name="comparewithgeometry"></a>ジオメトリを比較します。

このジオメトリと指定したジオメトリの間の交差部分を記述します。 比較は、指定されたフラット化許容値を使用して実行されます。

```
D2D1_GEOMETRY_RELATION CompareWithGeometry(
    CD2DGeometry& inputGeometry,
    const D2D1_MATRIX_3X2_F& inputGeometryTransform,
    FLOAT flatteningTolerance = D2D1_DEFAULT_FLATTENING_TOLERANCE) const;
```

### <a name="parameters"></a>パラメーター

*入力ジオメトリ*<br/>
テストするジオメトリ。

*変換を入力します。*<br/>
入力ジオメトリに適用する変換。

*フラット化許容範囲*<br/>
ジオメトリの多角形近似における点と点の間の距離の上限。 値が小さいほど、生成される結果の精度は高まりますが、実行速度が低下します。

### <a name="return-value"></a>戻り値

メソッドが成功すると、TRUE が返されます。 それ以外の場合は FALSE を返します。

## <a name="cd2dgeometrycomputearea"></a><a name="computearea"></a>CD2Dジオメトリ::コンピューティングエリア

指定した行列によって変換され、指定された許容値を使用してフラット化された後のジオメトリの領域を計算します。

```
BOOL ComputeArea(
    const D2D1_MATRIX_3X2_F& worldTransform,
    FLOAT& area,
    FLOAT flatteningTolerance = D2D1_DEFAULT_FLATTENING_TOLERANCE) const;
```

### <a name="parameters"></a>パラメーター

*世界トランスフォーム*<br/>
面積を計算する前に、このジオメトリに適用する変換。

*領域*<br/>
このメソッドが返されるときに、このジオメトリの変換されたフラット化されたバージョンの領域へのポインターを格納します。 このパラメーターのストレージを割り振る必要があります。

*フラット化許容範囲*<br/>
ジオメトリの多角形近似における点と点の間の距離の上限。 値が小さいほど、生成される結果の精度は高まりますが、実行速度が低下します。

### <a name="return-value"></a>戻り値

メソッドが成功すると、TRUE が返されます。 それ以外の場合は FALSE を返します。

## <a name="cd2dgeometrycomputelength"></a><a name="computelength"></a>CD2Dジオメトリ::コンピュートレンス

各セグメントがラインに展開されたかのように、ジオメトリの長さを計算します。

```
BOOL ComputeLength(
    const D2D1_MATRIX_3X2_F& worldTransform,
    FLOAT& length,
    FLOAT flatteningTolerance = D2D1_DEFAULT_FLATTENING_TOLERANCE) const;
```

### <a name="parameters"></a>パラメーター

*世界トランスフォーム*<br/>
長さを計算する前にジオメトリに適用する変換。

*length*<br/>
このメソッドが返されるときに、ジオメトリの長さへのポインターを格納します。 閉じたジオメトリの場合、長さには暗黙的な終了セグメントが含まれます。 このパラメーターのストレージを割り振る必要があります。

*フラット化許容範囲*<br/>
ジオメトリの多角形近似における点と点の間の距離の上限。 値が小さいほど、生成される結果の精度は高まりますが、実行速度が低下します。

### <a name="return-value"></a>戻り値

メソッドが成功すると、TRUE が返されます。 それ以外の場合は FALSE を返します。

## <a name="cd2dgeometrycomputepointatlength"></a><a name="computepointatlength"></a>CD2Dジオメトリ::コンピューティングポイントアットレングス

指定した行列によって変換され、指定された許容差を使用してフラット化された後、ジオメトリに沿って指定した距離でポイントおよびタンジェント ベクトルを計算します。

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
検索するポイントと接線のジオメトリに沿った距離。 この距離が 0 より小さい場合、このメソッドはジオメトリの最初の点を計算します。 この距離がジオメトリの長さより大きい場合、このメソッドはジオメトリの最後の点を計算します。

*世界トランスフォーム*<br/>
指定した点と接線を計算する前にジオメトリに適用する変換。

*ポイント*<br/>
ジオメトリに沿った指定した距離での位置。 ジオメトリが空の場合、このポイントには X 値と y 値として NaN が含まれます。

*ユニットタンジェントベクタ*<br/>
このメソッドが返されるときに、ジオメトリに沿って指定した距離にあるタンジェント ベクトルへのポインターを格納します。 ジオメトリが空の場合、このベクトルには X 値と y 値として NaN が含まれます。 このパラメーターのストレージを割り振る必要があります。

*フラット化許容範囲*<br/>
ジオメトリの多角形近似における点と点の間の距離の上限。 値が小さいほど、生成される結果の精度は高まりますが、実行速度が低下します。

### <a name="return-value"></a>戻り値

メソッドが成功すると、TRUE が返されます。 それ以外の場合は FALSE を返します。

## <a name="cd2dgeometrydestroy"></a><a name="destroy"></a>CD2Dジオメトリ::Dエストロイ

CD2DGeometry オブジェクトを破棄します。

```
virtual void Destroy();
```

## <a name="cd2dgeometrydetach"></a><a name="detach"></a>CD2Dジオメトリ::Dエタッハ

オブジェクトからリソース インターフェイスを切り離します。

```
ID2D1Geometry* Detach();
```

### <a name="return-value"></a>戻り値

デタッチされたリソース インターフェイスへのポインター。

## <a name="cd2dgeometryfillcontainspoint"></a><a name="fillcontainspoint"></a>CD2Dジオメトリ::フィルインスイ

指定したフラット化許容値に応じて、ジオメトリによって塗りつぶされた領域に指定された点が含まれるかどうかを示します。

```
BOOL FillContainsPoint(
    CD2DPointF point,
    const D2D1_MATRIX_3X2_F& worldTransform,
    BOOL* contains,
    FLOAT flatteningTolerance = D2D1_DEFAULT_FLATTENING_TOLERANCE) const;
```

### <a name="parameters"></a>パラメーター

*ポイント*<br/>
テストするポイント。

*世界トランスフォーム*<br/>
格納のテスト前にジオメトリに適用する変換。

*contains*<br/>
このメソッドが返されるときに、ジオメトリによって塗りつぶされた領域にポイントが含まれている場合は TRUE の bool 値が格納されます。それ以外の場合は FALSE。 このパラメーターのストレージを割り振る必要があります。

*フラット化許容範囲*<br/>
正確なジオメトリパスとパス交差が計算される数値精度。 許容値より小さい値で塗りつぶしが欠落しているポイントは、内部と見なされます。 値が小さいほど、生成される結果の精度は高まりますが、実行速度が低下します。

### <a name="return-value"></a>戻り値

メソッドが成功すると、TRUE が返されます。 それ以外の場合は FALSE を返します。

## <a name="cd2dgeometryget"></a><a name="get"></a>CD2Dジオメトリ::取得

ID2D1 ジオメトリ インターフェイスを返します。

```
ID2D1Geometry* Get();
```

### <a name="return-value"></a>戻り値

ID2D1Geometry インターフェイスへのポインターまたは NULL オブジェクトがまだ初期化されていない場合。

## <a name="cd2dgeometrygetbounds"></a><a name="getbounds"></a>CD2Dジオメトリ::ゲットバウンド

```
BOOL GetBounds(
const D2D1_MATRIX_3X2_F& worldTransform,
CD2DRectF& bounds) const;
```

### <a name="parameters"></a>パラメーター

*世界トランスフォーム*<br/>
*境界*

### <a name="return-value"></a>戻り値

## <a name="cd2dgeometrygetwidenedbounds"></a><a name="getwidenedbounds"></a>CD2Dジオメトリ::幅広い境界を取得します。

指定したストローク幅とスタイルによって広げられ、指定した行列によって変換された後のジオメトリの境界を取得します。

```
BOOL GetWidenedBounds(
    FLOAT strokeWidth,
    ID2D1StrokeStyle* strokeStyle,
    const D2D1_MATRIX_3X2_F& worldTransform,
    CD2DRectF& bounds,
    FLOAT flatteningTolerance = D2D1_DEFAULT_FLATTENING_TOLERANCE) const;
```

### <a name="parameters"></a>パラメーター

*ストローク幅*<br/>
アウトラインをなでることによってジオメトリを広げる量。

*ストロークスタイル*<br/>
ジオメトリを拡大するストロークのスタイル。

*世界トランスフォーム*<br/>
ジオメトリが変換された後、ジオメトリがストロークされた後にジオメトリに適用される変換。

*境界*<br/>
このメソッドが返されるときに、拡大されたジオメトリの境界を格納します。 このパラメーターのストレージを割り振る必要があります。

*フラット化許容範囲*<br/>
ジオメトリの多角形近似における点と点の間の距離の上限。 値が小さいほど、生成される結果の精度は高まりますが、実行速度が低下します。

### <a name="return-value"></a>戻り値

メソッドが成功すると、TRUE が返されます。 それ以外の場合は FALSE を返します。

## <a name="cd2dgeometryisvalid"></a><a name="isvalid"></a>CD2Dジオメトリ::IsValid

リソースの有効性を確認します

```
virtual BOOL IsValid() const;
```

### <a name="return-value"></a>戻り値

リソースが有効な場合は TRUE。それ以外の場合は FALSE。

## <a name="cd2dgeometrym_pgeometry"></a><a name="m_pgeometry"></a>CD2Dジオメトリ::m_pGeometry

ID2D1 ジオメトリへのポインター。

```
ID2D1Geometry* m_pGeometry;
```

## <a name="cd2dgeometryoperator-id2d1geometry"></a><a name="operator_id2d1geometry_star"></a>CD2D ジオメトリ::演算子 ID2D1 ジオメトリ*

ID2D1 ジオメトリ インターフェイスを返します。

```
operator ID2D1Geometry*();
```

### <a name="return-value"></a>戻り値

ID2D1Geometry インターフェイスへのポインターまたは NULL オブジェクトがまだ初期化されていない場合。

## <a name="cd2dgeometryoutline"></a><a name="outline"></a>CD2Dジオメトリ::アウトライン

ジオメトリのアウトラインを計算し、その結果を ID2D1 簡略ジオメトリ シンクに書き込みます。

```
BOOL Outline(
    const D2D1_MATRIX_3X2_F& worldTransform,
    ID2D1SimplifiedGeometrySink* geometrySink,
    FLOAT flatteningTolerance = D2D1_DEFAULT_FLATTENING_TOLERANCE) const;
```

### <a name="parameters"></a>パラメーター

*世界トランスフォーム*<br/>
ジオメトリ のアウトラインに適用する変換。

*ジオメトリシンク*<br/>
ジオメトリ変換されたアウトラインが追加される ID2D1簡体字ジオメトリシンク。

*フラット化許容範囲*<br/>
ジオメトリの多角形近似における点と点の間の距離の上限。 値が小さいほど、生成される結果の精度は高まりますが、実行速度が低下します。

### <a name="return-value"></a>戻り値

メソッドが成功すると、TRUE が返されます。 それ以外の場合は FALSE を返します。

## <a name="cd2dgeometrysimplify"></a><a name="simplify"></a>CD2Dジオメトリ::単純化

線のみを含むジオメトリの簡略化されたバージョンを作成し、(オプションで)3 次ベジエ曲線を含み、その結果を ID2D1簡体字ジオメトリシンクに書き込みます。

```
BOOL Simplify(
    D2D1_GEOMETRY_SIMPLIFICATION_OPTION simplificationOption,
    const D2D1_MATRIX_3X2_F& worldTransform,
    ID2D1SimplifiedGeometrySink* geometrySink,
    FLOAT flatteningTolerance = D2D1_DEFAULT_FLATTENING_TOLERANCE) const;
```

### <a name="parameters"></a>パラメーター

*単純化オプション*<br/>
単純化されたジオメトリに曲線を含めるかどうかを指定する値。

*世界トランスフォーム*<br/>
単純化されたジオメトリに適用する変換。

*ジオメトリシンク*<br/>
簡易ジオメトリが追加される ID2D1簡体字ジオメトリシンク。

*フラット化許容範囲*<br/>
ジオメトリの多角形近似における点と点の間の距離の上限。 値が小さいほど、生成される結果の精度は高まりますが、実行速度が低下します。

### <a name="return-value"></a>戻り値

メソッドが成功すると、TRUE が返されます。 それ以外の場合は FALSE を返します。

## <a name="cd2dgeometrystrokecontainspoint"></a><a name="strokecontainspoint"></a>CD2Dジオメトリ::ストロークContainsPoint

指定したストロークの太さ、スタイル、および変換を指定した点がジオメトリのストロークに含まれているかどうかを判断します。

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

*ポイント*<br/>
コンテインメントのテスト対象の点。

*ストローク幅*<br/>
適用するストロークの太さ。

*ストロークスタイル*<br/>
適用するストロークのスタイル。

*世界トランスフォーム*<br/>
ストロークされたジオメトリに適用する変換。

*contains*<br/>
このメソッドが返されるときに、ジオメトリのストロークに指定した点が含まれている場合は TRUE に設定されたブール値を格納します。それ以外の場合は FALSE。 このパラメーターのストレージを割り振る必要があります。

*フラット化許容範囲*<br/>
正確なジオメトリパスとパス交差が計算される数値精度。 許容値より小さい値でストロークが欠落しているポイントは、内部と見なされます。 値が小さいほど、生成される結果の精度は高まりますが、実行速度が低下します。

### <a name="return-value"></a>戻り値

メソッドが成功すると、TRUE が返されます。 それ以外の場合は FALSE を返します。

## <a name="cd2dgeometrytessellate"></a><a name="tessellate"></a>CD2Dジオメトリ::テッセレート

指定したマトリックスを使用して変換され、指定した許容範囲を使用してフラット化された後で、geometry をカバーする時計回りの三角形のセットを作成します。

```
BOOL Tessellate(
    const D2D1_MATRIX_3X2_F& worldTransform,
    ID2D1TessellationSink* tessellationSink,
    FLOAT flatteningTolerance = D2D1_DEFAULT_FLATTENING_TOLERANCE) const;
```

### <a name="parameters"></a>パラメーター

*世界トランスフォーム*<br/>
このジオメトリに適用する変換、または NULL。

*テッセレーションシンク*<br/>
テッセレーションが追加される ID2D1Tessellation シンク。

*フラット化許容範囲*<br/>
ジオメトリの多角形近似における点と点の間の距離の上限。 値が小さいほど、生成される結果の精度は高まりますが、実行速度が低下します。

### <a name="return-value"></a>戻り値

メソッドが成功すると、TRUE が返されます。 それ以外の場合は FALSE を返します。

## <a name="cd2dgeometrywiden"></a><a name="widen"></a>CD2Dジオメトリ::幅広く

指定したストロークによってジオメトリを拡大し、指定した行列によって変換され、指定された許容値を使用してフラット化された後、その結果を ID2D1簡体字ジオメトリ シンクに書き込みます。

```
BOOL Widen(
    FLOAT strokeWidth,
    ID2D1StrokeStyle* strokeStyle,
    const D2D1_MATRIX_3X2_F& worldTransform,
    ID2D1SimplifiedGeometrySink* geometrySink,
    FLOAT flatteningTolerance = D2D1_DEFAULT_FLATTENING_TOLERANCE) const;
```

### <a name="parameters"></a>パラメーター

*ストローク幅*<br/>
ジオメトリの幅を広げる量。

*ストロークスタイル*<br/>
ジオメトリに適用するストロークのスタイル、または NULL。

*世界トランスフォーム*<br/>
拡大した後でジオメトリに適用する変換。

*ジオメトリシンク*<br/>
拡張されたジオメトリが追加される ID2D1簡体字ジオメトリシンク。

*フラット化許容範囲*<br/>
ジオメトリの多角形近似における点と点の間の距離の上限。 値が小さいほど、生成される結果の精度は高まりますが、実行速度が低下します。

### <a name="return-value"></a>戻り値

メソッドが成功すると、TRUE が返されます。 それ以外の場合は FALSE を返します。

## <a name="see-also"></a>関連項目

[クラス](../../mfc/reference/mfc-classes.md)

---
title: CD2DGeometry クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
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
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 05bfd912d3c4b6ee8b462775f6919c5fe81cc936
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="cd2dgeometry-class"></a>CD2DGeometry クラス
ID2D1Geometry のラッパーです。  
  
## <a name="syntax"></a>構文  
  
```  
class CD2DGeometry : public CD2DResource;  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CD2DGeometry::CD2DGeometry](#cd2dgeometry)|CD2DGeometry オブジェクトを構築します。|  
|[CD2DGeometry:: ~ CD2DGeometry](#_dtorcd2dgeometry)|デストラクターです。 D2D geometry オブジェクトが破棄されるときに呼び出されます。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CD2DGeometry::Attach](#attach)|既存のリソースのインターフェイス オブジェクトへの接続|  
|[CD2DGeometry::CombineWithGeometry](#combinewithgeometry)|指定されたジオメトリを使用してこのジオメトリを結合し、その結果、ID2D1SimplifiedGeometrySink に格納します。|  
|[CD2DGeometry::CompareWithGeometry](#comparewithgeometry)|この geometry と指定した geometry の交差部分をについて説明します。 比較は、フラット化の指定された許容範囲を使用して実行します。|  
|[CD2DGeometry::ComputeArea](#computearea)|ジオメトリの領域が計算された後に、指定したマトリックスで変換を使用してフラット許容範囲を指定します。|  
|[CD2DGeometry::ComputeLength](#computelength)|各セグメントは 1 行にロールバックされたかのように、ジオメトリの長さを計算します。|  
|[CD2DGeometry::ComputePointAtLength](#computepointatlength)|ジオメトリに沿って指定された距離にあるポイントおよびタンジェント ベクターが計算された後に、指定したマトリックスで変換を使用してフラット許容範囲を指定します。|  
|[CD2DGeometry::Destroy](#destroy)|CD2DGeometry オブジェクトを破棄します。 (上書き[CD2DResource::Destroy](../../mfc/reference/cd2dresource-class.md#destroy))。|  
|[CD2DGeometry::Detach](#detach)|オブジェクトからリソースのインターフェイスの関連付けを解除します。|  
|[CD2DGeometry::FillContainsPoint](#fillcontainspoint)|ジオメトリで埋められた領域はフラット化の指定された許容範囲を指定した指定したポイントを含めるかどうかを示します。|  
|[CD2DGeometry::Get](#get)|返します ID2D1Geometry インターフェイス|  
|[CD2DGeometry::GetBounds](#getbounds)||  
|[CD2DGeometry::GetWidenedBounds](#getwidenedbounds)|指定した線の幅とスタイルで拡大変換し、指定した行列によって変換された後は、ジオメトリの境界を取得します。|  
|[CD2DGeometry::IsValid](#isvalid)|リソースの有効性をチェック (オーバーライド[CD2DResource::IsValid](../../mfc/reference/cd2dresource-class.md#isvalid))。|  
|[CD2DGeometry::Outline](#outline)|ジオメトリのアウトラインを計算し、ID2D1SimplifiedGeometrySink に結果を書き込みます。|  
|[CD2DGeometry::Simplify](#simplify)|行と (必要に応じて) 3 次ベジエ曲線のみを含み、その結果を ID2D1SimplifiedGeometrySink に書き込みますジオメトリの簡素化されたバージョンを作成します。|  
|[CD2DGeometry::StrokeContainsPoint](#strokecontainspoint)|ジオメトリの線が指定したストロークの太さ、スタイル、および変換を指定した指定したポイントを含むかどうかを判断します。|  
|[CD2DGeometry::Tessellate](#tessellate)|指定した行列を使用して変換された後に、geometry をカバーし、指定された許容範囲を使用してフラット化された時計回りの三角形のセットを作成します。|  
|[CD2DGeometry::Widen](#widen)|指定した線によって、ジオメトリを拡大し、結果、ID2D1SimplifiedGeometrySink にされた後に、指定したマトリックスで変換を使用してフラット許容範囲を指定します。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[CD2DGeometry::operator ID2D1Geometry *](#operator_id2d1geometry_star)|返します ID2D1Geometry インターフェイス|  
  
### <a name="protected-data-members"></a>プロテクト データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CD2DGeometry::m_pGeometry](#m_pgeometry)|ID2D1Geometry へのポインター。|  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CD2DResource](../../mfc/reference/cd2dresource-class.md)  
  
 `CD2DGeometry`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxrendertarget.h  
  
##  <a name="_dtorcd2dgeometry"></a>  CD2DGeometry:: ~ CD2DGeometry  
 デストラクターです。 D2D geometry オブジェクトが破棄されるときに呼び出されます。  
  
```  
virtual ~CD2DGeometry();
```  
  
##  <a name="attach"></a>  CD2DGeometry::Attach  
 既存のリソースのインターフェイス オブジェクトへの接続  
  
```  
void Attach(ID2D1Geometry* pResource);
```  
  
### <a name="parameters"></a>パラメーター  
 `pResource`  
 既存のリソースのインターフェイスです。 NULL をすることはできません。  
  
##  <a name="cd2dgeometry"></a>  CD2DGeometry::CD2DGeometry  
 CD2DGeometry オブジェクトを構築します。  
  
```  
CD2DGeometry(
    CRenderTarget* pParentTarget,  
    BOOL bAutoDestroy = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 `pParentTarget`  
 レンダー ターゲットへのポインター。  
  
 `bAutoDestroy`  
 所有者 (pParentTarget) によって、オブジェクトが破棄されることを示します。  
  
##  <a name="combinewithgeometry"></a>  CD2DGeometry::CombineWithGeometry  
 指定されたジオメトリを使用してこのジオメトリを結合し、その結果、ID2D1SimplifiedGeometrySink に格納します。  
  
```  
BOOL CombineWithGeometry(
    CD2DGeometry& inputGeometry,  
    D2D1_COMBINE_MODE combineMode,  
    const D2D1_MATRIX_3X2_F& inputGeometryTransform,  
    ID2D1SimplifiedGeometrySink* geometrySink,  
    FLOAT flatteningTolerance = D2D1_DEFAULT_FLATTENING_TOLERANCE) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `inputGeometry`  
 このインスタンスと結合するジオメトリ。  
  
 `combineMode`  
 実行する結合操作の種類。  
  
 `inputGeometryTransform`  
 結合前に、inputGeometry に適用する変換です。  
  
 `geometrySink`  
 結合操作の結果。  
  
 `flatteningTolerance`  
 多角形近似のジオメトリの点の間の距離の上限。 小さい値より正確な結果の作成が、実行速度が低下します。  
  
### <a name="return-value"></a>戻り値  
 メソッドが成功した場合は TRUE を返します。 それ以外の場合、FALSE を返します。  
  
##  <a name="comparewithgeometry"></a>  CD2DGeometry::CompareWithGeometry  
 この geometry と指定した geometry の交差部分をについて説明します。 比較は、フラット化の指定された許容範囲を使用して実行します。  
  
```  
D2D1_GEOMETRY_RELATION CompareWithGeometry(
    CD2DGeometry& inputGeometry,  
    const D2D1_MATRIX_3X2_F& inputGeometryTransform,  
    FLOAT flatteningTolerance = D2D1_DEFAULT_FLATTENING_TOLERANCE) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `inputGeometry`  
 テストするジオメトリ。  
  
 `inputGeometryTransform`  
 InputGeometry に適用する変換です。  
  
 `flatteningTolerance`  
 多角形近似のジオメトリの点の間の距離の上限。 小さい値より正確な結果の作成が、実行速度が低下します。  
  
### <a name="return-value"></a>戻り値  
 メソッドが成功した場合は TRUE を返します。 それ以外の場合、FALSE を返します。  
  
##  <a name="computearea"></a>  CD2DGeometry::ComputeArea  
 ジオメトリの領域が計算された後に、指定したマトリックスで変換を使用してフラット許容範囲を指定します。  
  
```  
BOOL ComputeArea(
    const D2D1_MATRIX_3X2_F& worldTransform,  
    FLOAT& area,  
    FLOAT flatteningTolerance = D2D1_DEFAULT_FLATTENING_TOLERANCE) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `worldTransform`  
 その領域を計算する前にこのジオメトリに適用する変換です。  
  
 `area`  
 このメソッドが戻るとき、変換されたフラット化されたバージョンのこの geometry の領域へのポインターが含まれています。 このパラメーターには、記憶域を割り当てる必要があります。  
  
 `flatteningTolerance`  
 多角形近似のジオメトリの点の間の距離の上限。 小さい値より正確な結果の作成が、実行速度が低下します。  
  
### <a name="return-value"></a>戻り値  
 メソッドが成功した場合は TRUE を返します。 それ以外の場合、FALSE を返します。  
  
##  <a name="computelength"></a>  CD2DGeometry::ComputeLength  
 各セグメントは 1 行にロールバックされたかのように、ジオメトリの長さを計算します。  
  
```  
BOOL ComputeLength(
    const D2D1_MATRIX_3X2_F& worldTransform,  
    FLOAT& length,  
    FLOAT flatteningTolerance = D2D1_DEFAULT_FLATTENING_TOLERANCE) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `worldTransform`  
 長さを計算する前に、ジオメトリに適用する変換です。  
  
 `length`  
 このメソッドが戻るときに、ジオメトリの長さへのポインターが含まれています。 閉じている場合は、長さには、暗黙的な終わりセグメントが含まれています。 このパラメーターには、記憶域を割り当てる必要があります。  
  
 `flatteningTolerance`  
 多角形近似のジオメトリの点の間の距離の上限。 小さい値より正確な結果の作成が、実行速度が低下します。  
  
### <a name="return-value"></a>戻り値  
 メソッドが成功した場合は TRUE を返します。 それ以外の場合、FALSE を返します。  
  
##  <a name="computepointatlength"></a>  CD2DGeometry::ComputePointAtLength  
 ジオメトリに沿って指定された距離にあるポイントおよびタンジェント ベクターが計算された後に、指定したマトリックスで変換を使用してフラット許容範囲を指定します。  
  
```  
BOOL ComputePointAtLength(
    FLOAT length,  
    const D2D1_MATRIX_3X2_F& worldTransform,  
    CD2DPointF& point,  
    CD2DPointF& unitTangentVector,  
    FLOAT flatteningTolerance = D2D1_DEFAULT_FLATTENING_TOLERANCE) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `length`  
 ポイントと検索に正接のジオメトリに沿った距離。 この距離が小さいし 0 の場合、このメソッドは、ジオメトリの最初のポイントを計算します。 この距離が、ジオメトリの長さより大きい場合は、このメソッドは、ジオメトリの最後の点を計算します。  
  
 `worldTransform`  
 指定した点と正接を計算する前に、ジオメトリに適用する変換です。  
  
 `point`  
 指定されたジオメトリに沿った距離にある場所です。 このポイントにはで、x および y と NaN が含まれています、ジオメトリが空の場合の値。  
  
 `unitTangentVector`  
 このメソッドが戻るときに、指定されたジオメトリに沿った距離にある正接ベクトルへのポインターが含まれています。 その x および y NaN がこのベクターに含まれています、ジオメトリが空の場合の値。 このパラメーターには、記憶域を割り当てる必要があります。  
  
 `flatteningTolerance`  
 多角形近似のジオメトリの点の間の距離の上限。 小さい値より正確な結果の作成が、実行速度が低下します。  
  
### <a name="return-value"></a>戻り値  
 メソッドが成功した場合は TRUE を返します。 それ以外の場合、FALSE を返します。  
  
##  <a name="destroy"></a>  CD2DGeometry::Destroy  
 CD2DGeometry オブジェクトを破棄します。  
  
```  
virtual void Destroy();
```  
  
##  <a name="detach"></a>  CD2DGeometry::Detach  
 オブジェクトからリソースのインターフェイスの関連付けを解除します。  
  
```  
ID2D1Geometry* Detach();
```  
  
### <a name="return-value"></a>戻り値  
 デタッチされたリソースのインターフェイスへのポインター。  
  
##  <a name="fillcontainspoint"></a>  CD2DGeometry::FillContainsPoint  
 ジオメトリで埋められた領域はフラット化の指定された許容範囲を指定した指定したポイントを含めるかどうかを示します。  
  
```  
BOOL FillContainsPoint(
    CD2DPointF point,  
    const D2D1_MATRIX_3X2_F& worldTransform,  
    BOOL* contains,  
    FLOAT flatteningTolerance = D2D1_DEFAULT_FLATTENING_TOLERANCE) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `point`  
 テストする点です。  
  
 `worldTransform`  
 コンテインメントのためのテストの前に、ジオメトリに適用する変換です。  
  
 `contains`  
 このメソッドが戻るとき、ジオメトリが塗りつぶし領域には、ポイントが含まれている場合は TRUE となるブール値が含まれています。それ以外の場合は FALSE です。 このパラメーターには、記憶域を割り当てる必要があります。  
  
 `flatteningTolerance`  
 これを使用した数値の精度幾何学模様の正確なパスとパスの交差部分を計算します。 許容範囲より小さいして塗りつぶしを見つからないポイントは内側考慮されます。 小さい値より正確な結果の作成が、実行速度が低下します。  
  
### <a name="return-value"></a>戻り値  
 メソッドが成功した場合は TRUE を返します。 それ以外の場合、FALSE を返します。  
  
##  <a name="get"></a>  CD2DGeometry::Get  
 返します ID2D1Geometry インターフェイス  
  
```  
ID2D1Geometry* Get();
```  
  
### <a name="return-value"></a>戻り値  
 ID2D1Geometry インターフェイスまたはオブジェクトがまだ初期化されていない場合は、NULL へのポインター。  
  
##  <a name="getbounds"></a>  CD2DGeometry::GetBounds  
  
```   
BOOL GetBounds(
const D2D1_MATRIX_3X2_F& worldTransform,  
CD2DRectF& bounds) const; 
```  
  
### <a name="parameters"></a>パラメーター  
 `worldTransform`  
 `bounds`  
  
### <a name="return-value"></a>戻り値  
  
##  <a name="getwidenedbounds"></a>  CD2DGeometry::GetWidenedBounds  
 指定した線の幅とスタイルで拡大変換し、指定した行列によって変換された後は、ジオメトリの境界を取得します。  
  
```  
BOOL GetWidenedBounds(
    FLOAT strokeWidth,  
    ID2D1StrokeStyle* strokeStyle,  
    const D2D1_MATRIX_3X2_F& worldTransform,  
    CD2DRectF& bounds,  
    FLOAT flatteningTolerance = D2D1_DEFAULT_FLATTENING_TOLERANCE) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `strokeWidth`  
 アウトラインを描画してジオメトリを拡大するために量。  
  
 `strokeStyle`  
 ジオメトリを拡大する線のスタイルです。  
  
 `worldTransform`  
 ジオメトリの変換後と、ジオメトリが描画された後に、ジオメトリに適用する変換です。  
  
 `bounds`  
 このメソッドが戻るとき、拡張された geometry の境界を格納します。 このパラメーターには、記憶域を割り当てる必要があります。  
  
 `flatteningTolerance`  
 多角形近似のジオメトリの点の間の距離の上限。 小さい値より正確な結果の作成が、実行速度が低下します。  
  
### <a name="return-value"></a>戻り値  
 メソッドが成功した場合は TRUE を返します。 それ以外の場合、FALSE を返します。  
  
##  <a name="isvalid"></a>  CD2DGeometry::IsValid  
 リソースの有効性のチェック  
  
```  
virtual BOOL IsValid() const;  
```  
  
### <a name="return-value"></a>戻り値  
 リソースが無効である場合は TRUE。それ以外の場合は FALSE。  
  
##  <a name="m_pgeometry"></a>  CD2DGeometry::m_pGeometry  
 ID2D1Geometry へのポインター。  
  
```  
ID2D1Geometry* m_pGeometry;  
```  
  
##  <a name="operator_id2d1geometry_star"></a>  CD2DGeometry::operator ID2D1Geometry *  
 返します ID2D1Geometry インターフェイス  
  
```  
operator ID2D1Geometry*();
```   
  
### <a name="return-value"></a>戻り値  
 ID2D1Geometry インターフェイスまたはオブジェクトがまだ初期化されていない場合は、NULL へのポインター。  
  
##  <a name="outline"></a>  CD2DGeometry::Outline  
 ジオメトリのアウトラインを計算し、ID2D1SimplifiedGeometrySink に結果を書き込みます。  
  
```  
BOOL Outline(
    const D2D1_MATRIX_3X2_F& worldTransform,  
    ID2D1SimplifiedGeometrySink* geometrySink,  
    FLOAT flatteningTolerance = D2D1_DEFAULT_FLATTENING_TOLERANCE) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `worldTransform`  
 輪郭のジオメトリに適用する変換です。  
  
 `geometrySink`  
 ジオメトリのアウトラインの変換先 ID2D1SimplifiedGeometrySink が追加されます。  
  
 `flatteningTolerance`  
 多角形近似のジオメトリの点の間の距離の上限。 小さい値より正確な結果の作成が、実行速度が低下します。  
  
### <a name="return-value"></a>戻り値  
 メソッドが成功した場合は TRUE を返します。 それ以外の場合、FALSE を返します。  
  
##  <a name="simplify"></a>  CD2DGeometry::Simplify  
 行と (必要に応じて) 3 次ベジエ曲線のみを含み、その結果を ID2D1SimplifiedGeometrySink に書き込みますジオメトリの簡素化されたバージョンを作成します。  
  
```  
BOOL Simplify(
    D2D1_GEOMETRY_SIMPLIFICATION_OPTION simplificationOption,  
    const D2D1_MATRIX_3X2_F& worldTransform,  
    ID2D1SimplifiedGeometrySink* geometrySink,  
    FLOAT flatteningTolerance = D2D1_DEFAULT_FLATTENING_TOLERANCE) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `simplificationOption`  
 簡略化されたジオメトリが曲線を含めるかどうかを指定する値。  
  
 `worldTransform`  
 簡略化されたジオメトリに適用する変換です。  
  
 `geometrySink`  
 簡略化されたジオメトリを追加する ID2D1SimplifiedGeometrySink です。  
  
 `flatteningTolerance`  
 多角形近似のジオメトリの点の間の距離の上限。 小さい値より正確な結果の作成が、実行速度が低下します。  
  
### <a name="return-value"></a>戻り値  
 メソッドが成功した場合は TRUE を返します。 それ以外の場合、FALSE を返します。  
  
##  <a name="strokecontainspoint"></a>  CD2DGeometry::StrokeContainsPoint  
 ジオメトリの線が指定したストロークの太さ、スタイル、および変換を指定した指定したポイントを含むかどうかを判断します。  
  
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
 `point`  
 含有をテストする点です。  
  
 `strokeWidth`  
 適用する線の太さ。  
  
 `strokeStyle`  
 適用する線のスタイルです。  
  
 `worldTransform`  
 線のジオメトリに適用する変換です。  
  
 `contains`  
 このメソッドが戻るときに、ジオメトリの線には、指定した点が含まれている場合に TRUE に設定するブール値が含まれていますそれ以外の場合は FALSE です。 このパラメーターには、記憶域を割り当てる必要があります。  
  
 `flatteningTolerance`  
 これを使用した数値の精度幾何学模様の正確なパスとパスの交差部分を計算します。 許容範囲より小さいして線を見つからないポイントは内側考慮されます。 小さい値より正確な結果の作成が、実行速度が低下します。  
  
### <a name="return-value"></a>戻り値  
 メソッドが成功した場合は TRUE を返します。 それ以外の場合、FALSE を返します。  
  
##  <a name="tessellate"></a>  CD2DGeometry::Tessellate  
 指定した行列を使用して変換された後に、geometry をカバーし、指定された許容範囲を使用してフラット化された時計回りの三角形のセットを作成します。  
  
```  
BOOL Tessellate(
    const D2D1_MATRIX_3X2_F& worldTransform,  
    ID2D1TessellationSink* tessellationSink,  
    FLOAT flatteningTolerance = D2D1_DEFAULT_FLATTENING_TOLERANCE) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `worldTransform`  
 この geometry 型、または NULL に適用する変換です。  
  
 `tessellationSink`  
 テセレーションされた追加 ID2D1TessellationSink です。  
  
 `flatteningTolerance`  
 多角形近似のジオメトリの点の間の距離の上限。 小さい値より正確な結果の作成が、実行速度が低下します。  
  
### <a name="return-value"></a>戻り値  
 メソッドが成功した場合は TRUE を返します。 それ以外の場合、FALSE を返します。  
  
##  <a name="widen"></a>  CD2DGeometry::Widen  
 指定した線によって、ジオメトリを拡大し、結果、ID2D1SimplifiedGeometrySink にされた後に、指定したマトリックスで変換を使用してフラット許容範囲を指定します。  
  
```  
BOOL Widen(
    FLOAT strokeWidth,  
    ID2D1StrokeStyle* strokeStyle,  
    const D2D1_MATRIX_3X2_F& worldTransform,  
    ID2D1SimplifiedGeometrySink* geometrySink,  
    FLOAT flatteningTolerance = D2D1_DEFAULT_FLATTENING_TOLERANCE) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `strokeWidth`  
 ジオメトリを拡大するために量。  
  
 `strokeStyle`  
 Geometry 型、または NULL に適用する線のスタイルです。  
  
 `worldTransform`  
 これを拡大した後、ジオメトリに適用する変換です。  
  
 `geometrySink`  
 拡張されたジオメトリが追加されます ID2D1SimplifiedGeometrySink です。  
  
 `flatteningTolerance`  
 多角形近似のジオメトリの点の間の距離の上限。 小さい値より正確な結果の作成が、実行速度が低下します。  
  
### <a name="return-value"></a>戻り値  
 メソッドが成功した場合は TRUE を返します。 それ以外の場合、FALSE を返します。  
  
## <a name="see-also"></a>関連項目  
 [クラス](../../mfc/reference/mfc-classes.md)

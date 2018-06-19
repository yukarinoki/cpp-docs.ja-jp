---
title: CD2DGeometrySink クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CD2DGeometrySink
- AFXRENDERTARGET/CD2DGeometrySink
- AFXRENDERTARGET/CD2DGeometrySink::CD2DGeometrySink
- AFXRENDERTARGET/CD2DGeometrySink::AddArc
- AFXRENDERTARGET/CD2DGeometrySink::AddBezier
- AFXRENDERTARGET/CD2DGeometrySink::AddBeziers
- AFXRENDERTARGET/CD2DGeometrySink::AddLine
- AFXRENDERTARGET/CD2DGeometrySink::AddLines
- AFXRENDERTARGET/CD2DGeometrySink::AddQuadraticBezier
- AFXRENDERTARGET/CD2DGeometrySink::AddQuadraticBeziers
- AFXRENDERTARGET/CD2DGeometrySink::BeginFigure
- AFXRENDERTARGET/CD2DGeometrySink::Close
- AFXRENDERTARGET/CD2DGeometrySink::EndFigure
- AFXRENDERTARGET/CD2DGeometrySink::Get
- AFXRENDERTARGET/CD2DGeometrySink::IsValid
- AFXRENDERTARGET/CD2DGeometrySink::SetFillMode
- AFXRENDERTARGET/CD2DGeometrySink::SetSegmentFlags
- AFXRENDERTARGET/CD2DGeometrySink::m_pSink
dev_langs:
- C++
helpviewer_keywords:
- CD2DGeometrySink [MFC], CD2DGeometrySink
- CD2DGeometrySink [MFC], AddArc
- CD2DGeometrySink [MFC], AddBezier
- CD2DGeometrySink [MFC], AddBeziers
- CD2DGeometrySink [MFC], AddLine
- CD2DGeometrySink [MFC], AddLines
- CD2DGeometrySink [MFC], AddQuadraticBezier
- CD2DGeometrySink [MFC], AddQuadraticBeziers
- CD2DGeometrySink [MFC], BeginFigure
- CD2DGeometrySink [MFC], Close
- CD2DGeometrySink [MFC], EndFigure
- CD2DGeometrySink [MFC], Get
- CD2DGeometrySink [MFC], IsValid
- CD2DGeometrySink [MFC], SetFillMode
- CD2DGeometrySink [MFC], SetSegmentFlags
- CD2DGeometrySink [MFC], m_pSink
ms.assetid: e5e07f41-0343-4ab1-9d6b-8c62ed33c04a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b67aa3345f8739714cb6758f8363c3d2054dd4e3
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33355286"
---
# <a name="cd2dgeometrysink-class"></a>CD2DGeometrySink クラス
ID2D1GeometrySink のラッパーです。  
  
## <a name="syntax"></a>構文  
  
```  
class CD2DGeometrySink;  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CD2DGeometrySink::CD2DGeometrySink](#cd2dgeometrysink)|CD2DPathGeometry オブジェクトから CD2DGeometrySink オブジェクトを構築します。|  
|[CD2DGeometrySink:: ~ CD2DGeometrySink](#_dtorcd2dgeometrysink)|デストラクターです。 D2D geometry シンク オブジェクトが破棄されるときに呼び出されます。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CD2DGeometrySink::AddArc](#addarc)|1 つの円弧をパス ジオメトリに追加します。|  
|[CD2DGeometrySink::AddBezier](#addbezier)|現在の点と指定された終点の間に 3 次ベジエ曲線を作成します。|  
|[CD2DGeometrySink::AddBeziers](#addbeziers)|3 次ベジエ曲線のシーケンスを作成し、geometry シンクにそれらを追加します。|  
|[CD2DGeometrySink::AddLine](#addline)|現在のポイントと指定したエンドポイントの間の直線セグメントを作成し、geometry シンクに追加します。|  
|[CD2DGeometrySink::AddLines](#addlines)|指定されたポイントを使用して線のシーケンスを作成し、geometry シンクにそれらを追加します。|  
|[CD2DGeometrySink::AddQuadraticBezier](#addquadraticbezier)|現在の点と指定された終点の間に 2 次ベジエ曲線を作成します。|  
|[CD2DGeometrySink::AddQuadraticBeziers](#addquadraticbeziers)|配列 1 回の呼び出しで 2 次ベジエ セグメントのシーケンスに追加します。|  
|[CD2DGeometrySink::BeginFigure](#beginfigure)|指定した位置に新しい図形を開始します。|  
|[CD2DGeometrySink::Close](#close)|Geometry シンクを閉じます|  
|[CD2DGeometrySink::EndFigure](#endfigure)|現在の図を終了します。必要に応じて、ウィンドウが閉じます。|  
|[CD2DGeometrySink::Get](#get)|返します ID2D1GeometrySink インターフェイス|  
|[CD2DGeometrySink::IsValid](#isvalid)|Geometry シンクの有効性をチェックします。|  
|[CD2DGeometrySink::SetFillMode](#setfillmode)|この geometry シンクによって記述された geometry の内部ポイントがあると外であるポイントを決定するために使用するメソッドを指定します。|  
|[CD2DGeometrySink::SetSegmentFlags](#setsegmentflags)|Geometry シンクに追加された新しいセグメントに適用する線と結合オプションを指定します。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[CD2DGeometrySink::operator ID2D1GeometrySink *](#operator_id2d1geometrysink_star)|返します ID2D1GeometrySink インターフェイス|  
  
### <a name="protected-data-members"></a>プロテクト データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CD2DGeometrySink::m_pSink](#m_psink)|ID2D1GeometrySink へのポインター。|  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `CD2DGeometrySink`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxrendertarget.h  
  
##  <a name="_dtorcd2dgeometrysink"></a>  CD2DGeometrySink:: ~ CD2DGeometrySink  
 デストラクターです。 D2D geometry シンク オブジェクトが破棄されるときに呼び出されます。  
  
```  
virtual ~CD2DGeometrySink();
```  
  
##  <a name="addarc"></a>  CD2DGeometrySink::AddArc  
 1 つの円弧をパス ジオメトリに追加します。  
  
```  
void AddArc(const D2D1_ARC_SEGMENT& arc);
```  
  
### <a name="parameters"></a>パラメーター  
 `arc`  
 円弧のセグメントの図に追加するには  
  
##  <a name="addbezier"></a>  CD2DGeometrySink::AddBezier  
 現在の点と指定された終点の間に 3 次ベジエ曲線を作成します。  
  
```  
void AddBezier(const D2D1_BEZIER_SEGMENT& bezier);
```  
  
### <a name="parameters"></a>パラメーター  
 `bezier`  
 構造体の制御点と追加をベジエ曲線の終了点について説明します。  
  
##  <a name="addbeziers"></a>  CD2DGeometrySink::AddBeziers  
 3 次ベジエ曲線のシーケンスを作成し、geometry シンクにそれらを追加します。  
  
```  
void AddBeziers(
    const CArray<D2D1_BEZIER_SEGMENT,  
    D2D1_BEZIER_SEGMENT>& beziers);
```  
  
### <a name="parameters"></a>パラメーター  
 `beziers`  
 作成するベジエ曲線を記述するベジエ セグメントの配列。 配列内の最初のベジエ線分の終点のジオメトリ シンクの現在のポイント (描画の最後のセグメントまたは BeginFigure で指定された場所の終了ポイント) から、曲線が描画されます。 配列に追加のベジエ セグメントが含まれている場合、後続の各ベジエ セグメントは開始ポイントとして前のベジエ線分の終点を使用します。  
  
##  <a name="addline"></a>  CD2DGeometrySink::AddLine  
 現在のポイントと指定したエンドポイントの間の直線セグメントを作成し、geometry シンクに追加します。  
  
```  
void AddLine(CD2DPointF point);
```  
  
### <a name="parameters"></a>パラメーター  
 `point`  
 描画する線の終点。  
  
##  <a name="addlines"></a>  CD2DGeometrySink::AddLines  
 指定されたポイントを使用して線のシーケンスを作成し、geometry シンクにそれらを追加します。  
  
```  
void AddLines(
    const CArray<CD2DPointF,  
    CD2DPointF>& points);
```  
  
### <a name="parameters"></a>パラメーター  
 `points`  
 描画する行を 1 つまたは複数の点の配列。 配列の最初のポイントのジオメトリ シンクの現在のポイント (描画の最後のセグメントまたは BeginFigure で指定された場所の終了ポイント) から線が描画されます。 配列に追加の点が含まれている場合、3 番目のポイントなどの 2 番目の点から、配列の 2 番目の点に行は最初の点から描画されます。 描画する線の終点のシーケンスの配列。  
  
##  <a name="addquadraticbezier"></a>  CD2DGeometrySink::AddQuadraticBezier  
 現在の点と指定された終点の間に 2 次ベジエ曲線を作成します。  
  
```  
void AddQuadraticBezier(const D2D1_QUADRATIC_BEZIER_SEGMENT& bezier);
```  
  
### <a name="parameters"></a>パラメーター  
 `bezier`  
 構造体の制御点と追加の 2 次ベジエ曲線の終了点について説明します。  
  
##  <a name="addquadraticbeziers"></a>  CD2DGeometrySink::AddQuadraticBeziers  
 配列 1 回の呼び出しで 2 次ベジエ セグメントのシーケンスに追加します。  
  
```  
void AddQuadraticBeziers(
    const CArray<D2D1_QUADRATIC_BEZIER_SEGMENT,  
    D2D1_QUADRATIC_BEZIER_SEGMENT>& beziers);
```  
  
### <a name="parameters"></a>パラメーター  
 `beziers`  
 一連の 2 次ベジエ セグメントの配列。  
  
##  <a name="beginfigure"></a>  CD2DGeometrySink::BeginFigure  
 指定した位置に新しい図形を開始します。  
  
```  
void BeginFigure(
    CD2DPointF startPoint,  
    D2D1_FIGURE_BEGIN figureBegin);
```  
  
### <a name="parameters"></a>パラメーター  
 `startPoint`  
 新しい図を開始する位置。  
  
 `figureBegin`  
 かどうか新しい図は、中空または塗りつぶされたにする必要があります。  
  
##  <a name="cd2dgeometrysink"></a>  CD2DGeometrySink::CD2DGeometrySink  
 CD2DPathGeometry オブジェクトから CD2DGeometrySink オブジェクトを構築します。  
  
```  
CD2DGeometrySink(CD2DPathGeometry& pathGeometry);
```  
  
### <a name="parameters"></a>パラメーター  
 `pathGeometry`  
 既存の CD2DPathGeometry オブジェクト。  
  
##  <a name="close"></a>  CD2DGeometrySink::Close  
 Geometry シンクを閉じます  
  
```  
BOOL Close();
```  
  
### <a name="return-value"></a>戻り値  
 成功した場合は 0 以外。それ以外の場合は FALSE。  
  
##  <a name="endfigure"></a>  CD2DGeometrySink::EndFigure  
 現在の図を終了します。必要に応じて、ウィンドウが閉じます。  
  
```  
void EndFigure(D2D1_FIGURE_END figureEnd);
```  
  
### <a name="parameters"></a>パラメーター  
 `figureEnd`  
 現在の図が閉じられたかどうかを示す値。 図が閉じている場合、現在のポイントと BeginFigure で指定された開始点の間で線を描画します。  
  
##  <a name="get"></a>  CD2DGeometrySink::Get  
 返します ID2D1GeometrySink インターフェイス  
  
```  
ID2D1GeometrySink* Get();
```  
  
### <a name="return-value"></a>戻り値  
 ID2D1GeometrySink インターフェイスまたはオブジェクトがまだ初期化されていない場合は、NULL へのポインター。  
  
##  <a name="isvalid"></a>  CD2DGeometrySink::IsValid  
 Geometry シンクの有効性をチェックします。  
  
```  
BOOL IsValid() const;  
```  
  
### <a name="return-value"></a>戻り値  
 Geometry シンクが有効である場合は TRUE。それ以外の場合は FALSE。  
  
##  <a name="m_psink"></a>  CD2DGeometrySink::m_pSink  
 ID2D1GeometrySink へのポインター。  
  
```  
ID2D1GeometrySink* m_pSink;  
```  
  
##  <a name="operator_id2d1geometrysink_star"></a>  CD2DGeometrySink::operator ID2D1GeometrySink *  
 返します ID2D1GeometrySink インターフェイス  
  
```  
operator ID2D1GeometrySink*();
```   
  
### <a name="return-value"></a>戻り値  
 ID2D1GeometrySink インターフェイスまたはオブジェクトがまだ初期化されていない場合は、NULL へのポインター。  
  
##  <a name="setfillmode"></a>  CD2DGeometrySink::SetFillMode  
 この geometry シンクによって記述された geometry の内部ポイントがあると外であるポイントを決定するために使用するメソッドを指定します。  
  
```  
void SetFillMode(D2D1_FILL_MODE fillMode);
```  
  
### <a name="parameters"></a>パラメーター  
 `fillMode`  
 特定の時点のジオメトリの一部であるかどうかを判断するために使用するメソッド。  
  
##  <a name="setsegmentflags"></a>  CD2DGeometrySink::SetSegmentFlags  
 Geometry シンクに追加された新しいセグメントに適用する線と結合オプションを指定します。  
  
```  
void SetSegmentFlags(D2D1_PATH_SEGMENT vertexFlags);
```  
  
### <a name="parameters"></a>パラメーター  
 `vertexFlags`  
 Geometry シンクに追加された新しいセグメントに適用する線と結合のオプションです。  
  
## <a name="see-also"></a>関連項目  
 [クラス](../../mfc/reference/mfc-classes.md)

---
description: '詳細情報: CD2DGeometrySink クラス'
title: CD2DGeometrySink クラス
ms.date: 11/04/2016
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
ms.openlocfilehash: e7916cdb39272e924a9d6ef6c0a8322d8ce6fb1f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97193423"
---
# <a name="cd2dgeometrysink-class"></a>CD2DGeometrySink クラス

ID2D1GeometrySink のラッパー。

## <a name="syntax"></a>構文

```
class CD2DGeometrySink;
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CD2DGeometrySink:: CD2DGeometrySink](#cd2dgeometrysink)|CD2DPathGeometry オブジェクトから CD2DGeometrySink オブジェクトを構築します。|
|[CD2DGeometrySink:: ~ CD2DGeometrySink](#_dtorcd2dgeometrysink)|デストラクターです。 D2D geometry シンクオブジェクトが破棄されるときに呼び出されます。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CD2DGeometrySink:: AddArc](#addarc)|パスジオメトリに1つの円弧を追加します|
|[CD2DGeometrySink:: AddBezier](#addbezier)|現在の点と指定された終点の間に 3 次ベジエ曲線を作成します。|
|[CD2DGeometrySink:: AddBeziers](#addbeziers)|3次ベジエ曲線のシーケンスを作成し、ジオメトリシンクに追加します。|
|[CD2DGeometrySink:: AddLine](#addline)|現在の点と指定された終点の間に線分を作成し、ジオメトリシンクに追加します。|
|[CD2DGeometrySink:: AddLines](#addlines)|指定した点を使用して直線のシーケンスを作成し、ジオメトリシンクに追加します。|
|[CD2DGeometrySink:: AddQuadraticBezier](#addquadraticbezier)|現在の点と指定された終点の間に 2 次ベジエ曲線を作成します。|
|[CD2DGeometrySink:: AddQuadraticBeziers](#addquadraticbeziers)|2次ベジエセグメントのシーケンスを1回の呼び出しで配列として追加します。|
|[CD2DGeometrySink:: BeginFigure](#beginfigure)|指定したポイントで新しい図形を開始します。|
|[CD2DGeometrySink:: Close](#close)|ジオメトリシンクを閉じます。|
|[CD2DGeometrySink:: EndFigure](#endfigure)|現在の図を終了します。必要に応じて、閉じます。|
|[CD2DGeometrySink:: Get](#get)|ID2D1GeometrySink インターフェイスを返します。|
|[CD2DGeometrySink:: IsValid](#isvalid)|ジオメトリシンクの有効性を確認します|
|[CD2DGeometrySink:: SetFillMode](#setfillmode)|このジオメトリシンクによって表されるジオメトリの内側にある点と、外側の点を決定するために使用するメソッドを指定します。|
|[CD2DGeometrySink:: SetSegmentFlags](#setsegmentflags)|ジオメトリシンクに追加される新しいセグメントに適用されるストロークおよび結合オプションを指定します。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[CD2DGeometrySink:: operator ID2D1GeometrySink *](#operator_id2d1geometrysink_star)|ID2D1GeometrySink インターフェイスを返します。|

### <a name="protected-data-members"></a>プロテクト データ メンバー

|名前|説明|
|----------|-----------------|
|[CD2DGeometrySink:: m_pSink](#m_psink)|ID2D1GeometrySink へのポインター。|

## <a name="inheritance-hierarchy"></a>継承階層

`CD2DGeometrySink`

## <a name="requirements"></a>要件

**ヘッダー:** afxrendertarget

## <a name="cd2dgeometrysinkcd2dgeometrysink"></a><a name="_dtorcd2dgeometrysink"></a> CD2DGeometrySink:: ~ CD2DGeometrySink

デストラクターです。 D2D geometry シンクオブジェクトが破棄されるときに呼び出されます。

```
virtual ~CD2DGeometrySink();
```

## <a name="cd2dgeometrysinkaddarc"></a><a name="addarc"></a> CD2DGeometrySink:: AddArc

パスジオメトリに1つの円弧を追加します

```cpp
void AddArc(const D2D1_ARC_SEGMENT& arc);
```

### <a name="parameters"></a>パラメーター

*曲げる*<br/>
図形に追加する円弧セグメント

## <a name="cd2dgeometrysinkaddbezier"></a><a name="addbezier"></a> CD2DGeometrySink:: AddBezier

現在の点と指定された終点の間に 3 次ベジエ曲線を作成します。

```cpp
void AddBezier(const D2D1_BEZIER_SEGMENT& bezier);
```

### <a name="parameters"></a>パラメーター

*ベジェ*<br/>
追加するベジエ曲線の制御点と終点を記述する構造体。

## <a name="cd2dgeometrysinkaddbeziers"></a><a name="addbeziers"></a> CD2DGeometrySink:: AddBeziers

3次ベジエ曲線のシーケンスを作成し、ジオメトリシンクに追加します。

```cpp
void AddBeziers(
    const CArray<D2D1_BEZIER_SEGMENT,
    D2D1_BEZIER_SEGMENT>& beziers);
```

### <a name="parameters"></a>パラメーター

*beziers*<br/>
作成するベジエ曲線を記述するベジエセグメントの配列。 曲線は、ジオメトリシンクの現在のポイント (描画された最後のセグメントの終点または BeginFigure によって指定された位置) から、配列内の最初のベジエセグメントの終点まで描画されます。 配列に追加のベジエセグメントが含まれている場合、後続の各ベジエセグメントは、その開始点として前のベジエセグメントの終点を使用します。

## <a name="cd2dgeometrysinkaddline"></a><a name="addline"></a> CD2DGeometrySink:: AddLine

現在の点と指定された終点の間に線分を作成し、ジオメトリシンクに追加します。

```cpp
void AddLine(CD2DPointF point);
```

### <a name="parameters"></a>パラメーター

*視点*<br/>
描画する線の終点。

## <a name="cd2dgeometrysinkaddlines"></a><a name="addlines"></a> CD2DGeometrySink:: AddLines

指定した点を使用して直線のシーケンスを作成し、ジオメトリシンクに追加します。

```cpp
void AddLines(
    const CArray<CD2DPointF,
    CD2DPointF>& points);
```

### <a name="parameters"></a>パラメーター

*先*<br/>
描画する行を記述する1つ以上の点の配列。 ジオメトリシンクの現在のポイント (描画された最後のセグメントの終点または BeginFigure によって指定された位置) から、配列の最初の点までの線が描画されます。 配列に追加の点が含まれている場合は、最初の点から配列の2番目の点まで、2番目の点から3番目の点までの線が描画されます。 描画する直線の終点のシーケンスの配列。

## <a name="cd2dgeometrysinkaddquadraticbezier"></a><a name="addquadraticbezier"></a> CD2DGeometrySink:: AddQuadraticBezier

現在の点と指定された終点の間に 2 次ベジエ曲線を作成します。

```cpp
void AddQuadraticBezier(const D2D1_QUADRATIC_BEZIER_SEGMENT& bezier);
```

### <a name="parameters"></a>パラメーター

*ベジェ*<br/>
追加する2次ベジエ曲線の制御点と終点を記述する構造体。

## <a name="cd2dgeometrysinkaddquadraticbeziers"></a><a name="addquadraticbeziers"></a> CD2DGeometrySink:: AddQuadraticBeziers

2次ベジエセグメントのシーケンスを1回の呼び出しで配列として追加します。

```cpp
void AddQuadraticBeziers(
    const CArray<D2D1_QUADRATIC_BEZIER_SEGMENT,
    D2D1_QUADRATIC_BEZIER_SEGMENT>& beziers);
```

### <a name="parameters"></a>パラメーター

*beziers*<br/>
2次ベジエセグメントのシーケンスの配列。

## <a name="cd2dgeometrysinkbeginfigure"></a><a name="beginfigure"></a> CD2DGeometrySink:: BeginFigure

指定したポイントで新しい図形を開始します。

```cpp
void BeginFigure(
    CD2DPointF startPoint,
    D2D1_FIGURE_BEGIN figureBegin);
```

### <a name="parameters"></a>パラメーター

*startPoint*<br/>
新しい図形を開始する位置。

*figureBegin*<br/>
新しい図形を白抜きにするか、塗りつぶすかを指定します。

## <a name="cd2dgeometrysinkcd2dgeometrysink"></a><a name="cd2dgeometrysink"></a> CD2DGeometrySink:: CD2DGeometrySink

CD2DPathGeometry オブジェクトから CD2DGeometrySink オブジェクトを構築します。

```
CD2DGeometrySink(CD2DPathGeometry& pathGeometry);
```

### <a name="parameters"></a>パラメーター

*pathGeometry*<br/>
既存の CD2DPathGeometry オブジェクト。

## <a name="cd2dgeometrysinkclose"></a><a name="close"></a> CD2DGeometrySink:: Close

ジオメトリシンクを閉じます。

```
BOOL Close();
```

### <a name="return-value"></a>戻り値

成功した場合は0以外の。それ以外の場合は FALSE。

## <a name="cd2dgeometrysinkendfigure"></a><a name="endfigure"></a> CD2DGeometrySink:: EndFigure

現在の図を終了します。必要に応じて、閉じます。

```cpp
void EndFigure(D2D1_FIGURE_END figureEnd);
```

### <a name="parameters"></a>パラメーター

*figureEnd*<br/>
現在の図形が閉じているかどうかを示す値。 図が閉じている場合は、現在のポイントと BeginFigure で指定された開始点の間に線が描画されます。

## <a name="cd2dgeometrysinkget"></a><a name="get"></a> CD2DGeometrySink:: Get

ID2D1GeometrySink インターフェイスを返します。

```
ID2D1GeometrySink* Get();
```

### <a name="return-value"></a>戻り値

ID2D1GeometrySink インターフェイスへのポインター。オブジェクトがまだ初期化されていない場合は NULL。

## <a name="cd2dgeometrysinkisvalid"></a><a name="isvalid"></a> CD2DGeometrySink:: IsValid

ジオメトリシンクの有効性を確認します

```
BOOL IsValid() const;
```

### <a name="return-value"></a>戻り値

ジオメトリシンクが有効な場合は TRUE。それ以外の場合は FALSE。

## <a name="cd2dgeometrysinkm_psink"></a><a name="m_psink"></a> CD2DGeometrySink:: m_pSink

ID2D1GeometrySink へのポインター。

```
ID2D1GeometrySink* m_pSink;
```

## <a name="cd2dgeometrysinkoperator-id2d1geometrysink"></a><a name="operator_id2d1geometrysink_star"></a> CD2DGeometrySink:: operator ID2D1GeometrySink *

ID2D1GeometrySink インターフェイスを返します。

```
operator ID2D1GeometrySink*();
```

### <a name="return-value"></a>戻り値

ID2D1GeometrySink インターフェイスへのポインター。オブジェクトがまだ初期化されていない場合は NULL。

## <a name="cd2dgeometrysinksetfillmode"></a><a name="setfillmode"></a> CD2DGeometrySink:: SetFillMode

このジオメトリシンクによって表されるジオメトリの内側にある点と、外側の点を決定するために使用するメソッドを指定します。

```cpp
void SetFillMode(D2D1_FILL_MODE fillMode);
```

### <a name="parameters"></a>パラメーター

*fillMode*<br/>
指定された点がジオメトリの一部であるかどうかを判断するために使用されるメソッド。

## <a name="cd2dgeometrysinksetsegmentflags"></a><a name="setsegmentflags"></a> CD2DGeometrySink:: SetSegmentFlags

ジオメトリシンクに追加される新しいセグメントに適用されるストロークおよび結合オプションを指定します。

```cpp
void SetSegmentFlags(D2D1_PATH_SEGMENT vertexFlags);
```

### <a name="parameters"></a>パラメーター

*vertexFlags*<br/>
ジオメトリシンクに追加される新しいセグメントに適用される Stroke オプションと join オプション。

## <a name="see-also"></a>関連項目

[クラス](../../mfc/reference/mfc-classes.md)

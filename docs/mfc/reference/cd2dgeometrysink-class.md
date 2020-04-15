---
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
ms.openlocfilehash: cb51c7b11f75debece61105bf20a201b6eab80a9
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81369234"
---
# <a name="cd2dgeometrysink-class"></a>CD2DGeometrySink クラス

ID2D1Geometry シンクのラッパー。

## <a name="syntax"></a>構文

```
class CD2DGeometrySink;
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[シンク::CD2Dジオメトリシンク](#cd2dgeometrysink)|オブジェクトを CD2DGeometry オブジェクトから構築します。|
|[シンク:~CD2Dジオメトリシンク](#_dtorcd2dgeometrysink)|デストラクターです。 D2D ジオメトリ シンク オブジェクトが破棄されるときに呼び出されます。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[シンク::追加アーク](#addarc)|パス ジオメトリに 1 つの円弧を追加します。|
|[シンク::アドベジエ](#addbezier)|現在の点と指定された終点の間に 3 次ベジエ曲線を作成します。|
|[シンク::追加ベジエ](#addbeziers)|3 次ベジエ曲線のシーケンスを作成し、ジオメトリ シンクに追加します。|
|[シンク::アドライン](#addline)|現在の点と指定した終点の間に線分セグメントを作成し、ジオメトリ シンクに追加します。|
|[シンク::アドライン](#addlines)|指定した点を使用してライン シーケンスを作成し、ジオメトリ シンクに追加します。|
|[CD2Dジオメトリシンク::アドクワドラティックベジエ](#addquadraticbezier)|現在の点と指定された終点の間に 2 次ベジエ曲線を作成します。|
|[CD2Dジオメトリシンク::AddQuadraticBeziers](#addquadraticbeziers)|2 次ベジェ セグメントのシーケンスを配列として 1 回の呼び出しで追加します。|
|[シンク::ビギンデ図](#beginfigure)|指定したポイントで新しい図形を開始します。|
|[シンク::閉じる](#close)|ジオメトリ シンクを閉じます。|
|[シンク::エンドフィギュア](#endfigure)|現在の図形を終了します。必要に応じて、閉じます。|
|[シンク::取得します。](#get)|インターフェイスを返します。|
|[シンク::IsValid](#isvalid)|ジオメトリ シンクの有効性をチェックします。|
|[シンク::セットフィルモード](#setfillmode)|このジオメトリ シンクで記述されているジオメトリ内にあるポイントと、どのポイントが外側にあるかを決定する方法を指定します。|
|[シンク::セグメントフラグを設定します。](#setsegmentflags)|ジオメトリ シンクに追加された新しいセグメントに適用するストロークおよび結合オプションを指定します。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[シンク::演算子 ID2D1ジオメトリシンク*](#operator_id2d1geometrysink_star)|インターフェイスを返します。|

### <a name="protected-data-members"></a>プロテクト データ メンバー

|名前|説明|
|----------|-----------------|
|[シンク:m_pSink](#m_psink)|ID2D1GeometrySink へのポインター。|

## <a name="inheritance-hierarchy"></a>継承階層

`CD2DGeometrySink`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxrendertarget.h

## <a name="cd2dgeometrysinkcd2dgeometrysink"></a><a name="_dtorcd2dgeometrysink"></a>シンク:~CD2Dジオメトリシンク

デストラクターです。 D2D ジオメトリ シンク オブジェクトが破棄されるときに呼び出されます。

```
virtual ~CD2DGeometrySink();
```

## <a name="cd2dgeometrysinkaddarc"></a><a name="addarc"></a>シンク::追加アーク

パス ジオメトリに 1 つの円弧を追加します。

```
void AddArc(const D2D1_ARC_SEGMENT& arc);
```

### <a name="parameters"></a>パラメーター

*アーク*<br/>
図に追加する円弧セグメント

## <a name="cd2dgeometrysinkaddbezier"></a><a name="addbezier"></a>シンク::アドベジエ

現在の点と指定された終点の間に 3 次ベジエ曲線を作成します。

```
void AddBezier(const D2D1_BEZIER_SEGMENT& bezier);
```

### <a name="parameters"></a>パラメーター

*ベジエ*<br/>
追加するベジェ曲線の制御点と終点を記述する構造体。

## <a name="cd2dgeometrysinkaddbeziers"></a><a name="addbeziers"></a>シンク::追加ベジエ

3 次ベジエ曲線のシーケンスを作成し、ジオメトリ シンクに追加します。

```
void AddBeziers(
    const CArray<D2D1_BEZIER_SEGMENT,
    D2D1_BEZIER_SEGMENT>& beziers);
```

### <a name="parameters"></a>パラメーター

*ベジエ*<br/>
作成するベジェ曲線を記述するベジェセグメントの配列。 曲線は、ジオメトリ シンクの現在のポイント (最後に描画されたセグメントの終点、または BeginFigure で指定した位置) から、配列内の最初のベジェ セグメントの終点まで描画されます。 配列に追加のベジェセグメントが含まれている場合、後続のベジェセグメントは、先行するベジェセグメントの終点を始点として使用します。

## <a name="cd2dgeometrysinkaddline"></a><a name="addline"></a>シンク::アドライン

現在の点と指定した終点の間に線分セグメントを作成し、ジオメトリ シンクに追加します。

```
void AddLine(CD2DPointF point);
```

### <a name="parameters"></a>パラメーター

*ポイント*<br/>
描画する線の終点。

## <a name="cd2dgeometrysinkaddlines"></a><a name="addlines"></a>シンク::アドライン

指定した点を使用してライン シーケンスを作成し、ジオメトリ シンクに追加します。

```
void AddLines(
    const CArray<CD2DPointF,
    CD2DPointF>& points);
```

### <a name="parameters"></a>パラメーター

*ポイント*<br/>
描画する線を記述する 1 つ以上のポイントの配列。 ジオメトリ シンクの現在の点 (最後に描画されたセグメントの終点、または BeginFigure で指定した位置) から、配列の最初の点まで線が描画されます。 配列に追加の点が含まれている場合、1 つ目の点から配列内の 2 番目の点、2 番目の点から 3 番目の点まで、その他の点が描画されます。 描画する線の終点のシーケンスの配列。

## <a name="cd2dgeometrysinkaddquadraticbezier"></a><a name="addquadraticbezier"></a>CD2Dジオメトリシンク::アドクワドラティックベジエ

現在の点と指定された終点の間に 2 次ベジエ曲線を作成します。

```
void AddQuadraticBezier(const D2D1_QUADRATIC_BEZIER_SEGMENT& bezier);
```

### <a name="parameters"></a>パラメーター

*ベジエ*<br/>
追加する 2 次ベジェ曲線の制御点と終点を記述する構造体。

## <a name="cd2dgeometrysinkaddquadraticbeziers"></a><a name="addquadraticbeziers"></a>CD2Dジオメトリシンク::AddQuadraticBeziers

2 次ベジェ セグメントのシーケンスを配列として 1 回の呼び出しで追加します。

```
void AddQuadraticBeziers(
    const CArray<D2D1_QUADRATIC_BEZIER_SEGMENT,
    D2D1_QUADRATIC_BEZIER_SEGMENT>& beziers);
```

### <a name="parameters"></a>パラメーター

*ベジエ*<br/>
2 次ベジエセグメントのシーケンスの配列。

## <a name="cd2dgeometrysinkbeginfigure"></a><a name="beginfigure"></a>シンク::ビギンデ図

指定したポイントで新しい図形を開始します。

```
void BeginFigure(
    CD2DPointF startPoint,
    D2D1_FIGURE_BEGIN figureBegin);
```

### <a name="parameters"></a>パラメーター

*startPoint*<br/>
新しい図形を開始するポイント。

*図始める*<br/>
新しい図形を空にするか塗りつぶすか。

## <a name="cd2dgeometrysinkcd2dgeometrysink"></a><a name="cd2dgeometrysink"></a>シンク::CD2Dジオメトリシンク

オブジェクトを CD2DGeometry オブジェクトから構築します。

```
CD2DGeometrySink(CD2DPathGeometry& pathGeometry);
```

### <a name="parameters"></a>パラメーター

*Pathgeometry*<br/>
既存の CD2D パスジオメトリ オブジェクト。

## <a name="cd2dgeometrysinkclose"></a><a name="close"></a>シンク::閉じる

ジオメトリ シンクを閉じます。

```
BOOL Close();
```

### <a name="return-value"></a>戻り値

成功した場合は 0 以外。それ以外の場合は FALSE。

## <a name="cd2dgeometrysinkendfigure"></a><a name="endfigure"></a>シンク::エンドフィギュア

現在の図形を終了します。必要に応じて、閉じます。

```
void EndFigure(D2D1_FIGURE_END figureEnd);
```

### <a name="parameters"></a>パラメーター

*フィギュアエンド*<br/>
現在の図形が閉じているかどうかを示す値。 図形が閉じている場合、現在の点と BeginFigure で指定された始点の間に線が描画されます。

## <a name="cd2dgeometrysinkget"></a><a name="get"></a>シンク::取得します。

インターフェイスを返します。

```
ID2D1GeometrySink* Get();
```

### <a name="return-value"></a>戻り値

ID2D1GeometrySink インターフェイスへのポインターまたは NULL オブジェクトがまだ初期化されていない場合。

## <a name="cd2dgeometrysinkisvalid"></a><a name="isvalid"></a>シンク::IsValid

ジオメトリ シンクの有効性をチェックします。

```
BOOL IsValid() const;
```

### <a name="return-value"></a>戻り値

ジオメトリ シンクが有効な場合は TRUE。それ以外の場合は FALSE。

## <a name="cd2dgeometrysinkm_psink"></a><a name="m_psink"></a>シンク:m_pSink

ID2D1GeometrySink へのポインター。

```
ID2D1GeometrySink* m_pSink;
```

## <a name="cd2dgeometrysinkoperator-id2d1geometrysink"></a><a name="operator_id2d1geometrysink_star"></a>シンク::演算子 ID2D1ジオメトリシンク*

インターフェイスを返します。

```
operator ID2D1GeometrySink*();
```

### <a name="return-value"></a>戻り値

ID2D1GeometrySink インターフェイスへのポインターまたは NULL オブジェクトがまだ初期化されていない場合。

## <a name="cd2dgeometrysinksetfillmode"></a><a name="setfillmode"></a>シンク::セットフィルモード

このジオメトリ シンクで記述されているジオメトリ内にあるポイントと、どのポイントが外側にあるかを決定する方法を指定します。

```
void SetFillMode(D2D1_FILL_MODE fillMode);
```

### <a name="parameters"></a>パラメーター

*フィルモード*<br/>
指定した点がジオメトリの一部であるかどうかを判断するために使用されるメソッド。

## <a name="cd2dgeometrysinksetsegmentflags"></a><a name="setsegmentflags"></a>シンク::セグメントフラグを設定します。

ジオメトリ シンクに追加された新しいセグメントに適用するストロークおよび結合オプションを指定します。

```
void SetSegmentFlags(D2D1_PATH_SEGMENT vertexFlags);
```

### <a name="parameters"></a>パラメーター

*頂点フラグ*<br/>
ジオメトリ シンクに追加された新しいセグメントに適用するストロークおよび結合オプション。

## <a name="see-also"></a>関連項目

[クラス](../../mfc/reference/mfc-classes.md)

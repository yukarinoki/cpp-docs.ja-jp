---
description: '詳細情報: CD2DPointF クラス'
title: CD2DPointF クラス
ms.date: 11/04/2016
f1_keywords:
- CD2DPointF
- AFXRENDERTARGET/CD2DPointF
- AFXRENDERTARGET/CD2DPointF::CD2DPointF
helpviewer_keywords:
- CD2DPointF [MFC], CD2DPointF
ms.assetid: 30f72083-1c8a-4f50-adb2-72dbbe3522d4
ms.openlocfilehash: 0f63aa35acb33504c96316b67ecc4f885f4f0247
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97193358"
---
# <a name="cd2dpointf-class"></a>CD2DPointF クラス

`D2D1_POINT_2F`のラッパー。

## <a name="syntax"></a>構文

```
class CD2DPointF : public D2D1_POINT_2F;
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CD2DPointF:: CD2DPointF](#cd2dpointf)|オーバーロードされます。 オブジェクト `CD2DPointF` からオブジェクトを構築 `D2D1_POINT_2F` します。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[CD2DPointF:: operator CPoint](#operator_cpoint)|`CD2DPointF`をオブジェクトに変換 `CPoint` します。|

## <a name="inheritance-hierarchy"></a>継承階層

`D2D1_POINT_2F`

`CD2DPointF`

## <a name="requirements"></a>要件

**ヘッダー:** afxrendertarget

## <a name="cd2dpointfcd2dpointf"></a><a name="cd2dpointf"></a> CD2DPointF:: CD2DPointF

CPoint オブジェクトから CD2DPointF オブジェクトを構築します。

```
CD2DPointF(const CPoint& pt);
CD2DPointF(const D2D1_POINT_2F& pt);
CD2DPointF(const D2D1_POINT_2F* pt);
CD2DPointF(FLOAT fX = 0., FLOAT fY = 0.);
```

### <a name="parameters"></a>パラメーター

*pt*<br/>
ソースポイント

*fX*<br/>
ソース X

*会計*<br/>
ソース Y

## <a name="cd2dpointfoperator-cpoint"></a><a name="operator_cpoint"></a> CD2DPointF:: operator CPoint

CD2DPointF を CPoint オブジェクトに変換します。

```
operator CPoint();
```

### <a name="return-value"></a>戻り値

D2D point の現在の値。

## <a name="see-also"></a>関連項目

[クラス](../../mfc/reference/mfc-classes.md)

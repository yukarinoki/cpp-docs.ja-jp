---
title: CD2DPointF クラス
ms.date: 11/04/2016
f1_keywords:
- CD2DPointF
- AFXRENDERTARGET/CD2DPointF
- AFXRENDERTARGET/CD2DPointF::CD2DPointF
helpviewer_keywords:
- CD2DPointF [MFC], CD2DPointF
ms.assetid: 30f72083-1c8a-4f50-adb2-72dbbe3522d4
ms.openlocfilehash: 5d66c31289f9e17df99df4681cff1d5cf6a0ec86
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81369160"
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
|[CD2Dポイントフ::CD2Dポイントフ](#cd2dpointf)|オーバーロードされます。 オブジェクトから`D2D1_POINT_2F`オブジェクト`CD2DPointF`を構築します。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[CD2DPointF::オペレーターCポイント](#operator_cpoint)|オブジェクトに`CD2DPointF``CPoint`変換します。|

## <a name="inheritance-hierarchy"></a>継承階層

`D2D1_POINT_2F`

`CD2DPointF`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxrendertarget.h

## <a name="cd2dpointfcd2dpointf"></a><a name="cd2dpointf"></a>CD2Dポイントフ::CD2Dポイントフ

CPoint オブジェクトから CD2DPointF オブジェクトを構築します。

```
CD2DPointF(const CPoint& pt);
CD2DPointF(const D2D1_POINT_2F& pt);
CD2DPointF(const D2D1_POINT_2F* pt);
CD2DPointF(FLOAT fX = 0., FLOAT fY = 0.);
```

### <a name="parameters"></a>パラメーター

*Pt*<br/>
ソース ポイント

*Fx*<br/>
ソース X

*年度*<br/>
ソース Y

## <a name="cd2dpointfoperator-cpoint"></a><a name="operator_cpoint"></a>CD2DPointF::オペレーターCポイント

CD2DPointF を CPoint オブジェクトに変換します。

```
operator CPoint();
```

### <a name="return-value"></a>戻り値

D2D 点の現在の値。

## <a name="see-also"></a>関連項目

[クラス](../../mfc/reference/mfc-classes.md)

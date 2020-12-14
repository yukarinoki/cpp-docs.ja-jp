---
description: '詳細情報: CD2DPointU クラス'
title: CD2DPointU クラス
ms.date: 08/29/2019
f1_keywords:
- CD2DPointU
- AFXRENDERTARGET/CD2DPointU
- AFXRENDERTARGET/CD2DPointU::CD2DPointU
helpviewer_keywords:
- CD2DPointU [MFC], CD2DPointU
ms.assetid: 04733f96-b6de-4a89-82e3-caad1e8087a9
ms.openlocfilehash: 04c1c366f3026e4a621892fc1c7617707c33d23d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97250999"
---
# <a name="cd2dpointu-class"></a>CD2DPointU クラス

`D2D1_POINT_2U`のラッパー。

## <a name="syntax"></a>構文

```
class CD2DPointU : public D2D1_POINT_2U;
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CD2DPointU:: CD2DPointU](#cd2dpointu)|オーバーロードされます。 `CD2DPointU`オブジェクトオブジェクトからを構築 `D2D1_POINT_2U` します。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[CD2DPointU:: operator CPoint](#operator_cpoint)|`CD2DPointU`をオブジェクトに変換 `CPoint` します。|

## <a name="inheritance-hierarchy"></a>継承階層

`D2D1_POINT_2U`

`CD2DPointU`

## <a name="requirements"></a>要件

**ヘッダー:** afxrendertarget

## <a name="cd2dpointucd2dpointu"></a><a name="cd2dpointu"></a> CD2DPointU:: CD2DPointU

CPoint オブジェクトから CD2DPointU オブジェクトを構築します。

```
CD2DPointU(const CPoint& pt);
CD2DPointU(const D2D1_POINT_2U& pt);
CD2DPointU(const D2D1_POINT_2U* pt);
CD2DPointU(UINT32 uX = 0, UINT32 uY = 0);
```

### <a name="parameters"></a>パラメーター

*pt*<br/>
ソースポイント

*uX*<br/>
ソース X

*uY*<br/>
ソース Y

## <a name="cd2dpointuoperator-cpoint"></a><a name="operator_cpoint"></a> CD2DPointU:: operator CPoint

CD2DPointU を CPoint オブジェクトに変換します。

```
operator CPoint();
```

### <a name="return-value"></a>戻り値

D2D point の現在の値。

## <a name="see-also"></a>関連項目

[クラス](../../mfc/reference/mfc-classes.md)

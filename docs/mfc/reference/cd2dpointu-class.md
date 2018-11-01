---
title: CD2DPointU クラス
ms.date: 11/04/2016
f1_keywords:
- CD2DPointU
- AFXRENDERTARGET/CD2DPointU
- AFXRENDERTARGET/CD2DPointU::CD2DPointU
helpviewer_keywords:
- CD2DPointU [MFC], CD2DPointU
ms.assetid: 04733f96-b6de-4a89-82e3-caad1e8087a9
ms.openlocfilehash: 138916efe781d8bef69a1c4eb61a73c5a405be67
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50551854"
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
|[CD2DPointU::CD2DPointU](#cd2dpointu)|オーバーロードされます。 構築、`CD2DPointU`オブジェクトから`D2D1_POINT_2U`オブジェクト。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[CD2DPointU::operator CPoint](#operator_cpoint)|変換`CD2DPointU`に`CPoint`オブジェクト。|

## <a name="inheritance-hierarchy"></a>継承階層

`D2D1_POINT_2U`

`CD2DPointU`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxrendertarget.h

##  <a name="cd2dpointu"></a>  CD2DPointU::CD2DPointU

CPoint オブジェクトから CD2DPointU オブジェクトを構築します。

```
CD2DPointU(const CPoint& pt);
CD2DPointU(const D2D1_POINT_2U& pt);
  CD2DPointU(const D2D1_POINT_2U* pt);
CD2DPointU(UINT32 uX = 0, UINT32 uY = 0);
```

### <a name="parameters"></a>パラメーター

*pt*<br/>
ソース ポイント

*uX*<br/>
ソース X

*uY*<br/>
ソース Y

##  <a name="operator_cpoint"></a>  CD2DPointU::operator CPoint

CD2DPointU CPoint オブジェクトに変換します。

```
operator CPoint();
```

### <a name="return-value"></a>戻り値

D2D ポイントの現在の値。

## <a name="see-also"></a>関連項目

[クラス](../../mfc/reference/mfc-classes.md)

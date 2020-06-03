---
title: CD2DRectU クラス
ms.date: 11/04/2016
f1_keywords:
- CD2DRectU
- AFXRENDERTARGET/CD2DRectU
- AFXRENDERTARGET/CD2DRectU::CD2DRectU
- AFXRENDERTARGET/CD2DRectU::IsNull
helpviewer_keywords:
- CD2DRectU [MFC], CD2DRectU
- CD2DRectU [MFC], IsNull
ms.assetid: a62f17d1-011d-4867-8f51-fd7e7c00561d
ms.openlocfilehash: 26e647ae01a498a6ad8ca2d7c866f33b01910881
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81369107"
---
# <a name="cd2drectu-class"></a>CD2DRectU クラス

`D2D1_RECT_U`のラッパー。

## <a name="syntax"></a>構文

```
class CD2DRectU : public D2D1_RECT_U;
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CD2DRectU::CD2DRectU](#cd2drectu)|オーバーロードされます。 オブジェクトから`D2D1_RECT_U`オブジェクト`CD2DRectU`を構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CD2DRectU::IsNull](#isnull)|式に有効なデータ (NULL) が含まれているかどうかを示す**ブール**値を返します。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[CD2DRectU::演算子 CRect](#operator_crect)|オブジェクトに`CD2DRectU``CRect`変換します。|

## <a name="inheritance-hierarchy"></a>継承階層

`D2D1_RECT_U`

`CD2DRectU`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxrendertarget.h

## <a name="cd2drectucd2drectu"></a><a name="cd2drectu"></a>CD2DRectU::CD2DRectU

CRect オブジェクトから CD2DRectU オブジェクトを構築します。

```
CD2DRectU(const CRect& rect);
CD2DRectU(const D2D1_RECT_U& rect);
CD2DRectU(const D2D1_RECT_U* rect);

CD2DRectU(
    UINT32 uLeft = 0,
    UINT32 uTop = 0,
    UINT32 uRight = 0,
    UINT32 uBottom = 0);
```

### <a name="parameters"></a>パラメーター

*Rect*<br/>
ソース矩形

*左から*<br/>
ソース左座標

*ユートップ*<br/>
ソースの上の座標

*右*<br/>
ソース右座標

*uボトム*<br/>
ソース底の座標

## <a name="cd2drectuisnull"></a><a name="isnull"></a>CD2DRectU::IsNull

式に有効なデータが含まれているかどうかを示すブール値を返します (Null)。

```
BOOL IsNull() const;
```

### <a name="return-value"></a>戻り値

四角形の上、左、下、および右の値がすべて 0 の場合は TRUE。それ以外の場合は FALSE。

## <a name="cd2drectuoperator-crect"></a><a name="operator_crect"></a>CD2DRectU::演算子 CRect

CD2DRectU を CRect オブジェクトに変換します。

```
operator CRect();
```

### <a name="return-value"></a>戻り値

D2D 四角形の現在の値。

## <a name="see-also"></a>関連項目

[クラス](../../mfc/reference/mfc-classes.md)

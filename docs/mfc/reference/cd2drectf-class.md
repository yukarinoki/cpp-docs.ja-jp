---
title: CD2DRectF クラス
ms.date: 11/04/2016
f1_keywords:
- CD2DRectF
- AFXRENDERTARGET/CD2DRectF
- AFXRENDERTARGET/CD2DRectF::CD2DRectF
- AFXRENDERTARGET/CD2DRectF::IsNull
helpviewer_keywords:
- CD2DRectF [MFC], CD2DRectF
- CD2DRectF [MFC], IsNull
ms.assetid: 87c12d87-9d18-4a19-ba14-0f51d6b6835a
ms.openlocfilehash: 33d3c5f9e795ad6c91b689436e8a3b1b56966dce
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81369119"
---
# <a name="cd2drectf-class"></a>CD2DRectF クラス

`D2D1_RECT_F`のラッパー。

## <a name="syntax"></a>構文

```
class CD2DRectF : public D2D1_RECT_F;
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CD2DRectF::CD2DRectF](#cd2drectf)|オーバーロードされます。 オブジェクトから`D2D1_RECT_F`オブジェクト`CD2DRectF`を構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[をクリックします。](#isnull)|式に有効なデータ (NULL) が含まれているかどうかを示す**ブール**値を返します。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[CD2DRectF::演算子 CRect](#operator_crect)|オブジェクトに`CD2DRectF``CRect`変換します。|

## <a name="inheritance-hierarchy"></a>継承階層

`D2D1_RECT_F`

`CD2DRectF`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxrendertarget.h

## <a name="cd2drectfcd2drectf"></a><a name="cd2drectf"></a>CD2DRectF::CD2DRectF

CRect オブジェクトから CD2DRectF オブジェクトを構築します。

```
CD2DRectF(const CRect& rect);
CD2DRectF(const D2D1_RECT_F& rect);
CD2DRectF(const D2D1_RECT_F* rect);

CD2DRectF(
    FLOAT fLeft = 0.,
    FLOAT fTop = 0.,
    FLOAT fRight = 0.,
    FLOAT fBottom = 0.);
```

### <a name="parameters"></a>パラメーター

*Rect*<br/>
ソース矩形

*f左*<br/>
ソース左座標

*fTop*<br/>
ソースの上の座標

*恐怖*<br/>
ソース右座標

*fボトム*<br/>
ソース底の座標

## <a name="cd2drectfisnull"></a><a name="isnull"></a>をクリックします。

式に有効なデータが含まれているかどうかを示すブール値を返します (Null)。

```
BOOL IsNull() const;
```

### <a name="return-value"></a>戻り値

四角形の上、左、下、および右の値がすべて 0 の場合は TRUE。それ以外の場合は FALSE。

## <a name="cd2drectfoperator-crect"></a><a name="operator_crect"></a>CD2DRectF::演算子 CRect

CD2DRectF を CRect オブジェクトに変換します。

```
operator CRect();
```

### <a name="return-value"></a>戻り値

D2D 四角形の現在の値。

## <a name="see-also"></a>関連項目

[クラス](../../mfc/reference/mfc-classes.md)

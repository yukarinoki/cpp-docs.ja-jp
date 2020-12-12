---
description: '詳細情報: CD2DRectU クラス'
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
ms.openlocfilehash: dadbaf37f1ed11f96f29c7e4cf78eebf8095590d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97301621"
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
|[CD2DRectU:: CD2DRectU](#cd2drectu)|オーバーロードされます。 オブジェクト `CD2DRectU` からオブジェクトを構築 `D2D1_RECT_U` します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CD2DRectU:: IsNull](#isnull)|式に有効なデータが含まれていない (NULL) かどうかを示す **ブール** 値を返します。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[CD2DRectU:: operator CRect](#operator_crect)|`CD2DRectU`をオブジェクトに変換 `CRect` します。|

## <a name="inheritance-hierarchy"></a>継承階層

`D2D1_RECT_U`

`CD2DRectU`

## <a name="requirements"></a>要件

**ヘッダー:** afxrendertarget

## <a name="cd2drectucd2drectu"></a><a name="cd2drectu"></a> CD2DRectU:: CD2DRectU

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

*rect*<br/>
ソース四角形

*uLeft*<br/>
ソースの左座標

*uTop*<br/>
基になる上座標

*uRight*<br/>
ソースの右座標

*uBottom*<br/>
基になる下座標

## <a name="cd2drectuisnull"></a><a name="isnull"></a> CD2DRectU:: IsNull

式に有効なデータが含まれていない (Null) かどうかを示すブール値を返します。

```
BOOL IsNull() const;
```

### <a name="return-value"></a>戻り値

四角形の上、左、下、および右の値がすべて0に等しい場合は TRUE。それ以外の場合は FALSE。

## <a name="cd2drectuoperator-crect"></a><a name="operator_crect"></a> CD2DRectU:: operator CRect

CD2DRectU を CRect オブジェクトに変換します。

```
operator CRect();
```

### <a name="return-value"></a>戻り値

D2D rectangle の現在の値。

## <a name="see-also"></a>関連項目

[クラス](../../mfc/reference/mfc-classes.md)

---
description: '詳細情報: CD2DEllipse クラス'
title: CD2DEllipse クラス
ms.date: 08/29/2019
f1_keywords:
- CD2DEllipse
- AFXRENDERTARGET/CD2DEllipse
- AFXRENDERTARGET/CD2DEllipse::CD2DEllipse
helpviewer_keywords:
- CD2DEllipse [MFC], CD2DEllipse
ms.assetid: e9f02f54-acf2-427e-b349-db50cd9a77df
ms.openlocfilehash: 827ba5515cb4b20cb8e5b10012590a001e01c08f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97313061"
---
# <a name="cd2dellipse-class"></a>CD2DEllipse クラス

`D2D1_ELLIPSE`のラッパー。

## <a name="syntax"></a>構文

```
class CD2DEllipse : public D2D1_ELLIPSE;
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CD2DEllipse:: CD2DEllipse](#cd2dellipse)|オーバーロードされます。 オブジェクト `CD2DEllipse` からオブジェクトを構築 `D2D1_ELLIPSE` します。|

## <a name="inheritance-hierarchy"></a>継承階層

`D2D1_ELLIPSE`

`CD2DEllipse`

## <a name="requirements"></a>要件

**ヘッダー:** afxrendertarget

## <a name="cd2dellipsecd2dellipse"></a><a name="cd2dellipse"></a> CD2DEllipse:: CD2DEllipse

CD2DRectF オブジェクトから CD2DEllipse オブジェクトを構築します。

```
CD2DEllipse(const CD2DRectF& rect);
CD2DEllipse(const D2D1_ELLIPSE& ellipse);
CD2DEllipse(const D2D1_ELLIPSE* ellipse);

CD2DEllipse(
    const CD2DPointF& ptCenter,
    const CD2DSizeF& sizeRadius);
```

### <a name="parameters"></a>パラメーター

*rect*<br/>
ソース四角形

*楕円*<br/>
変換元の楕円

*ptCenter*<br/>
楕円の中心点。

*sizeRadius*<br/>
楕円の X 半径と Y 半径。

## <a name="see-also"></a>関連項目

[クラス](../../mfc/reference/mfc-classes.md)

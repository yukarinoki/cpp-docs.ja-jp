---
title: CD2DEllipse クラス
ms.date: 08/29/2019
f1_keywords:
- CD2DEllipse
- AFXRENDERTARGET/CD2DEllipse
- AFXRENDERTARGET/CD2DEllipse::CD2DEllipse
helpviewer_keywords:
- CD2DEllipse [MFC], CD2DEllipse
ms.assetid: e9f02f54-acf2-427e-b349-db50cd9a77df
ms.openlocfilehash: 82ad2fbfb8558486134f85d7ec9bcaa6eb4e7507
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81369265"
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
|[CD2D楕円::CD2D楕円](#cd2dellipse)|オーバーロードされます。 オブジェクトから`D2D1_ELLIPSE`オブジェクト`CD2DEllipse`を構築します。|

## <a name="inheritance-hierarchy"></a>継承階層

`D2D1_ELLIPSE`

`CD2DEllipse`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxrendertarget.h

## <a name="cd2dellipsecd2dellipse"></a><a name="cd2dellipse"></a>CD2D楕円::CD2D楕円

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

*Rect*<br/>
ソース矩形

*ellipse*<br/>
ソース楕円

*ptセンター*<br/>
楕円の中心点。

*サイズ半径*<br/>
楕円の X 半径と Y 半径。

## <a name="see-also"></a>関連項目

[クラス](../../mfc/reference/mfc-classes.md)

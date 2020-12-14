---
description: '詳細情報: CD2DRoundedRect クラス'
title: CD2DRoundedRect クラス
ms.date: 11/04/2016
f1_keywords:
- CD2DRoundedRect
- AFXRENDERTARGET/CD2DRoundedRect
- AFXRENDERTARGET/CD2DRoundedRect::CD2DRoundedRect
helpviewer_keywords:
- CD2DRoundedRect [MFC], CD2DRoundedRect
ms.assetid: 06207fb5-e92b-41c0-bceb-b45d8f466531
ms.openlocfilehash: 13c1b0910c9d78f615d64e3eecba8bb813916413
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97240664"
---
# <a name="cd2droundedrect-class"></a>CD2DRoundedRect クラス

`D2D1_ROUNDED_RECT`のラッパー。

## <a name="syntax"></a>構文

```
class CD2DRoundedRect : public D2D1_ROUNDED_RECT;
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CD2DRoundedRect:: CD2DRoundedRect](#cd2droundedrect)|オーバーロードされます。 オブジェクト `CD2DRoundedRect` からオブジェクトを構築 `D2D1_ROUNDED_RECT` します。|

## <a name="inheritance-hierarchy"></a>継承階層

`D2D1_ROUNDED_RECT`

[CD2DRoundedRect](../../mfc/reference/cd2droundedrect-class.md)

## <a name="requirements"></a>要件

**ヘッダー:** afxrendertarget

## <a name="cd2droundedrectcd2droundedrect"></a><a name="cd2droundedrect"></a> CD2DRoundedRect:: CD2DRoundedRect

CD2DRectF オブジェクトから CD2DRoundedRect オブジェクトを構築します。

```
CD2DRoundedRect(
    const CD2DRectF& rectIn,
    const CD2DSizeF& sizeRadius);

CD2DRoundedRect(const D2D1_ROUNDED_RECT& rectIn);
CD2DRoundedRect(const D2D1_ROUNDED_RECT* rectIn);
```

### <a name="parameters"></a>パラメーター

*rectIn*<br/>
ソース四角形

*sizeRadius*<br/>
半径のサイズ

## <a name="see-also"></a>関連項目

[クラス](../../mfc/reference/mfc-classes.md)

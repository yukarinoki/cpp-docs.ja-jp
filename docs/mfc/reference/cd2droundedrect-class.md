---
title: CD2DRoundedRect クラス
ms.date: 11/04/2016
f1_keywords:
- CD2DRoundedRect
- AFXRENDERTARGET/CD2DRoundedRect
- AFXRENDERTARGET/CD2DRoundedRect::CD2DRoundedRect
helpviewer_keywords:
- CD2DRoundedRect [MFC], CD2DRoundedRect
ms.assetid: 06207fb5-e92b-41c0-bceb-b45d8f466531
ms.openlocfilehash: 6c1aa2bb9593cdf12aadc39ef8a85cc8ad14078a
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50677475"
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
|[CD2DRoundedRect::CD2DRoundedRect](#cd2droundedrect)|オーバーロードされます。 構築、`CD2DRoundedRect`オブジェクトから`D2D1_ROUNDED_RECT`オブジェクト。|

## <a name="inheritance-hierarchy"></a>継承階層

`D2D1_ROUNDED_RECT`

[CD2DRoundedRect](../../mfc/reference/cd2droundedrect-class.md)

## <a name="requirements"></a>必要条件

**ヘッダー:** afxrendertarget.h

##  <a name="cd2droundedrect"></a>  CD2DRoundedRect::CD2DRoundedRect

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
元の四角形

*sizeRadius*<br/>
半径のサイズ

## <a name="see-also"></a>関連項目

[クラス](../../mfc/reference/mfc-classes.md)

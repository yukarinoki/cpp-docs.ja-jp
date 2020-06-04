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
ms.openlocfilehash: 5189f3d824c008845570eac6eead4a35be1e483d
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81369084"
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
|[CD2D回り直しレック::CD2D回り直し](#cd2droundedrect)|オーバーロードされます。 オブジェクトから`D2D1_ROUNDED_RECT`オブジェクト`CD2DRoundedRect`を構築します。|

## <a name="inheritance-hierarchy"></a>継承階層

`D2D1_ROUNDED_RECT`

[CD2D回り直し](../../mfc/reference/cd2droundedrect-class.md)

## <a name="requirements"></a>必要条件

**ヘッダー:** afxrendertarget.h

## <a name="cd2droundedrectcd2droundedrect"></a><a name="cd2droundedrect"></a>CD2D回り直しレック::CD2D回り直し

CD2DRoundedRect オブジェクトから CD2DRoundedRect オブジェクトを構築します。

```
CD2DRoundedRect(
    const CD2DRectF& rectIn,
    const CD2DSizeF& sizeRadius);

CD2DRoundedRect(const D2D1_ROUNDED_RECT& rectIn);
CD2DRoundedRect(const D2D1_ROUNDED_RECT* rectIn);
```

### <a name="parameters"></a>パラメーター

*レクトイン*<br/>
ソース矩形

*サイズ半径*<br/>
半径サイズ

## <a name="see-also"></a>関連項目

[クラス](../../mfc/reference/mfc-classes.md)

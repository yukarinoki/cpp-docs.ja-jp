---
title: CD2DRoundedRect クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CD2DRoundedRect
- AFXRENDERTARGET/CD2DRoundedRect
- AFXRENDERTARGET/CD2DRoundedRect::CD2DRoundedRect
dev_langs:
- C++
helpviewer_keywords:
- CD2DRoundedRect [MFC], CD2DRoundedRect
ms.assetid: 06207fb5-e92b-41c0-bceb-b45d8f466531
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2037a00eb00fac1a14eca50031d213a5827ac425
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46448028"
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

## <a name="requirements"></a>要件

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

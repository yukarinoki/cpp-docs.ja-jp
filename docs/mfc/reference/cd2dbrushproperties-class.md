---
description: '詳細情報: CD2DBrushProperties クラス'
title: CD2DBrushProperties クラス
ms.date: 11/04/2016
f1_keywords:
- CD2DBrushProperties
- AFXRENDERTARGET/CD2DBrushProperties
- AFXRENDERTARGET/CD2DBrushProperties::CD2DBrushProperties
- AFXRENDERTARGET/CD2DBrushProperties::CommonInit
helpviewer_keywords:
- CD2DBrushProperties [MFC], CD2DBrushProperties
- CD2DBrushProperties [MFC], CommonInit
ms.assetid: c77d717f-0a16-4d74-b2ce-0ae1766ed6f9
ms.openlocfilehash: d16d08041b5096c8a5ad188201c6a06e21681849
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97227560"
---
# <a name="cd2dbrushproperties-class"></a>CD2DBrushProperties クラス

`D2D1_BRUSH_PROPERTIES`のラッパー。

## <a name="syntax"></a>構文

```
class CD2DBrushProperties : public D2D1_BRUSH_PROPERTIES;
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CD2DBrushProperties:: CD2DBrushProperties](#cd2dbrushproperties)|オーバーロードされます。 構造体を作成します。 `CD2D_BRUSH_PROPERTIES`|

### <a name="protected-methods"></a>プロテクト メソッド

|名前|説明|
|----------|-----------------|
|[CD2DBrushProperties:: CommonInit](#commoninit)|オブジェクトを初期化します。|

## <a name="inheritance-hierarchy"></a>継承階層

`D2D1_BRUSH_PROPERTIES`

`CD2DBrushProperties`

## <a name="requirements"></a>要件

**ヘッダー:** afxrendertarget

## <a name="cd2dbrushpropertiescd2dbrushproperties"></a><a name="cd2dbrushproperties"></a> CD2DBrushProperties:: CD2DBrushProperties

CD2D_BRUSH_PROPERTIES 構造体を作成します。

```
CD2DBrushProperties();
CD2DBrushProperties(FLOAT _opacity);

CD2DBrushProperties(
    D2D1_MATRIX_3X2_F _transform,
    FLOAT _opacity = 1.);
```

### <a name="parameters"></a>パラメーター

*_opacity*<br/>
ブラシの基本不透明度。 既定値は 1.0 です。

*_transform*<br/>
ブラシに適用する変換。

## <a name="cd2dbrushpropertiescommoninit"></a><a name="commoninit"></a> CD2DBrushProperties:: CommonInit

オブジェクトを初期化します。

```cpp
void CommonInit();
```

## <a name="see-also"></a>関連項目

[クラス](../../mfc/reference/mfc-classes.md)

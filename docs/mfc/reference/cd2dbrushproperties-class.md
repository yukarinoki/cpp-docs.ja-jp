---
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
ms.openlocfilehash: 2db720fd09c62f8b86baecea9229d946f3892333
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "81754185"
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
|[プロパティ::CD2Dブラシプロパティ](#cd2dbrushproperties)|オーバーロードされます。 構造体を`CD2D_BRUSH_PROPERTIES`作成します。|

### <a name="protected-methods"></a>プロテクト メソッド

|名前|説明|
|----------|-----------------|
|[プロパティ::コモンイニト](#commoninit)|オブジェクトを初期化します。|

## <a name="inheritance-hierarchy"></a>継承階層

`D2D1_BRUSH_PROPERTIES`

`CD2DBrushProperties`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxrendertarget.h

## <a name="cd2dbrushpropertiescd2dbrushproperties"></a><a name="cd2dbrushproperties"></a>プロパティ::CD2Dブラシプロパティ

CD2D_BRUSH_PROPERTIES構造を作成します。

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
ブラシに適用する変換

## <a name="cd2dbrushpropertiescommoninit"></a><a name="commoninit"></a>プロパティ::コモンイニト

オブジェクトを初期化します。

```cpp
void CommonInit();
```

## <a name="see-also"></a>関連項目

[クラス](../../mfc/reference/mfc-classes.md)

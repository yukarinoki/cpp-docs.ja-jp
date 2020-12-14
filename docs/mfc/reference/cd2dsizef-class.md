---
description: '詳細情報: CD2DSizeF クラス'
title: CD2DSizeF クラス
ms.date: 08/29/2019
f1_keywords:
- CD2DSizeF
- AFXRENDERTARGET/CD2DSizeF
- AFXRENDERTARGET/CD2DSizeF::CD2DSizeF
- AFXRENDERTARGET/CD2DSizeF::IsNull
helpviewer_keywords:
- CD2DSizeF [MFC], CD2DSizeF
- CD2DSizeF [MFC], IsNull
ms.assetid: f486a1e1-997d-4286-8cb9-26369dc82055
ms.openlocfilehash: d1416f7cd225be8edf1a7b08f06f611219d7846d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97240560"
---
# <a name="cd2dsizef-class"></a>CD2DSizeF クラス

D2D1_SIZE_F のラッパー。

## <a name="syntax"></a>構文

```
class CD2DSizeF : public D2D1_SIZE_F;
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CD2DSizeF:: CD2DSizeF](#cd2dsizef)|オーバーロードされます。 オブジェクト `CD2DSizeF` からオブジェクトを構築 `D2D1_SIZE_F` します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CD2DSizeF:: IsNull](#isnull)|式に有効なデータが含まれていない (NULL) かどうかを示す **ブール** 値を返します。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[CD2DSizeF:: operator CSize](#operator_csize)|`CD2DSizeF`をオブジェクトに変換 `CSize` します。|

## <a name="inheritance-hierarchy"></a>継承階層

`D2D1_SIZE_F`

[CD2DSizeF](../../mfc/reference/cd2dsizef-class.md)

## <a name="requirements"></a>要件

**ヘッダー:** afxrendertarget

## <a name="cd2dsizefcd2dsizef"></a><a name="cd2dsizef"></a> CD2DSizeF:: CD2DSizeF

CD2DSizeF オブジェクトを CSize オブジェクトから構築します。

```
CD2DSizeF(const CSize& size);
CD2DSizeF(const D2D1_SIZE_F& size);
CD2DSizeF(const D2D1_SIZE_F* size);

CD2DSizeF(
    FLOAT cx = 0.,
    FLOAT cy = 0.);
```

### <a name="parameters"></a>パラメーター

*size*<br/>
ソースサイズ

*シリーズ*<br/>
ソースの幅

*暦年*<br/>
ソースの高さ

## <a name="cd2dsizefisnull"></a><a name="isnull"></a> CD2DSizeF:: IsNull

式に有効なデータが含まれていない (Null) かどうかを示すブール値を返します。

```
BOOL IsNull() const;
```

### <a name="return-value"></a>戻り値

幅と高さが空の場合は TRUE。それ以外の場合は FALSE。

## <a name="cd2dsizefoperator-csize"></a><a name="operator_csize"></a> CD2DSizeF:: operator CSize

CD2DSizeF を CSize オブジェクトに変換します。

```
operator CSize();
```

### <a name="return-value"></a>戻り値

D2D サイズの現在の値。

## <a name="see-also"></a>関連項目

[クラス](../../mfc/reference/mfc-classes.md)

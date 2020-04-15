---
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
ms.openlocfilehash: be050f98855e5af794166e1f86962111a23bfa2e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81369063"
---
# <a name="cd2dsizef-class"></a>CD2DSizeF クラス

D2D1_SIZE_Fのラッパー。

## <a name="syntax"></a>構文

```
class CD2DSizeF : public D2D1_SIZE_F;
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CD2Dサイズフ::CD2Dサイズ](#cd2dsizef)|オーバーロードされます。 オブジェクトから`D2D1_SIZE_F`オブジェクト`CD2DSizeF`を構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[を使用します。](#isnull)|式に有効なデータ (NULL) が含まれているかどうかを示す**ブール**値を返します。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[CD2Dサイズ::オペレーターCサイズ](#operator_csize)|オブジェクトに`CD2DSizeF``CSize`変換します。|

## <a name="inheritance-hierarchy"></a>継承階層

`D2D1_SIZE_F`

[CD2Dサイズ](../../mfc/reference/cd2dsizef-class.md)

## <a name="requirements"></a>必要条件

**ヘッダー:** afxrendertarget.h

## <a name="cd2dsizefcd2dsizef"></a><a name="cd2dsizef"></a>CD2Dサイズフ::CD2Dサイズ

CSize オブジェクトから CD2DSizeF オブジェクトを構築します。

```
CD2DSizeF(const CSize& size);
CD2DSizeF(const D2D1_SIZE_F& size);
CD2DSizeF(const D2D1_SIZE_F* size);

CD2DSizeF(
    FLOAT cx = 0.,
    FLOAT cy = 0.);
```

### <a name="parameters"></a>パラメーター

*サイズ*<br/>
ソース サイズ

*Cx*<br/>
ソース幅

*Cy*<br/>
ソースの高さ

## <a name="cd2dsizefisnull"></a><a name="isnull"></a>を使用します。

式に有効なデータが含まれているかどうかを示すブール値を返します (Null)。

```
BOOL IsNull() const;
```

### <a name="return-value"></a>戻り値

幅と高さが空の場合は TRUE。それ以外の場合は FALSE。

## <a name="cd2dsizefoperator-csize"></a><a name="operator_csize"></a>CD2Dサイズ::オペレーターCサイズ

CD2DSizeF を CSize オブジェクトに変換します。

```
operator CSize();
```

### <a name="return-value"></a>戻り値

D2D サイズの現在の値。

## <a name="see-also"></a>関連項目

[クラス](../../mfc/reference/mfc-classes.md)

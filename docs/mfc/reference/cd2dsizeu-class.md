---
description: '詳細情報: CD2DSizeU クラス'
title: CD2DSizeU クラス
ms.date: 08/29/2019
f1_keywords:
- CD2DSizeU
- AFXRENDERTARGET/CD2DSizeU
- AFXRENDERTARGET/CD2DSizeU::CD2DSizeU
- AFXRENDERTARGET/CD2DSizeU::IsNull
helpviewer_keywords:
- CD2DSizeU [MFC], CD2DSizeU
- CD2DSizeU [MFC], IsNull
ms.assetid: 6e679ba8-2112-43c3-8275-70b660856f02
ms.openlocfilehash: 0bb2d7cc632012fe8d8c0e3ada09025c2b025e64
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97154709"
---
# <a name="cd2dsizeu-class"></a>CD2DSizeU クラス

D2D1_SIZE_U のラッパー。

## <a name="syntax"></a>構文

```
class CD2DSizeU : public D2D1_SIZE_U;
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CD2DSizeU:: CD2DSizeU](#cd2dsizeu)|オーバーロードされます。 オブジェクト `CD2DSizeU` からオブジェクトを構築 `D2D1_SIZE_U` します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CD2DSizeU:: IsNull](#isnull)|式に有効なデータが含まれていない (NULL) かどうかを示す **ブール** 値を返します。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[CD2DSizeU:: operator CSize](#operator_csize)|`CD2DSizeU`をオブジェクトに変換 `CSize` します。|

## <a name="inheritance-hierarchy"></a>継承階層

`D2D1_SIZE_U`

[CD2DSizeU](../../mfc/reference/cd2dsizeu-class.md)

## <a name="requirements"></a>要件

**ヘッダー:** afxrendertarget

## <a name="cd2dsizeucd2dsizeu"></a><a name="cd2dsizeu"></a> CD2DSizeU:: CD2DSizeU

CD2DSizeU オブジェクトを CSize オブジェクトから構築します。

```
CD2DSizeU(const CSize& size);
CD2DSizeU(const D2D1_SIZE_U& size);
CD2DSizeU(const D2D1_SIZE_U* size);

CD2DSizeU(
    UINT32 cx = 0,
    UINT32 cy = 0);
```

### <a name="parameters"></a>パラメーター

*size*<br/>
ソースサイズ

*シリーズ*<br/>
ソースの幅

*暦年*<br/>
ソースの高さ

## <a name="cd2dsizeuisnull"></a><a name="isnull"></a> CD2DSizeU:: IsNull

式に有効なデータが含まれていない (Null) かどうかを示すブール値を返します。

```
BOOL IsNull() const;
```

### <a name="return-value"></a>戻り値

幅と高さが空の場合は TRUE。それ以外の場合は FALSE。

## <a name="cd2dsizeuoperator-csize"></a><a name="operator_csize"></a> CD2DSizeU:: operator CSize

CD2DSizeU を CSize オブジェクトに変換します。

```
operator CSize();
```

### <a name="return-value"></a>戻り値

D2D サイズの現在の値。

## <a name="see-also"></a>関連項目

[クラス](../../mfc/reference/mfc-classes.md)

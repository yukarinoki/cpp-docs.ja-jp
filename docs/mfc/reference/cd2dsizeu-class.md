---
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
ms.openlocfilehash: a5b87fe2ddd8fb32ddbbb2884c630952afdb079c
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81359294"
---
# <a name="cd2dsizeu-class"></a>CD2DSizeU クラス

D2D1_SIZE_Uのラッパー。

## <a name="syntax"></a>構文

```
class CD2DSizeU : public D2D1_SIZE_U;
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CD2Dサイズ::CD2Dサイズ](#cd2dsizeu)|オーバーロードされます。 オブジェクトから`D2D1_SIZE_U`オブジェクト`CD2DSizeU`を構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[を使用します。](#isnull)|式に有効なデータ (NULL) が含まれているかどうかを示す**ブール**値を返します。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[キー・ク・サイズ](#operator_csize)|オブジェクトに`CD2DSizeU``CSize`変換します。|

## <a name="inheritance-hierarchy"></a>継承階層

`D2D1_SIZE_U`

[CD2Dサイズ](../../mfc/reference/cd2dsizeu-class.md)

## <a name="requirements"></a>必要条件

**ヘッダー:** afxrendertarget.h

## <a name="cd2dsizeucd2dsizeu"></a><a name="cd2dsizeu"></a>CD2Dサイズ::CD2Dサイズ

CSize オブジェクトから CD2DSizeU オブジェクトを構築します。

```
CD2DSizeU(const CSize& size);
CD2DSizeU(const D2D1_SIZE_U& size);
CD2DSizeU(const D2D1_SIZE_U* size);

CD2DSizeU(
    UINT32 cx = 0,
    UINT32 cy = 0);
```

### <a name="parameters"></a>パラメーター

*サイズ*<br/>
ソース サイズ

*Cx*<br/>
ソース幅

*Cy*<br/>
ソースの高さ

## <a name="cd2dsizeuisnull"></a><a name="isnull"></a>を使用します。

式に有効なデータが含まれているかどうかを示すブール値を返します (Null)。

```
BOOL IsNull() const;
```

### <a name="return-value"></a>戻り値

幅と高さが空の場合は TRUE。それ以外の場合は FALSE。

## <a name="cd2dsizeuoperator-csize"></a><a name="operator_csize"></a>キー・ク・サイズ

CD2DSizeU を CSize オブジェクトに変換します。

```
operator CSize();
```

### <a name="return-value"></a>戻り値

D2D サイズの現在の値。

## <a name="see-also"></a>関連項目

[クラス](../../mfc/reference/mfc-classes.md)

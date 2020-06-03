---
title: クラスのデフォルトチャートレイト
ms.date: 11/04/2016
f1_keywords:
- CDefaultCharTraits
- ATLCOLL/ATL::CDefaultCharTraits
- ATLCOLL/ATL::CDefaultCharTraits::CharToLower
- ATLCOLL/ATL::CDefaultCharTraits::CharToUpper
helpviewer_keywords:
- CDefaultCharTraits class
ms.assetid: f94a3934-597f-401d-8513-ed6924ae069a
ms.openlocfilehash: 40c4d107d05e6d7b610e7c46be920d91d8fe6086
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81327094"
---
# <a name="cdefaultchartraits-class"></a>クラスのデフォルトチャートレイト

このクラスには、大文字と小文字の間で文字を変換するための 2 つの静的関数が用意されています。

## <a name="syntax"></a>構文

```
template <typename T>
class CDefaultCharTraits
```

#### <a name="parameters"></a>パラメーター

*T*<br/>
コレクションに格納されるデータの型。

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[C デフォルトのチャルトレイト::シャルトローワー](#chartolower)|(静的)文字を大文字に変換します。|
|[Cデフォルトのチャルトレイト::シャルトアッパー](#chartoupper)|(静的)文字を小文字に変換します。|

## <a name="remarks"></a>解説

このクラスは、クラス[CStringElementTraitsI](../../atl/reference/cstringelementtraitsi-class.md)によって使用される関数を提供します。

## <a name="requirements"></a>必要条件

**ヘッダー:** atlcoll.h

## <a name="cdefaultchartraitschartolower"></a><a name="chartolower"></a>C デフォルトのチャルトレイト::シャルトローワー

文字を小文字に変換します。

```
static wchar_t CharToLower(wchar_t x);
static char CharToLower(char x);
```

### <a name="parameters"></a>パラメーター

*X*<br/>
小文字に変換する文字。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Utilities#132](../../atl/codesnippet/cpp/cdefaultchartraits-class_1.cpp)]

## <a name="cdefaultchartraitschartoupper"></a><a name="chartoupper"></a>Cデフォルトのチャルトレイト::シャルトアッパー

文字を大文字に変換します。

```
static wchar_t CharToUpper(wchar_t x);
static char CharToUpper(char x);
```

### <a name="parameters"></a>パラメーター

*X*<br/>
大文字に変換する文字。

## <a name="see-also"></a>関連項目

[クラスの概要](../../atl/atl-class-overview.md)

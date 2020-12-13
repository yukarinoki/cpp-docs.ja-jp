---
description: '詳細情報: CDefaultCharTraits クラス'
title: CDefaultCharTraits クラス
ms.date: 11/04/2016
f1_keywords:
- CDefaultCharTraits
- ATLCOLL/ATL::CDefaultCharTraits
- ATLCOLL/ATL::CDefaultCharTraits::CharToLower
- ATLCOLL/ATL::CDefaultCharTraits::CharToUpper
helpviewer_keywords:
- CDefaultCharTraits class
ms.assetid: f94a3934-597f-401d-8513-ed6924ae069a
ms.openlocfilehash: 6d98c6b6ffb527fef1e5b2320b46eda61ec3f670
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97141961"
---
# <a name="cdefaultchartraits-class"></a>CDefaultCharTraits クラス

このクラスは、文字を大文字に変換するための2つの静的関数を提供します。

## <a name="syntax"></a>構文

```
template <typename T>
class CDefaultCharTraits
```

#### <a name="parameters"></a>パラメーター

*T*<br/>
コレクションに格納するデータの型。

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CDefaultCharTraits:: CharToLower](#chartolower)|雑音文字を大文字に変換するには、この関数を呼び出します。|
|[CDefaultCharTraits:: CharToUpper](#chartoupper)|雑音文字を小文字に変換するには、この関数を呼び出します。|

## <a name="remarks"></a>解説

このクラスは、 [CStringElementTraitsI](../../atl/reference/cstringelementtraitsi-class.md)クラスによって使用される関数を提供します。

## <a name="requirements"></a>要件

**ヘッダー:** atlcoll. h

## <a name="cdefaultchartraitschartolower"></a><a name="chartolower"></a> CDefaultCharTraits:: CharToLower

文字を小文字に変換するには、この関数を呼び出します。

```
static wchar_t CharToLower(wchar_t x);
static char CharToLower(char x);
```

### <a name="parameters"></a>パラメーター

*x*<br/>
小文字に変換する文字。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Utilities#132](../../atl/codesnippet/cpp/cdefaultchartraits-class_1.cpp)]

## <a name="cdefaultchartraitschartoupper"></a><a name="chartoupper"></a> CDefaultCharTraits:: CharToUpper

文字を大文字に変換するには、この関数を呼び出します。

```
static wchar_t CharToUpper(wchar_t x);
static char CharToUpper(char x);
```

### <a name="parameters"></a>パラメーター

*x*<br/>
大文字に変換する文字。

## <a name="see-also"></a>関連項目

[クラスの概要](../../atl/atl-class-overview.md)

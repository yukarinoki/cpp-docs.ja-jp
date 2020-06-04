---
title: クラスの既定値
ms.date: 11/04/2016
f1_keywords:
- CDefaultHashTraits
- ATLCOLL/ATL::CDefaultHashTraits
- ATLCOLL/ATL::CDefaultHashTraits::Hash
helpviewer_keywords:
- CDefaultHashTraits class
ms.assetid: d8ec4b37-6d58-447b-a0c1-8580c5b1ab85
ms.openlocfilehash: 43932092621d44cfc8b07270df92e2765665f23f
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81327084"
---
# <a name="cdefaulthashtraits-class"></a>クラスの既定値

このクラスは、ハッシュ値を計算するための静的関数を提供します。

## <a name="syntax"></a>構文

```
template<typename T>
class CDefaultHashTraits
```

#### <a name="parameters"></a>パラメーター

*T*<br/>
コレクションに格納されるデータの型。

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[ハッシュの既定値](#hash)|(静的)指定した要素のハッシュ値を計算します。|

## <a name="remarks"></a>解説

このクラスには、指定された要素のハッシュ値を返す 1 つの静的関数が含まれています。 このクラスは、[クラスによって使用されます](../../atl/reference/cdefaultelementtraits-class.md)。

詳細については、「 [ATL コレクション クラス](../../atl/atl-collection-classes.md)」を参照してください。

## <a name="requirements"></a>必要条件

**ヘッダー:** atlcoll.h

## <a name="cdefaulthashtraitshash"></a><a name="hash"></a>ハッシュの既定値

指定した要素のハッシュ値を計算します。

```
static ULONG Hash(const T& element) throw();
```

### <a name="parameters"></a>パラメーター

*要素*<br/>
要素。

### <a name="return-value"></a>戻り値

ハッシュ値を返します。

### <a name="remarks"></a>解説

デフォルトのハッシュアルゴリズムは非常に単純です: 戻り値は要素番号です。 より複雑なアルゴリズムが必要な場合は、この関数をオーバーライドします。

## <a name="see-also"></a>関連項目

[クラスの概要](../../atl/atl-class-overview.md)

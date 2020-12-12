---
description: '詳細情報: CStringElementTraitsI クラス'
title: CStringElementTraitsI クラス
ms.date: 11/04/2016
f1_keywords:
- CStringElementTraitsI
- ATLCOLL/ATL::CStringElementTraitsI
- ATLCOLL/ATL::CStringElementTraitsI::INARGTYPE
- ATLCOLL/ATL::CStringElementTraitsI::OUTARGTYPE
- ATLCOLL/ATL::CStringElementTraitsI::CompareElements
- ATLCOLL/ATL::CStringElementTraitsI::CompareElementsOrdered
- ATLCOLL/ATL::CStringElementTraitsI::Hash
helpviewer_keywords:
- CStringElementTraitsI class
ms.assetid: c23f92b1-91e5-400f-96ed-258b02622b7a
ms.openlocfilehash: 0a626677f4a62805933b2effb4811394626374a7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97140402"
---
# <a name="cstringelementtraitsi-class"></a>CStringElementTraitsI クラス

このクラスは、コレクションクラスオブジェクトに格納されている文字列に関連する静的関数を提供します。 これは [Cstringelementtraits](../../atl/reference/cstringelementtraits-class.md)に似ていますが、大文字と小文字を区別しない比較を実行します。

## <a name="syntax"></a>構文

```
template <typename T, class CharTraits = CDefaultCharTraits<T ::XCHAR>>
class CStringElementTraitsI : public CElementTraitsBase<T>
```

#### <a name="parameters"></a>パラメーター

*T*<br/>
コレクションに格納するデータの型。

## <a name="members"></a>メンバー

### <a name="public-typedefs"></a>パブリック typedef

|名前|説明|
|----------|-----------------|
|[CStringElementTraitsI:: INARGTYPE](#inargtype)|コレクションクラスオブジェクトに要素を追加するために使用するデータ型。|
|[CStringElementTraitsI:: OUTARGTYPE](#outargtype)|コレクションクラスオブジェクトから要素を取得するために使用するデータ型。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CStringElementTraitsI:: CompareElements](#compareelements)|2つの文字列要素が等しいかどうかを比較するには、この静的関数を呼び出します。大文字小文字の違いは無視されます。|
|[CStringElementTraitsI::CompareElementsOrdered](#compareelementsordered)|2つの文字列要素を比較するには、この静的関数を呼び出します。大文字と小文字の違いは無視されます。|
|[CStringElementTraitsI:: Hash](#hash)|指定された文字列要素のハッシュ値を計算するには、この静的関数を呼び出します。|

## <a name="remarks"></a>解説

このクラスは、文字列を比較し、ハッシュ値を作成するための静的関数を提供します。 これらの関数は、コレクションクラスを使用して文字列ベースのデータを格納する場合に便利です。 文字列オブジェクトが参照として処理される場合は、 [Cstringrefelementtraits](../../atl/reference/cstringrefelementtraits-class.md) を使用します。

詳細については、「 [ATL コレクションクラス](../../atl/atl-collection-classes.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CElementTraitsBase](../../atl/reference/celementtraitsbase-class.md)

`CStringElementTraitsI`

## <a name="requirements"></a>要件

**ヘッダー:** atlcoll. h

## <a name="cstringelementtraitsicompareelements"></a><a name="compareelements"></a> CStringElementTraitsI:: CompareElements

2つの文字列要素が等しいかどうかを比較するには、この静的関数を呼び出します。大文字小文字の違いは無視されます。

```
static bool CompareElements(INARGTYPE str1, INARGTYPE str2) throw();
```

### <a name="parameters"></a>パラメーター

*str1*<br/>
最初の文字列要素。

*str2*<br/>
2番目の文字列要素。

### <a name="return-value"></a>戻り値

要素が等しい場合は true、それ以外の場合は false を返します。

### <a name="remarks"></a>解説

比較では大文字と小文字が区別されません。

## <a name="cstringelementtraitsicompareelementsordered"></a><a name="compareelementsordered"></a> CStringElementTraitsI::CompareElementsOrdered

2つの文字列要素を比較するには、この静的関数を呼び出します。大文字と小文字の違いは無視されます。

```
static int CompareElementsOrdered(INARGTYPE str1, INARGTYPE str2) throw();
```

### <a name="parameters"></a>パラメーター

*str1*<br/>
最初の文字列要素。

*str2*<br/>
2番目の文字列要素。

### <a name="return-value"></a>戻り値

文字列が同一の場合は0、 *str1* が *str2* 未満の場合は 0 <、 *str1* が *str2* より大きい場合は0を > ます。 この比較を実行するには、 [CStringT:: Compare](../../atl-mfc-shared/reference/cstringt-class.md#compare) メソッドを使用します。

### <a name="remarks"></a>解説

比較では大文字と小文字が区別されません。

## <a name="cstringelementtraitsihash"></a><a name="hash"></a> CStringElementTraitsI:: Hash

指定された文字列要素のハッシュ値を計算するには、この静的関数を呼び出します。

```
static ULONG Hash(INARGTYPE str) throw();
```

### <a name="parameters"></a>パラメーター

*str*<br/>
文字列要素。

### <a name="return-value"></a>戻り値

文字列の内容を使用して計算されたハッシュ値を返します。

## <a name="cstringelementtraitsiinargtype"></a><a name="inargtype"></a> CStringElementTraitsI:: INARGTYPE

コレクションクラスオブジェクトに要素を追加するために使用するデータ型。

```
typedef T::PCXSTR INARGTYPE;
```

## <a name="cstringelementtraitsioutargtype"></a><a name="outargtype"></a> CStringElementTraitsI:: OUTARGTYPE

コレクションクラスオブジェクトから要素を取得するために使用するデータ型。

```
typedef T& OUTARGTYPE;
```

## <a name="see-also"></a>関連項目

[CElementTraitsBase クラス](../../atl/reference/celementtraitsbase-class.md)<br/>
[クラスの概要](../../atl/atl-class-overview.md)<br/>
[CStringElementTraits クラス](../../atl/reference/cstringelementtraits-class.md)

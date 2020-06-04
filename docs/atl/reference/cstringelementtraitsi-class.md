---
title: クラス
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
ms.openlocfilehash: 32980e19443cb17a3a688c85ff21195c60ed2124
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81330598"
---
# <a name="cstringelementtraitsi-class"></a>クラス

このクラスは、コレクション クラス オブジェクトに格納されている文字列に関連する静的関数を提供します。 これは[CStringElementTraits](../../atl/reference/cstringelementtraits-class.md)に似ていますが、大文字と小文字を区別しない比較を実行します。

## <a name="syntax"></a>構文

```
template <typename T, class CharTraits = CDefaultCharTraits<T ::XCHAR>>
class CStringElementTraitsI : public CElementTraitsBase<T>
```

#### <a name="parameters"></a>パラメーター

*T*<br/>
コレクションに格納されるデータの型。

## <a name="members"></a>メンバー

### <a name="public-typedefs"></a>パブリック typedef

|名前|説明|
|----------|-----------------|
|[を切り分けて、次の要素を使用します。](#inargtype)|コレクション クラス オブジェクトに要素を追加するために使用するデータ型。|
|[を返します。](#outargtype)|コレクション クラス オブジェクトから要素を取得するために使用するデータ型。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[要素を比較します。](#compareelements)|大文字と小文字の違いを無視して、2 つの文字列要素を比較して等しいかどうかを比較します。|
|[並べ替え要素](#compareelementsordered)|この静的関数を呼び出して、大文字と小文字の違いを無視して 2 つの文字列要素を比較します。|
|[を見る](#hash)|指定した文字列要素のハッシュ値を計算します。|

## <a name="remarks"></a>解説

このクラスは、文字列を比較したり、ハッシュ値を作成したりするための静的関数を提供します。 これらの関数は、コレクション クラスを使用して文字列ベースのデータを格納する場合に便利です。 文字列オブジェクトが参照として扱われる場合は[、CStringRefElementTraits](../../atl/reference/cstringrefelementtraits-class.md)を使用します。

詳細については、「 [ATL コレクション クラス](../../atl/atl-collection-classes.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[Cエレメントトレイツベース](../../atl/reference/celementtraitsbase-class.md)

`CStringElementTraitsI`

## <a name="requirements"></a>必要条件

**ヘッダー:** atlcoll.h

## <a name="cstringelementtraitsicompareelements"></a><a name="compareelements"></a>要素を比較します。

大文字と小文字の違いを無視して、2 つの文字列要素を比較して等しいかどうかを比較します。

```
static bool CompareElements(INARGTYPE str1, INARGTYPE str2) throw();
```

### <a name="parameters"></a>パラメーター

*str1*<br/>
最初の文字列要素。

*str2*<br/>
2 番目の文字列要素。

### <a name="return-value"></a>戻り値

要素が等しい場合は true、そうでない場合は false を返します。

### <a name="remarks"></a>解説

比較では、大文字と小文字が区別されません。

## <a name="cstringelementtraitsicompareelementsordered"></a><a name="compareelementsordered"></a>並べ替え要素

この静的関数を呼び出して、大文字と小文字の違いを無視して 2 つの文字列要素を比較します。

```
static int CompareElementsOrdered(INARGTYPE str1, INARGTYPE str2) throw();
```

### <a name="parameters"></a>パラメーター

*str1*<br/>
最初の文字列要素。

*str2*<br/>
2 番目の文字列要素。

### <a name="return-value"></a>戻り値

文字列が同じ場合は*0、str1*が*str2*より小さい場合は < *0、str1*が*str2*より大きい場合は 0 を>。 比較を実行するには[、CStringT::Compare](../../atl-mfc-shared/reference/cstringt-class.md#compare)メソッドを使用します。

### <a name="remarks"></a>解説

比較では、大文字と小文字が区別されません。

## <a name="cstringelementtraitsihash"></a><a name="hash"></a>を見る

指定した文字列要素のハッシュ値を計算します。

```
static ULONG Hash(INARGTYPE str) throw();
```

### <a name="parameters"></a>パラメーター

*Str*<br/>
文字列要素。

### <a name="return-value"></a>戻り値

文字列の内容を使用して計算されたハッシュ値を返します。

## <a name="cstringelementtraitsiinargtype"></a><a name="inargtype"></a>を切り分けて、次の要素を使用します。

コレクション クラス オブジェクトに要素を追加するために使用するデータ型。

```
typedef T::PCXSTR INARGTYPE;
```

## <a name="cstringelementtraitsioutargtype"></a><a name="outargtype"></a>を返します。

コレクション クラス オブジェクトから要素を取得するために使用するデータ型。

```
typedef T& OUTARGTYPE;
```

## <a name="see-also"></a>関連項目

[クラス](../../atl/reference/celementtraitsbase-class.md)<br/>
[クラスの概要](../../atl/atl-class-overview.md)<br/>
[クラス](../../atl/reference/cstringelementtraits-class.md)

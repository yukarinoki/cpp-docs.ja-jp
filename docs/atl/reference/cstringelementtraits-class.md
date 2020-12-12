---
description: '詳細情報: CStringElementTraits クラス'
title: CStringElementTraits クラス
ms.date: 11/04/2016
f1_keywords:
- CStringElementTraits
- CSTRINGT/ATL::CStringElementTraits
- CSTRINGT/ATL::CStringElementTraits::INARGTYPE
- CSTRINGT/ATL::CStringElementTraits::OUTARGTYPE
- CSTRINGT/ATL::CStringElementTraits::CompareElements
- CSTRINGT/ATL::CStringElementTraits::CompareElementsOrdered
- CSTRINGT/ATL::CStringElementTraits::CopyElements
- CSTRINGT/ATL::CStringElementTraits::Hash
- CSTRINGT/ATL::CStringElementTraits::RelocateElements
helpviewer_keywords:
- CStringElementTraits class
ms.assetid: 74d7134b-099d-4455-bf91-3e68ccbf95bc
ms.openlocfilehash: 1e3f6a73e71530250d9dd88408165471028a18e9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97140492"
---
# <a name="cstringelementtraits-class"></a>CStringElementTraits クラス

このクラスは、オブジェクトを格納するコレクションクラスによって使用される静的関数を提供 `CString` します。

## <a name="syntax"></a>構文

```
template <typename T>
class CStringElementTraits
```

#### <a name="parameters"></a>パラメーター

*T*<br/>
コレクションに格納するデータの型。

## <a name="members"></a>メンバー

### <a name="public-typedefs"></a>パブリック typedef

|名前|説明|
|----------|-----------------|
|[CStringElementTraits:: INARGTYPE](#inargtype)|コレクションクラスオブジェクトに要素を追加するために使用するデータ型。|
|[CStringElementTraits:: OUTARGTYPE](#outargtype)|コレクションクラスオブジェクトから要素を取得するために使用するデータ型。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CStringElementTraits:: CompareElements](#compareelements)|雑音2つの文字列要素が等しいかどうかを比較するには、この関数を呼び出します。|
|[CStringElementTraits:: CompareElementsOrdered](#compareelementsordered)|雑音2つの文字列要素を比較するには、この関数を呼び出します。|
|[CStringElementTraits:: CopyElements](#copyelements)|雑音 `CString` コレクションクラスオブジェクトに格納されている要素をコピーするには、この関数を呼び出します。|
|[CStringElementTraits:: Hash](#hash)|雑音指定された文字列要素のハッシュ値を計算するには、この関数を呼び出します。|
|[CStringElementTraits:: RelocateElements](#relocateelements)|雑音 `CString` コレクションクラスオブジェクトに格納されている要素を再配置するには、この関数を呼び出します。|

## <a name="remarks"></a>解説

このクラスには、文字列のコピー、移動、比較、およびハッシュ値の作成を行うための静的関数が用意されています。 これらの関数は、コレクションクラスを使用して文字列ベースのデータを格納する場合に便利です。 大文字と小文字を区別しない比較が必要な場合は、 [CStringElementTraitsI](../../atl/reference/cstringelementtraitsi-class.md) を使用します。 文字列オブジェクトを参照として扱う場合は、 [Cstringrefelementtraits](../../atl/reference/cstringrefelementtraits-class.md) を使用します。

詳細については、「 [ATL コレクションクラス](../../atl/atl-collection-classes.md)」を参照してください。

## <a name="requirements"></a>要件

**ヘッダー:** cstringt

## <a name="cstringelementtraitscompareelements"></a><a name="compareelements"></a> CStringElementTraits:: CompareElements

2つの文字列要素が等しいかどうかを比較するには、この静的関数を呼び出します。

```
static bool CompareElements(INARGTYPE str1, INARGTYPE str2);
```

### <a name="parameters"></a>パラメーター

*str1*<br/>
最初の文字列要素。

*str2*<br/>
2番目の文字列要素。

### <a name="return-value"></a>戻り値

要素が等しい場合は true、それ以外の場合は false を返します。

## <a name="cstringelementtraitscompareelementsordered"></a><a name="compareelementsordered"></a> CStringElementTraits:: CompareElementsOrdered

2つの文字列要素を比較するには、この静的関数を呼び出します。

```
static int CompareElementsOrdered(INARGTYPE str1, INARGTYPE str2);
```

### <a name="parameters"></a>パラメーター

*str1*<br/>
最初の文字列要素。

*str2*<br/>
2番目の文字列要素。

### <a name="return-value"></a>戻り値

文字列が同一の場合は0、 *str1* が *str2* 未満の場合は 0 <、 *str1* が *str2* より大きい場合は0を > ます。 この比較を実行するには、 [CStringT:: Compare](../../atl-mfc-shared/reference/cstringt-class.md#compare) メソッドを使用します。

## <a name="cstringelementtraitscopyelements"></a><a name="copyelements"></a> CStringElementTraits:: CopyElements

`CString`コレクションクラスオブジェクトに格納されている要素をコピーするには、この静的関数を呼び出します。

```
static void CopyElements(
    T* pDest,
    const T* pSrc,
    size_t nElements);
```

### <a name="parameters"></a>パラメーター

*pDest*<br/>
コピーされたデータを受け取る最初の要素へのポインター。

*.Psrc*<br/>
コピーする最初の要素へのポインター。

*nElements*<br/>
コピーする要素の数。

### <a name="remarks"></a>解説

コピー元とコピー先の要素を重複させることはできません。

## <a name="cstringelementtraitshash"></a><a name="hash"></a> CStringElementTraits:: Hash

指定された文字列要素のハッシュ値を計算するには、この静的関数を呼び出します。

```
static ULONG Hash(INARGTYPE str);
```

### <a name="parameters"></a>パラメーター

*str*<br/>
文字列要素。

### <a name="return-value"></a>戻り値

文字列の内容を使用して計算されたハッシュ値を返します。

## <a name="cstringelementtraitsinargtype"></a><a name="inargtype"></a> CStringElementTraits:: INARGTYPE

コレクションクラスオブジェクトに要素を追加するために使用するデータ型。

```
typedef T::PCXSTR INARGTYPE;
```

## <a name="cstringelementtraitsoutargtype"></a><a name="outargtype"></a> CStringElementTraits:: OUTARGTYPE

コレクションクラスオブジェクトから要素を取得するために使用するデータ型。

```
typedef T& OUTARGTYPE;
```

## <a name="cstringelementtraitsrelocateelements"></a><a name="relocateelements"></a> CStringElementTraits:: RelocateElements

`CString`コレクションクラスオブジェクトに格納されている要素を再配置するには、この静的関数を呼び出します。

```
static void RelocateElements(
    T* pDest,
    T* pSrc,
    size_t nElements);
```

### <a name="parameters"></a>パラメーター

*pDest*<br/>
再配置されたデータを受け取る最初の要素へのポインター。

*.Psrc*<br/>
再配置する最初の要素へのポインター。

*nElements*<br/>
再配置する要素の数。

### <a name="remarks"></a>解説

この静的関数は、ほとんどのデータ型に対して十分な [memmove](../../c-runtime-library/reference/memmove-wmemmove.md)を呼び出します。 移動するオブジェクトに独自のメンバーへのポインターが含まれている場合は、この静的関数をオーバーライドする必要があります。

## <a name="see-also"></a>関連項目

[CElementTraitsBase クラス](../../atl/reference/celementtraitsbase-class.md)<br/>
[CStringElementTraitsI クラス](../../atl/reference/cstringelementtraitsi-class.md)<br/>
[クラスの概要](../../atl/atl-class-overview.md)

---
title: クラス
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
ms.openlocfilehash: 078cfd5ff93bfcd8acc747904ea05e6a2e762bc1
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81330620"
---
# <a name="cstringelementtraits-class"></a>クラス

このクラスは、オブジェクトを格納するコレクション`CString`クラスで使用される静的関数を提供します。

## <a name="syntax"></a>構文

```
template <typename T>
class CStringElementTraits
```

#### <a name="parameters"></a>パラメーター

*T*<br/>
コレクションに格納されるデータの型。

## <a name="members"></a>メンバー

### <a name="public-typedefs"></a>パブリック typedef

|名前|説明|
|----------|-----------------|
|[要素トレイト::イナルグタイプ](#inargtype)|コレクション クラス オブジェクトに要素を追加するために使用するデータ型。|
|[要素トレイト::アウトアルプタイプ](#outargtype)|コレクション クラス オブジェクトから要素を取得するために使用するデータ型。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[要素の比較](#compareelements)|(静的)2 つの文字列要素が等しいかどうかを比較します。|
|[並べ替え要素数::比較要素順序](#compareelementsordered)|(静的)2 つの文字列要素を比較します。|
|[要素のコピー::要素のコピー](#copyelements)|(静的)コレクション クラス オブジェクト`CString`に格納されている要素をコピーします。|
|[を見る要素::ハッシュ](#hash)|(静的)指定した文字列要素のハッシュ値を計算します。|
|[要素の再配置](#relocateelements)|(静的)コレクション クラス オブジェクトに`CString`格納されている要素を再配置します。|

## <a name="remarks"></a>解説

このクラスは、文字列のコピー、移動、および比較、およびハッシュ値の作成のための静的関数を提供します。 これらの関数は、コレクション クラスを使用して文字列ベースのデータを格納する場合に便利です。 大文字と小文字を区別しない比較が必要な場合は[、CStringElementTraitsI](../../atl/reference/cstringelementtraitsi-class.md)を使用します。 文字列オブジェクトを参照として扱う場合は[、CStringRefElementTraits](../../atl/reference/cstringrefelementtraits-class.md)を使用します。

詳細については、「 [ATL コレクション クラス](../../atl/atl-collection-classes.md)」を参照してください。

## <a name="requirements"></a>必要条件

**ヘッダー:** cstringt.h

## <a name="cstringelementtraitscompareelements"></a><a name="compareelements"></a>要素の比較

2 つの文字列要素が等しいかどうかを比較するには、この静的関数を呼び出します。

```
static bool CompareElements(INARGTYPE str1, INARGTYPE str2);
```

### <a name="parameters"></a>パラメーター

*str1*<br/>
最初の文字列要素。

*str2*<br/>
2 番目の文字列要素。

### <a name="return-value"></a>戻り値

要素が等しい場合は true、そうでない場合は false を返します。

## <a name="cstringelementtraitscompareelementsordered"></a><a name="compareelementsordered"></a>並べ替え要素数::比較要素順序

2 つの文字列要素を比較するには、この静的関数を呼び出します。

```
static int CompareElementsOrdered(INARGTYPE str1, INARGTYPE str2);
```

### <a name="parameters"></a>パラメーター

*str1*<br/>
最初の文字列要素。

*str2*<br/>
2 番目の文字列要素。

### <a name="return-value"></a>戻り値

文字列が同じ場合は*0、str1*が*str2*より小さい場合は < *0、str1*が*str2*より大きい場合は 0 を>。 比較を実行するには[、CStringT::Compare](../../atl-mfc-shared/reference/cstringt-class.md#compare)メソッドを使用します。

## <a name="cstringelementtraitscopyelements"></a><a name="copyelements"></a>要素のコピー::要素のコピー

コレクション クラス オブジェクトに`CString`格納されている要素をコピーするには、この静的関数を呼び出します。

```
static void CopyElements(
    T* pDest,
    const T* pSrc,
    size_t nElements);
```

### <a name="parameters"></a>パラメーター

*pDest*<br/>
コピーされたデータを受け取る最初の要素へのポインター。

*pSrc*<br/>
コピーする最初の要素へのポインター。

*n要素*<br/>
コピーする要素の数。

### <a name="remarks"></a>解説

ソース要素とコピー先要素は重複しないようにします。

## <a name="cstringelementtraitshash"></a><a name="hash"></a>を見る要素::ハッシュ

指定した文字列要素のハッシュ値を計算します。

```
static ULONG Hash(INARGTYPE str);
```

### <a name="parameters"></a>パラメーター

*Str*<br/>
文字列要素。

### <a name="return-value"></a>戻り値

文字列の内容を使用して計算されたハッシュ値を返します。

## <a name="cstringelementtraitsinargtype"></a><a name="inargtype"></a>要素トレイト::イナルグタイプ

コレクション クラス オブジェクトに要素を追加するために使用するデータ型。

```
typedef T::PCXSTR INARGTYPE;
```

## <a name="cstringelementtraitsoutargtype"></a><a name="outargtype"></a>要素トレイト::アウトアルプタイプ

コレクション クラス オブジェクトから要素を取得するために使用するデータ型。

```
typedef T& OUTARGTYPE;
```

## <a name="cstringelementtraitsrelocateelements"></a><a name="relocateelements"></a>要素の再配置

コレクション クラス オブジェクトに格納`CString`されている要素を再配置するには、この静的関数を呼び出します。

```
static void RelocateElements(
    T* pDest,
    T* pSrc,
    size_t nElements);
```

### <a name="parameters"></a>パラメーター

*pDest*<br/>
再配置されたデータを受け取る最初の要素へのポインター。

*pSrc*<br/>
再配置する最初の要素へのポインター。

*n要素*<br/>
再配置する要素の数。

### <a name="remarks"></a>解説

この静的関数は、ほとんどのデータ型に対して十分な[memmove](../../c-runtime-library/reference/memmove-wmemmove.md)を呼び出します。 移動するオブジェクトに自身のメンバーへのポインターが含まれている場合、この静的関数をオーバーライドする必要があります。

## <a name="see-also"></a>関連項目

[クラス](../../atl/reference/celementtraitsbase-class.md)<br/>
[クラス](../../atl/reference/cstringelementtraitsi-class.md)<br/>
[クラスの概要](../../atl/atl-class-overview.md)

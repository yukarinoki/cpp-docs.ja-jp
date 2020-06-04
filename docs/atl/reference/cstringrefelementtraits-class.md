---
title: クラス
ms.date: 11/04/2016
f1_keywords:
- CStringRefElementTraits
- ATLCOLL/ATL::CStringRefElementTraits
- ATLCOLL/ATL::CStringRefElementTraits::CompareElements
- ATLCOLL/ATL::CStringRefElementTraits::CompareElementsOrdered
- ATLCOLL/ATL::CStringRefElementTraits::Hash
helpviewer_keywords:
- CStringRefElementTraits class
ms.assetid: cc15062d-5627-46cc-ac2b-1744afdc2dbd
ms.openlocfilehash: b4dd76b9592b255a1553be3ca7a249f58fb2672e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81330577"
---
# <a name="cstringrefelementtraits-class"></a>クラス

このクラスは、コレクション クラス オブジェクトに格納されている文字列に関連する静的関数を提供します。 文字列オブジェクトは参照として扱われます。

## <a name="syntax"></a>構文

```
template <typename T>
class CStringRefElementTraits : public CElementTraitsBase<T>
```

#### <a name="parameters"></a>パラメーター

*T*<br/>
コレクションに格納されるデータの型。

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[要素の比較](#compareelements)|2 つの文字列要素が等しいかどうかを比較するには、この静的関数を呼び出します。|
|[並べ替え要素数::比較要素](#compareelementsordered)|2 つの文字列要素を比較するには、この静的関数を呼び出します。|
|[を見る要素::ハッシュ](#hash)|指定した文字列要素のハッシュ値を計算します。|

## <a name="remarks"></a>解説

このクラスは、文字列を比較したり、ハッシュ値を作成したりするための静的関数を提供します。 これらの関数は、コレクション クラスを使用して文字列ベースのデータを格納する場合に便利です。 [CStringElementTraits および](../../atl/reference/cstringelementtraits-class.md) [CStringElementTraitsI](../../atl/reference/cstringelementtraitsi-class.md)とは異なり、`CStringRefElementTraits`引数は`CString`**定数**`CString&`参照として渡されます。

詳細については、「 [ATL コレクション クラス](../../atl/atl-collection-classes.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[Cエレメントトレイツベース](../../atl/reference/celementtraitsbase-class.md)

`CStringRefElementTraits`

## <a name="requirements"></a>必要条件

**ヘッダー:** atlcoll.h

## <a name="cstringrefelementtraitscompareelements"></a><a name="compareelements"></a>要素の比較

2 つの文字列要素が等しいかどうかを比較するには、この静的関数を呼び出します。

```
static bool CompareElements(INARGTYPE element1, INARGTYPE element2) throw();
```

### <a name="parameters"></a>パラメーター

*要素1*<br/>
最初の文字列要素。

*要素2*<br/>
2 番目の文字列要素。

### <a name="return-value"></a>戻り値

要素が等しい場合は true、そうでない場合は false を返します。

## <a name="cstringrefelementtraitscompareelementsordered"></a><a name="compareelementsordered"></a>並べ替え要素数::比較要素

2 つの文字列要素を比較するには、この静的関数を呼び出します。

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

## <a name="cstringrefelementtraitshash"></a><a name="hash"></a>を見る要素::ハッシュ

指定した文字列要素のハッシュ値を計算します。

```
static ULONG Hash(INARGTYPE str) throw();
```

### <a name="parameters"></a>パラメーター

*Str*<br/>
文字列要素。

### <a name="return-value"></a>戻り値

文字列の内容を使用して計算されたハッシュ値を返します。

## <a name="see-also"></a>関連項目

[クラス](../../atl/reference/celementtraitsbase-class.md)<br/>
[クラスの概要](../../atl/atl-class-overview.md)

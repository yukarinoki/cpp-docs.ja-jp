---
description: '詳細情報: CStringRefElementTraits クラス'
title: CStringRefElementTraits クラス
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
ms.openlocfilehash: 5523a2a451fc1825c443cf2d2e518b1c8dc2b340
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97140388"
---
# <a name="cstringrefelementtraits-class"></a>CStringRefElementTraits クラス

このクラスは、コレクションクラスオブジェクトに格納されている文字列に関連する静的関数を提供します。 文字列オブジェクトは参照として処理されます。

## <a name="syntax"></a>構文

```
template <typename T>
class CStringRefElementTraits : public CElementTraitsBase<T>
```

#### <a name="parameters"></a>パラメーター

*T*<br/>
コレクションに格納するデータの型。

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CStringRefElementTraits:: CompareElements](#compareelements)|2つの文字列要素が等しいかどうかを比較するには、この静的関数を呼び出します。|
|[CStringRefElementTraits:: CompareElementsOrdered](#compareelementsordered)|2つの文字列要素を比較するには、この静的関数を呼び出します。|
|[CStringRefElementTraits:: Hash](#hash)|指定された文字列要素のハッシュ値を計算するには、この静的関数を呼び出します。|

## <a name="remarks"></a>解説

このクラスは、文字列を比較し、ハッシュ値を作成するための静的関数を提供します。 これらの関数は、コレクションクラスを使用して文字列ベースのデータを格納する場合に便利です。 [Cstringelementtraits](../../atl/reference/cstringelementtraits-class.md)および [CStringElementTraitsI](../../atl/reference/cstringelementtraitsi-class.md)とは異なり、 `CStringRefElementTraits` `CString` 引数は参照として渡され **`const`** `CString&` ます。

詳細については、「 [ATL コレクションクラス](../../atl/atl-collection-classes.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CElementTraitsBase](../../atl/reference/celementtraitsbase-class.md)

`CStringRefElementTraits`

## <a name="requirements"></a>要件

**ヘッダー:** atlcoll. h

## <a name="cstringrefelementtraitscompareelements"></a><a name="compareelements"></a> CStringRefElementTraits:: CompareElements

2つの文字列要素が等しいかどうかを比較するには、この静的関数を呼び出します。

```
static bool CompareElements(INARGTYPE element1, INARGTYPE element2) throw();
```

### <a name="parameters"></a>パラメーター

*element1*<br/>
最初の文字列要素。

*element2*<br/>
2番目の文字列要素。

### <a name="return-value"></a>戻り値

要素が等しい場合は true、それ以外の場合は false を返します。

## <a name="cstringrefelementtraitscompareelementsordered"></a><a name="compareelementsordered"></a> CStringRefElementTraits:: CompareElementsOrdered

2つの文字列要素を比較するには、この静的関数を呼び出します。

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

## <a name="cstringrefelementtraitshash"></a><a name="hash"></a> CStringRefElementTraits:: Hash

指定された文字列要素のハッシュ値を計算するには、この静的関数を呼び出します。

```
static ULONG Hash(INARGTYPE str) throw();
```

### <a name="parameters"></a>パラメーター

*str*<br/>
文字列要素。

### <a name="return-value"></a>戻り値

文字列の内容を使用して計算されたハッシュ値を返します。

## <a name="see-also"></a>関連項目

[CElementTraitsBase クラス](../../atl/reference/celementtraitsbase-class.md)<br/>
[クラスの概要](../../atl/atl-class-overview.md)

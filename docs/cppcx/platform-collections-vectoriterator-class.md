---
title: Platform::Collections::VectorIterator クラス
ms.date: 03/27/2019
ms.topic: reference
f1_keywords:
- COLLECTION/Platform::Collections::VectorIterator::VectorIterator
helpviewer_keywords:
- VectorIterator Class
ms.assetid: d531cb42-27e0-48a6-bf5e-c265891a18ff
ms.openlocfilehash: e649027c2ba3f637c42765af691f4d321913fb28
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81354368"
---
# <a name="platformcollectionsvectoriterator-class"></a>Platform::Collections::VectorIterator クラス

Windows ランタイム IVector インターフェイスから派生したオブジェクトの標準テンプレート ライブラリ反復器を提供します。

ベクターイテレータは、型 VectorProxy\<T>の要素を格納するプロキシ反復子です。 ただし、プロキシ オブジェクトは、ユーザー コードにはほとんどは表示されません。 詳細については、「 [Collections (C++/CX) (コレクション (C++/CX))](../cppcx/collections-c-cx.md)」を参照してください。

## <a name="syntax"></a>構文

```
template <typename T>
class VectorIterator;
```

#### <a name="parameters"></a>パラメーター

*T*<br/>
VectorIterator テンプレート クラスの型名。

### <a name="members"></a>メンバー

### <a name="public-typedefs"></a>パブリック typedef

|名前|説明|
|----------|-----------------|
|`difference_type`|ポインターの相違点 (ptrdiff_t)。|
|`iterator_category`|ランダム アクセス反復子 (::std::random_access_iterator_tag) のカテゴリ。|
|`pointer`|VectorIterator の実装に必要な内部型へのポインター、 プラットフォーム:コレクション::Details::VectorProxy\<T>。|
|`reference`|VectorIterator の実装に必要な内部型への参照、 プラットフォーム:コレクション::D:VectorProxy\<T>、。|
|`value_type`|`T` 型名。|

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[ベクトル反復器::ベクトル反復器](#ctor)|VectorIterator クラスの新しいインスタンスを初期化します。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[ベクトル反復器::演算子 - 演算子](#operator-minus)|現在の反復子から指定した数の要素を減算して新しい反復子を生成するか、現在の反復子から指定した反復子を減算して反復子間の要素数を生成します。|
|[ベクトル反復器::演算子 -- 演算子](#operator-decrement)|現在の VectorIterator をデクリメントします。|
|[ベクトル反復器::演算子!= 演算子](#operator-inequality)|現在の VectorIterator が、指定された VectorIterator と等しくないかどうかを示します。|
|[ベクトル反復器::演算子* 演算子](#operator-dereference)|現在の VectorIterator により指定された要素への参照を取得します。|
|[ベクトル反復器::演算子\[\]](#operator-at)|現在の VectorIterator から指定された転置にある要素への参照を取得します。|
|[ベクトル反復器::演算子+ 演算子](#operator-plus)|指定された VectorIterator から指定された転置にある要素を参照する VectorIterator を返します。|
|[ベクトル反復器::演算子++ 演算子](#operator-increment)|現在の VectorIterator をインクリメントします。|
|[ベクトル反復器::演算子+=演算子](#operator-plus-assign)|指定されたディスプレイスメントだけ現在の VectorIterator をインクリメントします。|
|[ベクトル反復器::演算子<演算子](#operator-less-than)|現在の VectorIterator が、指定された VectorIterator より小さいかどうかを示します。|
|[ベクトル反復器::演算子\<= 演算子](#operator-less-than-or-equals)|現在の VectorIterator が、指定された VectorIterator 以下かどうかを示します。|
|[ベクトル反復器::演算子- = 演算子](#operator-minus-equals)|指定されたディスプレイスメントだけ現在の VectorIterator をデクリメントします。|
|[ベクトル反復器::演算子==演算子](#operator-equality)|現在の VectorIterator が、指定された VectorIterator と等しいかどうかを示します。|
|[VectorIterator::operator> 演算子](#operator-greater-than)|現在の VectorIterator が、指定された VectorIterator より大きいかどうかを示します。|
|[ベクトル反復器::演算子>演算子](#operator-arrow)|現在の VectorIterator により参照される要素のアドレスを取得します。|
|[ベクトル反復器::演算子>= 演算子](#operator-greater-than-or-equals)|現在の VectorIterator が、指定された VectorIterator 以上であるかどうかを示します。|

## <a name="inheritance-hierarchy"></a>継承階層

`VectorIterator`

### <a name="requirements"></a>必要条件

**ヘッダー:** collection.h

**名前空間:** Platform::Collections

## <a name="vectoriteratoroperator-gt-operator"></a><a name="operator-arrow"></a>ベクトル反復器::演算子 -&gt;演算子

現在の VectorIterator により参照される要素のアドレスを取得します。

### <a name="syntax"></a>構文

```
Detail::ArrowProxy<T> operator->() const;
```

### <a name="return-value"></a>戻り値

現在の VectorIterator により参照される要素の値。

戻り値の型は、この演算子の実装に必要な、指定されていない内部型です。

## <a name="vectoriteratoroperator---operator"></a><a name="operator-decrement"></a>ベクトル反復器::演算子 -- 演算子

現在の VectorIterator をデクリメントします。

### <a name="syntax"></a>構文

```

VectorIterator& operator--();
VectorIterator operator--(int);
```

### <a name="return-value"></a>戻り値

最初の構文は、現在の VectorIterator をデクリメントしてから返します。 2 番目の構文は、現在の VectorIterator のコピーを返し、現在の VectorIterator をデクリメントします。

### <a name="remarks"></a>解説

最初の VectorIterator 構文は、現在の VectorIterator の前置デクリメントを実行します。

2 番目の構文は、現在の VectorIterator に後置デクリメントを実行します。 2 つ目の構文の `int` 型は、実際の整数オペランドではなく後置デクリメント演算を示します。

## <a name="vectoriteratoroperator-operator"></a><a name="operator-dereference"></a>ベクトル反復器::演算子\*

現在の VectorIterator により指定される要素のアドレスを取得します。

### <a name="syntax"></a>構文

```
reference operator*() const;
```

### <a name="return-value"></a>戻り値

現在の VectorIterator により指定される要素。

## <a name="vectoriteratoroperator-operator"></a><a name="operator-equality"></a>ベクトル反復器::演算子==演算子

現在の VectorIterator が、指定された VectorIterator と等しいかどうかを示します。

### <a name="syntax"></a>構文

```
bool operator==(const VectorIterator& other) const;
```

### <a name="parameters"></a>パラメーター

*他*<br/>
別の VectorIterator。

### <a name="return-value"></a>戻り値

現在の VectorIterator が*他*の値と等しい場合は**true。** それ以外の場合**は false。**

## <a name="vectoriteratoroperatorgt-operator"></a><a name="operator-greater-than"></a>ベクトル反復器::演算子&gt;

現在の VectorIterator が、指定された VectorIterator より大きいかどうかを示します。

### <a name="syntax"></a>構文

```cpp
bool operator>(const VectorIterator& other) const
```

### <a name="parameters"></a>パラメーター

*他*<br/>
別の VectorIterator。

### <a name="return-value"></a>戻り値

現在の VectorIterator が*他*のベクターよりも大きい場合は**true。** それ以外の場合**は false。**

## <a name="vectoriteratoroperatorgt-operator"></a><a name="operator-greater-than-or-equals"></a>ベクトル反復器::演算子&gt;= 演算子

現在の VectorIterator が、指定された VectorIterator 以上であるかどうかを示します。

### <a name="syntax"></a>構文

```cpp
bool operator>=(const VectorIterator& other) const
```

### <a name="parameters"></a>パラメーター

*他*<br/>
別の VectorIterator。

### <a name="return-value"></a>戻り値

現在の VectorIterator が*他*の値以上の場合は**true。** それ以外の場合**は false。**

## <a name="vectoriteratoroperator-operator"></a><a name="operator-increment"></a>ベクトル反復器::演算子++ 演算子

現在の VectorIterator をインクリメントします。

### <a name="syntax"></a>構文

```
VectorIterator& operator++();
VectorIterator operator++(int);
```

### <a name="return-value"></a>戻り値

最初の構文は、現在の VectorIterator をインクリメントしてから返します。 2 番目の構文は、現在の VectorIterator のコピーを返し、現在の VectorIterator をインクリメントします。

### <a name="remarks"></a>解説

最初の VectorIterator 構文は、現在の VectorIterator の前置インクリメントを実行します。

2 番目の構文は、現在の VectorIterator に後置インクリメントを実行します。 2 つ目の構文の `int` 型は、実際の整数オペランドではなく後置インクリメント演算を示します。

## <a name="vectoriteratoroperator-operator"></a><a name="operator-inequality"></a>ベクトル反復器::演算子!= 演算子

現在の VectorIterator が、指定された VectorIterator と等しくないかどうかを示します。

### <a name="syntax"></a>構文

```
bool operator!=(const VectorIterator& other) const;
```

### <a name="parameters"></a>パラメーター

*他*<br/>
別の VectorIterator。

### <a name="return-value"></a>戻り値

現在の VectorIterator が*他*の値と等しくない場合は**true。** それ以外の場合**は false。**

## <a name="vectoriteratoroperatorlt-operator"></a><a name="operator-less-than"></a>ベクトル反復器::演算子&lt;

現在の VectorIterator が、指定された VectorIterator より小さいかどうかを示します。

### <a name="syntax"></a>構文

```cpp
bool operator<(const VectorIterator& other) const
```

### <a name="parameters"></a>パラメーター

*他*<br/>
別の VectorIterator。

### <a name="return-value"></a>戻り値

現在の VectorIterator が*他*のベクトルよりも小さい場合は**true。** それ以外の場合**は false。**

## <a name="vectoriteratoroperatorlt-operator"></a><a name="operator-less-than-or-equals"></a>ベクトル反復器::演算子&lt;= 演算子

現在の VectorIterator が、指定された VectorIterator 以下かどうかを示します。

### <a name="syntax"></a>構文

```cpp
bool operator<=(const VectorIterator& other) const
```

### <a name="parameters"></a>パラメーター

*他*<br/>
別の VectorIterator。

### <a name="return-value"></a>戻り値

現在の VectorIterator が*他*の値以下の場合は**true。** それ以外の場合**は false。**

## <a name="vectoriteratoroperator--operator"></a><a name="operator-minus"></a>ベクトル反復器::演算子 - 演算子

現在の反復子から指定した数の要素を減算して新しい反復子を生成するか、現在の反復子から指定した反復子を減算して反復子間の要素数を生成します。

### <a name="syntax"></a>構文

```

VectorIterator operator-(difference_type n) const;

difference_type operator-(const VectorIterator& other) const;
```

### <a name="parameters"></a>パラメーター

*n*<br/>
要素の数。

*他*<br/>
別の VectorIterator。

### <a name="return-value"></a>戻り値

最初の演算子構文は、現在の VectorIterator より `n` 要素少ない VectorIterator オブジェクトを返します。 2 番目の演算子構文は、現在の VectorIterator と `other` VectorIterator の間の要素の数を返します。

## <a name="vectoriteratoroperator-operator"></a><a name="operator-plus-assign"></a>ベクトル反復器::演算子+=演算子

指定されたディスプレイスメントだけ現在の VectorIterator をインクリメントします。

### <a name="syntax"></a>構文

```
VectorIterator& operator+=(difference_type n);
```

### <a name="parameters"></a>パラメーター

*n*<br/>
整数の転置。

### <a name="return-value"></a>戻り値

更新された VectorIterator。

## <a name="vectoriteratoroperator-operator"></a><a name="operator-plus"></a>ベクトル反復器::演算子+ 演算子

指定された VectorIterator から指定された転置にある要素を参照する VectorIterator を返します。

### <a name="syntax"></a>構文

```

VectorIterator operator+(difference_type n);

template <typename T>
inline VectorIterator<T> operator+(
  ptrdiff_t n,
  const VectorIterator<T>& i);
```

### <a name="parameters"></a>パラメーター

*T*<br/>
2 番目の構文では、VectorIterator の型名。

*n*<br/>
整数のディスプレイスメント。

*私*<br/>
2 番目の構文では、VectorIterator。

### <a name="return-value"></a>戻り値

最初の構文では、現在の VectorIterator から指定された転置にある要素を参照する VectorIterator。

2 番目の構文では、`i` パラメーターの先頭から指定された転置にある要素を参照する VectorIterator。

### <a name="remarks"></a>解説

最初の構文例

## <a name="vectoriteratoroperator--operator"></a><a name="operator-minus-equals"></a>ベクトル反復器::演算子- = 演算子

指定されたディスプレイスメントだけ現在の VectorIterator をデクリメントします。

### <a name="syntax"></a>構文

```
VectorIterator& operator-=(difference_type n);
```

### <a name="parameters"></a>パラメーター

*n*<br/>
整数のディスプレイスメント。

### <a name="return-value"></a>戻り値

更新された VectorIterator。

## <a name="vectoriteratoroperator"></a><a name="operator-at"></a>ベクトル反復器::演算子\[\]

現在の VectorIterator から指定された転置にある要素への参照を取得します。

### <a name="syntax"></a>構文

```
reference operator[](difference_type n) const;
```

### <a name="parameters"></a>パラメーター

*n*<br/>
整数のディスプレイスメント。

### <a name="return-value"></a>戻り値

現在の VectorIterator からの `n` 個の要素によって転置される要素。

## <a name="vectoriteratorvectoriterator-constructor"></a><a name="ctor"></a>ベクトル反復器::ベクトル反復器コンストラクタ

VectorIterator クラスの新しいインスタンスを初期化します。

### <a name="syntax"></a>構文

```
VectorIterator();

explicit VectorIterator(
   Windows::Foundation::Collections::IVector<T>^ v);
```

### <a name="parameters"></a>パラメーター

*V*<br/>
IVector\<T>オブジェクト。

### <a name="remarks"></a>解説

最初の構文例は既定のコンストラクターです。 2 番目の構文例は、IVector\<T> オブジェクトから VectorIterator を構築するために使用される明示的なコンストラクターです。

## <a name="see-also"></a>関連項目

[プラットフォーム名前空間](platform-namespace-c-cx.md)

---
description: '詳細情報: Platform:: Collections:: VectorIterator クラス'
title: Platform::Collections::VectorIterator クラス
ms.date: 03/27/2019
ms.topic: reference
f1_keywords:
- COLLECTION/Platform::Collections::VectorIterator::VectorIterator
helpviewer_keywords:
- VectorIterator Class
ms.assetid: d531cb42-27e0-48a6-bf5e-c265891a18ff
ms.openlocfilehash: ad572a8b426092fb0ddb39db44f387598674c988
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97253911"
---
# <a name="platformcollectionsvectoriterator-class"></a>Platform::Collections::VectorIterator クラス

Windows ランタイム IVector インターフェイスから派生したオブジェクトの標準テンプレートライブラリ反復子を提供します。

VectorIterator は、VectorProxy 型の要素を格納するプロキシ反復子です \<T> 。 ただし、プロキシ オブジェクトは、ユーザー コードにはほとんどは表示されません。 詳細については、「 [Collections (C++/CX) (コレクション (C++/CX))](../cppcx/collections-c-cx.md)」を参照してください。

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
|`pointer`|\<T>VectorIterator の実装に必要な、Platform:: Collections::D etails:: VectorProxy の内部型へのポインター。|
|`reference`|\<T>VectorIterator の実装に必要な、Platform:: Collections::D etails:: VectorProxy の内部型への参照。|
|`value_type`|`T` 型名。|

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[VectorIterator:: VectorIterator](#ctor)|VectorIterator クラスの新しいインスタンスを初期化します。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[VectorIterator:: operator-演算子](#operator-minus)|現在の反復子から指定した数の要素を減算して新しい反復子を生成するか、現在の反復子から指定した反復子を減算して反復子間の要素数を生成します。|
|[VectorIterator:: operator--演算子](#operator-decrement)|現在の VectorIterator をデクリメントします。|
|[VectorIterator:: operator! = 演算子](#operator-inequality)|現在の VectorIterator が、指定された VectorIterator と等しくないかどうかを示します。|
|[VectorIterator:: operator * 演算子](#operator-dereference)|現在の VectorIterator により指定された要素への参照を取得します。|
|[VectorIterator:: operator\[\]](#operator-at)|現在の VectorIterator から指定された転置にある要素への参照を取得します。|
|[VectorIterator:: operator + 演算子](#operator-plus)|指定された VectorIterator から指定された転置にある要素を参照する VectorIterator を返します。|
|[VectorIterator:: operator + + 演算子](#operator-increment)|現在の VectorIterator をインクリメントします。|
|[VectorIterator:: operator + = 演算子](#operator-plus-assign)|指定されたディスプレイスメントだけ現在の VectorIterator をインクリメントします。|
|[VectorIterator:: operator< 演算子](#operator-less-than)|現在の VectorIterator が、指定された VectorIterator より小さいかどうかを示します。|
|[VectorIterator:: operator \< = 演算子](#operator-less-than-or-equals)|現在の VectorIterator が、指定された VectorIterator 以下かどうかを示します。|
|[VectorIterator:: operator-= 演算子](#operator-minus-equals)|指定されたディスプレイスメントだけ現在の VectorIterator をデクリメントします。|
|[VectorIterator:: operator = = 演算子](#operator-equality)|現在の VectorIterator が、指定された VectorIterator と等しいかどうかを示します。|
|[VectorIterator::operator> 演算子](#operator-greater-than)|現在の VectorIterator が、指定された VectorIterator より大きいかどうかを示します。|
|[VectorIterator:: operator-> 演算子](#operator-arrow)|現在の VectorIterator により参照される要素のアドレスを取得します。|
|[VectorIterator:: operator>= 演算子](#operator-greater-than-or-equals)|現在の VectorIterator が、指定された VectorIterator 以上であるかどうかを示します。|

## <a name="inheritance-hierarchy"></a>継承階層

`VectorIterator`

### <a name="requirements"></a>要件

**ヘッダー:** collection.h

**名前空間:** Platform::Collections

## <a name="vectoriteratoroperator-gt-operator"></a><a name="operator-arrow"></a> VectorIterator:: operator- &gt; 演算子

現在の VectorIterator により参照される要素のアドレスを取得します。

### <a name="syntax"></a>構文

```
Detail::ArrowProxy<T> operator->() const;
```

### <a name="return-value"></a>戻り値

現在の VectorIterator により参照される要素の値。

戻り値の型は、この演算子の実装に必要な、指定されていない内部型です。

## <a name="vectoriteratoroperator---operator"></a><a name="operator-decrement"></a> VectorIterator:: operator--演算子

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

2 番目の構文は、現在の VectorIterator に後置デクリメントを実行します。 **`int`** 2 番目の構文の型は、実際の整数オペランドではなく、デクリメント後の演算を示します。

## <a name="vectoriteratoroperator-operator"></a><a name="operator-dereference"></a> VectorIterator:: operator \* 演算子

現在の VectorIterator により指定される要素のアドレスを取得します。

### <a name="syntax"></a>構文

```
reference operator*() const;
```

### <a name="return-value"></a>戻り値

現在の VectorIterator により指定される要素。

## <a name="vectoriteratoroperator-operator"></a><a name="operator-equality"></a> VectorIterator:: operator = = 演算子

現在の VectorIterator が、指定された VectorIterator と等しいかどうかを示します。

### <a name="syntax"></a>構文

```
bool operator==(const VectorIterator& other) const;
```

### <a name="parameters"></a>パラメーター

*他の*<br/>
別の VectorIterator。

### <a name="return-value"></a>戻り値

**`true`** 現在の VectorIterator が *other* と等しい場合は。それ以外の場合は **`false`** 。

## <a name="vectoriteratoroperatorgt-operator"></a><a name="operator-greater-than"></a> VectorIterator:: operator &gt; 演算子

現在の VectorIterator が、指定された VectorIterator より大きいかどうかを示します。

### <a name="syntax"></a>構文

```cpp
bool operator>(const VectorIterator& other) const
```

### <a name="parameters"></a>パラメーター

*他の*<br/>
別の VectorIterator。

### <a name="return-value"></a>戻り値

**`true`** 現在の VectorIterator が *other* より大きい場合は。それ以外の場合は **`false`** 。

## <a name="vectoriteratoroperatorgt-operator"></a><a name="operator-greater-than-or-equals"></a> VectorIterator:: operator &gt; = 演算子

現在の VectorIterator が、指定された VectorIterator 以上であるかどうかを示します。

### <a name="syntax"></a>構文

```cpp
bool operator>=(const VectorIterator& other) const
```

### <a name="parameters"></a>パラメーター

*他の*<br/>
別の VectorIterator。

### <a name="return-value"></a>戻り値

**`true`** 現在の VectorIterator が *もう一方* の値以上の場合は。それ以外の場合は **`false`** 。

## <a name="vectoriteratoroperator-operator"></a><a name="operator-increment"></a> VectorIterator:: operator + + 演算子

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

2 番目の構文は、現在の VectorIterator に後置インクリメントを実行します。 **`int`** 2 番目の構文の型は、実際の整数オペランドではなく、後置インクリメント演算を示します。

## <a name="vectoriteratoroperator-operator"></a><a name="operator-inequality"></a> VectorIterator:: operator! = 演算子

現在の VectorIterator が、指定された VectorIterator と等しくないかどうかを示します。

### <a name="syntax"></a>構文

```
bool operator!=(const VectorIterator& other) const;
```

### <a name="parameters"></a>パラメーター

*他の*<br/>
別の VectorIterator。

### <a name="return-value"></a>戻り値

**`true`** 現在の VectorIterator が *other* と等しくない場合は。それ以外の場合は **`false`** 。

## <a name="vectoriteratoroperatorlt-operator"></a><a name="operator-less-than"></a> VectorIterator:: operator &lt; 演算子

現在の VectorIterator が、指定された VectorIterator より小さいかどうかを示します。

### <a name="syntax"></a>構文

```cpp
bool operator<(const VectorIterator& other) const
```

### <a name="parameters"></a>パラメーター

*他の*<br/>
別の VectorIterator。

### <a name="return-value"></a>戻り値

**`true`** 現在の VectorIterator が *other* より小さい場合は。それ以外の場合は **`false`** 。

## <a name="vectoriteratoroperatorlt-operator"></a><a name="operator-less-than-or-equals"></a> VectorIterator:: operator &lt; = 演算子

現在の VectorIterator が、指定された VectorIterator 以下かどうかを示します。

### <a name="syntax"></a>構文

```cpp
bool operator<=(const VectorIterator& other) const
```

### <a name="parameters"></a>パラメーター

*他の*<br/>
別の VectorIterator。

### <a name="return-value"></a>戻り値

**`true`** 現在の VectorIterator が *もう一方* の値以下である場合は。それ以外の場合は **`false`** 。

## <a name="vectoriteratoroperator--operator"></a><a name="operator-minus"></a> VectorIterator:: operator-演算子

現在の反復子から指定した数の要素を減算して新しい反復子を生成するか、現在の反復子から指定した反復子を減算して反復子間の要素数を生成します。

### <a name="syntax"></a>構文

```

VectorIterator operator-(difference_type n) const;

difference_type operator-(const VectorIterator& other) const;
```

### <a name="parameters"></a>パラメーター

*n*<br/>
要素の数。

*他の*<br/>
別の VectorIterator。

### <a name="return-value"></a>戻り値

最初の演算子構文は、現在の VectorIterator より `n` 要素少ない VectorIterator オブジェクトを返します。 2 番目の演算子構文は、現在の VectorIterator と `other` VectorIterator の間の要素の数を返します。

## <a name="vectoriteratoroperator-operator"></a><a name="operator-plus-assign"></a> VectorIterator:: operator + = 演算子

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

## <a name="vectoriteratoroperator-operator"></a><a name="operator-plus"></a> VectorIterator:: operator + 演算子

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

*i*<br/>
2 番目の構文では、VectorIterator。

### <a name="return-value"></a>戻り値

最初の構文では、現在の VectorIterator から指定された転置にある要素を参照する VectorIterator。

2 番目の構文では、`i` パラメーターの先頭から指定された転置にある要素を参照する VectorIterator。

### <a name="remarks"></a>解説

最初の構文例

## <a name="vectoriteratoroperator--operator"></a><a name="operator-minus-equals"></a> VectorIterator:: operator-= 演算子

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

## <a name="vectoriteratoroperator"></a><a name="operator-at"></a> VectorIterator:: operator\[\]

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

## <a name="vectoriteratorvectoriterator-constructor"></a><a name="ctor"></a> VectorIterator:: VectorIterator コンストラクター

VectorIterator クラスの新しいインスタンスを初期化します。

### <a name="syntax"></a>構文

```
VectorIterator();

explicit VectorIterator(
   Windows::Foundation::Collections::IVector<T>^ v);
```

### <a name="parameters"></a>パラメーター

*v*<br/>
IVector \<T> オブジェクト。

### <a name="remarks"></a>解説

最初の構文例は既定のコンストラクターです。 2番目の構文例は、IVector オブジェクトから VectorIterator を構築するために使用される明示的なコンストラクターです \<T> 。

## <a name="see-also"></a>関連項目

[Platform 名前空間](platform-namespace-c-cx.md)

---
title: Platform::Collections::VectorViewIterator クラス
ms.date: 03/27/2019
ms.topic: reference
f1_keywords:
- COLLECTION/Platform::Collections::VectorViewIterator::VectorViewIterator
helpviewer_keywords:
- VectorViewIterator Class
ms.assetid: be3aa1ae-e6ba-4a06-8d6b-86d8128026f7
ms.openlocfilehash: 01ae4286e996db9819cb697360f6de9c344edd21
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81363698"
---
# <a name="platformcollectionsvectorviewiterator-class"></a>Platform::Collections::VectorViewIterator クラス

Windows ランタイム`IVectorView`インターフェイスから派生したオブジェクトの標準テンプレート ライブラリ反復器を提供します。

`ViewVectorIterator` は、 `VectorProxy<T>`型の要素を格納するプロキシ反復子です。 ただし、プロキシ オブジェクトは、ユーザー コードにはほとんどは表示されません。 詳細については、「 [Collections (C++/CX) (コレクション (C++/CX))](../cppcx/collections-c-cx.md)」を参照してください。

## <a name="syntax"></a>構文

```
template <typename T>
class VectorViewIterator;
```

#### <a name="parameters"></a>パラメーター

*T*<br/>
VectorViewIterator テンプレート クラスの型名。

### <a name="members"></a>メンバー

### <a name="public-typedefs"></a>パブリック typedef

|名前|説明|
|----------|-----------------|
|`difference_type`|ポインターの相違点 (ptrdiff_t)。|
|`iterator_category`|ランダム アクセス反復子 (::std::random_access_iterator_tag) のカテゴリ。|
|`pointer`|VectorViewIterator の実装に必要な内部型へのポインター。|
|`reference`|VectorViewIterator の実装に必要な内部型への参照。|
|`value_type`|`T` 型名。|

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[ベクトルビュー・イットエレーター::ベクトルビュー・イットエレーター](#ctor)|VectorViewIterator クラスの新しいインスタンスを初期化します。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[ベクトルビュー反復器::演算子 - 演算子](#operator-minus)|現在の反復子から指定した数の要素を減算して新しい反復子を生成するか、現在の反復子から指定した反復子を減算して反復子間の要素数を生成します。|
|[ベクトルビュー反復器::演算子 -- 演算子](#operator-decrement)|現在の VectorViewIterator をデクリメントします。|
|[ベクトルビュー反復器::演算子!= 演算子](#operator-inequality)|現在の VectorViewIterator が、指定された VectorViewIterator と等しくないかどうかを示します。|
|[ベクトルビュー反復器::演算子* 演算子](#operator-dereference)|現在の VectorViewIterator により指定された要素への参照を取得します。|
|[ベクトルビュー反復器::演算子\[\]](#operator-at)|現在の VectorViewIterator から指定数だけ転置された要素への参照を取得します。|
|[ベクトルビュー・イットエレーター::オペレーター+ 演算子](#operator-plus)|指定された VectorViewIterator から指定された転置にある要素を参照する VectorViewIterator を返します。|
|[ベクトルビュー反復器::演算子++ 演算子](#operator-increment)|現在の VectorViewIterator をインクリメントします。|
|[ベクトルビュー・イットエレーター::オペレーター+= 演算子](#operator-plus-equals)|指定された転置数だけ現在の VectorViewIterator をインクリメントします。|
|[ベクトルビュー・ティテレーター::演算子<演算子](#operator-less-than)|現在の VectorViewIterator が、指定された VectorViewIterator より小さいかどうかを示します。|
|[ベクトルビュー反復器::演算子\<= 演算子](#operator-less-than-or-equals)|現在の VectorViewIterator が、指定された VectorViewIterator 以下であるかどうかを示します。|
|[ベクトルビュー反復器::演算子- = 演算子](#operator-minus-assign)|現在の VectorViewIterator を、指定されたディスプレイスメントだけデクリメントします。|
|[ベクトルビュー反復器::演算子==演算子](#operator-equality)|現在の VectorViewIterator が、指定された VectorViewIterator と等しいかどうかを示します。|
|[VectorViewIterator::operator> 演算子](#operator-greater-than)|現在の VectorViewIterator が、指定された VectorViewIterator より大きいかどうかを示します。|
|[ベクトルビュー反復器::演算子>演算子](#operator-arrow)|現在の VectorViewIterator により参照される要素のアドレスを取得します。|
|[ベクトルビュー・>:演算子 = 演算子](#operator-greater-than-or-equals)|現在の VectorViewIterator が、指定された VectorViewIterator 以上であるかどうかを示します。|

## <a name="inheritance-hierarchy"></a>継承階層

`VectorViewIterator`

### <a name="requirements"></a>必要条件

**ヘッダー:** collection.h

**名前空間:** Platform::Collections

## <a name="vectorviewiteratoroperator-gt-operator"></a><a name="operator-arrow"></a>ベクトルビュー反復器::演算子 -&gt;演算子

現在の VectorViewIterator により参照される要素のアドレスを取得します。

### <a name="syntax"></a>構文

```
Detail::ArrowProxy<T> operator->() const;
```

### <a name="return-value"></a>戻り値

現在の VectorViewIterator により参照される要素の値。

戻り値の型は、この演算子の実装に必要な、指定されていない内部型です。

## <a name="vectorviewiteratoroperator---operator"></a><a name="operator-decrement"></a>ベクトルビュー反復器::演算子 -- 演算子

現在の VectorViewIterator をデクリメントします。

### <a name="syntax"></a>構文

```
VectorViewIterator& operator--();
VectorViewIterator operator--(int);
```

### <a name="return-value"></a>戻り値

最初の構文は、現在の VectorViewIterator をデクリメントしてから返します。 2 番目の構文は、現在の VectorViewIterator のコピーを返してから、現在の VectorViewIterator をデクリメントします。

### <a name="remarks"></a>解説

最初の VectorViewIterator 構文は、現在の VectorViewIterator の前置デクリメントを実行します。

2 番目の構文は、現在の VectorViewIterator の後置デクリメントを実行します。 2 つ目の構文の `int` 型は、実際の整数オペランドではなく後置デクリメント演算を示します。

## <a name="vectorviewiteratoroperator-operator"></a><a name="operator-dereference"></a>ベクトルビュー反復器::演算子\*

現在の VectorViewIterator により指定された要素への参照を取得します。

### <a name="syntax"></a>構文

```
reference operator*() const;
```

### <a name="return-value"></a>戻り値

現在の VectorViewIterator により指定された要素。

## <a name="vectorviewiteratoroperator-operator"></a><a name="operator-equality"></a>ベクトルビュー反復器::演算子==演算子

現在の VectorViewIterator が、指定された VectorViewIterator と等しいかどうかを示します。

### <a name="syntax"></a>構文

```
bool operator==(const VectorViewIterator& other) const;
```

### <a name="parameters"></a>パラメーター

*他*<br/>
別の VectorViewIterator。

### <a name="return-value"></a>戻り値

現在`VectorViewIterator`が*他*の値と等しい場合は**true。** それ以外の場合**は false。**

## <a name="vectorviewiteratoroperatorgt-operator"></a><a name="operator-greater-than"></a>ベクトルビュー反復器::演算子&gt;

現在の VectorViewIterator が、指定された VectorViewIterator より大きいかどうかを示します。

### <a name="syntax"></a>構文

```

bool operator>(const VectorViewIterator& other) const;
```

### <a name="parameters"></a>パラメーター

*他*<br/>
別の VectorViewIterator。

### <a name="return-value"></a>戻り値

現在のベクタービューイテレータが*他*の値よりも大きい場合は**true。** それ以外の場合**は false。**

## <a name="vectorviewiteratoroperatorgt-operator"></a><a name="operator-greater-than-or-equals"></a>ベクトルビュー反復器::演算子&gt;= 演算子

現在`VectorViewIterator`の値が指定した`VectorViewIterator`.

### <a name="syntax"></a>構文

```

bool operator>=(const VectorViewIterator& other) const;
```

### <a name="parameters"></a>パラメーター

*他*<br/>
別の VectorViewIterator。

### <a name="return-value"></a>戻り値

**現在**`VectorViewIterator`が*他*の値以上の場合は true。それ以外の場合**は false。**

## <a name="vectorviewiteratoroperator-operator"></a><a name="operator-increment"></a>ベクトルビュー反復器::演算子++ 演算子

現在の VectorViewIterator をインクリメントします。

### <a name="syntax"></a>構文

```

VectorViewIterator& operator++();
VectorViewIterator operator++(int);
```

### <a name="return-value"></a>戻り値

最初の構文は、現在の VectorViewIterator をインクリメントしてから返します。 2 番目の構文は、現在の VectorViewIterator のコピーを返し、現在の VectorViewIterator をインクリメントします。

### <a name="remarks"></a>解説

最初の VectorViewIterator 構文は、現在の VectorViewIterator の前置インクリメントを実行します。

2 番目の構文は、現在の VectorViewIterator の後置インクリメントを実行します。 2 つ目の構文の `int` 型は、実際の整数オペランドではなく後置インクリメント演算を示します。

## <a name="vectorviewiteratoroperator-operator"></a><a name="operator-inequality"></a>ベクトルビュー反復器::演算子!= 演算子

現在の VectorViewIterator が、指定された VectorViewIterator と等しくないかどうかを示します。

### <a name="syntax"></a>構文

```
bool operator!=(const VectorViewIterator& other) const;
```

### <a name="parameters"></a>パラメーター

*他*<br/>
別の VectorViewIterator。

### <a name="return-value"></a>戻り値

現在`VectorViewIterator`が*他*の値と等しくない場合は**true。** それ以外の場合**は false。**

## <a name="vectorviewiteratoroperatorlt-operator"></a><a name="operator-less-than"></a>ベクトルビュー反復器::演算子&lt;

現在の VectorIterator が、指定された VectorIterator より小さいかどうかを示します。

### <a name="syntax"></a>構文

```
bool operator<(const VectorViewIterator& other) const;
```

### <a name="parameters"></a>パラメーター

*他*<br/>
別の `VectorIterator`。

### <a name="return-value"></a>戻り値

現在`VectorIterator`が*他*の電流より小さい場合は**true。** それ以外の場合**は false。**

## <a name="vectorviewiteratoroperatorlt-operator"></a><a name="operator-less-than-or-equals"></a>ベクトルビュー反復器::演算子&lt;= 演算子

現在`VectorIterator`の値が指定した`VectorIterator`.

### <a name="syntax"></a>構文

```

bool operator<=(const VectorViewIterator& other) const;
```

### <a name="parameters"></a>パラメーター

*他*<br/>
別の `VectorIterator`。

### <a name="return-value"></a>戻り値

**電流**`VectorIterator`が*他*の電流以下の場合は true。それ以外の場合**は false。**

## <a name="vectorviewiteratoroperator--operator"></a><a name="operator-minus"></a>ベクトルビュー反復器::演算子 - 演算子

現在の反復子から指定した数の要素を減算して新しい反復子を生成するか、現在の反復子から指定した反復子を減算して反復子間の要素数を生成します。

### <a name="syntax"></a>構文

```

VectorViewIterator operator-(difference_type n) const;

difference_type operator-(const VectorViewIterator& other) const;
```

### <a name="parameters"></a>パラメーター

*n*<br/>
要素の数。

*他*<br/>
別の VectorViewIterator。

### <a name="return-value"></a>戻り値

最初の演算子構文は、現在の VectorViewIterator より `n` 要素少ない VectorViewIterator オブジェクトを返します。 2 番目の演算子構文は、現在の VectorViewIterator と `other` VectorViewIterator の間の要素の数を返します。

## <a name="vectorviewiteratoroperator-operator"></a><a name="operator-plus-equals"></a>ベクトルビュー・イットエレーター::オペレーター+= 演算子

指定された転置数だけ現在の VectorViewIterator をインクリメントします。

### <a name="syntax"></a>構文

```
VectorViewIterator& operator+=(difference_type n);
```

### <a name="parameters"></a>パラメーター

*n*<br/>
整数の転置。

### <a name="return-value"></a>戻り値

更新された VectorViewIterator。

## <a name="vectorviewiteratoroperator-operator"></a><a name="operator-plus"></a>ベクトルビュー・イットエレーター::オペレーター+ 演算子

指定された VectorViewIterator から指定された転置にある要素を参照する VectorViewIterator を返します。

### <a name="syntax"></a>構文

```

VectorViewIterator operator+(difference_type n) const;

template <typename T>
inline VectorViewIterator<T> operator+
   (ptrdiff_t n,
   const VectorViewIterator<T>& i);
```

### <a name="parameters"></a>パラメーター

*T*<br/>
2 番目の構文では、VectorViewIterator の型名。

*n*<br/>
整数のディスプレイスメント。

*私*<br/>
2 番目の構文では、VectorViewIterator。

### <a name="return-value"></a>戻り値

最初の構文では、現在の VectorViewIterator から指定された転置にある要素を参照する VectorViewIterator。

2 番目の構文では、`i` パラメーターの先頭から指定された転置にある要素を参照する VectorViewIterator。

## <a name="vectorviewiteratoroperator--operator"></a><a name="operator-minus-assign"></a>ベクトルビュー反復器::演算子- = 演算子

指定されたディスプレイスメントだけ現在の VectorIterator をデクリメントします。

### <a name="syntax"></a>構文

```
VectorViewIterator& operator-=(difference_type n);
```

### <a name="parameters"></a>パラメーター

*n*<br/>
整数のディスプレイスメント。

### <a name="return-value"></a>戻り値

更新された VectorIterator。

## <a name="vectorviewiteratoroperator"></a><a name="operator-at"></a>ベクトルビュー反復器::演算子\[\]

現在の VectorViewIterator から指定数だけ転置された要素への参照を取得します。

### <a name="syntax"></a>構文

```
reference operator[](difference_type n) const;
```

### <a name="parameters"></a>パラメーター

*n*<br/>
整数のディスプレイスメント。

### <a name="return-value"></a>戻り値

現在の VectorViewIterator から `n` 要素だけ転置された要素。

## <a name="vectorviewiteratorvectorviewiterator-constructor"></a><a name="ctor"></a>ベクトルビュー反復器::ベクトルビュー反復器コンストラクタ

VectorViewIterator クラスの新しいインスタンスを初期化します。

### <a name="syntax"></a>構文

```

VectorViewIterator();

explicit VectorViewIterator(
   Windows::Foundation::Collections::IVectorView<T>^ v
);
```

### <a name="parameters"></a>パラメーター

*V*<br/>
オブジェクトを表示\<>。

### <a name="remarks"></a>解説

最初の構文例は既定のコンストラクターです。 2 番目の構文の例は、IVectorView\<T> オブジェクトから VectorViewIterator を構築するために使用される明示的なコンストラクターです。

## <a name="see-also"></a>関連項目

[プラットフォーム名前空間](platform-namespace-c-cx.md)

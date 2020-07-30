---
title: move_iterator クラス
ms.date: 03/27/2019
f1_keywords:
- iterator/std::move_iterator
- iterator/std::move_iterator::iterator_type
- iterator/std::move_iterator::iterator_category
- iterator/std::move_iterator::value_type
- iterator/std::move_iterator::difference_type
- iterator/std::move_iterator::pointer
- iterator/std::move_iterator::reference
- iterator/std::move_iterator::base
helpviewer_keywords:
- std::move_iterator [C++]
- std::move_iterator [C++], iterator_type
- std::move_iterator [C++], iterator_category
- std::move_iterator [C++], value_type
- std::move_iterator [C++], difference_type
- std::move_iterator [C++], pointer
- std::move_iterator [C++], reference
- std::move_iterator [C++], base
ms.assetid: a5e5cdd8-a264-4c6b-9f9c-68b0e8edaab7
ms.openlocfilehash: 55e0c23aaf085a132ecab739ec1d4ff1f11858a0
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87228194"
---
# <a name="move_iterator-class"></a>move_iterator クラス

クラス テンプレート `move_iterator` は反復子のラッパーです。 move_iterator は、ラップする (格納する) 反復子と同じ動作を提供します。ただし、格納されている反復子の逆参照演算子を右辺値参照に変換して、コピーを移動を切り替えます。 右辺値の詳細については、「[右辺値参照宣言子: &&](../cpp/rvalue-reference-declarator-amp-amp.md)」をご覧ください。

## <a name="syntax"></a>構文

```cpp
class move_iterator;
```

## <a name="remarks"></a>解説

クラステンプレートは、逆参照時以外は反復子のように動作するオブジェクトを表します。 これは、メンバー関数 `base()` を介してアクセスされる `Iterator` 型のランダム アクセス反復子を格納します。 `move_iterator` に対するすべての操作は、格納されている反復子で直接実行されます。ただし、`operator*` の結果は、`value_type&&` に暗黙的にキャストされ、右辺値参照が作成されます。

`move_iterator` は、ラップされた反復子で定義されていない操作が可能である場合があります。 これらの操作は使用しないでください。

### <a name="constructors"></a>コンストラクター

|コンストラクター|[説明]|
|-|-|
|[move_iterator](#move_iterator)|`move_iterator` 型のオブジェクトのコンストラクター。|

### <a name="typedefs"></a>Typedefs

|型名|説明|
|-|-|
|[iterator_type](#iterator_type)|テンプレート パラメーター `RandomIterator` のシノニム。|
|[iterator_category](#iterator_category)|**`typename`** 同じ名前の長い式のシノニムは、 `iterator_category` 反復子の一般的な機能を識別します。|
|[value_type](#value_type)|**`typename`** 同じ名前の長い式のシノニムは、 `value_type` 反復子要素の型を表します。|
|[difference_type](#difference_type)|**`typename`** 同じ名前の長い式のシノニムは、 `difference_type` 要素間の差の値を表現するために必要な整数型を表します。|
|[pointer](#pointer)|テンプレート パラメーター `RandomIterator` のシノニム。|
|[reference](#reference)|`rvalue` 参照 `value_type&&` のシノニム。|

### <a name="member-functions"></a>メンバー関数

|メンバー関数|[説明]|
|-|-|
|[base](#base)|このメンバー関数は、この `move_iterator` によってラップされた、格納されている反復子を返します。|

### <a name="operators"></a>オペレーター

|演算子|[説明]|
|-|-|
|[move_iterator:: operator *](#op_star)|`(reference)*base().` を返します。|
|[move_iterator:: operator + +](#op_add_add)|格納されている反復子をインクリメントします。 実際の動作は、前置インクリメント操作であるか、後置インクリメント操作であるかによって異なります。|
|[move_iterator::operator--](#operator--)|格納されている反復子をデクリメントします。 実際の動作は、前置インクリメント操作であるか、後置インクリメント操作であるかによって異なります。|
|[move_iterator:: operator-&gt;](#op_arrow)|`&**this` を返します。|
|[move_iterator:: operator-](#operator-)|最初に現在位置から右側の値を減算することによって `move_iterator(*this) -=` を返します。|
|[move_iterator:: operator []](#op_at)|`(reference)*(*this + off)` を返します。 現在のベースからのオフセットを指定し、その位置の値を取得できます。|
|[move_iterator:: operator +](#op_add)|`move_iterator(*this) +=` に値を返します。 ベースにオフセットを加算し、その位置の値を取得できます。|
|[move_iterator:: operator + =](#op_add_eq)|格納されている反復子に右辺値を追加し、を返し **`*this`** ます。|
|[move_iterator:: operator-=](#operator-_eq)|格納されている反復子から右辺値を減算し、を返し **`*this`** ます。|

## <a name="requirements"></a>必要条件

**ヘッダー:**\<iterator>

**名前空間:** std

## <a name="move_iteratorbase"></a><a name="base"></a>move_iterator:: base

この `move_iterator` の格納されている反復子を返します。

```cpp
RandomIterator base() const;
```

### <a name="remarks"></a>解説

このメンバー関数は、格納されている反復子を返します。

## <a name="move_iteratordifference_type"></a><a name="difference_type"></a>move_iterator::d ifference_type

型 `difference_type` は、 `move_iterator` **`typedef`** 反復子の特徴に基づい `difference_type` ており、その型と同義に使用できます。

```cpp
typedef typename iterator_traits<RandomIterator>::difference_type difference_type;
```

### <a name="remarks"></a>解説

この型は、反復子特性 `typename iterator_traits<RandomIterator>::pointer` の同意語です。

## <a name="move_iteratoriterator_category"></a><a name="iterator_category"></a>move_iterator:: iterator_category

型 `iterator_category` は、 `move_iterator` **`typedef`** 反復子の特徴に基づい `iterator_category` ており、その型と同義に使用できます。

```cpp
typedef typename iterator_traits<RandomIterator>::iterator_category  iterator_category;
```

### <a name="remarks"></a>解説

この型は、反復子特性 `typename iterator_traits<RandomIterator>::iterator_category` の同意語です。

## <a name="move_iteratoriterator_type"></a><a name="iterator_type"></a>move_iterator:: iterator_type

型 `iterator_type` は、クラス テンプレートの `move_iterator` のテンプレート パラメーター `RandomIterator` に基づいていて、代わりに互いに入れ替えて使用できます。

```cpp
typedef RandomIterator iterator_type;
```

### <a name="remarks"></a>解説

この型は、テンプレート パラメーター `RandomIterator` のシノニムです。

## <a name="move_iteratormove_iterator"></a><a name="move_iterator"></a>move_iterator:: move_iterator

移動反復子を構築します。 格納されている反復子としてパラメーターを使用します。

```cpp
move_iterator();
explicit move_iterator(RandomIterator right);
template <class Type>
move_iterator(const move_iterator<Type>& right);
```

### <a name="parameters"></a>パラメーター

*そうです*\
格納されている反復子として使用する反復子。

### <a name="remarks"></a>解説

最初のコンストラクターは、格納されている反復子を既定のコンストラクターによって初期化します。 残りのコンストラクターは、格納されている反復子を `base.base()` によって初期化します。

## <a name="move_iteratoroperator"></a><a name="op_add_eq"></a>move_iterator:: operator + =

格納された反復子にオフセットを追加し、その格納された反復子が新しい現在位置にある要素を指すようにします。 その後、演算子は新しい現在の要素を移動します。

```cpp
move_iterator& operator+=(difference_type _Off);
```

### <a name="parameters"></a>パラメーター

*_Off*\
新しい現在位置を決定するために現在位置に追加するオフセット。

### <a name="return-value"></a>戻り値

新しい現在の要素を返します。

### <a name="remarks"></a>解説

演算子は、格納されている反復子に *_Off*を追加します。 その後、を返し **`*this`** ます。

## <a name="move_iteratoroperator-"></a><a name="operator-_eq"></a>move_iterator:: operator-=

指定された数の前の要素の間で移動します。 この演算子は、格納された反復子からオフセットを減算します。

```cpp
move_iterator& operator-=(difference_type _Off);
```

### <a name="parameters"></a>パラメーター

### <a name="remarks"></a>解説

演算子は `*this += -_Off` を評価します。 その後、を返し **`*this`** ます。

## <a name="move_iteratoroperator"></a><a name="op_add_add"></a>move_iterator:: operator + +

`move_iterator.` に属する格納されている反復子をインクリメントします。現在の要素は後置インクリメント演算子によってアクセスされます。 次の要素は前置インクリメント演算子によってアクセスされます。

```cpp
move_iterator& operator++();
move_iterator operator++(int);
```

### <a name="parameters"></a>パラメーター

### <a name="remarks"></a>解説

最初の (前置インクリメント) 演算子は格納されている反復子をインクリメントします。 その後、を返し **`*this`** ます。

2番目の (postincrement) 演算子は、のコピーを作成し、 **`*this`** を評価 `++*this` します。 その後、コピーを返します。

## <a name="move_iteratoroperator"></a><a name="op_add"></a>move_iterator:: operator +

任意の要素の数だけ前方へ進んだ反復子の位置を返します。

```cpp
move_iterator operator+(difference_type _Off) const;
```

### <a name="parameters"></a>パラメーター

### <a name="remarks"></a>解説

演算子はを返し `move_iterator(*this) +=` `_Off` ます。

## <a name="move_iteratoroperator"></a><a name="op_at"></a>move_iterator:: operator []

`move iterator` の範囲の要素への配列インデックスのアクセスを許可します。

```cpp
reference operator[](difference_type _Off) const;
```

### <a name="parameters"></a>パラメーター

### <a name="remarks"></a>解説

この演算子は `(reference)*(*this + _Off)` を返します。

## <a name="move_iteratoroperator--"></a><a name="operator--"></a>move_iterator:: operator--

Predecrement と postdecrement メンバー演算子は、格納されている反復子でデクリメントを実行します。

```cpp
move_iterator& operator--();
move_iterator operator--();
```

### <a name="parameters"></a>パラメーター

### <a name="remarks"></a>解説

最初のメンバー演算子 (predecrement) は、格納されている反復子をデクリメントします。 その後、を返し **`*this`** ます。

2番目の (postdecrement) 演算子は、のコピーを作成し **`*this`** 、を評価 `--*this` します。 その後、コピーを返します。

## <a name="move_iteratoroperator-"></a><a name="operator-"></a>move_iterator:: operator-

格納されている反復子をデクリメントして、指定された値を返します。

```cpp
move_iterator operator-(difference_type _Off) const;
```

### <a name="parameters"></a>パラメーター

### <a name="remarks"></a>解説

この演算子は `move_iterator(*this) -= _Off` を返します。

## <a name="move_iteratoroperator"></a><a name="op_star"></a>move_iterator:: operator *

格納されている反復子を逆参照して値を返します。 これは、`rvalue reference` と同じように動作し、移動代入を実行します。 この演算子は、基本反復子から現在の要素を転送します。 後続の要素は、新しい現在の要素になります。

```cpp
reference operator*() const;
```

### <a name="remarks"></a>解説

この演算子は `(reference)*base()` を返します。

## <a name="move_iteratoroperator-gt"></a><a name="op_arrow"></a>move_iterator:: operator-&gt;

通常の`RandomIterator` `operator->` のように、現在の要素に属するフィールドへのアクセスを提供します。

```cpp
pointer operator->() const;
```

### <a name="remarks"></a>解説

この演算子は `&**this` を返します。

## <a name="move_iteratorpointer"></a><a name="pointer"></a>move_iterator::p ointer

型 `pointer` は、 **`typedef`** のランダム反復子に基づくで、同義に `RandomIterator` `move_iterator` 使用できます。

```cpp
typedef RandomIterator  pointer;
```

### <a name="remarks"></a>解説

この型は `RandomIterator` の同意語です。

## <a name="move_iteratorreference"></a><a name="reference"></a>move_iterator:: reference

この型 `reference` は、 **`typedef`** のに基づくであり、と `value_type&&` `move_iterator` 同じ意味で使用でき `value_type&&` ます。

```cpp
typedef value_type&& reference;
```

### <a name="remarks"></a>解説

この型は、右辺値参照である `value_type&&` のシノニムです。

## <a name="move_iteratorvalue_type"></a><a name="value_type"></a>move_iterator:: value_type

型 `value_type` は、 `move_iterator` **`typedef`** 反復子の特徴に基づい `value_type` ており、その型と同義に使用できます。

```cpp
typedef typename iterator_traits<RandomIterator>::value_type   value_type;
```

### <a name="remarks"></a>解説

この型は、反復子特性 `typename iterator_traits<RandomIterator>::value_type` の同意語です。

## <a name="see-also"></a>関連項目

[\<iterator>](../standard-library/iterator.md)\
[左辺値と右辺値](../cpp/lvalues-and-rvalues-visual-cpp.md)\
[移動コンストラクターと移動代入演算子 (C++)](../cpp/move-constructors-and-move-assignment-operators-cpp.md)\
[C++ 標準ライブラリリファレンス](../standard-library/cpp-standard-library-reference.md)

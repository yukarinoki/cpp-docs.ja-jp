---
title: duration クラス
ms.date: 03/27/2016
f1_keywords:
- chrono/std::chrono::duration
- chrono/std::chrono::duration::duration
- chrono/std::chrono::duration::count
- chrono/std::chrono::duration::max
- chrono/std::chrono::duration::min
- chrono/std::chrono::duration::zero
ms.assetid: 06b863b3-65be-4ded-a72e-6e1eb1531077
helpviewer_keywords:
- std::chrono [C++], duration
ms.openlocfilehash: 3669935bf094f476ca24a8170a0388dff29e0a0c
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81368753"
---
# <a name="duration-class"></a>duration クラス

2 つの時点の間における経過時間である *time interval* を保持する型を表します。

## <a name="syntax"></a>構文

```cpp
template <class Rep, class Period = ratio<1>>
class duration;
template <class Rep, class Period>
class duration;
template <class Rep, class Period1, class Period2>
class duration <duration<Rep, Period1>, Period2>;
```

## <a name="remarks"></a>解説

テンプレート引数 `Rep` では、間隔内でのクロック ティック数を保持するために使用する型を記述します。 テンプレート引数 `Period` は、各ティックが表す間隔のサイズを記述する [ratio](../standard-library/ratio.md) のインスタンス化です。

## <a name="members"></a>メンバー

### <a name="public-typedefs"></a>パブリック typedef

|名前|説明|
|----------|-----------------|
|duration::period Typedef|テンプレート パラメーター `Period` のシノニムを表します。|
|duration::rep Typedef|テンプレート パラメーター `Rep` のシノニムを表します。|

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[期間](#duration)|`duration` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[count](#count)|時間間隔内でのクロック ティック数を返します。|
|[max](#max)|静的。 テンプレート パラメーター `Ref` の最大許容値を返します。|
|[min](#min)|静的。 テンプレート パラメーター `Ref` の最小許容値を返します。|
|[ゼロ](#zero)|静的。 実際には、`Rep`(0) を返します。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[持続時間::演算子-](#operator-)|無効にされたティック カウントと共に、`duration` オブジェクトのコピーを返します。|
|[持続時間::演算子--](#operator--)|格納されたティック カウントをデクリメントします。|
|[持続時間::演算子=](#op_eq)|格納されたティック カウントを指定された値だけ少なくします。|
|[持続時間::演算子*=](#op_star_eq)|格納されたティック カウントを指定した値で乗算します。|
|[持続時間::演算子/=](#op_div_eq)|格納されたティック カウントを、指定した `duration` オブジェクトのティック カウントで除算します。|
|[期間::演算子+](#op_add)|`*this` が返されます。|
|[期間::演算子++](#op_add_add)|格納されたティック カウントをインクリメントします。|
|[持続時間::演算子+=](#op_add_eq)|指定した `duration` オブジェクトのティック カウントを、格納されたティック カウントに加算します。|
|[持続時間::演算子- =](#operator-_eq)|指定した `duration` オブジェクトのティック カウントを、格納されたティック カウントから減算します。|

## <a name="requirements"></a>必要条件

**ヘッダー:**\<クロノ>

**名前空間:** std::chrono

## <a name="durationcount"></a><a name="count"></a>期間::カウント

時間間隔内でのクロック ティック数を取得します。

```cpp
constexpr Rep count() const;
```

### <a name="return-value"></a>戻り値

時間間隔内でのクロック ティック数。

## <a name="durationduration-constructor"></a><a name="duration"></a>期間::dウレーションコンストラクタ

`duration` オブジェクトを構築します。

```cpp
constexpr duration() = default;

template <class Rep2>
constexpr explicit duration(const Rep2& R);

template <class Rep2, class Period2>
constexpr duration(const duration<Rep2, Period2>& Dur);
```

### <a name="parameters"></a>パラメーター

*担当者2*\
ティック数を表す演算型。

*期間2*\
秒単位でティック期間を表すための `std::ratio` テンプレートの特殊化。

*R*\
既定の期間のティック数。

*長調*\
*Period2*で指定された期間のティック数。

### <a name="remarks"></a>解説

既定のコンストラクターは、初期化されていないオブジェクトを作成します。 空のかっこを使う値の初期化は、ゼロ クロック ティックの時間間隔を表すオブジェクトを初期化します。

2 つ目のテンプレート引数コンストラクターは、既定の期間`std::ratio<1>`を使用して*R*クロック ティックの時間間隔を表すオブジェクトを構築します。 ティック数の丸めを避けるために、浮動小数点型として扱うことができない場合`duration::rep`に浮動小数点型として扱うことができる表現型*Rep2*からデュレーション オブジェクトを構築するとエラーになります。

3 つ目の 2 つのテンプレート引数コンストラクタは *、Dur*で指定された時間間隔を長さにする時間間隔を表すオブジェクトを構築します。 ティック カウントが切り捨てられないようにするため、対象の型と*通約可能*な型を持つ duration オブジェクトから duration オブジェクトを作成するとエラーになります。

`D2` を浮動小数点型として処理できず、[ratio_divide\<D1::period, D2::period>::type::den](../standard-library/ratio.md) が 1 ではない場合、duration 型の `D1` は、別の duration 型の `D2` と*通約可能*になります。

*Rep2*が暗黙的に`rep`変換可能で true`treat_as_floating_point<rep>`を保持`treat_as_floating_point<Rep2>`するか *、false*を*保持*している場合を除き、2 番目のコンストラクターはオーバーロード解決に参加しません。 詳しくは、「[<type_traits>](../standard-library/type-traits.md)」をご覧ください。

変換でオーバーフローが発生して `treat_as_floating_point<rep>` が *true を保持*していない場合、または両方の `ratio_divide<Period2, period>::den` が 1 ではなく `treat_as_floating_point<Rep2>` が *false を保持*していない場合、3 番目のコンストラクターはオーバーロードの解決に関与しません。 詳しくは、「[<type_traits>](../standard-library/type-traits.md)」をご覧ください。

## <a name="durationmax"></a><a name="max"></a>持続時間::最大

`Ref` テンプレート パラメーター型の値の上限の境界を返す静的メソッドです。

```cpp
static constexpr duration max();
```

### <a name="return-value"></a>戻り値

実際には、`duration(duration_values<rep>::max())` を返します。

## <a name="durationmin"></a><a name="min"></a>所要時間:分

`Ref` テンプレート パラメーター型の値の下限の境界を返す静的メソッドです。

```cpp
static constexpr duration min();
```

### <a name="return-value"></a>戻り値

実際には、`duration(duration_values<rep>::min())` を返します。

## <a name="durationoperator-"></a><a name="operator-"></a>持続時間::演算子-

無効にされたティック カウントと共に、`duration` オブジェクトのコピーを返します。

```cpp
constexpr duration operator-() const;
```

## <a name="durationoperator--"></a><a name="operator--"></a>持続時間::演算子--

格納されたティック カウントをデクリメントします。

```cpp
duration& operator--();

duration operator--(int);
```

### <a name="return-value"></a>戻り値

最初のメソッドは `*this` を返します。

2 番目のメソッドは、デクリメントの前に作成される `*this` のコピーを返します。

## <a name="durationoperator"></a><a name="op_eq"></a>持続時間::演算子=

格納されたティック カウントを指定された値だけ少なくします。

```cpp
duration& operator%=(const rep& Div);

duration& operator%=(const duration& Div);
```

### <a name="parameters"></a>パラメーター

*部*\
最初のメソッドでは *、Div*はティック数を表します。 2 番目のメソッドの*場合、Div*はティック数を含む`duration`オブジェクトです。

### <a name="return-value"></a>戻り値

モジュロ演算が実行された後の `duration` オブジェクト。

## <a name="durationoperator"></a><a name="op_star_eq"></a>持続時間::演算子*=

格納されたティック カウントを指定した値で乗算します。

```cpp
duration& operator*=(const rep& Mult);
```

### <a name="parameters"></a>パラメーター

*Mult*\
`duration::rep` によって指定される型の値。

### <a name="return-value"></a>戻り値

乗算が実行された後の `duration` オブジェクト。

## <a name="durationoperator"></a><a name="op_div_eq"></a>持続時間::演算子/=

指定された値で格納されているティック数を分割します。

```cpp
duration& operator/=(const rep& Div);
```

### <a name="parameters"></a>パラメーター

*部*\
`duration::rep` によって指定される型の値。

### <a name="return-value"></a>戻り値

分割後の `duration` オブジェクト。

## <a name="durationoperator"></a><a name="op_add"></a>期間::演算子+

`*this` が返されます。

```cpp
constexpr duration operator+() const;
```

## <a name="durationoperator"></a><a name="op_add_add"></a>期間::演算子++

格納されたティック カウントをインクリメントします。

```cpp
duration& operator++();

duration operator++(int);
```

### <a name="return-value"></a>戻り値

最初のメソッドは `*this` を返します。

2 番目のメソッドは、インクリメントの前に作成される `*this` のコピーを返します。

## <a name="durationoperator"></a><a name="op_add_eq"></a>持続時間::演算子+=

指定した `duration` オブジェクトのティック カウントを、格納されたティック カウントに加算します。

```cpp
duration& operator+=(const duration& Dur);
```

### <a name="parameters"></a>パラメーター

*長調*\
`duration` オブジェクト。

### <a name="return-value"></a>戻り値

加算が実行された後の `duration` オブジェクト。

## <a name="durationoperator-"></a><a name="operator-_eq"></a>持続時間::演算子- =

指定した `duration` オブジェクトのティック カウントを、格納されたティック カウントから減算します。

```cpp
duration& operator-=(const duration& Dur);
```

### <a name="parameters"></a>パラメーター

*長調*\
`duration` オブジェクト。

### <a name="return-value"></a>戻り値

減算が実行された後の `duration` オブジェクト。

## <a name="durationzero"></a><a name="zero"></a>期間::ゼロ

`duration(duration_values<rep>::zero())` が返されます。

```cpp
static constexpr duration zero();
```

## <a name="durationoperator-mod"></a><a name="op_mod_eq"></a>持続時間::演算子モッド=

格納されたティック カウント剰余の Div または Div.count() を減算します。

```cpp
duration& operator%=(const rep& Div);duration& operator%=(const duration& Div);
```

### <a name="parameters"></a>パラメーター

*部*\
除数。duration オブジェクトまたはティック カウントを表す値のいずれかです。

### <a name="remarks"></a>解説

最初のメンバー関数では、格納されたティック カウント剰余の Div を減算し、*this を返します。 最初のメンバー関数では、格納されたティック カウント剰余の Div.count() を減算し、\*this を返します。

## <a name="see-also"></a>関連項目

[ヘッダー ファイル リファレンス](../standard-library/cpp-standard-library-header-files.md)\
[\<クロノ>](../standard-library/chrono.md)\
[duration_values 構造体](../standard-library/duration-values-structure.md)

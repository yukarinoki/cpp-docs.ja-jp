---
title: コンカレンシー名前空間演算子
ms.date: 11/04/2016
f1_keywords:
- concrt/concurrency::operator!=
- concrt/concurrency:[operator&amp;&amp
ms.assetid: 8e373f23-fc8e-49f7-82e6-ba0c57b822f8
ms.openlocfilehash: 97553276a7c4ff687dd8bea4627f943d5666b2e9
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/25/2020
ms.locfileid: "88836012"
---
# <a name="concurrency-namespace-operators"></a>コンカレンシー名前空間演算子

:::row:::
   :::column span="":::
      [`operator||`](#operator_lor)\
      [`operator&&`](#operator_amp_amp)
   :::column-end:::
   :::column span="":::
      [`operator==`](#operator_eq_eq)\
      [`operator!=`](#operator_neq)
   :::column-end:::
   :::column span="":::
      [`operator<`](#operator_lt)\
      [`operator<=`](#operator_lt_eq)
   :::column-end:::
   :::column span="":::
      [`operator>`](#operator_gt)\
      [`operator>=`](#operator_gt_eq)
   :::column-end:::
:::row-end:::

## <a name="operator124124-operator"></a><a name="operator_lor"></a> operator&#124;&#124; 演算子

引数として指定されたいずれかのタスクが正常に完了したときに正常に完了するタスクを作成します。

```cpp
template<typename ReturnType>
task<ReturnType> operator||(
    const task<ReturnType>& lhs,
    const task<ReturnType>& rhs);

template<typename ReturnType>
task<std::vector<ReturnType>> operator||(
    const task<std::vector<ReturnType>>& lhs,
    const task<ReturnType>& rhs);

template<typename ReturnType>
task<std::vector<ReturnType>> operator||(
    const task<ReturnType>& lhs,
    const task<std::vector<ReturnType>>& rhs);

inline task<void> operator||(
    const task<void>& lhs,
    const task<void>& rhs);
```

### <a name="parameters"></a>パラメーター

*ReturnType*<br/>
返されるタスクの種類。

*lhs*<br/>
結果のタスクにまとめられる最初のタスク。

*rhs*<br/>
結果のタスクにまとめられる 2 番目のタスク。

### <a name="return-value"></a>戻り値

入力タスクのいずれかが正常に完了したときに正常に完了するタスク。 入力したタスクの種類が `T` である場合、この関数の出力は `task<std::vector<T>` になります。 入力タスクの種類がである場合は、 **`void`** 出力タスクもになり `task<void>` ます。

### <a name="remarks"></a>解説

両方のタスクがキャンセルされた場合、または例外をスローした場合、返されたタスクは canceled 状態で完了し、例外が発生した場合は、 `get()` そのタスクでまたはを呼び出すとスローされ `wait()` ます。

## <a name="operatorampamp-operator"></a><a name="operator_amp_amp"></a>operator &amp; &amp; 演算子

引数として指定された両方のタスクが正常に完了したときに正常に完了するタスクを作成します。

```cpp
template<typename ReturnType>
task<std::vector<ReturnType>>  operator&&(
    const task<ReturnType>& lhs,
    const task<ReturnType>& rhs);

template<typename ReturnType>
task<std::vector<ReturnType>>  operator&&(
    const task<std::vector<ReturnType>>& lhs,
    const task<ReturnType>& rhs);

template<typename ReturnType>
task<std::vector<ReturnType>>  operator&&(
    const task<ReturnType>& lhs,
    const task<std::vector<ReturnType>>& rhs);

template<typename ReturnType>
task<std::vector<ReturnType>>  operator&&(
    const task<std::vector<ReturnType>>& lhs,
    const task<std::vector<ReturnType>>& rhs);

inline task<void>  operator&&(
    const task<void>& lhs,
    const task<void>& rhs);
```

### <a name="parameters"></a>パラメーター

*ReturnType*<br/>
返されるタスクの種類。

*lhs*<br/>
結果のタスクにまとめられる最初のタスク。

*rhs*<br/>
結果のタスクにまとめられる 2 番目のタスク。

### <a name="return-value"></a>戻り値

入力した両方のタスクが正常に完了したときに正常に完了するタスク。 入力したタスクの種類が `T` である場合、この関数の出力は `task<std::vector<T>>` になります。 入力タスクの種類がである場合は、 **`void`** 出力タスクもになり `task<void>` ます。

### <a name="remarks"></a>解説

いずれかのタスクが取り消された場合、または例外がスローされた場合、返されたタスクは早期に完了し、取り消された状態になり `get()` ます。また、そのタスクでまたはを呼び出すと、例外が発生した場合は例外がスローされ `wait()` ます。

## <a name="operator-operator"></a><a name="operator_eq_eq"></a> operator = = 演算子

演算子の左側の `concurrent_vector` オブジェクトが右側の `concurrent_vector` オブジェクトと等しいかどうかを調べます。

```cpp
template<typename T, class A1, class A2>
inline bool operator== (
    const concurrent_vector<T, A1>& _A,
    const concurrent_vector<T, A2>& _B);
```

### <a name="parameters"></a>パラメーター

*T*<br/>
同時実行ベクターに格納されている要素のデータ型。

*A1*<br/>
最初のオブジェクトのアロケーター型 `concurrent_vector` 。

*A2*<br/>
2番目のオブジェクトのアロケーター型 `concurrent_vector` 。

*_A*<br/>
`concurrent_vector` 型のオブジェクト。

*_B*<br/>
`concurrent_vector` 型のオブジェクト。

### <a name="return-value"></a>戻り値

**`true`** 演算子の左辺の同時実行ベクターが、演算子の右辺の同時実行ベクターと等しい場合は。それ以外の場合は **`false`** 。

### <a name="remarks"></a>解説

2つの同時実行ベクターは、同じ数の要素を持ち、各要素の値が同じである場合に等しくなります。 それ以外の場合は等しくありません。

このメソッドは、同時実行ベクターまたはのいずれかを変更する可能性のある他のメソッドに関して、同時実行セーフではありません `_A` `_B` 。

## <a name="operator-operator"></a><a name="operator_neq"></a> operator! = 演算子

演算子の左側の `concurrent_vector` オブジェクトが右側の `concurrent_vector` オブジェクトと等しくないかどうかを調べます。

```cpp
template<typename T, class A1, class A2>
inline bool operator!= (
    const concurrent_vector<T, A1>& _A,
    const concurrent_vector<T, A2>& _B);
```

### <a name="parameters"></a>パラメーター

*T*<br/>
同時実行ベクターに格納されている要素のデータ型。

*A1*<br/>
最初のオブジェクトのアロケーター型 `concurrent_vector` 。

*A2*<br/>
2番目のオブジェクトのアロケーター型 `concurrent_vector` 。

*_A*<br/>
`concurrent_vector` 型のオブジェクト。

*_B*<br/>
`concurrent_vector` 型のオブジェクト。

### <a name="return-value"></a>戻り値

**`true`** 同時実行ベクターが等しくない場合は。 **`false`** 同時実行ベクターが等しい場合は。

### <a name="remarks"></a>解説

2つの同時実行ベクターは、同じ数の要素を持ち、各要素の値が同じである場合に等しくなります。 それ以外の場合は等しくありません。

このメソッドは、同時実行ベクターまたはのいずれかを変更する可能性のある他のメソッドに関して、同時実行セーフではありません `_A` `_B` 。

## <a name="operatorlt-operator"></a><a name="operator_lt"></a> operator &lt; 演算子

演算子の左側の `concurrent_vector` オブジェクトが右側の `concurrent_vector` オブジェクトより小さいかどうかを調べます。

```cpp
template<typename T, class A1, class A2>
inline bool operator<(
    const concurrent_vector<T, A1>& _A,
    const concurrent_vector<T, A2>& _B);
```

### <a name="parameters"></a>パラメーター

*T*<br/>
同時実行ベクターに格納されている要素のデータ型。

*A1*<br/>
最初のオブジェクトのアロケーター型 `concurrent_vector` 。

*A2*<br/>
2番目のオブジェクトのアロケーター型 `concurrent_vector` 。

*_A*<br/>
`concurrent_vector` 型のオブジェクト。

*_B*<br/>
`concurrent_vector` 型のオブジェクト。

### <a name="return-value"></a>戻り値

**`true`** 演算子の左辺の同時実行ベクターが、演算子の右辺の同時実行ベクターより小さい場合は。それ以外の場合は **`false`** 。

### <a name="remarks"></a>解説

この演算子の動作は、名前空間のクラスの同等の演算子と同じです `vector` `std` 。

このメソッドは、同時実行ベクターまたはのいずれかを変更する可能性のある他のメソッドに関して、同時実行セーフではありません `_A` `_B` 。

## <a name="operatorlt-operator"></a><a name="operator_lt_eq"></a> operator &lt; = 演算子

演算子の左側の `concurrent_vector` オブジェクトが右側の  `concurrent_vector` オブジェクト以下かどうかを調べます。

```cpp
template<typename T, class A1, class A2>
inline bool operator<= (
    const concurrent_vector<T, A1>& _A,
    const concurrent_vector<T, A2>& _B);
```

### <a name="parameters"></a>パラメーター

*T*<br/>
同時実行ベクターに格納されている要素のデータ型。

*A1*<br/>
最初のオブジェクトのアロケーター型 `concurrent_vector` 。

*A2*<br/>
2番目のオブジェクトのアロケーター型 `concurrent_vector` 。

*_A*<br/>
`concurrent_vector` 型のオブジェクト。

*_B*<br/>
`concurrent_vector` 型のオブジェクト。

### <a name="return-value"></a>戻り値

**`true`** 演算子の左辺の同時実行ベクターが、演算子の右辺の同時実行ベクター以下である場合は、。それ以外の場合は **`false`** 。

### <a name="remarks"></a>解説

この演算子の動作は、名前空間のクラスの同等の演算子と同じです `vector` `std` 。

このメソッドは、同時実行ベクターまたはのいずれかを変更する可能性のある他のメソッドに関して、同時実行セーフではありません `_A` `_B` 。

## <a name="operatorgt-operator"></a><a name="operator_gt"></a> operator &gt; 演算子

演算子の左側の `concurrent_vector` オブジェクトが右側の `concurrent_vector` オブジェクトより大きいかどうかを調べます。

```cpp
template<typename T, class A1, class A2>
inline bool operator>(
    const concurrent_vector<T, A1>& _A,
    const concurrent_vector<T, A2>& _B);
```

### <a name="parameters"></a>パラメーター

*T*<br/>
同時実行ベクターに格納されている要素のデータ型。

*A1*<br/>
最初のオブジェクトのアロケーター型 `concurrent_vector` 。

*A2*<br/>
2番目のオブジェクトのアロケーター型 `concurrent_vector` 。

*_A*<br/>
`concurrent_vector` 型のオブジェクト。

*_B*<br/>
`concurrent_vector` 型のオブジェクト。

### <a name="return-value"></a>戻り値

**`true`** 演算子の左辺の同時実行ベクターが演算子の右辺の同時実行ベクターより大きい場合は。それ以外の場合は **`false`** 。

### <a name="remarks"></a>解説

この演算子の動作は、名前空間のクラスの同等の演算子と同じです `vector` `std` 。

このメソッドは、同時実行ベクターまたはのいずれかを変更する可能性のある他のメソッドに関して、同時実行セーフではありません `_A` `_B` 。

## <a name="operatorgt-operator"></a><a name="operator_gt_eq"></a> operator &gt; = 演算子

演算子の左側の `concurrent_vector` オブジェクトが右側の `concurrent_vector` オブジェクト以上であるかどうかを調べます。

```cpp
template<typename T, class A1, class A2>
inline bool operator>= (
    const concurrent_vector<T, A1>& _A,
    const concurrent_vector<T, A2>& _B);
```

### <a name="parameters"></a>パラメーター

*T*<br/>
同時実行ベクターに格納されている要素のデータ型。

*A1*<br/>
最初のオブジェクトのアロケーター型 `concurrent_vector` 。

*A2*<br/>
2番目のオブジェクトのアロケーター型 `concurrent_vector` 。

*_A*<br/>
`concurrent_vector` 型のオブジェクト。

*_B*<br/>
`concurrent_vector` 型のオブジェクト。

### <a name="return-value"></a>戻り値

**`true`** 演算子の左辺の同時実行ベクターが、演算子の右辺の同時実行ベクター以上である場合は、。それ以外の場合は **`false`** 。

### <a name="remarks"></a>解説

この演算子の動作は、名前空間のクラスの同等の演算子と同じです `vector` `std` 。

このメソッドは、同時実行ベクターまたはのいずれかを変更する可能性のある他のメソッドに関して、同時実行セーフではありません `_A` `_B` 。

## <a name="see-also"></a>関連項目

[concurrency 名前空間](concurrency-namespace.md)

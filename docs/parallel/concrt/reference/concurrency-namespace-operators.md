---
title: concurrency 名前空間演算子
ms.date: 11/04/2016
f1_keywords:
- concrt/concurrency::operator!=
- concrt/concurrency:[operator&amp;&amp
ms.assetid: 8e373f23-fc8e-49f7-82e6-ba0c57b822f8
ms.openlocfilehash: d790833e7dcecb5776d2adecd5e6bc1f681db1cf
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62337688"
---
# <a name="concurrency-namespace-operators"></a>concurrency 名前空間演算子

||||
|-|-|-|
|[operator!=](#operator_neq)|[operator&amp;&amp;](#operator_amp_amp)|[operator&gt;](#operator_gt)|
|[operator&gt;=](#operator_gt_eq)|[operator&lt;](#operator_lt)|[operator&lt;=](#operator_lt_eq)|
|[operator==](#operator_eq_eq)|[operator&#124;&#124;](#operator_lor)| |

##  <a name="operator_lor"></a>  演算子&#124;&#124;演算子

引数として指定されたいずれかのタスクが正常に完了したときに正常に完了するタスクを作成します。

```
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

入力したタスクのいずれかが正常に完了したときに正常を完了するタスク。 入力したタスクの種類が `T` である場合、この関数の出力は `task<std::vector<T>` になります。 入力したタスクの種類が `void` である場合、出力のタスクも `task<void>` になります。

### <a name="remarks"></a>Remarks

両方のタスクが取り消されたまたは、例外をスローする、返されたタスクは取り消された状態で完了し、例外のいずれかが発生した場合スローされますを呼び出すと`get()`または`wait()`タスクにします。

##  <a name="operator_amp_amp"></a>  演算子&amp;&amp;演算子

引数として指定された両方のタスクが正常に完了したときに正常に完了するタスクを作成します。

```
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

入力した両方のタスクが正常に完了したときに正常に完了するタスク。 入力したタスクの種類が `T` である場合、この関数の出力は `task<std::vector<T>>` になります。 入力したタスクの種類が `void` である場合、出力のタスクも `task<void>` になります。

### <a name="remarks"></a>Remarks

タスクのどちらか 1 つが取り消された場合、または例外をスローした場合、返されるタスクは早期に完了し、取り消された状態になります。また例外が発生したときは、そのタスクに対して `get()` または `wait()` を呼び出す場合に、その例外がスローされます。

##  <a name="operator_eq_eq"></a>  operator = 演算子

演算子の左側の `concurrent_vector` オブジェクトが右側の `concurrent_vector` オブジェクトと等しいかどうかを調べます。

```
template<typename T, class A1, class A2>
inline bool operator== (
    const concurrent_vector<T, A1>& _A,
    const concurrent_vector<T, A2>& _B);
```

### <a name="parameters"></a>パラメーター

*T*<br/>
同時実行ベクターに格納されている要素のデータ型。

*A1*<br/>
1 つ目のアロケーターの型`concurrent_vector`オブジェクト。

*A2*<br/>
2 つ目のアロケーターの型`concurrent_vector`オブジェクト。

*_A*<br/>
`concurrent_vector` 型のオブジェクト。

*_B*<br/>
`concurrent_vector` 型のオブジェクト。

### <a name="return-value"></a>戻り値

**true**演算子の左側にある同時実行ベクターが演算子の右側にある同時実行ベクターそれ以外の場合**false**します。

### <a name="remarks"></a>Remarks

同じ数の要素があるし、各要素が同じ値を持つ場合は、2 つの同時実行ベクターは等しくなります。 それ以外の場合は等しくありません。

このメソッドは、同時実行ベクターのいずれかの変更を他のメソッドの同時実行セーフ`_A`または`_B`します。

##  <a name="operator_neq"></a>  演算子! = 演算子

演算子の左側の `concurrent_vector` オブジェクトが右側の `concurrent_vector` オブジェクトと等しくないかどうかを調べます。

```
template<typename T, class A1, class A2>
inline bool operator!= (
    const concurrent_vector<T, A1>& _A,
    const concurrent_vector<T, A2>& _B);
```

### <a name="parameters"></a>パラメーター

*T*<br/>
同時実行ベクターに格納されている要素のデータ型。

*A1*<br/>
1 つ目のアロケーターの型`concurrent_vector`オブジェクト。

*A2*<br/>
2 つ目のアロケーターの型`concurrent_vector`オブジェクト。

*_A*<br/>
`concurrent_vector` 型のオブジェクト。

*_B*<br/>
`concurrent_vector` 型のオブジェクト。

### <a name="return-value"></a>戻り値

**true**同時実行ベクターが等しくない場合**false**同時実行のベクトルが等しい場合。

### <a name="remarks"></a>Remarks

同じ数の要素があるし、各要素が同じ値を持つ場合は、2 つの同時実行ベクターは等しくなります。 それ以外の場合は等しくありません。

このメソッドは、同時実行ベクターのいずれかの変更を他のメソッドの同時実行セーフ`_A`または`_B`します。

##  <a name="operator_lt"></a>  演算子&lt;演算子

演算子の左側の `concurrent_vector` オブジェクトが右側の `concurrent_vector` オブジェクトより小さいかどうかを調べます。

```
template<typename T, class A1, class A2>
inline bool operator<(
    const concurrent_vector<T, A1>& _A,
    const concurrent_vector<T, A2>& _B);
```

### <a name="parameters"></a>パラメーター

*T*<br/>
同時実行ベクターに格納されている要素のデータ型。

*A1*<br/>
1 つ目のアロケーターの型`concurrent_vector`オブジェクト。

*A2*<br/>
2 つ目のアロケーターの型`concurrent_vector`オブジェクト。

*_A*<br/>
`concurrent_vector` 型のオブジェクト。

*_B*<br/>
`concurrent_vector` 型のオブジェクト。

### <a name="return-value"></a>戻り値

**true**演算子の左側にある同時実行ベクターが、同時実行ベクターは、演算子の右側にあるより小さい場合それ以外の場合**false**します。

### <a name="remarks"></a>Remarks

この演算子の動作に相当する演算子のと同じです、`vector`クラス、`std`名前空間。

このメソッドは、同時実行ベクターのいずれかの変更を他のメソッドの同時実行セーフ`_A`または`_B`します。

##  <a name="operator_lt_eq"></a>  演算子&lt;= 演算子

演算子の左側の `concurrent_vector` オブジェクトが右側の  `concurrent_vector` オブジェクト以下かどうかを調べます。

```
template<typename T, class A1, class A2>
inline bool operator<= (
    const concurrent_vector<T, A1>& _A,
    const concurrent_vector<T, A2>& _B);
```

### <a name="parameters"></a>パラメーター

*T*<br/>
同時実行ベクターに格納されている要素のデータ型。

*A1*<br/>
1 つ目のアロケーターの型`concurrent_vector`オブジェクト。

*A2*<br/>
2 つ目のアロケーターの型`concurrent_vector`オブジェクト。

*_A*<br/>
`concurrent_vector` 型のオブジェクト。

*_B*<br/>
`concurrent_vector` 型のオブジェクト。

### <a name="return-value"></a>戻り値

**true**演算子の左側にある同時実行ベクター、または、同時実行ベクター演算子の右辺と等しいそれ以外の場合**false**します。

### <a name="remarks"></a>Remarks

この演算子の動作に相当する演算子のと同じです、`vector`クラス、`std`名前空間。

このメソッドは、同時実行ベクターのいずれかの変更を他のメソッドの同時実行セーフ`_A`または`_B`します。

##  <a name="operator_gt"></a>  演算子&gt;演算子

演算子の左側の `concurrent_vector` オブジェクトが右側の `concurrent_vector` オブジェクトより大きいかどうかを調べます。

```
template<typename T, class A1, class A2>
inline bool operator>(
    const concurrent_vector<T, A1>& _A,
    const concurrent_vector<T, A2>& _B);
```

### <a name="parameters"></a>パラメーター

*T*<br/>
同時実行ベクターに格納されている要素のデータ型。

*A1*<br/>
1 つ目のアロケーターの型`concurrent_vector`オブジェクト。

*A2*<br/>
2 つ目のアロケーターの型`concurrent_vector`オブジェクト。

*_A*<br/>
`concurrent_vector` 型のオブジェクト。

*_B*<br/>
`concurrent_vector` 型のオブジェクト。

### <a name="return-value"></a>戻り値

**true**演算子の左側にある同時実行ベクターがそれ以外の演算子の右側にある同時実行ベクターより大きい場合**false**します。

### <a name="remarks"></a>Remarks

この演算子の動作に相当する演算子のと同じです、`vector`クラス、`std`名前空間。

このメソッドは、同時実行ベクターのいずれかの変更を他のメソッドの同時実行セーフ`_A`または`_B`します。

##  <a name="operator_gt_eq"></a>  演算子&gt;= 演算子

演算子の左側の `concurrent_vector` オブジェクトが右側の `concurrent_vector` オブジェクト以上であるかどうかを調べます。

```
template<typename T, class A1, class A2>
inline bool operator>= (
    const concurrent_vector<T, A1>& _A,
    const concurrent_vector<T, A2>& _B);
```

### <a name="parameters"></a>パラメーター

*T*<br/>
同時実行ベクターに格納されている要素のデータ型。

*A1*<br/>
1 つ目のアロケーターの型`concurrent_vector`オブジェクト。

*A2*<br/>
2 つ目のアロケーターの型`concurrent_vector`オブジェクト。

*_A*<br/>
`concurrent_vector` 型のオブジェクト。

*_B*<br/>
`concurrent_vector` 型のオブジェクト。

### <a name="return-value"></a>戻り値

**true**演算子の左側にある同時実行ベクターがより大きいまたは演算子の右側にある同時実行ベクターと等しいそれ以外の場合**false**します。

### <a name="remarks"></a>Remarks

この演算子の動作に相当する演算子のと同じです、`vector`クラス、`std`名前空間。

このメソッドは、同時実行ベクターのいずれかの変更を他のメソッドの同時実行セーフ`_A`または`_B`します。

## <a name="see-also"></a>関連項目

[コンカレンシー名前空間](concurrency-namespace.md)

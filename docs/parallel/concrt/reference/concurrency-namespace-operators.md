---
title: コンカレンシー名前空間演算子
ms.date: 11/04/2016
f1_keywords:
- concrt/concurrency::operator!=
- concrt/concurrency:[operator&amp;&amp
ms.assetid: 8e373f23-fc8e-49f7-82e6-ba0c57b822f8
ms.openlocfilehash: aac43a15b09bd792118fbfe7ea51493b73b8ac9d
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81374380"
---
# <a name="concurrency-namespace-operators"></a>コンカレンシー名前空間演算子

||||
|-|-|-|
|[演算子!=](#operator_neq)|[演算子&amp;&amp;](#operator_amp_amp)|[演算子&gt;](#operator_gt)|
|[演算子&gt;=](#operator_gt_eq)|[演算子&lt;](#operator_lt)|[演算子&lt;=](#operator_lt_eq)|
|[演算子==](#operator_eq_eq)|[operator&#124;&#124;](#operator_lor)| |

## <a name="operator124124-operator"></a><a name="operator_lor"></a>演算子&#124;&#124; 演算子

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

*リターンタイプ*<br/>
返されるタスクの種類。

*lhs*<br/>
結果のタスクにまとめられる最初のタスク。

*rhs*<br/>
結果のタスクにまとめられる 2 番目のタスク。

### <a name="return-value"></a>戻り値

入力タスクのいずれかが正常に完了したときに正常に完了するタスク。 入力したタスクの種類が `T` である場合、この関数の出力は `task<std::vector<T>` になります。 入力したタスクの種類が `void` である場合、出力のタスクも `task<void>` になります。

### <a name="remarks"></a>解説

両方のタスクがキャンセルまたは例外をスローした場合、返されたタスクはキャンセルされた状態で完了し、例外のいずれかが発生した場合は、そのタスクを呼び出`get()`すときまたはその`wait()`タスクに対してスローされます。

## <a name="operatorampamp-operator"></a><a name="operator_amp_amp"></a>演算子&amp;&amp;演算子

引数として指定されたタスクの両方が正常に完了したときに正常に完了するタスクを作成します。

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

*リターンタイプ*<br/>
返されるタスクの種類。

*lhs*<br/>
結果のタスクにまとめられる最初のタスク。

*rhs*<br/>
結果のタスクにまとめられる 2 番目のタスク。

### <a name="return-value"></a>戻り値

入力した両方のタスクが正常に完了したときに正常に完了するタスク。 入力したタスクの種類が `T` である場合、この関数の出力は `task<std::vector<T>>` になります。 入力したタスクの種類が `void` である場合、出力のタスクも `task<void>` になります。

### <a name="remarks"></a>解説

いずれかのタスクがキャンセルされるか、例外がスローされた場合、返されたタスクは、取り消された状態で早く完了し、例外が発生した場合は、そのタスクを呼び出`get()`すか、`wait()`そのタスクに対してスローされます。

## <a name="operator-operator"></a><a name="operator_eq_eq"></a>演算子== 演算子

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
最初`concurrent_vector`のオブジェクトのアロケーターの種類。

*A2*<br/>
2 番目`concurrent_vector`のオブジェクトのアロケーターの種類。

*_A*<br/>
`concurrent_vector` 型オブジェクト。

*_B*<br/>
`concurrent_vector` 型オブジェクト。

### <a name="return-value"></a>戻り値

演算子の左側の並行ベクトルが、演算子の右側の並行ベクトルと等しい場合は**true。** それ以外**の場合は false。**

### <a name="remarks"></a>解説

2 つの同時実行ベクターは、同じ数の要素を持ち、それぞれの要素の値が同じである場合に等しくなります。 それ以外の場合は等しくありません。

このメソッドは、同時実行ベクター`_A`または`_B`のいずれかを変更できる他のメソッドに関しては、同時実行安全ではありません。

## <a name="operator-operator"></a><a name="operator_neq"></a>演算子!= 演算子

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
最初`concurrent_vector`のオブジェクトのアロケーターの種類。

*A2*<br/>
2 番目`concurrent_vector`のオブジェクトのアロケーターの種類。

*_A*<br/>
`concurrent_vector` 型オブジェクト。

*_B*<br/>
`concurrent_vector` 型オブジェクト。

### <a name="return-value"></a>戻り値

並行ベクトルが等しくない場合は**true。** 同時実行ベクターが等しい場合は**false。**

### <a name="remarks"></a>解説

2 つの同時実行ベクターは、同じ数の要素を持ち、それぞれの要素の値が同じである場合に等しくなります。 それ以外の場合は等しくありません。

このメソッドは、同時実行ベクター`_A`または`_B`のいずれかを変更できる他のメソッドに関しては、同時実行安全ではありません。

## <a name="operatorlt-operator"></a><a name="operator_lt"></a>演算子&lt;演算子

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
最初`concurrent_vector`のオブジェクトのアロケーターの種類。

*A2*<br/>
2 番目`concurrent_vector`のオブジェクトのアロケーターの種類。

*_A*<br/>
`concurrent_vector` 型オブジェクト。

*_B*<br/>
`concurrent_vector` 型オブジェクト。

### <a name="return-value"></a>戻り値

演算子の左側の並行ベクトルが、演算子の右側の並行ベクトルより小さい場合は**true。** それ以外**の場合は false。**

### <a name="remarks"></a>解説

この演算子の動作は、名前空間内のクラスの同等の`vector`演算子と`std`同じです。

このメソッドは、同時実行ベクター`_A`または`_B`のいずれかを変更できる他のメソッドに関しては、同時実行安全ではありません。

## <a name="operatorlt-operator"></a><a name="operator_lt_eq"></a>演算子&lt;= 演算子

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
最初`concurrent_vector`のオブジェクトのアロケーターの種類。

*A2*<br/>
2 番目`concurrent_vector`のオブジェクトのアロケーターの種類。

*_A*<br/>
`concurrent_vector` 型オブジェクト。

*_B*<br/>
`concurrent_vector` 型オブジェクト。

### <a name="return-value"></a>戻り値

演算子の左側の並行ベクトルが、演算子の右側の並行ベクトル以下の場合は**true。** それ以外**の場合は false。**

### <a name="remarks"></a>解説

この演算子の動作は、名前空間内のクラスの同等の`vector`演算子と`std`同じです。

このメソッドは、同時実行ベクター`_A`または`_B`のいずれかを変更できる他のメソッドに関しては、同時実行安全ではありません。

## <a name="operatorgt-operator"></a><a name="operator_gt"></a>演算子&gt;演算子

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
最初`concurrent_vector`のオブジェクトのアロケーターの種類。

*A2*<br/>
2 番目`concurrent_vector`のオブジェクトのアロケーターの種類。

*_A*<br/>
`concurrent_vector` 型オブジェクト。

*_B*<br/>
`concurrent_vector` 型オブジェクト。

### <a name="return-value"></a>戻り値

演算子の左側の並行ベクトルが、演算子の右側の並行ベクトルより大きい場合は**true。** それ以外**の場合は false。**

### <a name="remarks"></a>解説

この演算子の動作は、名前空間内のクラスの同等の`vector`演算子と`std`同じです。

このメソッドは、同時実行ベクター`_A`または`_B`のいずれかを変更できる他のメソッドに関しては、同時実行安全ではありません。

## <a name="operatorgt-operator"></a><a name="operator_gt_eq"></a>演算子&gt;= 演算子

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
最初`concurrent_vector`のオブジェクトのアロケーターの種類。

*A2*<br/>
2 番目`concurrent_vector`のオブジェクトのアロケーターの種類。

*_A*<br/>
`concurrent_vector` 型オブジェクト。

*_B*<br/>
`concurrent_vector` 型オブジェクト。

### <a name="return-value"></a>戻り値

演算子の左側の並行ベクトルが、演算子の右側の並行ベクトル以上の場合は**true。** それ以外**の場合は false。**

### <a name="remarks"></a>解説

この演算子の動作は、名前空間内のクラスの同等の`vector`演算子と`std`同じです。

このメソッドは、同時実行ベクター`_A`または`_B`のいずれかを変更できる他のメソッドに関しては、同時実行安全ではありません。

## <a name="see-also"></a>関連項目

[同時実行名前空間](concurrency-namespace.md)

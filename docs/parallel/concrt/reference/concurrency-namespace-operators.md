---
title: concurrency 名前空間演算子 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- concrt/concurrency::operator!=
- concrt/concurrency:[operator&amp;&amp
dev_langs:
- C++
ms.assetid: 8e373f23-fc8e-49f7-82e6-ba0c57b822f8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 90c8fbbdd0e5d2baf0ba82998a6951242b73203a
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
ms.locfileid: "33693511"
---
# <a name="concurrency-namespace-operators"></a>concurrency 名前空間演算子
||||  
|-|-|-|  
|[operator!=](#operator_neq)|[operator&amp;&amp;](#operator_amp_amp)|[operator&gt;](#operator_gt)|  
|[operator&gt;=](#operator_gt_eq)|[operator&lt;](#operator_lt)|[operator&lt;=](#operator_lt_eq)|  
|[operator==](#operator_eq_eq)|[operator||](#operator_lor)|  
  
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
 `ReturnType`  
 返されるタスクの種類。  
  
 `lhs`  
 結果のタスクにまとめられる最初のタスク。  
  
 `rhs`  
 結果のタスクにまとめられる 2 番目のタスク。  
  
### <a name="return-value"></a>戻り値  
 完了するタスクを正常に入力したタスクのいずれかが正常に完了するとします。 入力したタスクの種類が `T` である場合、この関数の出力は `task<std::vector<T>` になります。 入力したタスクの種類が `void` である場合、出力のタスクも `task<void>` になります。  
  
### <a name="remarks"></a>コメント  
 両方のタスクが取り消されると、例外をスローする場合、返されるタスクは完了して取り消された状態にし、例外のいずれかのいずれかが発生した場合がスローされますを呼び出すと`get()`または`wait()`タスクにします。  
  
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
 `ReturnType`  
 返されるタスクの種類。  
  
 `lhs`  
 結果のタスクにまとめられる最初のタスク。  
  
 `rhs`  
 結果のタスクにまとめられる 2 番目のタスク。  
  
### <a name="return-value"></a>戻り値  
 入力した両方のタスクが正常に完了したときに正常に完了するタスク。 入力したタスクの種類が `T` である場合、この関数の出力は `task<std::vector<T>>` になります。 入力したタスクの種類が `void` である場合、出力のタスクも `task<void>` になります。  
  
### <a name="remarks"></a>コメント  
 タスクのどちらか 1 つが取り消された場合、または例外をスローした場合、返されるタスクは早期に完了し、取り消された状態になります。また例外が発生したときは、そのタスクに対して `get()` または `wait()` を呼び出す場合に、その例外がスローされます。  
  
##  <a name="operator_eq_eq"></a>  演算子 = = 演算子  
 演算子の左側の `concurrent_vector` オブジェクトが右側の `concurrent_vector` オブジェクトと等しいかどうかを調べます。  
  
```  
template<typename T, class A1, class A2>  
inline bool operator== (
    const concurrent_vector<T, A1>& _A,  
    const concurrent_vector<T, A2>& _B);
```  
  
### <a name="parameters"></a>パラメーター  
 `T`  
 同時実行ベクターに格納されている要素のデータ型。  
  
 `A1`  
 1 つ目のアロケーターの型`concurrent_vector`オブジェクト。  
  
 `A2`  
 2 つ目のアロケーターの型`concurrent_vector`オブジェクト。  
  
 `_A`  
 `concurrent_vector` 型のオブジェクト。  
  
 `_B`  
 `concurrent_vector` 型のオブジェクト。  
  
### <a name="return-value"></a>戻り値  
 `true` 演算子の左側にある、同時実行ベクターが演算子の右側にある、同時実行ベクターに等しい場合それ以外の場合`false`です。  
  
### <a name="remarks"></a>コメント  
 同じ数の要素が存在し、対応する要素が同じ値を持つ場合、2 つの同時実行ベクターは等価です。 それ以外の場合は等しくありません。  
  
 このメソッドは同時実行ベクターのいずれかを変更する可能性を他のメソッドは同時実行セーフではありません`_A`または`_B`です。  
  
##  <a name="operator_neq"></a>  operator! = 演算子  
 演算子の左側の `concurrent_vector` オブジェクトが右側の `concurrent_vector` オブジェクトと等しくないかどうかを調べます。  
  
```  
template<typename T, class A1, class A2>  
inline bool operator!= (
    const concurrent_vector<T, A1>& _A,  
    const concurrent_vector<T, A2>& _B);
```  
  
### <a name="parameters"></a>パラメーター  
 `T`  
 同時実行ベクターに格納されている要素のデータ型。  
  
 `A1`  
 1 つ目のアロケーターの型`concurrent_vector`オブジェクト。  
  
 `A2`  
 2 つ目のアロケーターの型`concurrent_vector`オブジェクト。  
  
 `_A`  
 `concurrent_vector` 型のオブジェクト。  
  
 `_B`  
 `concurrent_vector` 型のオブジェクト。  
  
### <a name="return-value"></a>戻り値  
 `true` 同時実行ベクターが等しくない場合`false`同時実行ベクターが等しい場合は。  
  
### <a name="remarks"></a>コメント  
 同じ数の要素が存在し、対応する要素が同じ値を持つ場合、2 つの同時実行ベクターは等価です。 それ以外の場合は等しくありません。  
  
 このメソッドは同時実行ベクターのいずれかを変更する可能性を他のメソッドは同時実行セーフではありません`_A`または`_B`です。  
  
##  <a name="operator_lt"></a>  演算子&lt;演算子  
 演算子の左側の `concurrent_vector` オブジェクトが右側の `concurrent_vector` オブジェクトより小さいかどうかを調べます。  
  
```  
template<typename T, class A1, class A2>  
inline bool operator<(
    const concurrent_vector<T, A1>& _A,  
    const concurrent_vector<T, A2>& _B);
```  
  
### <a name="parameters"></a>パラメーター  
 `T`  
 同時実行ベクターに格納されている要素のデータ型。  
  
 `A1`  
 1 つ目のアロケーターの型`concurrent_vector`オブジェクト。  
  
 `A2`  
 2 つ目のアロケーターの型`concurrent_vector`オブジェクト。  
  
 `_A`  
 `concurrent_vector` 型のオブジェクト。  
  
 `_B`  
 `concurrent_vector` 型のオブジェクト。  
  
### <a name="return-value"></a>戻り値  
 `true` 演算子の左側にある、同時実行ベクターが演算子の右側にある、同時実行ベクターより小さい場合それ以外の場合`false`です。  
  
### <a name="remarks"></a>コメント  
 この演算子の動作は等価演算子と同じ、`vector`クラス内で、`std`名前空間。  
  
 このメソッドは同時実行ベクターのいずれかを変更する可能性を他のメソッドは同時実行セーフではありません`_A`または`_B`です。  
  
##  <a name="operator_lt_eq"></a>  演算子&lt;= 演算子  
 演算子の左側の `concurrent_vector` オブジェクトが右側の  `concurrent_vector` オブジェクト以下かどうかを調べます。  
  
```  
template<typename T, class A1, class A2>  
inline bool operator<= (
    const concurrent_vector<T, A1>& _A,  
    const concurrent_vector<T, A2>& _B);
```  
  
### <a name="parameters"></a>パラメーター  
 `T`  
 同時実行ベクターに格納されている要素のデータ型。  
  
 `A1`  
 1 つ目のアロケーターの型`concurrent_vector`オブジェクト。  
  
 `A2`  
 2 つ目のアロケーターの型`concurrent_vector`オブジェクト。  
  
 `_A`  
 `concurrent_vector` 型のオブジェクト。  
  
 `_B`  
 `concurrent_vector` 型のオブジェクト。  
  
### <a name="return-value"></a>戻り値  
 `true` 演算子の左側にある、同時実行ベクターより小さいか、演算子の右側にある、同時実行ベクターに等しい場合それ以外の場合`false`です。  
  
### <a name="remarks"></a>コメント  
 この演算子の動作は等価演算子と同じ、`vector`クラス内で、`std`名前空間。  
  
 このメソッドは同時実行ベクターのいずれかを変更する可能性を他のメソッドは同時実行セーフではありません`_A`または`_B`です。  
  
##  <a name="operator_gt"></a>  演算子&gt;演算子  
 演算子の左側の `concurrent_vector` オブジェクトが右側の `concurrent_vector` オブジェクトより大きいかどうかを調べます。  
  
```  
template<typename T, class A1, class A2>  
inline bool operator>(
    const concurrent_vector<T, A1>& _A,  
    const concurrent_vector<T, A2>& _B);
```  
  
### <a name="parameters"></a>パラメーター  
 `T`  
 同時実行ベクターに格納されている要素のデータ型。  
  
 `A1`  
 1 つ目のアロケーターの型`concurrent_vector`オブジェクト。  
  
 `A2`  
 2 つ目のアロケーターの型`concurrent_vector`オブジェクト。  
  
 `_A`  
 `concurrent_vector` 型のオブジェクト。  
  
 `_B`  
 `concurrent_vector` 型のオブジェクト。  
  
### <a name="return-value"></a>戻り値  
 `true` 演算子の左側にある、同時実行ベクターが演算子の右側にある、同時実行ベクターを超える場合それ以外の場合`false`です。  
  
### <a name="remarks"></a>コメント  
 この演算子の動作は等価演算子と同じ、`vector`クラス内で、`std`名前空間。  
  
 このメソッドは同時実行ベクターのいずれかを変更する可能性を他のメソッドは同時実行セーフではありません`_A`または`_B`です。  
  
##  <a name="operator_gt_eq"></a>  演算子&gt;= 演算子  
 演算子の左側の `concurrent_vector` オブジェクトが右側の `concurrent_vector` オブジェクト以上であるかどうかを調べます。  
  
```  
template<typename T, class A1, class A2>  
inline bool operator>= (
    const concurrent_vector<T, A1>& _A,  
    const concurrent_vector<T, A2>& _B);
```  
  
### <a name="parameters"></a>パラメーター  
 `T`  
 同時実行ベクターに格納されている要素のデータ型。  
  
 `A1`  
 1 つ目のアロケーターの型`concurrent_vector`オブジェクト。  
  
 `A2`  
 2 つ目のアロケーターの型`concurrent_vector`オブジェクト。  
  
 `_A`  
 `concurrent_vector` 型のオブジェクト。  
  
 `_B`  
 `concurrent_vector` 型のオブジェクト。  
  
### <a name="return-value"></a>戻り値  
 `true` 演算子の左側にある、同時実行ベクターがより大きいか、演算子の右側にある、同時実行ベクターに等しい場合それ以外の場合`false`です。  
  
### <a name="remarks"></a>コメント  
 この演算子の動作は等価演算子と同じ、`vector`クラス内で、`std`名前空間。  
  
 このメソッドは同時実行ベクターのいずれかを変更する可能性を他のメソッドは同時実行セーフではありません`_A`または`_B`です。  
  
## <a name="see-also"></a>関連項目  
 [concurrency 名前空間](concurrency-namespace.md)

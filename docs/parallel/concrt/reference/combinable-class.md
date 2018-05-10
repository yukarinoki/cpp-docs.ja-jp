---
title: combinable クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
f1_keywords:
- combinable
- PPL/concurrency::combinable
- PPL/concurrency::combinable::combinable
- PPL/concurrency::combinable::clear
- PPL/concurrency::combinable::combine
- PPL/concurrency::combinable::combine_each
- PPL/concurrency::combinable::local
dev_langs:
- C++
helpviewer_keywords:
- combinable class
ms.assetid: fe0bfbf6-6250-47da-b8d0-f75369f0b5be
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 695081e6513965a89222d1108c632e2f22580184
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
---
# <a name="combinable-class"></a>combinable クラス
`combinable<T>` オブジェクトは、スレッド プライベートなデータのコピーを提供し、並列アルゴリズムにおいてロック制御不要なスレッド ローカルのサブ計算を実行するために用意されています。 並列操作の最後に、スレッド プライベート サブ計算を最終結果にマージできます。 共有変数に多数の競合が発生する可能性がある場合、共有変数の代わりにこのクラスを使用することにより、パフォーマンスを改善できます。  
  
## <a name="syntax"></a>構文  
  
```
template<typename T>
class combinable;
```  
  
#### <a name="parameters"></a>パラメーター  
 `T`  
 最終的なマージされた結果のデータ型。 種類は、コピー コンス トラクターと既定のコンス トラクターが必要です。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[combinable](#ctor)|オーバーロードされます。 新しい `combinable` オブジェクトを構築します。|  
|[~ combinable デストラクター](#dtor)|`combinable` オブジェクトを破棄します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[clear](#clear)|以前の使用法から中間の計算結果をクリアします。|  
|[combine](#combine)|指定された結合ファンクターを呼び出すことによって、スレッド ローカルのサブ計算のセットから最終的な値を計算します。|  
|[combine_each](#combine_each)|スレッド ローカルのサブ計算ごとに 1 回、指定された結合ファンクタを呼び出すことによって、スレッド ローカルのサブ計算のセットから最終的な値を計算します。 最終的な結果は、関数オブジェクトで累積されます。|  
|[local](#local)|オーバーロードされます。 スレッド プライベート サブ計算への参照を返します。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[operator=](#operator_eq)|割り当てます、`combinable`から別のオブジェクト`combinable`オブジェクト。|  
  
## <a name="remarks"></a>コメント  
 詳細については、次を参照してください。[並列コンテナーと並列オブジェクト](../../../parallel/concrt/parallel-containers-and-objects.md)です。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `combinable`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** ppl.h  
  
 **名前空間:** concurrency  
  
##  <a name="clear"></a> オフ 

 以前の使用法から中間の計算結果をクリアします。  
  
```
void clear();
```  
  
##  <a name="ctor"></a> combinable 

 新しい `combinable` オブジェクトを構築します。  
  
```
combinable();

template <typename _Function>
explicit combinable(_Function _FnInitialize);

combinable(const combinable& _Copy);
```  
  
### <a name="parameters"></a>パラメーター  
 `_Function`  
 初期化ファンクター オブジェクトの型。  
  
 `_FnInitialize`  
 型の新しい各スレッド プライベート値を初期化するために呼び出される関数`T`です。 シグネチャを持つ関数呼び出し演算子をサポートする必要があります`T ()`です。  
  
 `_Copy`  
 既存の`combinable`この 1 つにコピーされるオブジェクト。  
  
### <a name="remarks"></a>コメント  
 最初のコンス トラクターが型の既定のコンス トラクターを持つ新しい要素を初期化します`T`です。  
  
 2 番目のコンス トラクターとして指定された初期化ファンクタを使用して、新しい要素の初期化、`_FnInitialize`パラメーター。  
  
 3 番目のコンス トラクターは、コピー コンス トラクターです。  
  
##  <a name="dtor"></a> ~ combinable 

 `combinable` オブジェクトを破棄します。  
  
```
~combinable();
```  
  
##  <a name="combine"></a> 結合 

 指定された結合ファンクターを呼び出すことによって、スレッド ローカルのサブ計算のセットから最終的な値を計算します。  
  
```
template<typename _Function>
T combine(_Function _FnCombine) const;
```  
  
### <a name="parameters"></a>パラメーター  
 `_Function`  
 2 つのスレッド ローカルのサブ計算を結合する呼び出される関数オブジェクトの型。  
  
 `_FnCombine`  
 サブ計算を結合に使用されるファンクタ。 シグニチャは`T (T, T)`または`T (const T&, const T&)`、結合規則および可換性があります。  
  
### <a name="return-value"></a>戻り値  
 すべてのスレッド プライベート サブ計算を結合した最終的な結果。  
  
##  <a name="combine_each"></a> combine_each 

 スレッド ローカルのサブ計算ごとに 1 回、指定された結合ファンクタを呼び出すことによって、スレッド ローカルのサブ計算のセットから最終的な値を計算します。 最終的な結果は、関数オブジェクトで累積されます。  
  
```
template<typename _Function>
void combine_each(_Function _FnCombine) const;
```  
  
### <a name="parameters"></a>パラメーター  
 `_Function`  
 1 つのスレッド ローカルのサブ計算を結合する呼び出される関数オブジェクトの型。  
  
 `_FnCombine`  
 このファンクターは、1 つのサブ計算を結合するために使用します。 シグニチャは`void (T)`または`void (const T&)`、結合規則および可換にする必要があります。  
  
##  <a name="local"></a> 地元の 

 スレッド プライベート サブ計算への参照を返します。  
  
```
T& local();

T& local(bool& _Exists);
```  
  
### <a name="parameters"></a>パラメーター  
 `_Exists`  
 ブール値への参照。 この引数が参照するブール値に設定されます`true`サブ計算が既にこのスレッドで存在し、設定かどうか`false`このスレッドでの最初のサブ計算の場合。  
  
### <a name="return-value"></a>戻り値  
 スレッド プライベート サブ計算への参照。  
  
##  <a name="operator_eq"></a> 演算子 = 

 割り当てます、`combinable`から別のオブジェクト`combinable`オブジェクト。  
  
```
combinable& operator= (const combinable& _Copy);
```  
  
### <a name="parameters"></a>パラメーター  
 `_Copy`  
 既存の`combinable`この 1 つにコピーされるオブジェクト。  
  
### <a name="return-value"></a>戻り値  
 この `combinable` オブジェクトへの参照。  
  
## <a name="see-also"></a>関連項目  
 [concurrency 名前空間](concurrency-namespace.md)

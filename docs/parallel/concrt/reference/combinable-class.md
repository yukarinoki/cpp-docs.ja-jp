---
title: combinable クラス
ms.date: 11/04/2016
f1_keywords:
- combinable
- PPL/concurrency::combinable
- PPL/concurrency::combinable::combinable
- PPL/concurrency::combinable::clear
- PPL/concurrency::combinable::combine
- PPL/concurrency::combinable::combine_each
- PPL/concurrency::combinable::local
helpviewer_keywords:
- combinable class
ms.assetid: fe0bfbf6-6250-47da-b8d0-f75369f0b5be
ms.openlocfilehash: 05256516c0a693a282b8d0de56d6c9e7465f2740
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/04/2019
ms.locfileid: "57299974"
---
# <a name="combinable-class"></a>combinable クラス

`combinable<T>` オブジェクトは、スレッド プライベートなデータのコピーを提供し、並列アルゴリズムにおいてロック制御不要なスレッド ローカルのサブ計算を実行するために用意されています。 並列操作の最後に、スレッド プライベート サブ計算を最終結果にマージできます。 共有変数に多数の競合が発生する可能性がある場合、共有変数の代わりにこのクラスを使用することにより、パフォーマンスを改善できます。

## <a name="syntax"></a>構文

```
template<typename T>
class combinable;
```

#### <a name="parameters"></a>パラメーター

*T*<br/>
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
|[combine_each](#combine_each)|スレッド ローカルのサブ計算ごとに 1 回、指定された結合ファンクターを呼び出すことによって、スレッド ローカルのサブ計算のセットから最終的な値を計算します。 関数オブジェクトによって、最終的な結果が累積されます。|
|[local](#local)|オーバーロードされます。 スレッド プライベート サブ計算への参照を返します。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[operator=](#operator_eq)|割り当てられます、`combinable`から別のオブジェクト`combinable`オブジェクト。|

## <a name="remarks"></a>Remarks

詳細については、[並列コンテナーとオブジェクト](../../../parallel/concrt/parallel-containers-and-objects.md)を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

`combinable`

## <a name="requirements"></a>必要条件

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

*_Function*<br/>
初期化ファンクター オブジェクトの型。

*_FnInitialize*<br/>
型の新しい各スレッド プライベート値を初期化するために呼び出される関数`T`します。 シグネチャを持つ関数呼び出し演算子をサポートする必要があります`T ()`します。

*_Copy*<br/>
既存の`combinable`この 1 つにコピーされるオブジェクト。

### <a name="remarks"></a>Remarks

最初のコンス トラクターが型の既定のコンス トラクターを持つ新しい要素を初期化します`T`します。

2 番目のコンス トラクターによって初期化として指定された初期化ファンクタを使用して新しい要素、`_FnInitialize`パラメーター。

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

*_Function*<br/>
2 つのスレッド ローカルのサブ計算を結合するときに呼び出される関数オブジェクトの型。

*_FnCombine*<br/>
このファンクターは、サブ計算を結合するために使用します。 シグニチャは`T (T, T)`または`T (const T&, const T&)`、連想と可換性があります。

### <a name="return-value"></a>戻り値

すべてのスレッド プライベート サブ計算を組み合わせることの最終結果。

##  <a name="combine_each"></a> combine_each

スレッド ローカルのサブ計算ごとに 1 回、指定された結合ファンクターを呼び出すことによって、スレッド ローカルのサブ計算のセットから最終的な値を計算します。 関数オブジェクトによって、最終的な結果が累積されます。

```
template<typename _Function>
void combine_each(_Function _FnCombine) const;
```

### <a name="parameters"></a>パラメーター

*_Function*<br/>
スレッド ローカルの 1 つのサブ計算を結合するときに呼び出される関数オブジェクトの型。

*_FnCombine*<br/>
このファンクターは、1 つのサブ計算を結合するために使用します。 シグニチャは`void (T)`または`void (const T&)`、連想と可換的である必要があります。

##  <a name="local"></a> 地元の

スレッド プライベート サブ計算への参照を返します。

```
T& local();

T& local(bool& _Exists);
```

### <a name="parameters"></a>パラメーター

*_Exists*<br/>
ブール値への参照。 この引数によって参照されるブール値に設定されます**true**サブ計算が既にこのスレッドで存在し、設定かどうか**false**場合、これは、このスレッドで最初のサブ計算します。

### <a name="return-value"></a>戻り値

スレッド プライベート サブ計算への参照。

##  <a name="operator_eq"></a> 演算子 =

割り当てられます、`combinable`から別のオブジェクト`combinable`オブジェクト。

```
combinable& operator= (const combinable& _Copy);
```

### <a name="parameters"></a>パラメーター

*_Copy*<br/>
既存の`combinable`この 1 つにコピーされるオブジェクト。

### <a name="return-value"></a>戻り値

この `combinable` オブジェクトへの参照。

## <a name="see-also"></a>関連項目

[コンカレンシー名前空間](concurrency-namespace.md)

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
ms.openlocfilehash: d445b8ac1d2a8487e9e1ec4f21f63cf5ef071e91
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87224969"
---
# <a name="combinable-class"></a>combinable クラス

`combinable<T>` オブジェクトは、スレッド プライベートなデータのコピーを提供し、並列アルゴリズムにおいてロック制御不要なスレッド ローカルのサブ計算を実行するために用意されています。 並列操作の最後に、スレッド プライベート サブ計算を最終結果にマージできます。 共有変数に多数の競合が発生する可能性がある場合、共有変数の代わりにこのクラスを使用することにより、パフォーマンスを改善できます。

## <a name="syntax"></a>構文

```cpp
template<typename T>
class combinable;
```

### <a name="parameters"></a>パラメーター

*T*<br/>
最終的にマージされた結果のデータ型。 型には、コピーコンストラクターと既定のコンストラクターが必要です。

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|[説明]|
|----------|-----------------|
|[組み合わせ](#ctor)|オーバーロードされます。 新しい `combinable` オブジェクトを構築します。|
|[~ の組み合わせ可能デストラクター](#dtor)|`combinable` オブジェクトを破棄します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|[説明]|
|----------|-----------------|
|[オフ](#clear)|以前の使用状況からのすべての中間計算結果を消去します。|
|[結合](#combine)|指定された結合ファンクタを呼び出して、スレッドローカルサブ計算のセットから最終的な値を計算します。|
|[combine_each](#combine_each)|指定された結合ファンをスレッドローカルサブ計算ごとに1回呼び出して、スレッドローカルサブ計算のセットから最終的な値を計算します。 最終的な結果は、関数オブジェクトによって累積されます。|
|[地元の](#local)|オーバーロードされます。 スレッドプライベートサブ計算への参照を返します。|

### <a name="public-operators"></a>パブリック演算子

|名前|[説明]|
|----------|-----------------|
|[operator =](#operator_eq)|`combinable`別のオブジェクトからオブジェクトにを割り当て `combinable` ます。|

## <a name="remarks"></a>解説

詳細については、「[並列コンテナーとオブジェクト](../../../parallel/concrt/parallel-containers-and-objects.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

`combinable`

## <a name="requirements"></a>必要条件

**ヘッダー:** ppl

**名前空間:** concurrency

## <a name="clear"></a><a name="clear"></a>クリア

以前の使用状況からのすべての中間計算結果を消去します。

```cpp
void clear();
```

## <a name="combinable"></a><a name="ctor"></a>組み合わせ

新しい `combinable` オブジェクトを構築します。

```cpp
combinable();

template <typename _Function>
explicit combinable(_Function _FnInitialize);

combinable(const combinable& _Copy);
```

### <a name="parameters"></a>パラメーター

*_Function*<br/>
初期化ファンクタオブジェクトの型。

*_FnInitialize*<br/>
型の新しいスレッドプライベート値を初期化するために呼び出される関数 `T` 。 シグネチャを持つ関数呼び出し演算子をサポートする必要があり `T ()` ます。

*_Copy*<br/>
`combinable`このオブジェクトにコピーされる既存のオブジェクト。

### <a name="remarks"></a>解説

最初のコンストラクターは、型の既定のコンストラクターを使用して新しい要素を初期化し `T` ます。

2番目のコンストラクターは、パラメーターとして指定された初期化ファンを使用して、新しい要素を初期化し `_FnInitialize` ます。

3番目のコンストラクターは、コピーコンストラクターです。

## <a name="combinable"></a><a name="dtor"></a>~ の組み合わせ可能

`combinable` オブジェクトを破棄します。

```cpp
~combinable();
```

## <a name="combine"></a><a name="combine"></a>結合

指定された結合ファンクタを呼び出して、スレッドローカルサブ計算のセットから最終的な値を計算します。

```cpp
template<typename _Function>
T combine(_Function _FnCombine) const;
```

### <a name="parameters"></a>パラメーター

*_Function*<br/>
2つのスレッドローカルサブ計算を結合するために呼び出される関数オブジェクトの型。

*_FnCombine*<br/>
サブ計算を結合するために使用されるファンクタ。 その署名は `T (T, T)` または `T (const T&, const T&)` であり、結合と可換である必要があります。

### <a name="return-value"></a>戻り値

すべてのスレッドプライベートサブ計算の最終的な結果。

## <a name="combine_each"></a><a name="combine_each"></a>combine_each

指定された結合ファンをスレッドローカルサブ計算ごとに1回呼び出して、スレッドローカルサブ計算のセットから最終的な値を計算します。 最終的な結果は、関数オブジェクトによって累積されます。

```cpp
template<typename _Function>
void combine_each(_Function _FnCombine) const;
```

### <a name="parameters"></a>パラメーター

*_Function*<br/>
1つのスレッドローカルのサブ計算を結合するために呼び出される関数オブジェクトの型。

*_FnCombine*<br/>
1つのサブ計算を結合するために使用されるファンクタ。 その署名は `void (T)` または `void (const T&)` であり、結合および可換である必要があります。

## <a name="local"></a><a name="local"></a>地元の

スレッドプライベートサブ計算への参照を返します。

```cpp
T& local();

T& local(bool& _Exists);
```

### <a name="parameters"></a>パラメーター

*_Exists*<br/>
ブール値への参照。 この引数によって参照されるブール値は、このスレッドにサブ計算が既に存在する場合はに設定され、この **`true`** **`false`** スレッドの最初のサブ計算である場合はに設定されます。

### <a name="return-value"></a>戻り値

スレッドプライベートサブ計算への参照。

## <a name="operator"></a><a name="operator_eq"></a>operator =

`combinable`別のオブジェクトからオブジェクトにを割り当て `combinable` ます。

```cpp
combinable& operator= (const combinable& _Copy);
```

### <a name="parameters"></a>パラメーター

*_Copy*<br/>
`combinable`このオブジェクトにコピーされる既存のオブジェクト。

### <a name="return-value"></a>戻り値

この `combinable` オブジェクトへの参照。

## <a name="see-also"></a>関連項目

[concurrency 名前空間](concurrency-namespace.md)

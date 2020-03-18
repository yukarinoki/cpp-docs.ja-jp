---
title: Platform::Collections::BackInsertIterator クラス
ms.date: 03/27/2019
ms.topic: reference
f1_keywords:
- COLLECTION/Platform::Collections::BackInsertIterator::BackInsertIterator
helpviewer_keywords:
- BackInsertIterator Class
ms.assetid: aecee1ff-100d-4129-b84b-1966f0923dbf
ms.openlocfilehash: 79854d8ead089aeba88fbdc151fdc0788dd181c1
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/17/2020
ms.locfileid: "79445784"
---
# <a name="platformcollectionsbackinsertiterator-class"></a>Platform::Collections::BackInsertIterator クラス

要素を上書きするのではなく、シーケンシャル コレクションの末尾に要素を挿入する反復子を表します。

## <a name="syntax"></a>構文

```
template <typename T>
class BackInsertIterator :
public ::std::iterator<::std::output_iterator_tag, void, void, void, void>;
```

#### <a name="parameters"></a>パラメーター

*T*<br/>
現在のコレクション内の項目の型。

### <a name="remarks"></a>コメント

BackInsertIterator クラスは、 [back_insert_iterator Class](../standard-library/back-insert-iterator-class.md)が要求する規則を実装します。

### <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|Name|説明|
|----------|-----------------|
|[BackInsertIterator:: Backtiterator](#ctor)|BackInsertIterator クラスの新しいインスタンスを初期化します。|

### <a name="public-operators"></a>パブリック演算子

|Name|説明|
|----------|-----------------|
|[BackInsertIterator::operator* 演算子](#operator-dereference)|現在の BackInsertIterator への参照を取得します。|
|[BackInsertIterator::operator++ 演算子](#operator-increment)|現在の BackInsertIterator への参照を返します。 反復子は変更されません。|
|[BackInsertIterator::operator= 演算子](#operator-assign)|指定されたオブジェクトを、現在のシーケンシャル コレクションの末尾に追加します。|

## <a name="inheritance-hierarchy"></a>継承階層

`BackInsertIterator`

### <a name="requirements"></a>要件

**ヘッダー:** collection.h

**名前空間:** Platform::Collections

## <a name="ctor"></a>BackInsertIterator:: Backの Titerator コンストラクター

`BackInsertIterator` クラスの新しいインスタンスを初期化します。

## <a name="syntax"></a>構文

```
explicit BackInsertIterator(
   Windows::Foundation::Collections::IVector<T>^ v);
```

#### <a name="parameters"></a>パラメーター

*v*<br/>
IVector\<T > オブジェクト。

### <a name="remarks"></a>コメント

`BackInsertIterator` は、`v` パラメーターで指定されたオブジェクトの最後の要素の後に要素を挿入します。

## <a name="operator-assign"></a>BackInsertIterator:: operator = 演算子

指定されたオブジェクトを、現在のシーケンシャル コレクションの末尾に追加します。

## <a name="syntax"></a>構文

```
BackInsertIterator& operator=( const T& t);
```

#### <a name="parameters"></a>パラメーター

*t*<br/>
現在のコレクションに追加するオブジェクト。

### <a name="return-value"></a>戻り値

現在の BackInsertIterator への参照。

## <a name="operator-dereference"></a>BackInsertIterator:: operator * 演算子

現在の BackInsertIterator への参照を取得します。

## <a name="syntax"></a>構文

```
BackInsertIterator& operator*();
```

### <a name="return-value"></a>戻り値

現在の BackInsertIterator への参照。

### <a name="remarks"></a>コメント

この演算子は、現在のコレクション内の要素ではなく、現在の BackInsertIterator への参照を返します。

## <a name="operator-increment"></a>BackInsertIterator:: operator + + 演算子

現在の BackInsertIterator への参照を返します。 反復子は変更されません。

## <a name="syntax"></a>構文

```
BackInsertIterator& operator++();

BackInsertIterator operator++(int);
```

### <a name="return-value"></a>戻り値

現在の BackInsertIterator への参照。

### <a name="remarks"></a>コメント

仕様では、最初の構文は現在の BackInsertIterator に前置インクリメント演算を行い、2 つ目の構文は現在の BackInsertIterator に後置インクリメント演算を行います。 2 つ目の構文の `int` 型は、実際の整数オペランドではなく後置インクリメント演算を示します。

ただし、この演算子は実際には BackInsertIterator を変更しません。 代わりに、この演算子は変更されていない現在の反復子への参照を返します。 これは、 [operator *](#operator-dereference)と同じ動作です。

## <a name="see-also"></a>参照

[Platform 名前空間](platform-namespace-c-cx.md)

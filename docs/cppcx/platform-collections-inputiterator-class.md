---
description: '詳細情報: Platform:: Collections:: InputIterator クラス'
title: Platform::Collections::InputIterator クラス
ms.date: 03/27/2019
ms.topic: reference
f1_keywords:
- COLLECTION/Platform::Collections::InputIterator::InputIterator
helpviewer_keywords:
- InputIterator Class
ms.assetid: ef72eea4-32a9-42b9-8119-ce87dbdcd3be
ms.openlocfilehash: 7345435c57c75c04f0eb30d9773d655d713853de
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97283957"
---
# <a name="platformcollectionsinputiterator-class"></a>Platform::Collections::InputIterator クラス

Windows ランタイムから派生したコレクションの標準テンプレートライブラリ InputIterator を提供します。

## <a name="syntax"></a>構文

```
template <typename X>
class InputIterator;
```

#### <a name="parameters"></a>パラメーター

*X*<br/>
InputIterator テンプレート クラスの型名。

### <a name="members"></a>メンバー

### <a name="public-typedefs"></a>パブリック typedef

|名前|説明|
|----------|-----------------|
|`difference_type`|ポインターの相違点 (ptrdiff_t)。|
|`iterator_category`|入力反復子のカテゴリ (::std::input_iterator_tag)。|
|`pointer`|へのポインター。 `const X`|
|`reference`|への参照。 `const X`|
|`value_type`|`X` 型名。|

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[InputIterator:: InputIterator](#ctor)|InputIterator クラスの新しいインスタンスを初期化します。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[InputIterator:: operator! = 演算子](#operator-inequality)|現在の InputIterator が、指定された InputIterator と等しくないかどうかを示します。|
|[InputIterator::operator* 演算子](#operator-dereference)|現在の InputIterator により指定された要素への参照を取得します。|
|[InputIterator:: operator + + 演算子](#operator-increment)|現在の InputIterator をインクリメントします。|
|[InputIterator:: operator = = 演算子](#operator-equality)|現在の InputIterator が、指定された InputIterator と等しいかどうかを示します。|
|[InputIterator:: operator-> 演算子](#operator-arrow)|現在の InputIterator により参照される要素のアドレスを取得します。|

## <a name="inheritance-hierarchy"></a>継承階層

`InputIterator`

### <a name="requirements"></a>要件

**ヘッダー:** collection.h

**名前空間:** Platform::Collections

## <a name="inputiteratorinputiterator-constructor"></a><a name="ctor"></a> InputIterator:: InputIterator コンストラクター

InputIterator クラスの新しいインスタンスを初期化します。

### <a name="syntax"></a>構文

```
InputIterator();
explicit InputIterator(Windows::Foundation::Collections<X>^ iterator);
```

### <a name="parameters"></a>パラメーター

*iterator*<br/>
反復子オブジェクト。

## <a name="inputiteratoroperator-gt-operator"></a><a name="operator-arrow"></a> InputIterator:: operator- &gt; 演算子

現在の InputIterator により指定される要素のアドレスを取得します。

### <a name="syntax"></a>構文

```
pointer operator->() const;
```

### <a name="return-value"></a>戻り値

現在の InputIterator により指定される要素のアドレス。

## <a name="inputiteratoroperator-operator"></a><a name="operator-dereference"></a> InputIterator:: operator \* 演算子

現在の InputIterator により指定された要素への参照を取得します。

### <a name="syntax"></a>構文

```
reference operator*() const;
```

### <a name="return-value"></a>戻り値

現在の InputIterator により指定された要素。

## <a name="inputiteratoroperator-operator"></a><a name="operator-equality"></a> InputIterator:: operator = = 演算子

現在の InputIterator が、指定された InputIterator と等しいかどうかを示します。

### <a name="syntax"></a>構文

```
bool operator== (const InputIterator& other) const;
```

### <a name="parameters"></a>パラメーター

*他の*<br/>
別の InputIterator。

### <a name="return-value"></a>戻り値

**`true`** 現在の InputIterator が *other* と等しい場合は。それ以外の場合は **`false`** 。

## <a name="inputiteratoroperator-operator"></a><a name="operator-increment"></a> InputIterator:: operator + + 演算子

現在の InputIterator をインクリメントします。

### <a name="syntax"></a>構文

```
InputIterator& operator++();
InputIterator operator++(int);
```

### <a name="return-value"></a>戻り値

最初の構文は、現在の InputIterator をインクリメントしてから返します。 2 番目の構文は、現在の InputIterator のコピーを返し、現在の InputIterator をインクリメントします。

### <a name="remarks"></a>解説

最初の InputIterator 構文は、現在の InputIterator の前置インクリメントを実行します。

2 番目の構文は、現在の InputIterator の後置インクリメントを実行します。 **`int`** 2 番目の構文の型は、実際の整数オペランドではなく、後置インクリメント演算を示します。

## <a name="inputiteratoroperator-operator"></a><a name="operator-inequality"></a> InputIterator:: operator! = 演算子

現在の InputIterator が、指定された InputIterator と等しくないかどうかを示します。

### <a name="syntax"></a>構文

```
bool operator!=(const InputIterator& other) const;
```

### <a name="parameters"></a>パラメーター

*他の*<br/>
別の InputIterator。

### <a name="return-value"></a>戻り値

**`true`** 現在の InputIterator が *other* と等しくない場合は。それ以外の場合は **`false`** 。

## <a name="see-also"></a>関連項目

[Platform 名前空間](platform-namespace-c-cx.md)

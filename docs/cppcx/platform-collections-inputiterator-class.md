---
title: Platform::Collections::InputIterator クラス
ms.date: 03/27/2019
ms.topic: reference
f1_keywords:
- COLLECTION/Platform::Collections::InputIterator::InputIterator
helpviewer_keywords:
- InputIterator Class
ms.assetid: ef72eea4-32a9-42b9-8119-ce87dbdcd3be
ms.openlocfilehash: 92f9b15f474a5aa3d063f0ccfb663f56baf8de31
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81354561"
---
# <a name="platformcollectionsinputiterator-class"></a>Platform::Collections::InputIterator クラス

Windows ランタイムから派生したコレクションの標準テンプレート ライブラリ入力 Iterator を提供します。

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
|`pointer`|へのポインタ`const X`|
|`reference`|への参照`const X`|
|`value_type`|`X` 型名。|

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[入力反復器::入力反復器](#ctor)|InputIterator クラスの新しいインスタンスを初期化します。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[入力反復器::演算子!= 演算子](#operator-inequality)|現在の InputIterator が、指定された InputIterator と等しくないかどうかを示します。|
|[InputIterator::operator* 演算子](#operator-dereference)|現在の InputIterator により指定された要素への参照を取得します。|
|[入力反復器::演算子++ 演算子](#operator-increment)|現在の InputIterator をインクリメントします。|
|[入力反復器::演算子== 演算子](#operator-equality)|現在の InputIterator が、指定された InputIterator と等しいかどうかを示します。|
|[入力反復演算子::演算子>演算子](#operator-arrow)|現在の InputIterator により参照される要素のアドレスを取得します。|

## <a name="inheritance-hierarchy"></a>継承階層

`InputIterator`

### <a name="requirements"></a>必要条件

**ヘッダー:** collection.h

**名前空間:** Platform::Collections

## <a name="inputiteratorinputiterator-constructor"></a><a name="ctor"></a>入力反復器::入力反復器コンストラクタ

InputIterator クラスの新しいインスタンスを初期化します。

### <a name="syntax"></a>構文

```
InputIterator();
explicit InputIterator(Windows::Foundation::Collections<X>^ iterator);
```

### <a name="parameters"></a>パラメーター

*反復 子*<br/>
反復子オブジェクト。

## <a name="inputiteratoroperator-gt-operator"></a><a name="operator-arrow"></a>入力反復器::演算子 -&gt;演算子

現在の InputIterator により指定される要素のアドレスを取得します。

### <a name="syntax"></a>構文

```
pointer operator->() const;
```

### <a name="return-value"></a>戻り値

現在の InputIterator により指定される要素のアドレス。

## <a name="inputiteratoroperator-operator"></a><a name="operator-dereference"></a>入力反復器::演算子\*

現在の InputIterator により指定された要素への参照を取得します。

### <a name="syntax"></a>構文

```
reference operator*() const;
```

### <a name="return-value"></a>戻り値

現在の InputIterator により指定された要素。

## <a name="inputiteratoroperator-operator"></a><a name="operator-equality"></a>入力反復器::演算子== 演算子

現在の InputIterator が、指定された InputIterator と等しいかどうかを示します。

### <a name="syntax"></a>構文

```
bool operator== (const InputIterator& other) const;
```

### <a name="parameters"></a>パラメーター

*他*<br/>
別の InputIterator。

### <a name="return-value"></a>戻り値

現在の InputIterator が*他*の値と等しい場合は**true。** それ以外の場合**は false。**

## <a name="inputiteratoroperator-operator"></a><a name="operator-increment"></a>入力反復器::演算子++ 演算子

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

2 番目の構文は、現在の InputIterator の後置インクリメントを実行します。 2 つ目の構文の `int` 型は、実際の整数オペランドではなく後置インクリメント演算を示します。

## <a name="inputiteratoroperator-operator"></a><a name="operator-inequality"></a>入力反復器::演算子!= 演算子

現在の InputIterator が、指定された InputIterator と等しくないかどうかを示します。

### <a name="syntax"></a>構文

```
bool operator!=(const InputIterator& other) const;
```

### <a name="parameters"></a>パラメーター

*他*<br/>
別の InputIterator。

### <a name="return-value"></a>戻り値

現在の InputIterator が*他*の値と等しくない場合は**true。** それ以外の場合**は false。**

## <a name="see-also"></a>関連項目

[プラットフォーム名前空間](platform-namespace-c-cx.md)

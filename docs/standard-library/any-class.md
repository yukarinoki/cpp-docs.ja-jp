---
title: 任意のクラス
ms.date: 04/04/2019
f1_keywords:
- any/std::any
- any/std::any::emplace
- any/std::any::has_value
- any/std::any::reset
- any/std::any::swap
- any/std::any::type
helpviewer_keywords:
- any/std::any
- any/std::any::emplace
- any/std::any::has_value
- any/std::any::reset
- any/std::any::swap
- any/std::any::type
ms.openlocfilehash: defec0f6ab8f59219afddcefc67ea93435347978
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/25/2020
ms.locfileid: "88844744"
---
# <a name="any-class"></a>任意のクラス

コンストラクターの要件を満たす任意の型のインスタンスを格納します。または、クラスのオブジェクトの状態と呼ばれる値も持っていません。

格納されているインスタンスは、含まれている値と呼ばれます。 両方の状態に値がない場合、または両方に値があり、含まれている値が同じ場合、2つの状態は同じになります。

## <a name="syntax"></a>構文

```cpp
class any
```

## <a name="members"></a>メンバー

### <a name="constructors"></a>コンストラクター

|名前|説明|
|-|-|
|[いつ](#any)|`any` 型のオブジェクトを構築します。|

### <a name="functions"></a>Functions

|名前|説明|
|-|-|
|[emplace](#emplace)|任意の値を設定します。|
|[has_value](#has_value)|**`true`** に値がある場合はを返します。|
|[reset](#reset)|Any をリセットします。|
|[スワップ](#swap)|2つのオブジェクトを交換します。|
|[type](#type)|任意の型を返します。|

### <a name="operators"></a>演算子

|名前|説明|
|-|-|
|[operator =](#op_eq)|Any を別ののコピーで置き換えます。|

## <a name="any"></a><a name="any"></a> いつ

`any` 型のオブジェクトを構築します。 には、デストラクターも含まれています。

```cpp
constexpr any() noexcept;
any(const any& other);
any(any&& other) noexcept;
template <class T>
    any(T&& value);
template <class T, class... Args>
    explicit any(in_place_type_t<T>, Args&&...);
template <class T, class U, class... Args>
    explicit any(in_place_type_t<T>, initializer_list<U>, Args&&...);

~any();
```

## <a name="emplace"></a><a name="emplace"></a> emplace

任意の値を設定します。

```cpp
template <class T, class... Args>
    decay_t<T>& emplace(Args&& ...);
template <class T, class U, class... Args>
    decay_t<T>& emplace(initializer_list<U>, Args&&...);
```

## <a name="has_value"></a><a name="has_value"></a> has_value

**`true`** に値がある場合はを返します。

```cpp
bool has_value() const noexcept;
```

## <a name="operator"></a><a name="op_eq"></a> operator =

Any を別ののコピーで置き換えます。

```cpp
any& operator=(const any& right);
any& operator=(any&& right) noexcept;
template <class T>
    any& operator=(T&& right);
```

### <a name="parameters"></a>パラメーター

*そうです*\
Any にコピーされる。

## <a name="reset"></a><a name="reset"></a> 解除

Any をリセットします。

```cpp
void reset() noexcept;
```

## <a name="swap"></a><a name="swap"></a> フォト

2つのオブジェクトを交換します。

```cpp
void swap(any& rhs) noexcept;
```

## <a name="type"></a><a name="type"></a> 型

任意の型を返します。

```cpp
const type_info& type() const noexcept;
```

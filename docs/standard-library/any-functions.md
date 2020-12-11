---
description: '詳細情報: &lt; 任意の &gt; 関数'
title: '&lt;任意の &gt; 関数'
ms.date: 04/04/2019
f1_keywords:
- any/std::any_cast
- any/std::make_any
- any/std::swap
ms.openlocfilehash: 03f699ac5c48962bb32a604a885bc0b3c60c8b22
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97163393"
---
# <a name="ltanygt-functions"></a>&lt;任意の &gt; 関数

## <a name="any_cast"></a><a name="any_cast"></a> any_cast

オブジェクトを任意のに作成します。

```cpp
template<class T>
    T any_cast(const any& operand);
template<class T>
    T any_cast(any& operand);
template<class T>
    T any_cast(any&& operand);
template<class T>
    const T* any_cast(const any* operand) noexcept;
template<class T>
    T* any_cast(any* operand) noexcept;
```

## <a name="make_any"></a><a name="make_any"></a> make_any

値を受け取り、任意のオブジェクトを作成します。

```cpp
template <class T, class... Args>
    any make_any(Args&& ...args);
template <class T, class U, class... Args>
    any make_any(initializer_list<U> il, Args&& ...args);
```

## <a name="swap"></a><a name="swap"></a> フォト

2つのオブジェクトの要素を交換します。

```cpp
void swap(any& left, any& right) noexcept;
```

### <a name="parameters"></a>パラメーター

*左側*\
`any` 型のオブジェクト。

*そうです*\
`any` 型のオブジェクト。

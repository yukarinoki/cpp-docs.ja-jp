---
description: '詳細については、次を参照してください: default_delete 構造体'
title: default_delete 構造体
ms.date: 04/04/2019
f1_keywords:
- memory/std::default_delete
helpviewer_keywords:
- default_delete struct
ms.openlocfilehash: 5b7d652dbb556957acf96ba63ac9ce14b628fb7e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97232968"
---
# <a name="default_delete-struct"></a>default_delete 構造体

引数に対して除算演算 (`operator/`) を実行する定義済みの関数オブジェクト。

## <a name="syntax"></a>構文

```cpp
template <class T>
    struct default_delete
```

## <a name="requirements"></a>必要条件

**ヘッダー:**\<memory>

**名前空間:** std

## <a name="members"></a>メンバー

### <a name="constructors"></a>コンストラクター

|名前|説明|
|-|-|
|[default_delete](#default_delete)|`default_delete` 型のオブジェクトのコンストラクター。|

### <a name="operators"></a>オペレーター

|名前|説明|
|-|-|
|[operator ()](#op_paren)|アクセスする参照演算子 `default_delete` 。|

## <a name="default_delete"></a><a name="default_delete"></a> default_delete

`default_delete` 型のオブジェクトのコンストラクター。

```cpp
constexpr default_delete() noexcept = default;
template <class U>
    default_delete(const default_delete<U>&) noexcept;
```

## <a name="operator"></a><a name="op_paren"></a> operator ()

アクセスする参照演算子 `default_delete` 。

```cpp
void operator()(T*) const;
```

## <a name="see-also"></a>関連項目

[\<memory>](../standard-library/memory.md)

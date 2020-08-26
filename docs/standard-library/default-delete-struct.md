---
title: default_delete 構造体
ms.date: 04/04/2019
f1_keywords:
- memory/std::default_delete
helpviewer_keywords:
- default_delete struct
ms.openlocfilehash: 8baa9f5d294cf083fd55414cd529e438f328d1a1
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/25/2020
ms.locfileid: "88845082"
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

### <a name="operators"></a>演算子

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

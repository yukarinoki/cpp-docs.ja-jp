---
title: '&lt;system_error&gt; 関数'
ms.date: 03/15/2019
f1_keywords:
- system_error/std::generic_category
- system_error/std::make_error_code
- system_error/std::make_error_condition
- system_error/std::system_category
ms.assetid: 57d6f15f-f0b7-4e2f-80fe-31d3c320ee33
helpviewer_keywords:
- std::generic_category
- std::make_error_code
- std::make_error_condition
- std::system_category
ms.openlocfilehash: 2ddeb256c974294e2e46d516219a6b5b0cac3ae2
ms.sourcegitcommit: 8e285a766523e653aeeb34d412dc6f615ef7b17b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/21/2020
ms.locfileid: "80076356"
---
# <a name="ltsystem_errorgt-functions"></a>&lt;system_error&gt; 関数

## <a name="generic_category"></a><a name="generic_category"></a>generic_category

一般的なエラーのカテゴリを表します。

```cpp
const error_category& generic_category() noexcept;
```

### <a name="remarks"></a>解説

`generic_category` オブジェクトは[error_category](../standard-library/error-category-class.md)の実装です。

## <a name="is_error_code_enum_v"></a><a name="is_error_code_enum_v"></a>is_error_code_enum_v

```cpp
template <class T>
    inline constexpr bool is_error_code_enum_v = is_error_code_enum<T>::value;
```

## <a name="is_error_condition_enum_v"></a><a name="is_error_condition_enum_v"></a>is_error_condition_enum_v

```cpp
template <class T>
    inline constexpr bool is_error_condition_enum_v = is_error_condition_enum<T>::value;
```

## <a name="make_error_code"></a><a name="make_error_code"></a>make_error_code

エラー コード オブジェクトを作成します。

```cpp
error_code make_error_code(std::errc error) noexcept;
```

### <a name="parameters"></a>パラメーター

*エラー*\
エラーコードオブジェクトに格納する `std::errc` 列挙値。

### <a name="return-value"></a>戻り値

エラー コード オブジェクト。

### <a name="remarks"></a>解説

## <a name="make_error_condition"></a><a name="make_error_condition"></a>make_error_condition

エラー条件オブジェクトを作成します。

```cpp
error_condition make_error_condition(std::errc error) noexcept;
```

### <a name="parameters"></a>パラメーター

*エラー*\
エラーコードオブジェクトに格納する `std::errc` 列挙値。

### <a name="return-value"></a>戻り値

エラー条件オブジェクト。

### <a name="remarks"></a>解説

## <a name="system_category"></a><a name="system_category"></a>system_category

低レベル システム オーバーフローによって発生したエラーのカテゴリを表します。

```cpp
const error_category& system_category() noexcept;
```

### <a name="remarks"></a>解説

`system_category` オブジェクトは[error_category](../standard-library/error-category-class.md)の実装です。

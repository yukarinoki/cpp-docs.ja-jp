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
ms.openlocfilehash: 78be83af678b553babbf1cde3d96c1507940b611
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62412112"
---
# <a name="ltsystemerrorgt-functions"></a>&lt;system_error&gt; 関数

||||
|-|-|-|
|[generic_category](#generic_category)|[make_error_code](#make_error_code)|[make_error_condition](#make_error_condition)|
|[system_category](#system_category)|||

## <a name="generic_category"></a> generic_category

一般的なエラーのカテゴリを表します。

```cpp
const error_category& generic_category() noexcept;
```

### <a name="remarks"></a>Remarks

`generic_category`オブジェクトの実装は、 [error_category](../standard-library/error-category-class.md)します。

## <a name="make_error_code"></a>  make_error_code

エラー コード オブジェクトを作成します。

```cpp
error_code make_error_code(std::errc error) noexcept;
```

### <a name="parameters"></a>パラメーター

*エラー*\
`std::errc`エラー コード オブジェクトに格納する列挙値。

### <a name="return-value"></a>戻り値

エラー コード オブジェクト。

### <a name="remarks"></a>Remarks

## <a name="make_error_condition"></a>  make_error_condition

エラー条件オブジェクトを作成します。

```cpp
error_condition make_error_condition(std::errc error) noexcept;
```

### <a name="parameters"></a>パラメーター

*エラー*\
`std::errc`エラー コード オブジェクトに格納する列挙値。

### <a name="return-value"></a>戻り値

エラー条件オブジェクト。

### <a name="remarks"></a>Remarks

## <a name="system_category"></a>  system_category

低レベル システム オーバーフローによって発生したエラーのカテゴリを表します。

```cpp
const error_category& system_category() noexcept;
```

### <a name="remarks"></a>Remarks

`system_category`オブジェクトの実装は、 [error_category](../standard-library/error-category-class.md)します。

## <a name="see-also"></a>関連項目

[\<system_error>](../standard-library/system-error.md)<br/>

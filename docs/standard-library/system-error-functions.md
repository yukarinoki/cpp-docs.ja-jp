---
title: '&lt;system_error&gt; 関数 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.topic: reference
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
ms.openlocfilehash: 6135a3dc51b372c85545f01f52c70cbc6f236e64
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
---
# <a name="ltsystemerrorgt-functions"></a>&lt;system_error&gt; 関数

||||
|-|-|-|
|[generic_category](#generic_category)|[make_error_code](#make_error_code)|[make_error_condition](#make_error_condition)|
|[system_category](#system_category)|

## <a name="generic_category"></a>  generic_category

一般的なエラーのカテゴリを表します。

```cpp
extern const error_category& generic_category();
```

### <a name="remarks"></a>コメント

`generic_category`オブジェクトの実装は、 [error_category](../standard-library/error-category-class.md)です。

## <a name="make_error_code"></a>  make_error_code

エラー コード オブジェクトを作成します。

```cpp
error_code make_error_code(generic_errno _Errno);
```

### <a name="parameters"></a>パラメーター

|パラメーター|説明|
|---------------|-----------------|
|`_Errno`|エラー コード オブジェクトに格納する列挙値。|

### <a name="return-value"></a>戻り値

エラー コード オブジェクト。

### <a name="remarks"></a>コメント

## <a name="make_error_condition"></a>  make_error_condition

エラー条件オブジェクトを作成します。

```cpp
error_condition make_error_condition(generic_errno _Errno);
```

### <a name="parameters"></a>パラメーター

|パラメーター|説明|
|---------------|-----------------|
|`_Errno`|エラー条件オブジェクトに格納する列挙値。|

### <a name="return-value"></a>戻り値

エラー条件オブジェクト。

### <a name="remarks"></a>コメント

## <a name="system_category"></a>  system_category

低レベル システム オーバーフローによって発生したエラーのカテゴリを表します。

```cpp
extern const error_category& system_category();
```

### <a name="remarks"></a>コメント

`system_category`オブジェクトの実装は、 [error_category](../standard-library/error-category-class.md)です。

## <a name="see-also"></a>関連項目

[<system_error>](../standard-library/system-error.md)<br/>

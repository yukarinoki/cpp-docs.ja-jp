---
title: '&lt;system_error&gt; 関数'
ms.date: 11/04/2016
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
ms.openlocfilehash: 24890830456e3c1026b02960aa650a43da3b6067
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50554388"
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

### <a name="remarks"></a>Remarks

`generic_category`オブジェクトの実装は、 [error_category](../standard-library/error-category-class.md)します。

## <a name="make_error_code"></a>  make_error_code

エラー コード オブジェクトを作成します。

```cpp
error_code make_error_code(generic_errno _Errno);
```

### <a name="parameters"></a>パラメーター

|パラメーター|説明|
|---------------|-----------------|
|*_Errno*|エラー コード オブジェクトに格納する列挙値。|

### <a name="return-value"></a>戻り値

エラー コード オブジェクト。

### <a name="remarks"></a>Remarks

## <a name="make_error_condition"></a>  make_error_condition

エラー条件オブジェクトを作成します。

```cpp
error_condition make_error_condition(generic_errno _Errno);
```

### <a name="parameters"></a>パラメーター

|パラメーター|説明|
|---------------|-----------------|
|*_Errno*|エラー条件オブジェクトに格納する列挙値。|

### <a name="return-value"></a>戻り値

エラー条件オブジェクト。

### <a name="remarks"></a>Remarks

## <a name="system_category"></a>  system_category

低レベル システム オーバーフローによって発生したエラーのカテゴリを表します。

```cpp
extern const error_category& system_category();
```

### <a name="remarks"></a>Remarks

`system_category`オブジェクトの実装は、 [error_category](../standard-library/error-category-class.md)します。

## <a name="see-also"></a>関連項目

[<system_error>](../standard-library/system-error.md)<br/>

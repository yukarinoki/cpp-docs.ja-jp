---
title: error_category クラス
ms.date: 11/04/2016
f1_keywords:
- system_error/std::error_category
- system_error/std::error_category::value_type
- system_error/std::error_category::default_error_condition
- system_error/std::error_category::equivalent
- system_error/std::error_category::message
- system_error/std::error_category::name
helpviewer_keywords:
- std::error_category
- std::error_category::value_type
- std::error_category::default_error_condition
- std::error_category::equivalent
- std::error_category::message
- std::error_category::name
ms.assetid: e0a71e14-852d-4905-acd6-5f8ed426706d
ms.openlocfilehash: 55ff55b2026b741a2b7062d815fe43d6d19b078b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50451962"
---
# <a name="errorcategory-class"></a>error_category クラス

エラー コードのカテゴリを表すオブジェクトの抽象的な共通基底を表します。

## <a name="syntax"></a>構文

```cpp
class error_category;
```

## <a name="remarks"></a>Remarks

定義済みの 2 つのオブジェクト [generic_category](../standard-library/system-error-functions.md#generic_category) および [system_category](../standard-library/system-error-functions.md#system_category) によって `error_category` が実装されます。

### <a name="typedefs"></a>Typedef

|型名|説明|
|-|-|
|[value_type](#value_type)|格納されたエラー コード値を表す型。|

### <a name="member-functions"></a>メンバー関数

|メンバー関数|説明|
|-|-|
|[default_error_condition](#default_error_condition)|エラー条件オブジェクトのエラー コード値を格納します。|
|[equivalent](#equivalent)|エラー オブジェクトが同等であるかどうかを示す値を返します。|
|[message](#message)|指定したエラー コードの名前を返します。|
|[name](#name)|カテゴリの名前を返します。|

### <a name="operators"></a>演算子

|演算子|説明|
|-|-|
|[operator==](#op_eq_eq)|`error_category` オブジェクト間の同等性をテストします。|
|[operator!=](#op_neq)|`error_category` オブジェクト間の不等性をテストします。|
|[operator<](#op_lt)|[error_category](../standard-library/error-category-class.md) オブジェクトが比較のために渡される `error_category` オブジェクトより小さいかどうかをテストします。|

## <a name="requirements"></a>必要条件

**ヘッダー:** \<system_error>

**名前空間:** std

## <a name="default_error_condition"></a>  error_category::default_error_condition

エラー条件オブジェクトのエラー コード値を格納します。

```cpp
virtual error_condition default_error_condition(int _Errval) const;
```

### <a name="parameters"></a>パラメーター

|パラメーター|説明|
|---------------|-----------------|
|*_Errval*|[error_condition](../standard-library/error-condition-class.md) オブジェクトに格納するエラー コード値。|

### <a name="return-value"></a>戻り値

`error_condition(_Errval, *this)` を返します。

### <a name="remarks"></a>Remarks

## <a name="equivalent"></a>  error_category::equivalent

エラー オブジェクトが同等であるかどうかを示す値を返します。

```cpp
virtual bool equivalent(value_type _Errval,
    const error_condition& _Cond) const;

virtual bool equivalent(const error_code& _Code,
    value_type _Errval) const;
```

### <a name="parameters"></a>パラメーター

|パラメーター|説明|
|---------------|-----------------|
|*_Errval*|比較するエラー コード値。|
|*_Cond*|比較する [error_condition](../standard-library/error-condition-class.md) オブジェクト。|
|*(_C)*|比較する [error_code](../standard-library/error-code-class.md) オブジェクト。|

### <a name="return-value"></a>戻り値

**true**カテゴリと値が、それ以外の場合は**false**します。

### <a name="remarks"></a>Remarks

最初のメンバー関数は `*this == _Cond.category() && _Cond.value() == _Errval` を返します。

2 番目のメンバー関数は `*this == _Code.category() && _Code.value() == _Errval` を返します。

## <a name="message"></a>  error_category::message

指定したエラー コードの名前を返します。

```cpp
virtual string message(error_code::value_type val) const = 0;
```

### <a name="parameters"></a>パラメーター

|パラメーター|説明|
|---------------|-----------------|
|*val*|記述するエラー コード値。|

### <a name="return-value"></a>戻り値

エラー コードのわかりやすい名前を返します*val*のカテゴリ。

### <a name="remarks"></a>Remarks

## <a name="name"></a>  error_category::name

カテゴリの名前を返します。

```cpp
virtual const char *name() const = 0;
```

### <a name="return-value"></a>戻り値

カテゴリの名前を、null 終端バイト文字列として返します。

### <a name="remarks"></a>Remarks

## <a name="op_eq_eq"></a>  error_category::operator==

`error_category` オブジェクト間の同等性をテストします。

```cpp
bool operator==(const error_category& right) const;
```

### <a name="parameters"></a>パラメーター

|パラメーター|説明|
|---------------|-----------------|
|*right*|等しいかどうかをテストするオブジェクト。|

### <a name="return-value"></a>戻り値

オブジェクトが等しい場合は **true**、オブジェクトが等しくない場合は **false**。

### <a name="remarks"></a>Remarks

このメンバー演算子は、`this == &right` を返します。

## <a name="op_neq"></a>  error_category::operator!=

`error_category` オブジェクト間の不等性をテストします。

```cpp
bool operator!=(const error_category& right) const;
```

### <a name="parameters"></a>パラメーター

|パラメーター|説明|
|---------------|-----------------|
|*right*|不等性をテストするオブジェクト。|

### <a name="return-value"></a>戻り値

**true**場合、`error_category`オブジェクトが等しく、`error_category`で渡されるオブジェクト*右*。 そうしないと**false**します。

### <a name="remarks"></a>Remarks

このメンバー演算子は、 `(!*this == right)`を返します。

## <a name="op_lt"></a>  error_category::operator&lt;

[error_category](../standard-library/error-category-class.md) オブジェクトが比較のために渡される `error_category` オブジェクトより小さいかどうかをテストします。

```cpp
bool operator<(const error_category& right) const;
```

### <a name="parameters"></a>パラメーター

|パラメーター|説明|
|---------------|-----------------|
|*right*|比較される `error_category` オブジェクト。|

### <a name="return-value"></a>戻り値

`error_category` オブジェクトが、比較対象として渡された `error_category` より小さい場合は **true**。それ以外の場合は **false**。

### <a name="remarks"></a>Remarks

このメンバー演算子は、 `this < &right`を返します。

## <a name="value_type"></a>  error_category::value_type

格納されたエラー コード値を表す型。

```cpp
typedef int value_type;
```

### <a name="remarks"></a>Remarks

この型定義のシノニムは、 **int**します。

## <a name="see-also"></a>関連項目

[<system_error>](../standard-library/system-error.md)<br/>

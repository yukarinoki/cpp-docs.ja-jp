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
ms.openlocfilehash: 3ed2eceb60c2efa78181faea58a256b0e35d489f
ms.sourcegitcommit: 8e285a766523e653aeeb34d412dc6f615ef7b17b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/21/2020
ms.locfileid: "80076608"
---
# <a name="error_category-class"></a>error_category クラス

エラー コードのカテゴリを表すオブジェクトの抽象的な共通基底を表します。

## <a name="syntax"></a>構文

```cpp
class error_category;

constexpr error_category() noexcept;
virtual ~error_category();
error_category(const error_category&) = delete
```

## <a name="remarks"></a>解説

定義済みの 2 つのオブジェクト `error_category`generic_category[ および ](../standard-library/system-error-functions.md#generic_category)system_category[ によって ](../standard-library/system-error-functions.md#system_category) が実装されます。

## <a name="members"></a>メンバー

### <a name="typedefs"></a>Typedefs

|||
|-|-|
|[value_type](#value_type)|格納されたエラー コード値を表す型。|

### <a name="functions"></a>関数

|||
|-|-|
|[default_error_condition](#default_error_condition)|エラー条件オブジェクトのエラー コード値を格納します。|
|[equivalent](#equivalent)|エラー オブジェクトが同等であるかどうかを示す値を返します。|
|[generic_category](#generic)||
|[message](#message)|指定したエラー コードの名前を返します。|
|[name](#name)|カテゴリの名前を返します。|
|[system_category](#system)||

### <a name="operators"></a>オペレーター

|||
|-|-|
|[operator=](#op_as)||
|[operator==](#op_eq_eq)|`error_category` オブジェクト間の同等性をテストします。|
|[operator!=](#op_neq)|`error_category` オブジェクト間の不等性をテストします。|
|[operator<](#op_lt)|[error_category](../standard-library/error-category-class.md) オブジェクトが比較のために渡される `error_category` オブジェクトより小さいかどうかをテストします。|

## <a name="default_error_condition"></a><a name="default_error_condition"></a>default_error_condition

エラー条件オブジェクトのエラー コード値を格納します。

```cpp
virtual error_condition default_error_condition(int _Errval) const;
```

### <a name="parameters"></a>パラメーター

*_Errval*\
[error_condition](../standard-library/error-condition-class.md) オブジェクトに格納するエラー コード値。

### <a name="return-value"></a>戻り値

`error_condition(_Errval, *this)` が返されます。

### <a name="remarks"></a>解説

### <a name="equivalent"></a><a name="equivalent"></a>表現

エラー オブジェクトが同等であるかどうかを示す値を返します。

```cpp
virtual bool equivalent(value_type _Errval,
    const error_condition& _Cond) const;

virtual bool equivalent(const error_code& _Code,
    value_type _Errval) const;
```

#### <a name="parameters"></a>パラメーター

*_Errval*\
比較するエラー コード値。

*_Cond*\
比較する [error_condition](../standard-library/error-condition-class.md) オブジェクト。

*_Code*\
比較する [error_code](../standard-library/error-code-class.md) オブジェクト。

#### <a name="return-value"></a>戻り値

カテゴリと値が等しい場合は**true** 。それ以外の場合は**false**。

#### <a name="remarks"></a>解説

最初のメンバー関数は `*this == _Cond.category() && _Cond.value() == _Errval` を返します。

2 番目のメンバー関数は `*this == _Code.category() && _Code.value() == _Errval` を返します。

### <a name="generic_category"></a><a name="generic"></a>generic_category

```cpp
const error_category& generic_category();
```

### <a name="message"></a><a name="message"></a>メッセージ

指定したエラー コードの名前を返します。

```cpp
virtual string message(error_code::value_type val) const = 0;
```

#### <a name="parameters"></a>パラメーター

*val*\
記述するエラー コード値。

#### <a name="return-value"></a>戻り値

カテゴリのエラーコード*val*のわかりやすい名前を返します。

#### <a name="remarks"></a>解説

### <a name="name"></a><a name="name"></a>指定

カテゴリの名前を返します。

```cpp
virtual const char *name() const = 0;
```

#### <a name="return-value"></a>戻り値

カテゴリの名前を、null 終端バイト文字列として返します。

### <a name="operator"></a><a name="op_as"></a>operator =

```cpp
error_category& operator=(const error_category&) = delete;
```

### <a name="operator"></a><a name="op_eq_eq"></a>operator = =

`error_category` オブジェクト間の同等性をテストします。

```cpp
bool operator==(const error_category& right) const;
```

#### <a name="parameters"></a>パラメーター

*右*\
等しいかどうかをテストするオブジェクト。

#### <a name="return-value"></a>戻り値

オブジェクトが等しい場合は **true**、オブジェクトが等しくない場合は **false**。

#### <a name="remarks"></a>解説

このメンバー演算子は、`this == &right` を返します。

### <a name="operator"></a><a name="op_neq"></a>operator! =

`error_category` オブジェクト間の不等性をテストします。

```cpp
bool operator!=(const error_category& right) const;
```

#### <a name="parameters"></a>パラメーター

*右*\
不等性をテストするオブジェクト。

#### <a name="return-value"></a>戻り値

`error_category` オブジェクトが、渡された `error_category` オブジェクトと等しくない*場合は* **true** 。それ以外の場合は**false**。

#### <a name="remarks"></a>解説

このメンバー演算子は、 `(!*this == right)`を返します。

### <a name="operatorlt"></a><a name="op_lt"></a> 演算子&lt;

[error_category](../standard-library/error-category-class.md) オブジェクトが比較のために渡される `error_category` オブジェクトより小さいかどうかをテストします。

```cpp
bool operator<(const error_category& right) const;
```

#### <a name="parameters"></a>パラメーター

*右*\
比較される `error_category` オブジェクト。

#### <a name="return-value"></a>戻り値

**オブジェクトが、比較対象として渡された** より小さい場合は `error_category`true`error_category`。それ以外の場合は **false**。

#### <a name="remarks"></a>解説

このメンバー演算子は、 `this < &right`を返します。

### <a name="system_category"></a><a name="system"></a>system_category

```cpp
const error_category& system_category();
```

### <a name="value_type"></a><a name="value_type"></a>value_type

格納されたエラー コード値を表す型。

```cpp
typedef int value_type;
```

#### <a name="remarks"></a>解説

この型定義は、 **int**のシノニムです。

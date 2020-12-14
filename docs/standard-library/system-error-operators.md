---
description: 詳細については、「 &lt; system_error 演算子」を参照してください。 &gt;
title: '&lt;system_error&gt; 演算子'
ms.date: 11/04/2016
f1_keywords:
- system_error/std::operator!=
- system_error/std::operator==
ms.assetid: c14edefb-bd8a-4e90-88d3-c59c98e6f73c
ms.openlocfilehash: 0ebbb4d9de0ef8bf27aaa276dfee14d94c29eabb
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97259423"
---
# <a name="ltsystem_errorgt-operators"></a>&lt;system_error&gt; 演算子

## <a name="operator"></a><a name="op_eq_eq"></a> operator = =

演算子の左側のオブジェクトが右側のオブジェクトと等しいかどうかを調べます。

```cpp
bool operator==(const error_code& left,
    const error_condition& right);

bool operator==(const error_condition& left,
    const error_code& right);

bool operator==(const error_condition& left,
    const error_condition& right);
```

### <a name="parameters"></a>パラメーター

*左側*\
等しいかどうかをテストするオブジェクト。

*そうです*\
等しいかどうかをテストするオブジェクト。

### <a name="return-value"></a>戻り値

**`true`** オブジェクトが等しい場合は。 **`false`** オブジェクトが等しくない場合は。

### <a name="remarks"></a>解説

この関数は `left.category() == right.category() && left.value() == right.value()` を返します。

## <a name="operator"></a><a name="op_neq"></a> operator! =

演算子の左側のオブジェクトが右側のオブジェクトと等しくないかどうかを調べます。

```cpp
bool operator!=(const error_code& left, const error_condition& right);
bool operator!=(const error_condition& left, const error_code& right);
bool operator!=(const error_code& left, const error_code& right);
bool operator!=(const error_condition& left, const error_condition& right);
```

### <a name="parameters"></a>パラメーター

*左側*\
不等性をテストするオブジェクト。

*そうです*\
不等性をテストするオブジェクト。

### <a name="return-value"></a>戻り値

**`true`***左* に渡されたオブジェクトが、渡されたオブジェクトと等しくない場合 *は。* それ以外の場合は **`false`** 。

### <a name="remarks"></a>解説

この関数は `!(left == right)` を返します。

## <a name="operatorlt"></a><a name="op_lt"></a> operator&lt;

オブジェクトが比較のために渡されるオブジェクトより小さいかどうかをテストします。

```cpp
template <class _Enum>
inline bool operator<(
    _Enum left,
    typename enable_if<is_error_code_enum<_Enum>::value,
    const error_code&>::type right);

template <class _Enum>
inline bool operator<(
    typename enable_if<is_error_code_enum<_Enum>::value,
    const error_code&>::type left, _Enum right);

template <class _Enum>
inline bool operator<(
    _Enum left,
    typename enable_if<is_error_condition_enum<_Enum>::value,
    const error_condition&>::type right);

template <class _Enum>
inline bool operator<(
    typename enable_if<is_error_condition_enum<_Enum>::value,
    const error_condition&>::type left, _Enum right);
```

### <a name="parameters"></a>パラメーター

*左側*\
比較されるオブジェクト。

*そうです*\
比較されるオブジェクト。

### <a name="return-value"></a>戻り値

**`true`** 渡さ *れたオブジェクトが、* 渡されたオブジェクトより小さい場合 *は。* それ以外の場合は **`false`** 。

### <a name="remarks"></a>解説

この関数はエラー順序をテストします。

## <a name="operatorltlt"></a><a name="op_ostream"></a> operator&lt;&lt;

```cpp
template <class charT, class traits>
    basic_ostream<charT, traits>& operator<<(basic_ostream<charT, traits>& os, const error_code& ec);
```

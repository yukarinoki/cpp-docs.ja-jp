---
title: '&lt;system_error&gt; 演算子'
ms.date: 11/04/2016
f1_keywords:
- system_error/std::operator!=
- system_error/std::operator==
ms.assetid: c14edefb-bd8a-4e90-88d3-c59c98e6f73c
ms.openlocfilehash: 8631cae146a311f1890583900b564471d5a80958
ms.sourcegitcommit: 8e285a766523e653aeeb34d412dc6f615ef7b17b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/21/2020
ms.locfileid: "80076258"
---
# <a name="ltsystem_errorgt-operators"></a>&lt;system_error&gt; 演算子

## <a name="operator"></a><a name="op_eq_eq"></a>operator = =

演算子の左辺のオブジェクトが右辺のオブジェクトと等しいかどうかを調べます。

```cpp
bool operator==(const error_code& left,
    const error_condition& right);

bool operator==(const error_condition& left,
    const error_code& right);

bool operator==(const error_condition& left,
    const error_condition& right);
```

### <a name="parameters"></a>パラメーター

*左*\
等しいかどうかをテストするオブジェクト。

*右*\
等しいかどうかをテストするオブジェクト。

### <a name="return-value"></a>戻り値

オブジェクトが等しい場合は **true**、オブジェクトが等しくない場合は **false**。

### <a name="remarks"></a>解説

この関数は `left.category() == right.category() && left.value() == right.value()` を返します。

## <a name="operator"></a><a name="op_neq"></a>operator! =

演算子の左側のオブジェクトが右側のオブジェクトと等しくないかどうかを調べます。

```cpp
bool operator!=(const error_code& left, const error_condition& right);
bool operator!=(const error_condition& left, const error_code& right);
bool operator!=(const error_code& left, const error_code& right);
bool operator!=(const error_condition& left, const error_condition& right);
```

### <a name="parameters"></a>パラメーター

*左*\
不等性をテストするオブジェクト。

*右*\
不等性をテストするオブジェクト。

### <a name="return-value"></a>戻り値

*左* *に渡さ*れたオブジェクトが、渡されたオブジェクトと等しくない場合は**true** 。それ以外の場合は**false**。

### <a name="remarks"></a>解説

この関数は `!(left == right)` を返します。

## <a name="operatorlt"></a><a name="op_lt"></a> 演算子&lt;

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

*左*\
比較されるオブジェクト。

*右*\
比較されるオブジェクト。

### <a name="return-value"></a>戻り値

*左* *に渡さ*れたオブジェクトが、渡されたオブジェクトより小さい場合は**true** 。それ以外の場合は**false**。

### <a name="remarks"></a>解説

この関数はエラー順序をテストします。

## <a name="operatorltlt"></a><a name="op_ostream"></a>演算子&lt;&lt;

```cpp
template <class charT, class traits>
    basic_ostream<charT, traits>& operator<<(basic_ostream<charT, traits>& os, const error_code& ec);
```

---
title: '&lt;allocators&gt; 演算子 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- allocators/std::operator!=
- allocators/std::operator==
dev_langs:
- C++
ms.assetid: b55d67cb-3c69-46bf-ad40-e845fb096c4e
ms.openlocfilehash: 25e40157c1872df3e970bb234accab5c487c6287
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
---
# <a name="ltallocatorsgt-operators"></a>&lt;allocators&gt; 演算子

これらで定義されているグローバル テンプレート演算子関数は、&lt;アロケーター&gt;です。 クラスのメンバー演算子関数は、クラスのドキュメントを参照してください。

|||
|-|-|
|[operator!=](#op_neq)|[operator==](#op_eq_eq)|

## <a name="op_neq"></a>  operator!=

指定したクラスのアロケーター オブジェクト間の非等値をテストします。

```cpp
template <class Type, class Sync>
bool operator!=(
    const allocator_base<Type, Sync>& left,
    const allocator_base<Type, Sync>& right);
```

### <a name="parameters"></a>パラメーター

|パラメーター|説明|
|---------------|-----------------|
|`left`|不等性をテストする一方のアロケーター オブジェクト。|
|`right`|不等性をテストする一方のアロケーター オブジェクト。|

### <a name="return-value"></a>戻り値

アロケーター オブジェクトが等しくない場合は **true**、アロケーター オブジェクトが等しい場合は **false**。

### <a name="remarks"></a>コメント

テンプレート演算子は `!(left == right)` を返します。

## <a name="op_eq_eq"></a>  operator==

指定したクラスのアロケーター オブジェクト間の等値をテストします。

```cpp
template <class Type, class Sync>
bool operator==(
    const allocator_base<Type, Sync>& left,
    const allocator_base<Type, Sync>& right);
```

### <a name="parameters"></a>パラメーター

|パラメーター|説明|
|---------------|-----------------|
|`left`|等しいかどうかをテストする一方のアロケーター オブジェクト。|
|`right`|等しいかどうかをテストする一方のアロケーター オブジェクト。|

### <a name="return-value"></a>戻り値

アロケーター オブジェクトが等しい場合は **true**、アロケーター オブジェクトが等しくない場合は **false**。

### <a name="remarks"></a>コメント

このテンプレート演算子は `left.equals(right)` を返します。

## <a name="see-also"></a>関連項目

[\<allocators>](../standard-library/allocators-header.md)

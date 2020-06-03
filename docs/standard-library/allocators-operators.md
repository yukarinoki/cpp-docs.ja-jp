---
title: '&lt;allocators&gt; 演算子'
ms.date: 11/04/2016
f1_keywords:
- allocators/std::operator!=
- allocators/std::operator==
ms.assetid: b55d67cb-3c69-46bf-ad40-e845fb096c4e
ms.openlocfilehash: 7bc37e98ed85582cac8fc7ae21e54a6d5da9e06f
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81364959"
---
# <a name="ltallocatorsgt-operators"></a>&lt;allocators&gt; 演算子

これらは、 アロケーター で定義された&lt;グローバル テンプレート&gt;演算子関数です。 クラス メンバー演算子関数については、クラスのドキュメントを参照してください。

|||
|-|-|
|[演算子!=](#op_neq)|[演算子==](#op_eq_eq)|

## <a name="operator"></a><a name="op_neq"></a>演算子!=

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
|*左*|不等性をテストする一方のアロケーター オブジェクト。|
|*そうです*|不等性をテストする一方のアロケーター オブジェクト。|

### <a name="return-value"></a>戻り値

アロケーター オブジェクトが等しくない場合は **true**、アロケーター オブジェクトが等しい場合は **false**。

### <a name="remarks"></a>解説

このテンプレート演算子は `!(left == right)` を返します。

## <a name="operator"></a><a name="op_eq_eq"></a>演算子==

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
|*左*|等しいかどうかをテストする一方のアロケーター オブジェクト。|
|*そうです*|等しいかどうかをテストする一方のアロケーター オブジェクト。|

### <a name="return-value"></a>戻り値

アロケーター オブジェクトが等しい場合は **true**、アロケーター オブジェクトが等しくない場合は **false**。

### <a name="remarks"></a>解説

このテンプレート演算子は `left.equals(right)` を返します。

## <a name="see-also"></a>関連項目

[\<アロケーター>](../standard-library/allocators-header.md)

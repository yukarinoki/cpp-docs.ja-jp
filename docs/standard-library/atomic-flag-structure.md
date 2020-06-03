---
title: atomic_flag 構造体
ms.date: 11/04/2016
f1_keywords:
- atomic/std::atomic_flag
- atomic/std::atomic_flag::clear
- atomic/std::atomic_flag::test_and_set
ms.assetid: 17f0c2f5-fd39-4a44-873a-b569720a670e
ms.openlocfilehash: ad4b6dcaf6db1a8abe5b81b4d630e84b54fbaa63
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81376870"
---
# <a name="atomic_flag-structure"></a>atomic_flag 構造体

**bool**フラグをアトミックに設定およびクリアするオブジェクトを記述します。 アトミック フラグの操作は常にロック制御不要です。

## <a name="syntax"></a>構文

```cpp
struct atomic_flag;
```

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[クリア](#clear)|格納されているフラグを**false**に設定します。|
|[test_and_set](#test_and_set)|格納されているフラグを**true**に設定し、初期フラグ値を返します。|

## <a name="remarks"></a>解説

`atomic_flag` オブジェクトは、[atomic_flag_clear](../standard-library/atomic-functions.md#atomic_flag_clear)、[atomic_flag_clear_explicit](../standard-library/atomic-functions.md#atomic_flag_clear_explicit)、[atomic_flag_test_and_set](../standard-library/atomic-functions.md#atomic_flag_test_and_set)、および [atomic_flag_test_and_set_explicit](../standard-library/atomic-functions.md#atomic_flag_test_and_set_explicit) の非メンバー関数に渡すことができます。 これらは、`ATOMIC_FLAG_INIT` の値を使用して初期化できます。

## <a name="requirements"></a>必要条件

**ヘッダー:**\<アトミック>

**名前空間:** std

## <a name="atomic_flagclear"></a><a name="clear"></a>atomic_flag::クリア

指定した[memory_order](../standard-library/atomic-enums.md#memory_order_enum)制約内で`*this`に格納される**bool**フラグを**false**に設定します。

```cpp
void atomic_flag::clear(memory_order Order = memory_order_seq_cst) volatile noexcept;
void atomic_flag::clear(memory_order Order = memory_order_seq_cst) noexcept;
```

### <a name="parameters"></a>パラメーター

*順序*\
[memory_order](../standard-library/atomic-enums.md#memory_order_enum)。

## <a name="atomic_flagtest_and_set"></a><a name="test_and_set"></a>atomic_flag::test_and_set

指定した[memory_order](../standard-library/atomic-enums.md#memory_order_enum)制約内の`*this`に格納される**bool**フラグを**true**に設定します。

```cpp
bool atomic_flag::test_and_set(memory_order Order = memory_order_seq_cst) volatile noexcept;
bool atomic_flag::test_and_set(memory_order Order = memory_order_seq_cst) noexcept;
```

### <a name="parameters"></a>パラメーター

*順序*\
[memory_order](../standard-library/atomic-enums.md#memory_order_enum)。

### <a name="return-value"></a>戻り値

`*this` に格納されているフラグの初期値。

## <a name="see-also"></a>関連項目

[\<原子>](../standard-library/atomic.md)

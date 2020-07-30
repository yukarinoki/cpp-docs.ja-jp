---
title: atomic_flag 構造体
ms.date: 11/04/2016
f1_keywords:
- atomic/std::atomic_flag
- atomic/std::atomic_flag::clear
- atomic/std::atomic_flag::test_and_set
ms.assetid: 17f0c2f5-fd39-4a44-873a-b569720a670e
ms.openlocfilehash: ff60e05c7d14104e164e8251a9146f8b0d0dcde3
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87203924"
---
# <a name="atomic_flag-structure"></a>atomic_flag 構造体

フラグをアトミックに設定およびクリアするオブジェクトを記述し **`bool`** ます。 アトミック フラグの操作は常にロック制御不要です。

## <a name="syntax"></a>構文

```cpp
struct atomic_flag;
```

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[オフ](#clear)|格納されているフラグをに設定 **`false`** します。|
|[test_and_set](#test_and_set)|に格納されているフラグをに設定 **`true`** し、初期フラグ値を返します。|

## <a name="remarks"></a>解説

`atomic_flag` オブジェクトは、[atomic_flag_clear](../standard-library/atomic-functions.md#atomic_flag_clear)、[atomic_flag_clear_explicit](../standard-library/atomic-functions.md#atomic_flag_clear_explicit)、[atomic_flag_test_and_set](../standard-library/atomic-functions.md#atomic_flag_test_and_set)、および [atomic_flag_test_and_set_explicit](../standard-library/atomic-functions.md#atomic_flag_test_and_set_explicit) の非メンバー関数に渡すことができます。 これらは、`ATOMIC_FLAG_INIT` の値を使用して初期化できます。

## <a name="requirements"></a>必要条件

**ヘッダー:**\<atomic>

**名前空間:** std

## <a name="atomic_flagclear"></a><a name="clear"></a>atomic_flag:: clear

**`bool`** **`*this`** **`false`** 指定された[memory_order](../standard-library/atomic-enums.md#memory_order_enum)制約内で、に格納されているフラグをに設定します。

```cpp
void atomic_flag::clear(memory_order Order = memory_order_seq_cst) volatile noexcept;
void atomic_flag::clear(memory_order Order = memory_order_seq_cst) noexcept;
```

### <a name="parameters"></a>パラメーター

*順序*\
[memory_order](../standard-library/atomic-enums.md#memory_order_enum)。

## <a name="atomic_flagtest_and_set"></a><a name="test_and_set"></a>atomic_flag:: test_and_set

**`bool`** **`*this`** **`true`** 指定された[memory_order](../standard-library/atomic-enums.md#memory_order_enum)制約内で、に格納されているフラグをに設定します。

```cpp
bool atomic_flag::test_and_set(memory_order Order = memory_order_seq_cst) volatile noexcept;
bool atomic_flag::test_and_set(memory_order Order = memory_order_seq_cst) noexcept;
```

### <a name="parameters"></a>パラメーター

*順序*\
[memory_order](../standard-library/atomic-enums.md#memory_order_enum)。

### <a name="return-value"></a>戻り値

に格納されているフラグの初期値 **`*this`** 。

## <a name="see-also"></a>関連項目

[\<atomic>](../standard-library/atomic.md)

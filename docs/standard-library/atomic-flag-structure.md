---
title: atomic_flag 構造体 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- atomic/std::atomic_flag
- atomic/std::atomic_flag::clear
- atomic/std::atomic_flag::test_and_set
dev_langs:
- C++
ms.assetid: 17f0c2f5-fd39-4a44-873a-b569720a670e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f763181424bafc4b8b3af41c135753dbe2f2577b
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2018
ms.locfileid: "44110319"
---
# <a name="atomicflag-structure"></a>atomic_flag 構造体

アトミックに設定し、クリアするオブジェクトについて説明します、 **bool**フラグ。 アトミック フラグの操作は常にロック制御不要です。

## <a name="syntax"></a>構文

```cpp
struct atomic_flag;
```

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[clear](#clear)|格納されたフラグを設定**false**します。|
|[test_and_set](#test_and_set)|格納されたフラグを設定**true**フラグの初期値を返します。|

## <a name="remarks"></a>Remarks

`atomic_flag` オブジェクトは、[atomic_flag_clear](../standard-library/atomic-functions.md#atomic_flag_clear)、[atomic_flag_clear_explicit](../standard-library/atomic-functions.md#atomic_flag_clear_explicit)、[atomic_flag_test_and_set](../standard-library/atomic-functions.md#atomic_flag_test_and_set)、および [atomic_flag_test_and_set_explicit](../standard-library/atomic-functions.md#atomic_flag_test_and_set_explicit) の非メンバー関数に渡すことができます。 これらは、`ATOMIC_FLAG_INIT` の値を使用して初期化できます。

## <a name="requirements"></a>要件

**ヘッダー:** \<atomic >

**名前空間:** std

## <a name="clear"></a>  atomic_flag::clear

セット、 **bool**に格納されているフラグ`*this`に**false**、指定した[memory_order](../standard-library/atomic-enums.md#memory_order_enum)制約。

```cpp
void atomic_flag::clear(memory_order Order = memory_order_seq_cst) volatile noexcept;
void atomic_flag::clear(memory_order Order = memory_order_seq_cst) noexcept;
```

### <a name="parameters"></a>パラメーター

*順序*<br/>
[memory_order](../standard-library/atomic-enums.md#memory_order_enum)。

## <a name="test_and_set"></a>  atomic_flag::test_and_set

セット、 **bool**に格納されているフラグ`*this`に**true**、指定した[memory_order](../standard-library/atomic-enums.md#memory_order_enum)制約。

```cpp
bool atomic_flag::test_and_set(memory_order Order = memory_order_seq_cst) volatile noexcept;
bool atomic_flag::test_and_set(memory_order Order = memory_order_seq_cst) noexcept;
```

### <a name="parameters"></a>パラメーター

*順序*<br/>
[memory_order](../standard-library/atomic-enums.md#memory_order_enum)。

### <a name="return-value"></a>戻り値

`*this` に格納されているフラグの初期値。

## <a name="see-also"></a>関連項目

[\<atomic>](../standard-library/atomic.md)<br/>

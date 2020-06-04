---
title: scheduler_interface 構造体
ms.date: 11/04/2016
f1_keywords:
- scheduler_interface
- PPLINTERFACE/concurrency::scheduler_interface
- PPLINTERFACE/concurrency::scheduler_interface::scheduler_interface::schedule
ms.assetid: 4de61c78-a2c6-4698-bd47-964baf7fa287
ms.openlocfilehash: da2ebc2f9c2878baefcfa792bac08f420dbbb281
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81358785"
---
# <a name="scheduler_interface-structure"></a>scheduler_interface 構造体

スケジューラ インターフェイス

## <a name="syntax"></a>構文

```cpp
struct __declspec(novtable) scheduler_interface;
```

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[scheduler_interface::スケジュール](#schedule)||

## <a name="inheritance-hierarchy"></a>継承階層

`scheduler_interface`

## <a name="requirements"></a>必要条件

**ヘッダー:** pplinterface.h

**名前空間:** 同時実行

## <a name="scheduler_interfaceschedule-method"></a><a name="schedule"></a>scheduler_interface::スケジュール方法

```cpp
virtual void schedule(
    TaskProc_t,
void*) = 0;
```

## <a name="see-also"></a>関連項目

[同時実行名前空間](concurrency-namespace.md)

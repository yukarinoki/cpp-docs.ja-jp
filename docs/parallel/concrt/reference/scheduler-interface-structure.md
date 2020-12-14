---
description: '詳細情報: scheduler_interface 構造'
title: scheduler_interface 構造体
ms.date: 11/04/2016
f1_keywords:
- scheduler_interface
- PPLINTERFACE/concurrency::scheduler_interface
- PPLINTERFACE/concurrency::scheduler_interface::scheduler_interface::schedule
ms.assetid: 4de61c78-a2c6-4698-bd47-964baf7fa287
ms.openlocfilehash: ba56ef809cf398a192810eb96a8b4e4ca50ec1cc
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97188873"
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
|[scheduler_interface:: schedule](#schedule)||

## <a name="inheritance-hierarchy"></a>継承階層

`scheduler_interface`

## <a name="requirements"></a>要件

**ヘッダー:** pplinterface.h

**名前空間:** concurrency

## <a name="scheduler_interfaceschedule-method"></a><a name="schedule"></a> scheduler_interface:: schedule メソッド

```cpp
virtual void schedule(
    TaskProc_t,
void*) = 0;
```

## <a name="see-also"></a>関連項目

[concurrency 名前空間](concurrency-namespace.md)

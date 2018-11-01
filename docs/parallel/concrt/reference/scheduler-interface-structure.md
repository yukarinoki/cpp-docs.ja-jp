---
title: scheduler_interface 構造体
ms.date: 11/04/2016
f1_keywords:
- scheduler_interface
- PPLINTERFACE/concurrency::scheduler_interface
- PPLINTERFACE/concurrency::scheduler_interface::scheduler_interface::schedule
ms.assetid: 4de61c78-a2c6-4698-bd47-964baf7fa287
ms.openlocfilehash: 9fa51aa5bd1fdea4eb1c35488654f0b5003e2efe
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50612772"
---
# <a name="schedulerinterface-structure"></a>scheduler_interface 構造体

スケジューラ インターフェイス

## <a name="syntax"></a>構文

```
struct __declspec(novtable) scheduler_interface;
```

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[scheduler_interface::schedule](#schedule)||

## <a name="inheritance-hierarchy"></a>継承階層

`scheduler_interface`

## <a name="requirements"></a>必要条件

**ヘッダー:** pplinterface.h

**名前空間:** concurrency

##  <a name="schedule"></a>  scheduler_interface::schedule メソッド

```
virtual void schedule(
    TaskProc_t,
void*) = 0;
```

## <a name="see-also"></a>関連項目

[コンカレンシー名前空間](concurrency-namespace.md)

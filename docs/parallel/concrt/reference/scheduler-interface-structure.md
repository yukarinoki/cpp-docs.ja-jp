---
title: scheduler_interface 構造体
ms.date: 11/04/2016
f1_keywords:
- scheduler_interface
- PPLINTERFACE/concurrency::scheduler_interface
- PPLINTERFACE/concurrency::scheduler_interface::scheduler_interface::schedule
ms.assetid: 4de61c78-a2c6-4698-bd47-964baf7fa287
ms.openlocfilehash: 99a3ea8b6ad1f23b4f3d54b7f2f406a3d115b374
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/04/2019
ms.locfileid: "57283372"
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

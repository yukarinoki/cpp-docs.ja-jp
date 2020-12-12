---
description: '詳細情報: scoped_lock クラス'
title: scoped_lock クラス
ms.date: 11/04/2016
f1_keywords:
- mutex/std::scoped_lock
ms.openlocfilehash: 929dadab1f476f4254a46fcd0dbec4b8e162228b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97197115"
---
# <a name="scoped_lock-class"></a>scoped_lock クラス

## <a name="syntax"></a>構文

```cpp
template <class... MutexTypes>
class scoped_lock {
    using mutex_type = Mutex; // If MutexTypes... consists of the single type Mutex
    explicit scoped_lock(MutexTypes&... m);
    explicit scoped_lock(MutexTypes&... m, adopt_lock_t);
    ~scoped_lock();
    scoped_lock(const scoped_lock&) = delete;
    scoped_lock& operator=(const scoped_lock&) = delete;
}
```

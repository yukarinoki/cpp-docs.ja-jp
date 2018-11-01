---
title: default_scheduler_exists クラス
ms.date: 11/04/2016
f1_keywords:
- default_scheduler_exists
- CONCRT/concurrency::default_scheduler_exists
- CONCRT/concurrency::default_scheduler_exists::default_scheduler_exists
helpviewer_keywords:
- default_scheduler_exists class
ms.assetid: f6e575e2-4e0f-455a-9e06-54f462ce0c1c
ms.openlocfilehash: 149a220ba9498b1e1c3b7f09cef94c76c34ac4b5
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50501973"
---
# <a name="defaultschedulerexists-class"></a>default_scheduler_exists クラス

このクラスは、既定のスケジューラが既にプロセス内に存在するときに `Scheduler::SetDefaultSchedulerPolicy` メソッドが呼び出された場合にスローされる例外を表します。

## <a name="syntax"></a>構文

```
class default_scheduler_exists : public std::exception;
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[default_scheduler_exists](#ctor)|オーバーロードされます。 `default_scheduler_exists` オブジェクトを構築します。|

## <a name="inheritance-hierarchy"></a>継承階層

`exception`

`default_scheduler_exists`

## <a name="requirements"></a>必要条件

**ヘッダー:** concrt.h

**名前空間:** concurrency

##  <a name="ctor"></a> default_scheduler_exists

`default_scheduler_exists` オブジェクトを構築します。

```
explicit _CRTIMP default_scheduler_exists(_In_z_ const char* _Message) throw();

default_scheduler_exists() throw();
```

### <a name="parameters"></a>パラメーター

*メッセージ (_m)*<br/>
エラーの説明メッセージ。

## <a name="see-also"></a>関連項目

[コンカレンシー名前空間](concurrency-namespace.md)

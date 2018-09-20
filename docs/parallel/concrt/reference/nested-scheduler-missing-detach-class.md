---
title: nested_scheduler_missing_detach クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
f1_keywords:
- nested_scheduler_missing_detach
- CONCRT/concurrency::nested_scheduler_missing_detach
- CONCRT/concurrency::nested_scheduler_missing_detach::nested_scheduler_missing_detach
dev_langs:
- C++
helpviewer_keywords:
- nested_scheduler_missing_detach class
ms.assetid: 65d3f277-6d43-4160-97ef-caf8b26c1641
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e7c862cdf778b726a4d416ea490f5da9c3d7eb01
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46414889"
---
# <a name="nestedschedulermissingdetach-class"></a>nested_scheduler_missing_detach クラス

このクラスは、`CurrentScheduler::Detach` オブジェクトの `Attach` メソッドによって別のスケジューラにアタッチされているコンテキストで `Scheduler` メソッドが呼び出されなかったことを、同時実行ランタイムが検出した場合にスローされる例外を表します。

## <a name="syntax"></a>構文

```
class nested_scheduler_missing_detach : public std::exception;
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[nested_scheduler_missing_detach](#ctor)|オーバーロードされます。 `nested_scheduler_missing_detach` オブジェクトを構築します。|

## <a name="remarks"></a>Remarks

呼び出して別のスケジューラ内に入れ子にする場合にのみ、この例外がスローされます、`Attach`のメソッド、`Scheduler`既にによって所有されているか、別のスケジューラにアタッチされているコンテキスト上のオブジェクト。 同時実行ランタイムは、問題の特定を支援するために、シナリオを検出できるとさせるこの例外をスローします。 すべてのインスタンスの呼び出しを無視して、`CurrentScheduler::Detach`メソッドは、この例外をスローすることが保証されます。

## <a name="inheritance-hierarchy"></a>継承階層

`exception`

`nested_scheduler_missing_detach`

## <a name="requirements"></a>要件

**ヘッダー:** concrt.h

**名前空間:** concurrency

##  <a name="ctor"></a> nested_scheduler_missing_detach

`nested_scheduler_missing_detach` オブジェクトを構築します。

```
explicit _CRTIMP nested_scheduler_missing_detach(_In_z_ const char* _Message) throw();

nested_scheduler_missing_detach() throw();
```

### <a name="parameters"></a>パラメーター

*メッセージ (_m)*<br/>
エラーの説明メッセージ。

## <a name="see-also"></a>関連項目

[コンカレンシー名前空間](concurrency-namespace.md)<br/>
[Scheduler クラス](scheduler-class.md)

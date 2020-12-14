---
description: '詳細情報: nested_scheduler_missing_detach クラス'
title: nested_scheduler_missing_detach クラス
ms.date: 11/04/2016
f1_keywords:
- nested_scheduler_missing_detach
- CONCRT/concurrency::nested_scheduler_missing_detach
- CONCRT/concurrency::nested_scheduler_missing_detach::nested_scheduler_missing_detach
helpviewer_keywords:
- nested_scheduler_missing_detach class
ms.assetid: 65d3f277-6d43-4160-97ef-caf8b26c1641
ms.openlocfilehash: 3d1232b8f9b807835f5b4b1e19c6049d049f12f1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97202107"
---
# <a name="nested_scheduler_missing_detach-class"></a>nested_scheduler_missing_detach クラス

このクラスは、`CurrentScheduler::Detach` オブジェクトの `Attach` メソッドによって別のスケジューラにアタッチされているコンテキストで `Scheduler` メソッドが呼び出されなかったことを、コンカレンシー ランタイムが検出した場合にスローされる例外を表します。

## <a name="syntax"></a>構文

```cpp
class nested_scheduler_missing_detach : public std::exception;
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[nested_scheduler_missing_detach](#ctor)|オーバーロードされます。 `nested_scheduler_missing_detach` オブジェクトを構築します。|

## <a name="remarks"></a>解説

この例外がスローされるのは、既にに `Attach` `Scheduler` よって所有されているか別のスケジューラにアタッチされているコンテキストでオブジェクトのメソッドを呼び出すことによって、あるスケジューラを別の内部に入れ子にする場合のみです。 同時実行ランタイムは、問題を特定するための支援としてシナリオを検出できる場合に、この例外させるをスローします。 メソッドを呼び出すための怠りのすべてのインスタンス `CurrentScheduler::Detach` が、この例外をスローすることは保証されていません。

## <a name="inheritance-hierarchy"></a>継承階層

`exception`

`nested_scheduler_missing_detach`

## <a name="requirements"></a>要件

**ヘッダー:** concrt .h

**名前空間:** concurrency

## <a name="nested_scheduler_missing_detach"></a><a name="ctor"></a> nested_scheduler_missing_detach

`nested_scheduler_missing_detach` オブジェクトを構築します。

```cpp
explicit _CRTIMP nested_scheduler_missing_detach(_In_z_ const char* _Message) throw();

nested_scheduler_missing_detach() throw();
```

### <a name="parameters"></a>パラメーター

*_Message*<br/>
エラーの説明メッセージ。

## <a name="see-also"></a>関連項目

[concurrency 名前空間](concurrency-namespace.md)<br/>
[Scheduler クラス](scheduler-class.md)

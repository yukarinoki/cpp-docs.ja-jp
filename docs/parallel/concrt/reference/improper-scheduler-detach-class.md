---
description: '詳細情報: improper_scheduler_detach クラス'
title: improper_scheduler_detach クラス
ms.date: 11/04/2016
f1_keywords:
- improper_scheduler_detach
- CONCRT/concurrency::improper_scheduler_detach
- CONCRT/concurrency::improper_scheduler_detach::improper_scheduler_detach
helpviewer_keywords:
- improper_scheduler_detach class
ms.assetid: 30132102-c900-4951-a470-b63b4e3aa2d2
ms.openlocfilehash: 62def23a4a3459c4cb8268b3b0f4df4a77025668
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97334615"
---
# <a name="improper_scheduler_detach-class"></a>improper_scheduler_detach クラス

このクラスは、`CurrentScheduler::Detach` オブジェクトの `Attach` メソッドによってスケジューラにアタッチされていないコンテキストで `Scheduler` メソッドが呼び出された場合にスローされる例外を表します。

## <a name="syntax"></a>構文

```cpp
class improper_scheduler_detach : public std::exception;
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[improper_scheduler_detach](#ctor)|オーバーロードされます。 `improper_scheduler_detach` オブジェクトを構築します。|

## <a name="inheritance-hierarchy"></a>継承階層

`exception`

`improper_scheduler_detach`

## <a name="requirements"></a>要件

**ヘッダー:** concrt .h

**名前空間:** concurrency

## <a name="improper_scheduler_detach"></a><a name="ctor"></a> improper_scheduler_detach

`improper_scheduler_detach` オブジェクトを構築します。

```cpp
explicit _CRTIMP improper_scheduler_detach(_In_z_ const char* _Message) throw();

improper_scheduler_detach() throw();
```

### <a name="parameters"></a>パラメーター

*_Message*<br/>
エラーの説明メッセージ。

## <a name="see-also"></a>関連項目

[concurrency 名前空間](concurrency-namespace.md)<br/>
[Scheduler クラス](scheduler-class.md)

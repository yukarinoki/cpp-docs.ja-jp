---
description: '詳細情報: improper_scheduler_reference クラス'
title: improper_scheduler_reference クラス
ms.date: 11/04/2016
f1_keywords:
- improper_scheduler_reference
- CONCRT/concurrency::improper_scheduler_reference
- CONCRT/concurrency::improper_scheduler_reference::improper_scheduler_reference
helpviewer_keywords:
- improper_scheduler_reference class
ms.assetid: 434a7512-7796-4255-92a7-f3bf71c6a7a7
ms.openlocfilehash: 4857418e14908b2d085d52249236d6395284b98a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97334598"
---
# <a name="improper_scheduler_reference-class"></a>improper_scheduler_reference クラス

このクラスは、終了中の `Reference` オブジェクトで、スケジューラに属していないコンテキストから `Scheduler` メソッドが呼び出された場合にスローされる例外を表します。

## <a name="syntax"></a>構文

```cpp
class improper_scheduler_reference : public std::exception;
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[improper_scheduler_reference](#ctor)|オーバーロードされます。 `improper_scheduler_reference` オブジェクトを構築します。|

## <a name="inheritance-hierarchy"></a>継承階層

`exception`

`improper_scheduler_reference`

## <a name="requirements"></a>要件

**ヘッダー:** concrt .h

**名前空間:** concurrency

## <a name="improper_scheduler_reference"></a><a name="ctor"></a> improper_scheduler_reference

`improper_scheduler_reference` オブジェクトを構築します。

```cpp
explicit _CRTIMP improper_scheduler_reference(_In_z_ const char* _Message) throw();

improper_scheduler_reference() throw();
```

### <a name="parameters"></a>パラメーター

*_Message*<br/>
エラーの説明メッセージ。

## <a name="see-also"></a>関連項目

[concurrency 名前空間](concurrency-namespace.md)<br/>
[Scheduler クラス](scheduler-class.md)

---
description: '詳細情報: improper_scheduler_attach クラス'
title: improper_scheduler_attach クラス
ms.date: 11/04/2016
f1_keywords:
- improper_scheduler_attach
- CONCRT/concurrency::improper_scheduler_attach
- CONCRT/concurrency::improper_scheduler_attach::improper_scheduler_attach
helpviewer_keywords:
- improper_scheduler_attach class
ms.assetid: 5a76da0a-091b-4748-8f62-b3a28f674f9e
ms.openlocfilehash: 755cd72d20eb88dbd1ff7c58586f0aaf3b964a6a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97334620"
---
# <a name="improper_scheduler_attach-class"></a>improper_scheduler_attach クラス

このクラスは、現在のコンテキストに既にアタッチされている `Attach` オブジェクトで `Scheduler` メソッドが呼び出された場合にスローされる例外を表します。

## <a name="syntax"></a>構文

```cpp
class improper_scheduler_attach : public std::exception;
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[improper_scheduler_attach](#ctor)|オーバーロードされます。 `improper_scheduler_attach` オブジェクトを構築します。|

## <a name="inheritance-hierarchy"></a>継承階層

`exception`

`improper_scheduler_attach`

## <a name="requirements"></a>要件

**ヘッダー:** concrt .h

**名前空間:** concurrency

## <a name="improper_scheduler_attach"></a><a name="ctor"></a> improper_scheduler_attach

`improper_scheduler_attach` オブジェクトを構築します。

```cpp
explicit _CRTIMP improper_scheduler_attach(_In_z_ const char* _Message) throw();

improper_scheduler_attach() throw();
```

### <a name="parameters"></a>パラメーター

*_Message*<br/>
エラーの説明メッセージ。

## <a name="see-also"></a>関連項目

[concurrency 名前空間](concurrency-namespace.md)<br/>
[Scheduler クラス](scheduler-class.md)

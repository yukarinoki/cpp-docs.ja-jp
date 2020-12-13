---
description: '詳細情報: invalid_scheduler_policy_value クラス'
title: invalid_scheduler_policy_value クラス
ms.date: 11/04/2016
f1_keywords:
- concrt/concurrency::invalid_scheduler_policy_value
helpviewer_keywords:
- invalid_scheduler_policy_value class
ms.assetid: 8c533e3f-2774-4192-8616-b2313b859bf7
ms.openlocfilehash: c91295646b0bc85ea4ed5ee8f376c1ed029e4f0a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97334488"
---
# <a name="invalid_scheduler_policy_value-class"></a>invalid_scheduler_policy_value クラス

このクラスは、`SchedulerPolicy` オブジェクトのポリシー キーがそのキーの無効な値に設定された場合にスローされる例外を表します。

## <a name="syntax"></a>構文

```cpp
class invalid_scheduler_policy_value : public std::exception;
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[invalid_scheduler_policy_value](無効-スケジューラ-ポリシー-スレッドの指定-クラス。 md # .ctor|オーバーロードされます。 `invalid_scheduler_policy_value` オブジェクトを構築します。|

## <a name="inheritance-hierarchy"></a>継承階層

`exception`

`invalid_scheduler_policy_value`

## <a name="requirements"></a>要件

**ヘッダー:** concrt .h

**名前空間:** concurrency

## <a name="invalid_scheduler_policy_value"></a><a name="ctor"></a> invalid_scheduler_policy_value

`invalid_scheduler_policy_value` オブジェクトを構築します。

```cpp
explicit _CRTIMP invalid_scheduler_policy_value(_In_z_ const char* _Message) throw();

invalid_scheduler_policy_value() throw();
```

### <a name="parameters"></a>パラメーター

*_Message*<br/>
エラーの説明メッセージ。

## <a name="see-also"></a>関連項目

[concurrency 名前空間](concurrency-namespace.md)<br/>
[スケジューラポリシークラス](schedulerpolicy-class.md)

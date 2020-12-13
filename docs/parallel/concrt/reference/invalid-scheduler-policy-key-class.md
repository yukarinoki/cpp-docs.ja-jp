---
description: '詳細情報: invalid_scheduler_policy_key クラス'
title: invalid_scheduler_policy_key クラス
ms.date: 11/04/2016
f1_keywords:
- invalid_scheduler_policy_key
- CONCRT/concurrency::invalid_scheduler_policy_key
- CONCRT/concurrency::invalid_scheduler_policy_key::invalid_scheduler_policy_key
helpviewer_keywords:
- invalid_scheduler_policy_key class
ms.assetid: 6a7c42fe-9bc4-4a02-bebb-99fe9ef9817d
ms.openlocfilehash: d352246cf0fe94f0ba5ee567f353680c89efcddc
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97334509"
---
# <a name="invalid_scheduler_policy_key-class"></a>invalid_scheduler_policy_key クラス

このクラスは、無効なキーまたは不明なキーが `SchedulerPolicy` オブジェクトのコンストラクターに渡された場合、あるいは、本来他の方法 (`SetPolicyValue` メソッドなど) で変更する必要のあるキーが `SchedulerPolicy` オブジェクトの `SetConcurrencyLimits` メソッドに渡された場合にスローされる例外を表します。

## <a name="syntax"></a>構文

```cpp
class invalid_scheduler_policy_key : public std::exception;
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[invalid_scheduler_policy_key](#ctor)|オーバーロードされます。 `invalid_scheduler_policy_key` オブジェクトを構築します。|

## <a name="inheritance-hierarchy"></a>継承階層

`exception`

`invalid_scheduler_policy_key`

## <a name="requirements"></a>要件

**ヘッダー:** concrt .h

**名前空間:** concurrency

## <a name="invalid_scheduler_policy_key"></a><a name="ctor"></a> invalid_scheduler_policy_key

`invalid_scheduler_policy_key` オブジェクトを構築します。

```cpp
explicit _CRTIMP invalid_scheduler_policy_key(_In_z_ const char* _Message) throw();

invalid_scheduler_policy_key() throw();
```

### <a name="parameters"></a>パラメーター

*_Message*<br/>
エラーの説明メッセージ。

## <a name="see-also"></a>関連項目

[concurrency 名前空間](concurrency-namespace.md)<br/>
[スケジューラポリシークラス](schedulerpolicy-class.md)

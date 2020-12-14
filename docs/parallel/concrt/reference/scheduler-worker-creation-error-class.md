---
description: '詳細情報: scheduler_worker_creation_error クラス'
title: scheduler_worker_creation_error クラス
ms.date: 11/04/2016
f1_keywords:
- scheduler_worker_creation_error
- CONCRT/concurrency::scheduler_worker_creation_error
- CONCRT/concurrency::scheduler_worker_creation_error::scheduler_worker_creation_error
helpviewer_keywords:
- scheduler_worker_creation_error class
ms.assetid: 4aec1c3e-c32a-41b2-899d-2d898f23b3c7
ms.openlocfilehash: f0fbb0aed19738bb88e4cbfe3a72580627c4fca9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97188717"
---
# <a name="scheduler_worker_creation_error-class"></a>scheduler_worker_creation_error クラス

このクラスは、コンカレンシー ランタイムでワーカー実行コンテキストを作成できないためにスローされる例外を表します。

## <a name="syntax"></a>構文

```cpp
class scheduler_worker_creation_error : public scheduler_resource_allocation_error;
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[scheduler_worker_creation_error](#ctor)|オーバーロードされます。 `scheduler_worker_creation_error` オブジェクトを構築します。|

## <a name="remarks"></a>解説

この例外は、通常、同時実行ランタイム内から実行コンテキストを作成するためにオペレーティングシステムへの呼び出しが失敗した場合にスローされます。 実行コンテキストは、同時実行ランタイムでタスクを実行するスレッドです。 通常、Win32 メソッドの呼び出しから返されるエラーコード `GetLastError` は型の値に変換され、 `HRESULT` 基本クラスのメソッドを使用して取得でき `get_error_code` ます。

## <a name="inheritance-hierarchy"></a>継承階層

`exception`

[scheduler_resource_allocation_error](scheduler-resource-allocation-error-class.md)

`scheduler_worker_creation_error`

## <a name="requirements"></a>要件

**ヘッダー:** concrt .h

**名前空間:** concurrency

## <a name="scheduler_worker_creation_error"></a><a name="ctor"></a> scheduler_worker_creation_error

`scheduler_worker_creation_error` オブジェクトを構築します。

```cpp
scheduler_worker_creation_error(
    _In_z_ const char* _Message,
    HRESULT _Hresult) throw();

explicit _CRTIMP scheduler_worker_creation_error(
    HRESULT _Hresult) throw();
```

### <a name="parameters"></a>パラメーター

*_Message*<br/>
エラーの説明メッセージ。

*_Hresult*<br/>
`HRESULT`例外の原因となったエラーの値。

## <a name="see-also"></a>関連項目

[concurrency 名前空間](concurrency-namespace.md)

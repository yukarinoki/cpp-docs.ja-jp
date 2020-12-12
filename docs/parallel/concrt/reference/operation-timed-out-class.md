---
description: '詳細情報: operation_timed_out クラス'
title: operation_timed_out クラス
ms.date: 11/04/2016
f1_keywords:
- operation_timed_out
- CONCRT/concurrency::operation_timed_out
- CONCRT/concurrency::operation_timed_out::operation_timed_out
helpviewer_keywords:
- operation_timed_out class
ms.assetid: 963efe1d-a6e0-477c-9a70-d93d8412c897
ms.openlocfilehash: 476dfc2d7f29b2769c076ff525f3d0eb1e20a8f5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97236556"
---
# <a name="operation_timed_out-class"></a>operation_timed_out クラス

このクラスは、操作がタイムアウトした場合にスローされる例外を表します。

## <a name="syntax"></a>構文

```cpp
class operation_timed_out : public std::exception;
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[operation_timed_out](#ctor)|オーバーロードされます。 `operation_timed_out` オブジェクトを構築します。|

## <a name="inheritance-hierarchy"></a>継承階層

`exception`

`operation_timed_out`

## <a name="requirements"></a>要件

**ヘッダー:** concrt .h

**名前空間:** concurrency

## <a name="operation_timed_out"></a><a name="ctor"></a> operation_timed_out

`operation_timed_out` オブジェクトを構築します。

```cpp
explicit _CRTIMP operation_timed_out(_In_z_ const char* _Message) throw();

operation_timed_out() throw();
```

### <a name="parameters"></a>パラメーター

*_Message*<br/>
エラーの説明メッセージ。

## <a name="see-also"></a>関連項目

[concurrency 名前空間](concurrency-namespace.md)

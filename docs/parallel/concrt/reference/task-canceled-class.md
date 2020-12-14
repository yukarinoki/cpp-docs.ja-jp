---
description: '詳細情報: task_canceled クラス'
title: task_canceled クラス
ms.date: 11/04/2016
f1_keywords:
- task_canceled
- CONCRT/concurrency::task_canceled
- CONCRT/concurrency::task_canceled::task_canceled
helpviewer_keywords:
- task_canceled class
ms.assetid: c3f0b234-2cc1-435f-a48e-995f45b190be
ms.openlocfilehash: 223a1168464e312c272f770247b3574311ff97ed
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97188405"
---
# <a name="task_canceled-class"></a>task_canceled クラス

このクラスは、現在のタスクを強制的に取り消すために PPL タスク レイヤーによってスローされる例外を表します。 取り消されたタスクについても、タスクのメソッドによってスローされ `get()` ます。 [](/visualstudio/extensibility/debugger/task-class-internal-members)

## <a name="syntax"></a>構文

```cpp
class task_canceled : public std::exception;
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[task_canceled](#ctor)|オーバーロードされます。 `task_canceled` オブジェクトを構築します。|

## <a name="inheritance-hierarchy"></a>継承階層

`exception`

`task_canceled`

## <a name="requirements"></a>要件

**ヘッダー:** concrt .h

**名前空間:** concurrency

## <a name="task_canceled"></a><a name="ctor"></a> task_canceled

`task_canceled` オブジェクトを構築します。

```cpp
explicit _CRTIMP task_canceled(_In_z_ const char* _Message) throw();

task_canceled() throw();
```

### <a name="parameters"></a>パラメーター

*_Message*<br/>
エラーの説明メッセージ。

## <a name="see-also"></a>関連項目

[concurrency 名前空間](concurrency-namespace.md)

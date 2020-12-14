---
description: '詳細情報: missing_wait クラス'
title: missing_wait クラス
ms.date: 11/04/2016
f1_keywords:
- missing_wait
- CONCRT/concurrency::missing_wait
- CONCRT/concurrency::missing_wait::missing_wait
helpviewer_keywords:
- missing_wait class
ms.assetid: ff981875-bd43-47e3-806f-b03c9f418b18
ms.openlocfilehash: bfbfdf4c2a52573d08c048bac278386aed1dc5a8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97202185"
---
# <a name="missing_wait-class"></a>missing_wait クラス

このクラスは、`task_group` オブジェクトまたは `structured_task_group` オブジェクトのデストラクターの実行時に、そのオブジェクトにスケジュールされたタスクがまだ存在する場合にスローされる例外を表します。 例外の結果としてのスタック アンワインドによりデストラクターが実行される場合、この例外はスローされません。

## <a name="syntax"></a>構文

```cpp
class missing_wait : public std::exception;
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[missing_wait](#ctor)|オーバーロードされます。 `missing_wait` オブジェクトを構築します。|

## <a name="remarks"></a>解説

例外フローが存在しない場合は、 `wait` オブジェクトまたはオブジェクトのメソッドまたはメソッドを呼び出して、そのオブジェクトが破棄されるようにする必要があり `run_and_wait` `task_group` `structured_task_group` ます。 ランタイムは、メソッドまたはメソッドの呼び出しを忘れたことを示すために、この例外をスローし `wait` `run_and_wait` ます。

## <a name="inheritance-hierarchy"></a>継承階層

`exception`

`missing_wait`

## <a name="requirements"></a>要件

**ヘッダー:** concrt .h

**名前空間:** concurrency

## <a name="missing_wait"></a><a name="ctor"></a> missing_wait

`missing_wait` オブジェクトを構築します。

```cpp
explicit _CRTIMP missing_wait(_In_z_ const char* _Message) throw();

missing_wait() throw();
```

### <a name="parameters"></a>パラメーター

*_Message*<br/>
エラーの説明メッセージ。

## <a name="see-also"></a>関連項目

[concurrency 名前空間](concurrency-namespace.md)<br/>
[task_group クラス](task-group-class.md)<br/>
[wait](task-group-class.md)<br/>
[run_and_wait](task-group-class.md)<br/>
[structured_task_group クラス](structured-task-group-class.md)

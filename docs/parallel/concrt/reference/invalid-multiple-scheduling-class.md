---
title: invalid_multiple_scheduling クラス
ms.date: 11/04/2016
f1_keywords:
- invalid_multiple_scheduling
- CONCRT/concurrency::invalid_multiple_scheduling
- CONCRT/concurrency::invalid_multiple_scheduling::invalid_multiple_scheduling
helpviewer_keywords:
- invalid_multiple_scheduling class
ms.assetid: e9a47cb7-a778-4df7-92b0-3752119fd4c7
ms.openlocfilehash: 7c8ce0aefc12097a71e79933d34a116997c8105f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62252770"
---
# <a name="invalidmultiplescheduling-class"></a>invalid_multiple_scheduling クラス

このクラスは、`task_handle` オブジェクトまたは `run` オブジェクトの `task_group` メソッドを使用して `structured_task_group` オブジェクトが複数回スケジュールされた場合、間に `wait` メソッドまたは `run_and_wait` メソッドを呼び出さなかったときにスローされる例外を表します。

## <a name="syntax"></a>構文

```
class invalid_multiple_scheduling : public std::exception;
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[invalid_multiple_scheduling](#ctor)|オーバーロードされます。 `invalid_multiple_scheduling` オブジェクトを構築します。|

## <a name="inheritance-hierarchy"></a>継承階層

`exception`

`invalid_multiple_scheduling`

## <a name="requirements"></a>必要条件

**ヘッダー:** concrt.h

**名前空間:** concurrency

##  <a name="ctor"></a> invalid_multiple_scheduling

`invalid_multiple_scheduling` オブジェクトを構築します。

```
explicit _CRTIMP invalid_multiple_scheduling(_In_z_ const char* _Message) throw();

invalid_multiple_scheduling() throw();
```

### <a name="parameters"></a>パラメーター

*_Message*<br/>
エラーの説明メッセージ。

## <a name="see-also"></a>関連項目

[コンカレンシー名前空間](concurrency-namespace.md)<br/>
[task_handle クラス](task-handle-class.md)<br/>
[task_group クラス](task-group-class.md)<br/>
[run](task-group-class.md)<br/>
[wait](task-group-class.md)<br/>
[run_and_wait](task-group-class.md)<br/>
[structured_task_group クラス](structured-task-group-class.md)

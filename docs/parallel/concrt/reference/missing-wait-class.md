---
title: missing_wait クラス
ms.date: 11/04/2016
f1_keywords:
- missing_wait
- CONCRT/concurrency::missing_wait
- CONCRT/concurrency::missing_wait::missing_wait
helpviewer_keywords:
- missing_wait class
ms.assetid: ff981875-bd43-47e3-806f-b03c9f418b18
ms.openlocfilehash: 68d24d710eec4fd602e64cc3cbde810db2b1a495
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62409968"
---
# <a name="missingwait-class"></a>missing_wait クラス

このクラスは、`task_group` オブジェクトまたは `structured_task_group` オブジェクトのデストラクターの実行時に、そのオブジェクトにスケジュールされたタスクがまだ存在する場合にスローされる例外を表します。 例外の結果としてのスタック アンワインドによりデストラクターが実行される場合、この例外はスローされません。

## <a name="syntax"></a>構文

```
class missing_wait : public std::exception;
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[missing_wait](#ctor)|オーバーロードされます。 `missing_wait` オブジェクトを構築します。|

## <a name="remarks"></a>Remarks

例外のフロー、存在しない必要がありますいずれかを呼び出す、`wait`または`run_and_wait`のメソッド、`task_group`または`structured_task_group`消滅させるためには、そのオブジェクトを許可する前にオブジェクト。 ランタイムが呼び出しを忘れた場合を示す値としては、この例外をスロー、`wait`または`run_and_wait`メソッド。

## <a name="inheritance-hierarchy"></a>継承階層

`exception`

`missing_wait`

## <a name="requirements"></a>必要条件

**ヘッダー:** concrt.h

**名前空間:** concurrency

##  <a name="ctor"></a> missing_wait

`missing_wait` オブジェクトを構築します。

```
explicit _CRTIMP missing_wait(_In_z_ const char* _Message) throw();

missing_wait() throw();
```

### <a name="parameters"></a>パラメーター

*_Message*<br/>
エラーの説明メッセージ。

## <a name="see-also"></a>関連項目

[コンカレンシー名前空間](concurrency-namespace.md)<br/>
[task_group クラス](task-group-class.md)<br/>
[wait](task-group-class.md)<br/>
[run_and_wait](task-group-class.md)<br/>
[structured_task_group クラス](structured-task-group-class.md)

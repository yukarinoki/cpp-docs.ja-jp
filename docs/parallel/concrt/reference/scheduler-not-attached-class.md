---
title: scheduler_not_attached クラス
ms.date: 11/04/2016
f1_keywords:
- scheduler_not_attached
- CONCRT/concurrency::scheduler_not_attached
- CONCRT/concurrency::scheduler_not_attached::scheduler_not_attached
helpviewer_keywords:
- scheduler_not_attached class
ms.assetid: 26001970-b400-463b-be3d-8623359c399a
ms.openlocfilehash: be8a04c7cf6ef5aa4d6070e92df14e643395ef00
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62160121"
---
# <a name="schedulernotattached-class"></a>scheduler_not_attached クラス

このクラスは、現在のコンテキストにスケジューラがアタッチされている必要がある操作を実行するときにスケジューラがアタッチされていない場合にスローされる例外を表します。

## <a name="syntax"></a>構文

```
class scheduler_not_attached : public std::exception;
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[scheduler_not_attached](#ctor)|オーバーロードされます。 `scheduler_not_attached` オブジェクトを構築します。|

## <a name="inheritance-hierarchy"></a>継承階層

`exception`

`scheduler_not_attached`

## <a name="requirements"></a>必要条件

**ヘッダー:** concrt.h

**名前空間:** concurrency

##  <a name="ctor"></a> scheduler_not_attached

`scheduler_not_attached` オブジェクトを構築します。

```
explicit _CRTIMP scheduler_not_attached(_In_z_ const char* _Message) throw();

scheduler_not_attached() throw();
```

### <a name="parameters"></a>パラメーター

*_Message*<br/>
エラーの説明メッセージ。

## <a name="see-also"></a>関連項目

[コンカレンシー名前空間](concurrency-namespace.md)<br/>
[Scheduler クラス](scheduler-class.md)

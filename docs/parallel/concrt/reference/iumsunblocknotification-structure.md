---
title: IUMSUnblockNotification 構造体
ms.date: 11/04/2016
f1_keywords:
- IUMSUnblockNotification
- CONCRTRM/concurrency::IUMSUnblockNotification
- CONCRTRM/concurrency::IUMSUnblockNotification::IUMSUnblockNotification::GetContext
- CONCRTRM/concurrency::IUMSUnblockNotification::IUMSUnblockNotification::GetNextUnblockNotification
helpviewer_keywords:
- IUMSUnblockNotification structure
ms.assetid: eaca9529-c1cc-472b-8ec6-722a1ff0fa2a
ms.openlocfilehash: bdf083e2ad418269e49e53dc164f2a60f693d5d6
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/04/2019
ms.locfileid: "57261389"
---
# <a name="iumsunblocknotification-structure"></a>IUMSUnblockNotification 構造体

ブロックされ、スケジューラの指定されたスケジュール コンテキストに制御を戻すことをトリガーされたスレッド プロキシが、ブロック解除され、スケジュールできる状態であることを示す、リソース マネージャーからの通知を表します。 このインターフェイスは、`GetContext` メソッドから返される、スレッド プロキシの関連付けられた実行コンテキストが再スケジュールされると無効になります。

## <a name="syntax"></a>構文

```
struct IUMSUnblockNotification;
```

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[IUMSUnblockNotification::GetContext](#getcontext)|返します、`IExecutionContext`がブロック解除したスレッド プロキシに関連付けられている実行コンテキストのインターフェイス。 このメソッドが戻るし、基になる実行コンテキストは呼び出しにスケジュールが変更された後、`IThreadProxy::SwitchTo`メソッドでは、このインターフェイスは無効になりました。|
|[IUMSUnblockNotification::GetNextUnblockNotification](#getnextunblocknotification)|次を返します`IUMSUnblockNotification`メソッドから返されるチェーン内のインターフェイス`IUMSCompletionList::GetUnblockNotifications`します。|

## <a name="inheritance-hierarchy"></a>継承階層

`IUMSUnblockNotification`

## <a name="requirements"></a>必要条件

**ヘッダー:** concrtrm.h

**名前空間:** concurrency

##  <a name="getcontext"></a>  Iumsunblocknotification::getcontext メソッド

返します、`IExecutionContext`がブロック解除したスレッド プロキシに関連付けられている実行コンテキストのインターフェイス。 このメソッドが戻るし、基になる実行コンテキストは呼び出しにスケジュールが変更された後、`IThreadProxy::SwitchTo`メソッドでは、このインターフェイスは無効になりました。

```
virtual IExecutionContext* GetContext() = 0;
```

### <a name="return-value"></a>戻り値

`IExecutionContext`をブロック解除スレッド プロキシの実行コンテキストのインターフェイス。

##  <a name="getnextunblocknotification"></a>  Iumsunblocknotification::getnextunblocknotification メソッド

次を返します`IUMSUnblockNotification`メソッドから返されるチェーン内のインターフェイス`IUMSCompletionList::GetUnblockNotifications`します。

```
virtual IUMSUnblockNotification* GetNextUnblockNotification() = 0;
```

### <a name="return-value"></a>戻り値

次`IUMSUnblockNotification`メソッドから返されるチェーン内のインターフェイス`IUMSCompletionList::GetUnblockNotifications`します。

## <a name="see-also"></a>関連項目

[コンカレンシー名前空間](concurrency-namespace.md)<br/>
[IUMSScheduler 構造体](iumsscheduler-structure.md)<br/>
[IUMSCompletionList 構造体](iumscompletionlist-structure.md)

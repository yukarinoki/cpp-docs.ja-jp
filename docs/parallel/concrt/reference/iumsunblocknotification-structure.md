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
ms.openlocfilehash: 0b88ddd4184e982a5e07c536efc301eaa16f4a41
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81368069"
---
# <a name="iumsunblocknotification-structure"></a>IUMSUnblockNotification 構造体

ブロックされ、スケジューラの指定されたスケジュール コンテキストに制御を戻すことをトリガーされたスレッド プロキシが、ブロック解除され、スケジュールできる状態であることを示す、リソース マネージャーからの通知を表します。 このインターフェイスは、`GetContext` メソッドから返される、スレッド プロキシの関連付けられた実行コンテキストが再スケジュールされると無効になります。

## <a name="syntax"></a>構文

```cpp
struct IUMSUnblockNotification;
```

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[ブロック解除通知::コンテキストを取得します。](#getcontext)|ブロックされていない`IExecutionContext`スレッド プロキシに関連付けられている実行コンテキストのインターフェイスを返します。 このメソッドが返り、メソッドの呼び出しによって基になる実行コンテキストが`IThreadProxy::SwitchTo`再スケジュールされると、このインターフェイスは無効になります。|
|[通知をブロック解除:次のブロック解除通知](#getnextunblocknotification)|メソッド`IUMSCompletionList::GetUnblockNotifications`から返`IUMSUnblockNotification`されるチェーン内の次のインターフェイスを返します。|

## <a name="inheritance-hierarchy"></a>継承階層

`IUMSUnblockNotification`

## <a name="requirements"></a>必要条件

**ヘッダー:** concrtrm.h

**名前空間:** 同時実行

## <a name="iumsunblocknotificationgetcontext-method"></a><a name="getcontext"></a>メソッドをブロック解除します。

ブロックされていない`IExecutionContext`スレッド プロキシに関連付けられている実行コンテキストのインターフェイスを返します。 このメソッドが返り、メソッドの呼び出しによって基になる実行コンテキストが`IThreadProxy::SwitchTo`再スケジュールされると、このインターフェイスは無効になります。

```cpp
virtual IExecutionContext* GetContext() = 0;
```

### <a name="return-value"></a>戻り値

ブロック`IExecutionContext`が解除されたスレッド プロキシへの実行コンテキストのインターフェイス。

## <a name="iumsunblocknotificationgetnextunblocknotification-method"></a><a name="getnextunblocknotification"></a>通知をブロック解除:次のブロック解除通知メソッド

メソッド`IUMSCompletionList::GetUnblockNotifications`から返`IUMSUnblockNotification`されるチェーン内の次のインターフェイスを返します。

```cpp
virtual IUMSUnblockNotification* GetNextUnblockNotification() = 0;
```

### <a name="return-value"></a>戻り値

メソッド`IUMSCompletionList::GetUnblockNotifications`から`IUMSUnblockNotification`返されるチェーン内の次のインターフェイス。

## <a name="see-also"></a>関連項目

[同時実行名前空間](concurrency-namespace.md)<br/>
[IUMSScheduler 構造体](iumsscheduler-structure.md)<br/>
[IUMSCompletionList 構造体](iumscompletionlist-structure.md)

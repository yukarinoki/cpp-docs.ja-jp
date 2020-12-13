---
description: '詳細については、次を参照してください: IUMSUnblockNotification 構造体'
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
ms.openlocfilehash: bec40ee1e7326ad37e205c3035f965cb3f0ec8d4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97334318"
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
|[IUMSUnblockNotification:: GetContext](#getcontext)|ブロック解除され `IExecutionContext` たスレッドプロキシに関連付けられている実行コンテキストのインターフェイスを返します。 このメソッドが返され、基になる実行コンテキストがメソッドの呼び出しによって再スケジュールされると `IThreadProxy::SwitchTo` 、このインターフェイスは無効になります。|
|[IUMSUnblockNotification:: GetNextUnblockNotification](#getnextunblocknotification)|`IUMSUnblockNotification`メソッドから返されたチェーン内の次のインターフェイスを返し `IUMSCompletionList::GetUnblockNotifications` ます。|

## <a name="inheritance-hierarchy"></a>継承階層

`IUMSUnblockNotification`

## <a name="requirements"></a>要件

**ヘッダー:** concrtrm. h

**名前空間:** concurrency

## <a name="iumsunblocknotificationgetcontext-method"></a><a name="getcontext"></a> IUMSUnblockNotification:: GetContext メソッド

ブロック解除され `IExecutionContext` たスレッドプロキシに関連付けられている実行コンテキストのインターフェイスを返します。 このメソッドが返され、基になる実行コンテキストがメソッドの呼び出しによって再スケジュールされると `IThreadProxy::SwitchTo` 、このインターフェイスは無効になります。

```cpp
virtual IExecutionContext* GetContext() = 0;
```

### <a name="return-value"></a>戻り値

ブロック解除さ `IExecutionContext` れたスレッドプロキシへの実行コンテキストのインターフェイス。

## <a name="iumsunblocknotificationgetnextunblocknotification-method"></a><a name="getnextunblocknotification"></a> IUMSUnblockNotification:: GetNextUnblockNotification メソッド

`IUMSUnblockNotification`メソッドから返されたチェーン内の次のインターフェイスを返し `IUMSCompletionList::GetUnblockNotifications` ます。

```cpp
virtual IUMSUnblockNotification* GetNextUnblockNotification() = 0;
```

### <a name="return-value"></a>戻り値

`IUMSUnblockNotification`メソッドから返された、チェーン内の次のインターフェイス `IUMSCompletionList::GetUnblockNotifications` 。

## <a name="see-also"></a>関連項目

[concurrency 名前空間](concurrency-namespace.md)<br/>
[IUMSScheduler 構造体](iumsscheduler-structure.md)<br/>
[IUMSCompletionList 構造体](iumscompletionlist-structure.md)

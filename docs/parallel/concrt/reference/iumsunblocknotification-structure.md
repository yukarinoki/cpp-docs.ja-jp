---
title: IUMSUnblockNotification 構造体 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
f1_keywords:
- IUMSUnblockNotification
- CONCRTRM/concurrency::IUMSUnblockNotification
- CONCRTRM/concurrency::IUMSUnblockNotification::IUMSUnblockNotification::GetContext
- CONCRTRM/concurrency::IUMSUnblockNotification::IUMSUnblockNotification::GetNextUnblockNotification
dev_langs:
- C++
helpviewer_keywords:
- IUMSUnblockNotification structure
ms.assetid: eaca9529-c1cc-472b-8ec6-722a1ff0fa2a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: bda4f6e2b0565d39fd604767f3a89bcdd9a6df2c
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
ms.locfileid: "33687008"
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
|[IUMSUnblockNotification::GetContext](#getcontext)|返します、`IExecutionContext`ブロック解除、スレッド プロキシに関連付けられている実行コンテキストのインターフェイスです。 このメソッドが戻るし、基になる実行コンテキストは呼び出しを経由してスケジュールが変更された後、`IThreadProxy::SwitchTo`メソッドでは、このインターフェイスは無効になりました。|  
|[IUMSUnblockNotification::GetNextUnblockNotification](#getnextunblocknotification)|次を返します`IUMSUnblockNotification`メソッドから返されたチェーン内のインターフェイス`IUMSCompletionList::GetUnblockNotifications`です。|  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `IUMSUnblockNotification`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** concrtrm.h  
  
 **名前空間:** concurrency  
  
##  <a name="getcontext"></a>  Iumsunblocknotification::getcontext メソッド  
 返します、`IExecutionContext`ブロック解除、スレッド プロキシに関連付けられている実行コンテキストのインターフェイスです。 このメソッドが戻るし、基になる実行コンテキストは呼び出しを経由してスケジュールが変更された後、`IThreadProxy::SwitchTo`メソッドでは、このインターフェイスは無効になりました。  
  
```
virtual IExecutionContext* GetContext() = 0;
```  
  
### <a name="return-value"></a>戻り値  
 `IExecutionContext`スレッド プロキシがブロック解除する実行コンテキストのインターフェイスです。  
  
##  <a name="getnextunblocknotification"></a>  Iumsunblocknotification::getnextunblocknotification メソッド  
 次を返します`IUMSUnblockNotification`メソッドから返されたチェーン内のインターフェイス`IUMSCompletionList::GetUnblockNotifications`です。  
  
```
virtual IUMSUnblockNotification* GetNextUnblockNotification() = 0;
```  
  
### <a name="return-value"></a>戻り値  
 次`IUMSUnblockNotification`メソッドから返されたチェーン内のインターフェイス`IUMSCompletionList::GetUnblockNotifications`です。  
  
## <a name="see-also"></a>関連項目  
 [同時実行 Namespace](concurrency-namespace.md)   
 [IUMSScheduler 構造体](iumsscheduler-structure.md)   
 [IUMSCompletionList 構造体](iumscompletionlist-structure.md)

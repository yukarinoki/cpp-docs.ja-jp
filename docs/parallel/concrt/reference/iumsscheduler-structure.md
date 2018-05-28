---
title: IUMSScheduler 構造体 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
f1_keywords:
- IUMSScheduler
- CONCRTRM/concurrency::IUMSScheduler
- CONCRTRM/concurrency::IUMSScheduler::IUMSScheduler::SetCompletionList
dev_langs:
- C++
helpviewer_keywords:
- IUMSScheduler structure
ms.assetid: 3a500225-4e02-4849-bb56-d744865f5870
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 489978a97d42439e5560a75e429c38be10c18c29
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
---
# <a name="iumsscheduler-structure"></a>IUMSScheduler 構造体
同時実行ランタイムのリソース マネージャーによってユーザー モード スケジュール可能 (UMS) スレッドが渡される必要がある作業スケジューラの抽象化のインターフェイスです。 リソース マネージャーでは、このインターフェイスを使用して UMS スレッド スケジューラと通信します。 `IUMSScheduler` インターフェイスは `IScheduler` のインターフェイスから継承されます。  
  
## <a name="syntax"></a>構文  
  
```
struct IUMSScheduler : public IScheduler;
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[IUMSScheduler::SetCompletionList](#setcompletionlist)|割り当てます、 `IUMSCompletionList` UMS スレッド スケジューラへのインターフェイスです。|  
  
## <a name="remarks"></a>コメント  
 リソース マネージャーとの通信を行うカスタム スケジューラを実装して、通常の Win32 スレッドではなく、スケジューラに渡す UMS スレッドは場合の実装を提供する必要があります、`IUMSScheduler`インターフェイスです。 さらに、スケジューラ ポリシー キーのポリシーの値を設定する必要があります`SchedulerKind`する`UmsThreadDefault`です。 ポリシーが UMS スレッドを指定する場合、`IScheduler`インターフェイスへのパラメーターとして渡される、 [iresourcemanager::registerscheduler](iresourcemanager-structure.md#registerscheduler)メソッドである必要があります、`IUMSScheduler`インターフェイスです。  
  
 リソース マネージャーでは、UMS 機能を持つオペレーティング システムでのみ、UMS スレッドです。 64 ビット オペレーティング システムが Windows 7 以降のバージョンでは、UMS スレッドをサポートします。 スケジューラを使用してポリシーを作成する場合、`SchedulerKind`キー値に設定されて`UmsThreadDefault`基になるプラットフォームでは、UMS の値をサポートしていない、`SchedulerKind`そのポリシーのキーは、値に変更されます`ThreadScheduler`です。 必ず確認してこのポリシーの値 UMS スレッドが表示されることを想定します。  
  
 `IUMSScheduler`インターフェイスは、双方向チャネル スケジューラおよびリソース マネージャー間の通信の一方の端。 もう一方の end がによって表される、`IResourceManager`と`ISchedulerProxy`リソース マネージャーによって実装されるインターフェイス。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [IScheduler](ischeduler-structure.md)  
  
 `IUMSScheduler`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** concrtrm.h  
  
 **名前空間:** concurrency  
  
##  <a name="setcompletionlist"></a>  Iumsscheduler::setcompletionlist メソッド  
 割り当てます、 `IUMSCompletionList` UMS スレッド スケジューラへのインターフェイスです。  
  
```
virtual void SetCompletionList(_Inout_ IUMSCompletionList* pCompletionList) = 0;
```  
  
### <a name="parameters"></a>パラメーター  
 `pCompletionList`  
 スケジューラの完了リスト インターフェイスです。 スケジューラあたり 1 つのリストがあります。  
  
### <a name="remarks"></a>コメント  
 リソース マネージャーでは、スケジューラがリソースの最初の割り当てを要求された後に UMS スレッドが必要であるスケジューラでは、このメソッドを呼び出します。 スケジューラが使用できる、 `IUMSCompletionList` UMS スレッド プロキシがブロックされない場合を決定するインターフェイスです。 UMS スケジューラに割り当てられている仮想プロセッサ ルートで実行されているスレッド プロキシからこのインターフェイスにアクセスすることはのみです。  
  
## <a name="see-also"></a>関連項目  
 [同時実行 Namespace](concurrency-namespace.md)   
 [PolicyElementKey](concurrency-namespace-enums.md)   
 [IScheduler 構造体](ischeduler-structure.md)   
 [IUMSCompletionList 構造体](iumscompletionlist-structure.md)   
 [IResourceManager 構造体](iresourcemanager-structure.md)

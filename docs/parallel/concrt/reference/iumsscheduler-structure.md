---
title: IUMSScheduler 構造体 |Microsoft Docs
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
ms.openlocfilehash: 46ed7dac35dce4b5df51cd4c218a1a70a84d21df
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46079064"
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
|[IUMSScheduler::SetCompletionList](#setcompletionlist)|割り当てます、 `IUMSCompletionList` UMS スレッド スケジューラのインターフェイス。|  
  
## <a name="remarks"></a>Remarks  
 Resource Manager での通信を行うカスタム スケジューラを実装して、通常の Win32 スレッドではなく、スケジューラに渡す UMS スレッドは場合の実装を提供する必要があります、`IUMSScheduler`インターフェイス。 さらに、スケジューラ ポリシー キーのポリシー値を設定する必要があります`SchedulerKind`する`UmsThreadDefault`します。 ポリシーは、UMS スレッドを指定する場合、`IScheduler`インターフェイスへのパラメーターとして渡される、 [iresourcemanager::registerscheduler](iresourcemanager-structure.md#registerscheduler)メソッドである必要があります、`IUMSScheduler`インターフェイス。  
  
 Resource Manager では、UMS スレッドを UMS 機能になっているオペレーティング システムでのみできます。 Windows 7 以降のバージョンと 64 ビット オペレーティング システムでは、UMS スレッドをサポートします。 スケジューラ ポリシーを作成する場合、`SchedulerKind`キー値に設定`UmsThreadDefault`UMS の値を基になるプラットフォームがサポートしていませんし、`SchedulerKind`そのポリシーのキーは、値に変更されます`ThreadScheduler`します。 常にお読みくださいバックアップ ポリシーの値はこの UMS スレッドが表示されることを想定します。  
  
 `IUMSScheduler`インターフェイスは、スケジューラとリソース マネージャー間の通信の双方向チャネルの片端となります。 もう一方の end がによって表される、`IResourceManager`と`ISchedulerProxy`インターフェイスで、リソース マネージャーでは実装されています。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [IScheduler](ischeduler-structure.md)  
  
 `IUMSScheduler`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** concrtrm.h  
  
 **名前空間:** concurrency  
  
##  <a name="setcompletionlist"></a>  Iumsscheduler::setcompletionlist メソッド  
 割り当てます、 `IUMSCompletionList` UMS スレッド スケジューラのインターフェイス。  
  
```
virtual void SetCompletionList(_Inout_ IUMSCompletionList* pCompletionList) = 0;
```  
  
### <a name="parameters"></a>パラメーター  
*pCompletionList*<br/>
スケジューラの完了リスト インターフェイスです。 スケジューラごとの 1 つのリストがあります。  
  
### <a name="remarks"></a>Remarks  
 Resource Manager では、スケジューラがリソースの最初の割り当てを要求した後、UMS スレッドが必要であるスケジューラでは、このメソッドを呼び出します。 スケジューラを使用できる、 `IUMSCompletionList` UMS スレッド プロキシがブロック解除が決定するインターフェイス。 UMS スケジューラに割り当てられている仮想プロセッサ ルートで実行されているスレッド プロキシからこのインターフェイスにアクセスすることはのみです。  
  
## <a name="see-also"></a>関連項目  
 [同時実行 Namespace](concurrency-namespace.md)   
 [PolicyElementKey](concurrency-namespace-enums.md)   
 [IScheduler 構造体](ischeduler-structure.md)   
 [IUMSCompletionList 構造体](iumscompletionlist-structure.md)   
 [IResourceManager 構造体](iresourcemanager-structure.md)

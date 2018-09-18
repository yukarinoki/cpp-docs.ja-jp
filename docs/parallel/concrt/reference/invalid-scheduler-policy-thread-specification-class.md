---
title: invalid_scheduler_policy_thread_specification クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
f1_keywords:
- concrt/concurrency::invalid_scheduler_policy_thread_specification
dev_langs:
- C++
helpviewer_keywords:
- invalid_scheduler_policy_thread_specification class
ms.assetid: 2d0fafb2-18f8-4284-8040-3db640d33303
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ab180a5f52a7645b7ce6cc0f8a04e2ea506f8aa4
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46016612"
---
# <a name="invalidschedulerpolicythreadspecification-class"></a>invalid_scheduler_policy_thread_specification クラス
このクラスは、`SchedulerPolicy` オブジェクトの同時実行数の限度を設定する際に、`MinConcurrency` キーに指定された値が `MaxConcurrency` キーの値よりも小さい場合にスローされる例外を表します。  
  
## <a name="syntax"></a>構文  
  
```
class invalid_scheduler_policy_thread_specification : public std::exception;
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[invalid_scheduler_policy_thread_specification](無効です-scheduler-ポリシーの値-class.md #ctor|オーバーロードされます。 `invalid_scheduler_policy_value` オブジェクトを構築します。|  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `exception`  
  
 `invalid_scheduler_policy_thread_specification`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** concrt.h  
  
 **名前空間:** concurrency  
##  <a name="ctor"></a> invalid_scheduler_policy_thread_specification 

 `invalid_scheduler_policy_value` オブジェクトを構築します。  
  
```
explicit _CRTIMP invalid_scheduler_policy_thread_specification(_In_z_ const char* _Message) throw();

invalid_scheduler_policy_thread_specification() throw();
```  
  
### <a name="parameters"></a>パラメーター  
*メッセージ (_m)*<br/>
エラーの説明メッセージ。  

## <a name="see-also"></a>関連項目  
 [同時実行 Namespace](concurrency-namespace.md)   
 [SchedulerPolicy クラス](schedulerpolicy-class.md)

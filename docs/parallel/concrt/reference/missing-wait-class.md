---
title: missing_wait クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
f1_keywords:
- missing_wait
- CONCRT/concurrency::missing_wait
- CONCRT/concurrency::missing_wait::missing_wait
dev_langs:
- C++
helpviewer_keywords:
- missing_wait class
ms.assetid: ff981875-bd43-47e3-806f-b03c9f418b18
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a2a44cbdb5abeed7d5dbd7be7dfaba37ba1d0145
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46024958"
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
  
## <a name="requirements"></a>要件  
 **ヘッダー:** concrt.h  
  
 **名前空間:** concurrency  
  
##  <a name="ctor"></a> missing_wait 

 `missing_wait` オブジェクトを構築します。  
  
```
explicit _CRTIMP missing_wait(_In_z_ const char* _Message) throw();

missing_wait() throw();
```  
  
### <a name="parameters"></a>パラメーター  
*メッセージ (_m)*<br/>
エラーの説明メッセージ。  
  
## <a name="see-also"></a>関連項目  
 [同時実行 Namespace](concurrency-namespace.md)   
 [task_group クラス](task-group-class.md)   
 [wait](task-group-class.md)   
 [run_and_wait](task-group-class.md)   
 [structured_task_group クラス](structured-task-group-class.md)

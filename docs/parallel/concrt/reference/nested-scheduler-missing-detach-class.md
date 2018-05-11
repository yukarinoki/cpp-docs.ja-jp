---
title: nested_scheduler_missing_detach クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
f1_keywords:
- nested_scheduler_missing_detach
- CONCRT/concurrency::nested_scheduler_missing_detach
- CONCRT/concurrency::nested_scheduler_missing_detach::nested_scheduler_missing_detach
dev_langs:
- C++
helpviewer_keywords:
- nested_scheduler_missing_detach class
ms.assetid: 65d3f277-6d43-4160-97ef-caf8b26c1641
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 26027693209bc5b4687686efeae5d190ed374607
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
---
# <a name="nestedschedulermissingdetach-class"></a>nested_scheduler_missing_detach クラス
このクラスは、`CurrentScheduler::Detach` オブジェクトの `Attach` メソッドによって別のスケジューラにアタッチされているコンテキストで `Scheduler` メソッドが呼び出されなかったことを、同時実行ランタイムが検出した場合にスローされる例外を表します。  
  
## <a name="syntax"></a>構文  
  
```
class nested_scheduler_missing_detach : public std::exception;
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[nested_scheduler_missing_detach](#ctor)|オーバーロードされます。 `nested_scheduler_missing_detach` オブジェクトを構築します。|  
  
## <a name="remarks"></a>コメント  
 呼び出して別のスケジューラ内に入れ子にする場合にのみ、この例外がスローされます、`Attach`のメソッド、`Scheduler`オブジェクトは既に所有してか、別のスケジューラにアタッチされているコンテキストでします。 同時実行ランタイムは、問題の特定に役立てるために、シナリオを検出できるとな場合にこの例外をスローします。 呼び出しを無視していないすべてのインスタンス、`CurrentScheduler::Detach`メソッドがこの例外をスローすることが保証されます。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `exception`  
  
 `nested_scheduler_missing_detach`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** concrt.h  
  
 **名前空間:** concurrency  
  
##  <a name="ctor"></a> nested_scheduler_missing_detach 

 `nested_scheduler_missing_detach` オブジェクトを構築します。  
  
```
explicit _CRTIMP nested_scheduler_missing_detach(_In_z_ const char* _Message) throw();

nested_scheduler_missing_detach() throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `_Message`  
 エラーの説明メッセージ。  
  
## <a name="see-also"></a>関連項目  
 [同時実行 Namespace](concurrency-namespace.md)   
 [Scheduler クラス](scheduler-class.md)

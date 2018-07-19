---
title: ScheduleGroup クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
f1_keywords:
- ScheduleGroup
- CONCRT/concurrency::ScheduleGroup
- CONCRT/concurrency::ScheduleGroup::Id
- CONCRT/concurrency::ScheduleGroup::Reference
- CONCRT/concurrency::ScheduleGroup::Release
- CONCRT/concurrency::ScheduleGroup::ScheduleTask
dev_langs:
- C++
helpviewer_keywords:
- ScheduleGroup class
ms.assetid: 86d380ff-f2e8-411c-b1a8-22bd3079824a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: cf679abbeb1134332d98ef0bd2ba8f2b845d30a4
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
ms.locfileid: "33688688"
---
# <a name="schedulegroup-class"></a>ScheduleGroup クラス
スケジュール グループの抽象化を表します。 スケジュール グループは、(別のグループに移動する前に同じグループ内の別のタスクを実行することで) 一時的に、または (同じ NUMA ノードまたは物理ソケットの同じグループ内の複数の項目を実行することにより) 空間的に、短い間隔でスケジュールするとメリットがある関連作業のセットを編成します。  
  
## <a name="syntax"></a>構文  
  
```
class ScheduleGroup;
```  
  
## <a name="members"></a>メンバー  
  
### <a name="protected-constructors"></a>プロテクト コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[~ ScheduleGroup デストラクター](#dtor)||  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[Id](#id)|スケジュール グループが属するスケジューラ内で一意のスケジュール グループの識別子を返します。|  
|[参照](#reference)|スケジュール グループの参照カウントをインクリメントします。|  
|[Release](#release)|スケジュール グループの参照カウントをデクリメントします。|  
|[ScheduleTask](#scheduletask)|スケジュール グループ内の軽量タスクをスケジュールします。|  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `ScheduleGroup`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** concrt.h  
  
 **名前空間:** concurrency  
  
##  <a name="id"></a> id 

 スケジュール グループが属するスケジューラ内で一意のスケジュール グループの識別子を返します。  
  
```
virtual unsigned int Id() const = 0;
```  
  
### <a name="return-value"></a>戻り値  
 グループが属するスケジューラ内で一意では、スケジュール グループの識別子です。  
  
##  <a name="operator_delete"></a> delete 演算子 

 A`ScheduleGroup`オブジェクトが破棄される内部的には、ランタイムによってすべての外部参照がリリースされたときにします。 明示的に削除できません。  
  
```
void operator delete(
    void* _PObject);

void operator delete(
    void* _PObject,
    int,
 const char *,
    int);
```    
  
### <a name="parameters"></a>パラメーター  
 `_PObject`  
 削除するオブジェクトへのポインター。  
  
##  <a name="reference"></a> 参照 

 スケジュール グループの参照カウントをインクリメントします。  
  
```
virtual unsigned int Reference() = 0;
```  
  
### <a name="return-value"></a>戻り値  
 新たにインクリメントされた参照カウントします。  
  
### <a name="remarks"></a>コメント  
 これは、スケジュール グループの構成の有効期間を管理に通常使用されます。 スケジュール グループの参照カウントがゼロになる、スケジュール グループは、ランタイムによって削除されます。 いずれかを使用して作成されたスケジュール グループ、 [currentscheduler::createschedulegroup](currentscheduler-class.md#createschedulegroup)メソッド、または[scheduler::createschedulegroup](scheduler-class.md#createschedulegroup)メソッドを 1 つの参照カウント開始します。  
  
##  <a name="release"></a> リリース 

 スケジュール グループの参照カウントをデクリメントします。  
  
```
virtual unsigned int Release() = 0;
```  
  
### <a name="return-value"></a>戻り値  
 新たにデクリメントされた参照カウントします。  
  
### <a name="remarks"></a>コメント  
 これは、スケジュール グループの構成の有効期間を管理に通常使用されます。 スケジュール グループの参照カウントがゼロになる、スケジュール グループは、ランタイムによって削除されます。 呼び出した後、`Release`メソッド作成を削除する、特定回数の参照カウントと、その他の参照を使用して配置、`Reference`メソッド、さらに、スケジュール グループを使用することはできません。 これにより、未定義の動作が発生します。  
  
 スケジュール グループは、特定のスケジューラ インスタンスに関連付けられます。 スケジュール グループにすべての参照に確実に解放スケジューラへのすべての参照がリリースされると、おそれがあるため、後者で破棄されているスケジューラを確認する必要があります。 未定義の動作のそれ以外の場合の結果を行っています。  
  
##  <a name="dtor"></a> ~ ScheduleGroup 

```
virtual ~ScheduleGroup();
```  
  
##  <a name="scheduletask"></a> ScheduleTask 

 スケジュール グループ内の軽量タスクをスケジュールします。  
  
```
virtual void ScheduleTask(
    TaskProc _Proc,
    _Inout_opt_ void* _Data) = 0;
```  
  
### <a name="parameters"></a>パラメーター  
 `_Proc`  
 軽量タスクの本体を実行するために実行する関数へのポインター。  
  
 `_Data`  
 タスクの本体にパラメーターとして渡されるデータへの void ポインターです。  
  
### <a name="remarks"></a>コメント  
 呼び出す、`ScheduleTask`メソッドが、ランタイムによって、タスクの実行後に適切なタイミングで削除されるスケジュール グループに暗黙的に参照カウントを配置します。  
  
## <a name="see-also"></a>関連項目  
 [同時実行 Namespace](concurrency-namespace.md)   
 [CurrentScheduler クラス](currentscheduler-class.md)   
 [Scheduler クラス](scheduler-class.md)   
 [タスク スケジューラ](../../../parallel/concrt/task-scheduler-concurrency-runtime.md)




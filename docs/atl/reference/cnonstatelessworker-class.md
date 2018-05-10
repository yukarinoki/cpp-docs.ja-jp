---
title: CNonStatelessWorker クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CNonStatelessWorker
- ATLUTIL/ATL::CNonStatelessWorker
- ATLUTIL/ATL::CNonStatelessWorker::RequestType
- ATLUTIL/ATL::CNonStatelessWorker::Execute
- ATLUTIL/ATL::CNonStatelessWorker::Initialize
- ATLUTIL/ATL::CNonStatelessWorker::Terminate
dev_langs:
- C++
helpviewer_keywords:
- CNonStatelessWorker class
ms.assetid: d00936c6-9e7d-49fb-b87d-417b963367d1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: de03ded4bc0021a8884f608d10368e3d09c11cf8
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="cnonstatelessworker-class"></a>CNonStatelessWorker クラス
スレッド プールからの要求を受信し、各要求の作成し、破棄がワーカー オブジェクトに渡されます。  
  
> [!IMPORTANT]
>  このクラスとそのメンバーは、Windows ランタイムで実行するアプリケーションでは使用できません。  
  
## <a name="syntax"></a>構文  
  
```
template <class Worker>  
class CNonStatelessWorker
```  
  
#### <a name="parameters"></a>パラメーター  
 *ワーカー*  
 準拠しているワーカー スレッドのクラス、[ワーカー原型](../../atl/reference/worker-archetype.md)キューに置かれた要求を処理するのに適した[CThreadPool](../../atl/reference/cthreadpool-class.md)です。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-typedefs"></a>パブリック typedef  
  
|名前|説明|  
|----------|-----------------|  
|[CNonStatelessWorker::RequestType](#requesttype)|実装[WorkerArchetype::RequestType](worker-archetype.md#requesttype)です。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CNonStatelessWorker::Execute](#execute)|実装[WorkerArchetype::Execute](worker-archetype.md#execute)です。|  
|[CNonStatelessWorker::Initialize](#initialize)|実装[WorkerArchetype::Initialize](worker-archetype.md#initialize)です。|  
|[CNonStatelessWorker::Terminate](#terminate)|実装[WorkerArchetype::Terminate](worker-archetype.md#terminate)です。|  
  
## <a name="remarks"></a>コメント  
 このクラスで使用するための単純なワーカー スレッド[CThreadPool](../../atl/reference/cthreadpool-class.md)です。 このクラスは、独自の要求の処理機能を提供しません。 代わりに、1 つのインスタンスをインスタンス化*ワーカー* 1 回の要求し、そのインスタンスにそのメソッドの実装のデリゲートします。  
  
 このクラスの利点では、既存のワーカー スレッドのクラスの状態モデルを変更する便利な手段を提供することです。 `CThreadPool` スレッドの有効期間の 1 つのワーカーを作成ワーカー クラスには、状態が保持している場合は保持する必要が、複数の要求でようにします。 そのクラスをラップするだけで、`CNonStatelessWorker`と共に使用する前にテンプレート`CThreadPool`、作業者と 1 つの要求に制限されますが、保持している状態の有効期間。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlutil.h  
  
##  <a name="execute"></a>  CNonStatelessWorker::Execute  
 実装[WorkerArchetype::Execute](worker-archetype.md#execute)です。  

  
```
void Execute(
    Worker::RequestType request,
    void* pvWorkerParam,
    OVERLAPPED* pOverlapped);
```  
  
### <a name="remarks"></a>コメント  
 このメソッドのインスタンスを作成、*ワーカー*スタックとの呼び出しでクラス[初期化](worker-archetype.md#initialize)そのオブジェクトにします。 初期化が成功した場合、このメソッドも呼び出します[Execute](worker-archetype.md#execute)と[Terminate](worker-archetype.md#terminate)同じオブジェクトにします。  

  
##  <a name="initialize"></a>  CNonStatelessWorker::Initialize  
 実装[WorkerArchetype::Initialize](worker-archetype.md#initialize)です。  
  
```
BOOL Initialize(void* /* pvParam */) throw();
```  
  
### <a name="return-value"></a>戻り値  
 常に TRUE を返します。  
  
### <a name="remarks"></a>コメント  
 このクラス初期化を行わない`Initialize`です。  
  
##  <a name="requesttype"></a>  CNonStatelessWorker::RequestType  
 実装[WorkerArchetype::RequestType](worker-archetype.md#requesttype)です。  
  
```
typedef Worker::RequestType RequestType;
```  
  
### <a name="remarks"></a>コメント  
 このクラスは、同じ作業項目の種類に使用するクラスとして、処理、*ワーカー*テンプレート パラメーター。 参照してください[CNonStatelessWorker 概要](../../atl/reference/cnonstatelessworker-class.md)詳細についてはします。  
  
##  <a name="terminate"></a>  CNonStatelessWorker::Terminate  
 実装[WorkerArchetype::Terminate](worker-archetype.md#terminate)です。  
  
```
void Terminate(void* /* pvParam */) throw();
```  
  
### <a name="remarks"></a>コメント  
 このクラスは任意のクリーンアップを行えません`Terminate`です。  
  
## <a name="see-also"></a>関連項目  
 [CThreadPool クラス](../../atl/reference/cthreadpool-class.md)   
 [ワーカー原型](../../atl/reference/worker-archetype.md)   
 [クラス](../../atl/reference/atl-classes.md)

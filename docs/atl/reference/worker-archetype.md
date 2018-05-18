---
title: ワーカー原型 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- Worker archetype
ms.assetid: 834145cd-09d3-4149-bc99-620e1871cbfb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: cee9df0b137655fe66e68c189de756f15233a94d
ms.sourcegitcommit: 19a108b4b30e93a9ad5394844c798490cb3e2945
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/17/2018
---
# <a name="worker-archetype"></a>ワーカー原型
準拠するクラス、*ワーカー*原型がスレッド プールのキューに作業アイテムを処理するコードを提供します。  
  
 **実装**  
  
 この原型に準拠するクラスを実装するには、クラスは、次の機能を提供する必要があります。  
  
|メソッド|説明|  
|------------|-----------------|  
|[Initialize](#initialize)|すべての要求に渡される前にワーカー オブジェクトを初期化するために呼び出されます[Execute](#execute)です。|  
|[実行します。](#execute)|作業項目を処理と呼ばれます。|  
|[終了](#terminate)|初期化ワーカー オブジェクトのすべての要求に渡された後に呼び出された[Execute](#execute)です。|  
  
|Typedef|説明|  
|-------------|-----------------|  
|[RequestType](#requesttype)|ワーカー クラスによって処理できる作業項目の種類の typedef。|  
  
 一般的な*ワーカー*クラスは、次のようになります。  
  
 [!code-cpp[NVC_ATL_Utilities#137](../../atl/codesnippet/cpp/worker-archetype_1.cpp)]  
  
 **既存の実装**  
  
 これらのクラスは、この原型に準拠します。  
  
|クラス|説明|  
|-----------|-----------------|  
|[CNonStatelessWorker](../../atl/reference/cnonstatelessworker-class.md)|スレッド プールからの要求を受信し、作成され、要求ごとに破棄されるワーカー オブジェクトに渡します。|  
  
 **使用します。**  
  
 これらのテンプレート パラメーターには、この原型に準拠するようにクラスが期待される結果します。  
  
|パラメーター名|使用者|  
|--------------------|-------------|  
|*ワーカー*|[CThreadPool](../../atl/reference/cthreadpool-class.md)|  
|*ワーカー*|[CNonStatelessWorker](../../atl/reference/cnonstatelessworker-class.md)|  
  
### <a name="requirements"></a>要件  
 **ヘッダー:** atlutil.h  
  
## <a name="execute"></a>WorkerArchetype::Execute
作業項目を処理と呼ばれます。  
  
  
  
```  
void Execute(
    RequestType request,  
    void* pvWorkerParam,  
    OVERLAPPED* pOverlapped);
```  
  
#### <a name="parameters"></a>パラメーター  
 `request`  
 処理する作業アイテム。 作業項目のと同じ型が`RequestType`です。  
  
 `pvWorkerParam`  
 Worker クラスで認識されるカスタム パラメーターです。 渡されるも`WorkerArchetype::Initialize`と`Terminate`です。  
  
 `pOverlapped`  
 ポインター、 [OVERLAPPED](http://msdn.microsoft.com/library/windows/desktop/ms684342)構造体のどの作業項目がキューに入れ、キューを作成するために使用します。  
  
## <a name="initialize"></a> WorkerArchetype::Initialize
すべての要求に渡される前にワーカー オブジェクトを初期化するために呼び出されます`WorkerArchetype::Execute`です。  
```
BOOL Initialize(void* pvParam) throw();
```  
  
#### <a name="parameters"></a>パラメーター  
 `pvParam`  
 Worker クラスで認識されるカスタム パラメーターです。 渡されるも`WorkerArchetype::Terminate`と`WorkerArchetype::Execute`です。  
  
### <a name="return-value"></a>戻り値  
 返す**TRUE**成功した場合、 **FALSE**エラー発生時にします。  
  
## <a name="requesttype"></a> WorkerArchetype::RequestType
ワーカー クラスによって処理できる作業項目の種類の typedef。  
  
```  
typedef MyRequestType RequestType;    
```  
  
### <a name="remarks"></a>コメント  
 この型は、の最初のパラメーターとして使用する必要があります`WorkerArchetype::Execute`ULONG_PTR からキャストできる必要があるとします。  
  
## <a name="terminate"></a> WorkerArchetype::Terminate
初期化ワーカー オブジェクトのすべての要求に渡された後に呼び出された`WorkerArchetype::Execute`)。  
    
``` 
void Terminate(void* pvParam) throw();
```  
  
#### <a name="parameters"></a>パラメーター  
 `pvParam`  
 Worker クラスで認識されるカスタム パラメーターです。 渡されるも`WorkerArchetype::Initialize`と`WorkerArchetype::Execute`です。  
  
## <a name="see-also"></a>関連項目  
 [概念](../../atl/active-template-library-atl-concepts.md)   
 [ATL COM デスクトップ コンポーネント](../../atl/atl-com-desktop-components.md)




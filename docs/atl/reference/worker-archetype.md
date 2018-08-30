---
title: ワーカーのアーキタイプ |Microsoft Docs
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
ms.openlocfilehash: fd9e665a83db3b824e03eb960baf54f296d15d4f
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/29/2018
ms.locfileid: "43204855"
---
# <a name="worker-archetype"></a>ワーカーのアーキタイプ
準拠するクラス、*ワーカー*アーキタイプが作業項目を処理するコードがスレッド プール キューに登録を提供します。  
  
 **実装**  
  
 このアーキタイプに準拠するクラスを実装するには、クラスは、次の機能を用意する必要があります。  
  
|メソッド|説明|  
|------------|-----------------|  
|[Initialize](#initialize)|すべての要求が渡される前に、ワーカーのオブジェクトを初期化するために呼び出されます[Execute](#execute)します。|  
|[Execute](#execute)|作業項目の処理と呼ばれます。|  
|[Terminate](#terminate)|ワーカーのオブジェクトの初期化解除に渡されたすべての要求後に呼び出された[Execute](#execute)します。|  
  
|Typedef|説明|  
|-------------|-----------------|  
|[RequestType](#requesttype)|Worker クラスで処理できる作業項目の種類の typedef。|  
  
 一般的な*ワーカー*クラスは次のようになります。  
  
 [!code-cpp[NVC_ATL_Utilities#137](../../atl/codesnippet/cpp/worker-archetype_1.cpp)]  
  
 **既存の実装**  
  
 これらのクラスは、このアーキタイプに準拠しています。  
  
|クラス|説明|  
|-----------|-----------------|  
|[CNonStatelessWorker](../../atl/reference/cnonstatelessworker-class.md)|スレッド プールからの要求を受信し、作成され、要求ごとに破棄する worker オブジェクトにメッセージを渡します。|  
  
 **使用**  
  
 これらのテンプレート パラメーターには、このアーキタイプに準拠するクラスが想定されます。  
  
|パラメーター名|使用者|  
|--------------------|-------------|  
|*ワーカー*|[CThreadPool](../../atl/reference/cthreadpool-class.md)|  
|*ワーカー*|[CNonStatelessWorker](../../atl/reference/cnonstatelessworker-class.md)|  
  
### <a name="requirements"></a>要件  
 **ヘッダー:** atlutil.h  
  
## <a name="execute"></a>WorkerArchetype::Execute
作業項目の処理と呼ばれます。  
  
  
  
```  
void Execute(
    RequestType request,  
    void* pvWorkerParam,  
    OVERLAPPED* pOverlapped);
```  
  
#### <a name="parameters"></a>パラメーター  
 *要求*  
 処理する作業項目。 同じ型の作業項目は、`RequestType`します。  
  
 *pvWorkerParam*  
 Worker クラスで認識されるカスタム パラメーターです。 渡されるも`WorkerArchetype::Initialize`と`Terminate`します。  
  
 *pOverlapped*  
 ポインター、 [OVERLAPPED](/windows/desktop/api/minwinbase/ns-minwinbase-_overlapped)構造体のどの作業項目のキューに入ったキューを作成するために使用します。  
  
## <a name="initialize"></a> WorkerArchetype::Initialize
すべての要求が渡される前に、ワーカーのオブジェクトを初期化するために呼び出されます`WorkerArchetype::Execute`します。  
```
BOOL Initialize(void* pvParam) throw();
```  
  
#### <a name="parameters"></a>パラメーター  
 *pvParam*  
 Worker クラスで認識されるカスタム パラメーターです。 渡されるも`WorkerArchetype::Terminate`と`WorkerArchetype::Execute`します。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、TRUE を返すを返します。  
  
## <a name="requesttype"></a> WorkerArchetype::RequestType
Worker クラスで処理できる作業項目の種類の typedef。  
  
```  
typedef MyRequestType RequestType;    
```  
  
### <a name="remarks"></a>Remarks  
 この型の最初のパラメーターとして使用する必要があります`WorkerArchetype::Execute`ULONG_PTR との間でキャストされている対応する必要があります。  
  
## <a name="terminate"></a> WorkerArchetype::Terminate
ワーカーのオブジェクトの初期化解除に渡されたすべての要求後に呼び出された`WorkerArchetype::Execute`)。  
    
``` 
void Terminate(void* pvParam) throw();
```  
  
#### <a name="parameters"></a>パラメーター  
 *pvParam*  
 Worker クラスで認識されるカスタム パラメーターです。 渡されるも`WorkerArchetype::Initialize`と`WorkerArchetype::Execute`します。  
  
## <a name="see-also"></a>関連項目  
 [概念](../../atl/active-template-library-atl-concepts.md)   
 [ATL COM デスクトップ コンポーネント](../../atl/atl-com-desktop-components.md)




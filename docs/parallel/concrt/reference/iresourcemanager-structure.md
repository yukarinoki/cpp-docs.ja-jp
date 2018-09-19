---
title: IResourceManager 構造体 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
f1_keywords:
- IResourceManager
- CONCRTRM/concurrency::IResourceManager
- CONCRTRM/concurrency::IResourceManager::IResourceManager::OSVersion
- CONCRTRM/concurrency::IResourceManager::IResourceManager::CreateNodeTopology
- CONCRTRM/concurrency::IResourceManager::IResourceManager::GetAvailableNodeCount
- CONCRTRM/concurrency::IResourceManager::IResourceManager::GetFirstNode
- CONCRTRM/concurrency::IResourceManager::IResourceManager::Reference
- CONCRTRM/concurrency::IResourceManager::IResourceManager::RegisterScheduler
- CONCRTRM/concurrency::IResourceManager::IResourceManager::Release
dev_langs:
- C++
helpviewer_keywords:
- IResourceManager structure
ms.assetid: 3dd5ec2c-fe53-4121-ae77-1bc1d1167ff4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4d1032b2db7d1552beb40eb724b9953142b9b2ac
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46027415"
---
# <a name="iresourcemanager-structure"></a>IResourceManager 構造体
同時実行ランタイムのリソース マネージャーに対するインターフェイスです。 これは、スケジューラがリソース マネージャーと通信する際に使用されるインターフェイスです。  
  
## <a name="syntax"></a>構文  
  
```
struct IResourceManager;
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-enumerations"></a>パブリック列挙型  
  
|名前|説明|  
|----------|-----------------|  
|[Iresourcemanager::osversion](#osversion)|オペレーティング システムのバージョンを表す列挙型。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[IResourceManager::CreateNodeTopology](#createnodetopology)|デバッグにのみ存在するが、ランタイムのビルドは、このメソッドは、Resource Manager のハードウェア トポロジをさまざまな構成に一致する実際のハードウェアを必要とせずにテストを容易にするためのテスト フック。 ランタイムの製品版ビルドでは、このメソッドは操作を実行せずに戻ります。|  
|[IResourceManager::GetAvailableNodeCount](#getavailablenodecount)|Resource Manager を使用可能なノードの数を返します。|  
|[IResourceManager::GetFirstNode](#getfirstnode)|リソース マネージャーで定義される列挙の順番で最初のノードを返します。|  
|[IResourceManager::Reference](#reference)|リソース マネージャー インスタンスの参照カウントをインクリメントします。|  
|[IResourceManager::RegisterScheduler](#registerscheduler)|スケジューラを Resource Manager を登録します。 使用して、Resource Manager と通信する必要があります、スケジューラが登録されたら、`ISchedulerProxy`返されるインターフェイス。|  
|[IResourceManager::Release](#release)|Resource Manager インスタンスで、参照カウントをデクリメントします。 参照カウントになると、リソース マネージャーが破棄される`0`します。|  
  
## <a name="remarks"></a>Remarks  
 使用して、 [CreateResourceManager](concurrency-namespace-functions.md)シングルトン Resource Manager のインスタンスへのインターフェイスを取得します。 メソッドは、Resource Manager での参照カウントをインクリメントし、呼び出す必要があります、 [iresourcemanager::release](#release)したら Resource Manager での参照を解放します。 通常、各スケジューラを作成するは、作成中に、このメソッドを呼び出すし、シャット ダウンした後は、Resource Manager への参照を解放します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `IResourceManager`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** concrtrm.h  
  
 **名前空間:** concurrency  
  
##  <a name="createnodetopology"></a>  Iresourcemanager::createnodetopology メソッド  
 デバッグにのみ存在するが、ランタイムのビルドは、このメソッドは、Resource Manager のハードウェア トポロジをさまざまな構成に一致する実際のハードウェアを必要とせずにテストを容易にするためのテスト フック。 ランタイムの製品版ビルドでは、このメソッドは操作を実行せずに戻ります。  
  
```
virtual void CreateNodeTopology(
    unsigned int nodeCount,
    _In_reads_(nodeCount) unsigned int* pCoreCount,
    _In_reads_opt_(nodeCount) unsigned int** pNodeDistance,
    _In_reads_(nodeCount) unsigned int* pProcessorGroups) = 0;
```  
  
### <a name="parameters"></a>パラメーター  
*nodeCount*<br/>
シミュレートされているプロセッサ ノードの数。  
  
*pCoreCount*<br/>
各ノードのコアの数を指定する配列。  
  
*pNodeDistance*<br/>
2 つのノード間の距離を指定する行列。 このパラメーターは、値を持つことができます`NULL`します。  
  
*pProcessorGroups*<br/>
プロセッサ グループを指定する配列に各ノードが属しています。  
  
### <a name="remarks"></a>Remarks  
 [invalid_argument](../../../standard-library/invalid-argument-class.md)場合にスローされるパラメーター `nodeCount` 、値を持つ`0`が渡され、またはパラメーター `pCoreCount` 、値を持つ`NULL`します。  
  
 [invalid_operation](invalid-operation-class.md)プロセスの他のスケジューラが存在している間、このメソッドが呼び出された場合にスローされます。  
  
##  <a name="getavailablenodecount"></a>  Iresourcemanager::getavailablenodecount メソッド  
 Resource Manager を使用可能なノードの数を返します。  
  
```
virtual unsigned int GetAvailableNodeCount() const = 0;
```  
  
### <a name="return-value"></a>戻り値  
 Resource Manager を使用可能なノードの数。  
  
##  <a name="getfirstnode"></a>  Iresourcemanager::getfirstnode メソッド  
 リソース マネージャーで定義される列挙の順番で最初のノードを返します。  
  
```
virtual ITopologyNode* GetFirstNode() const = 0;
```  
  
### <a name="return-value"></a>戻り値  
 リソース マネージャーで定義される列挙の順番で最初のノードです。  
  
##  <a name="iresourcemanager__osversion"></a>  Iresourcemanager::osversion 列挙  
 オペレーティング システムのバージョンを表す列挙型。  
  
```
enum OSVersion;
```  
  
##  <a name="reference"></a>  Iresourcemanager::reference メソッド  
 リソース マネージャー インスタンスの参照カウントをインクリメントします。  
  
```
virtual unsigned int Reference() = 0;
```  
  
### <a name="return-value"></a>戻り値  
 結果として得られる、参照カウントします。  
  
##  <a name="registerscheduler"></a>  Iresourcemanager::registerscheduler メソッド  
 スケジューラを Resource Manager を登録します。 使用して、Resource Manager と通信する必要があります、スケジューラが登録されたら、`ISchedulerProxy`返されるインターフェイス。  
  
```
virtual ISchedulerProxy *RegisterScheduler(
    _Inout_ IScheduler* pScheduler,
    unsigned int version) = 0;
```  
  
### <a name="parameters"></a>パラメーター  
*pScheduler*<br/>
`IScheduler`を登録する scheduler へのインターフェイス。  
  
*version*<br/>
通信インターフェイスのバージョン、スケジューラは Resource Manager での通信を使用します。 バージョンを使用すると、スケジューラに古い機能のアクセス権を取得しながら、通信インターフェイスを進化させるリソース マネージャーができます。 Visual Studio 2010 に存在するリソース マネージャーの機能を使用するスケジューラは、バージョンを使用する必要があります`CONCRT_RM_VERSION_1`します。  
  
### <a name="return-value"></a>戻り値  
 `ISchedulerProxy` Resource Manager が、スケジューラに関連付けられているインターフェイス。 スケジューラのこのポイントから Resource Manager での通信にこのインターフェイスを使用する必要があります。  
  
### <a name="remarks"></a>Remarks  
 このメソッドを使用して、リソース マネージャーとの通信を開始します。 メソッドを関連付けます、`IScheduler`インターフェイスを使用して、スケジューラ、`ISchedulerProxy`インターフェイスと、再度の手です。 、スケジューラによって使用される実行リソースを要求するか、Resource Manager でのスレッドを購読、返されたインターフェイスを使用することができます。 Resource Manager がによって返されるスケジューラ ポリシーからポリシー要素を使用して、 [ischeduler::getpolicy](ischeduler-structure.md#getpolicy)メソッドは、スケジューラ スレッドの種類を決定するのには作業を実行する必要があります。 場合、`SchedulerKind`ポリシー キーは、値を持つ`UmsThreadDefault`値として、ポリシーから戻さ値は読み取り専用と`UmsThreadDefault`、`IScheduler`インターフェイス、メソッドに渡される必要があります、`IUMSScheduler`インターフェイス。  
  
 メソッドをスロー、`invalid_argument`例外場合パラメーター `pScheduler` 、値を持つ`NULL`場合は、パラメーター`version`通信インターフェイスの有効なバージョンではありません。  
  
##  <a name="release"></a>  Iresourcemanager::release メソッド  
 Resource Manager インスタンスで、参照カウントをデクリメントします。 参照カウントになると、リソース マネージャーが破棄される`0`します。  
  
```
virtual unsigned int Release() = 0;
```  
  
### <a name="return-value"></a>戻り値  
 結果として得られる、参照カウントします。  
  
## <a name="see-also"></a>関連項目  
 [同時実行 Namespace](concurrency-namespace.md)   
 [ISchedulerProxy 構造体](ischedulerproxy-structure.md)   
 [IScheduler 構造体](ischeduler-structure.md)

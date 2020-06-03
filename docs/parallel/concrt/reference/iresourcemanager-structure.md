---
title: IResourceManager 構造体
ms.date: 03/27/2019
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
helpviewer_keywords:
- IResourceManager structure
ms.assetid: 3dd5ec2c-fe53-4121-ae77-1bc1d1167ff4
ms.openlocfilehash: 15e27a586fc039791255c01a053f6a1109183f90
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81368189"
---
# <a name="iresourcemanager-structure"></a>IResourceManager 構造体

コンカレンシー ランタイムのリソース マネージャーに対するインターフェイスです。 これは、スケジューラがリソース マネージャーと通信する際に使用されるインターフェイスです。

## <a name="syntax"></a>構文

```cpp
struct IResourceManager;
```

## <a name="members"></a>メンバー

### <a name="public-enumerations"></a>パブリック列挙型

|名前|説明|
|----------|-----------------|
|[リソースマネージャー::OSVersion](#osversion)|オペレーティング システムのバージョンを表す列挙型。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[Iリソースマネージャー:ノードトポロジを作成します。](#createnodetopology)|ランタイムのデバッグ ビルドでのみ存在するこのメソッドは、構成に一致する実際のハードウェアを必要とせずに、さまざまなハードウェア トポロジで Resource Manager のテストを容易にするように設計されたテスト フックです。 ランタイムの製品版ビルドでは、このメソッドは何もアクションを実行せずに戻ります。|
|[を使用します。](#getavailablenodecount)|リソース マネージャーで使用できるノードの数を返します。|
|[を使用します。](#getfirstnode)|リソース マネージャーで定義されている列挙順の最初のノードを返します。|
|[リソースマネージャー::参照](#reference)|リソース マネージャー インスタンスの参照カウントをインクリメントします。|
|[を使用します。](#registerscheduler)|リソース マネージャーにスケジューラを登録します。 スケジューラは、登録されると、返されるインターフェイスを使用してリソース マネージャー`ISchedulerProxy`と通信する必要があります。|
|[Iリソースマネージャー::リリース](#release)|リソース マネージャー インスタンスの参照カウントをデクリメントします。 リソース マネージャの参照カウントが に行くと`0`、リソース マネージャは破棄されます。|

## <a name="remarks"></a>解説

シングルトン リソース マネージャー インスタンスへのインターフェイスを取得するには[、CreateResourceManager](concurrency-namespace-functions.md)関数を使用します。 このメソッドはリソース マネージャーの参照カウントをインクリメントし、リソース マネージャーでの完了時に参照を解放する[IResourceManager::Release](#release)メソッドを呼び出す必要があります。 通常、作成する各スケジューラは、作成時にこのメソッドを呼び出し、リソース マネージャーがシャットダウンした後にリソース マネージャーへの参照を解放します。

## <a name="inheritance-hierarchy"></a>継承階層

`IResourceManager`

## <a name="requirements"></a>必要条件

**ヘッダー:** concrtrm.h

**名前空間:** 同時実行

## <a name="iresourcemanagercreatenodetopology-method"></a><a name="createnodetopology"></a>Iリソースマネージャー::ノードトポロジメソッドの作成

ランタイムのデバッグ ビルドでのみ存在するこのメソッドは、構成に一致する実際のハードウェアを必要とせずに、さまざまなハードウェア トポロジで Resource Manager のテストを容易にするように設計されたテスト フックです。 ランタイムの製品版ビルドでは、このメソッドは何もアクションを実行せずに戻ります。

```cpp
virtual void CreateNodeTopology(
    unsigned int nodeCount,
    _In_reads_(nodeCount) unsigned int* pCoreCount,
    _In_reads_opt_(nodeCount) unsigned int** pNodeDistance,
    _In_reads_(nodeCount) unsigned int* pProcessorGroups) = 0;
```

### <a name="parameters"></a>パラメーター

*ノード数*<br/>
シミュレートされるプロセッサ ノードの数。

*カウント*<br/>
各ノードのコア数を指定する配列。

*距離*<br/>
任意の 2 つのノード間のノード距離を指定する行列。 このパラメーターには、 値`NULL`を指定できます。

*プロセッサグループ*<br/>
各ノードが属するプロセッサ グループを指定する配列。

### <a name="remarks"></a>解説

[invalid_argument](../../../standard-library/invalid-argument-class.md)は、`nodeCount`パラメーターに値が渡された`0`場合、またはパラメーター`pCoreCount`に値`NULL`が含まれる場合にスローされます。

[invalid_operation](invalid-operation-class.md)は、プロセス内に他のスケジューラが存在する間に、このメソッドが呼び出されるとスローされます。

## <a name="iresourcemanagergetavailablenodecount-method"></a><a name="getavailablenodecount"></a>メソッドを取得します。

リソース マネージャーで使用できるノードの数を返します。

```cpp
virtual unsigned int GetAvailableNodeCount() const = 0;
```

### <a name="return-value"></a>戻り値

リソース マネージャーで使用できるノードの数。

## <a name="iresourcemanagergetfirstnode-method"></a><a name="getfirstnode"></a>メソッドを取得します。

リソース マネージャーで定義されている列挙順の最初のノードを返します。

```cpp
virtual ITopologyNode* GetFirstNode() const = 0;
```

### <a name="return-value"></a>戻り値

リソース マネージャーで定義されている列挙順の最初のノード。

## <a name="iresourcemanagerosversion-enumeration"></a><a name="osversion"></a>を使用します。

オペレーティング システムのバージョンを表す列挙型。

```cpp
enum OSVersion;
```

## <a name="iresourcemanagerreference-method"></a><a name="reference"></a>メソッドを参照します。

リソース マネージャー インスタンスの参照カウントをインクリメントします。

```cpp
virtual unsigned int Reference() = 0;
```

### <a name="return-value"></a>戻り値

結果の参照カウント。

## <a name="iresourcemanagerregisterscheduler-method"></a><a name="registerscheduler"></a>メソッドを登録します。

リソース マネージャーにスケジューラを登録します。 スケジューラは、登録されると、返されるインターフェイスを使用してリソース マネージャー`ISchedulerProxy`と通信する必要があります。

```cpp
virtual ISchedulerProxy *RegisterScheduler(
    _Inout_ IScheduler* pScheduler,
    unsigned int version) = 0;
```

### <a name="parameters"></a>パラメーター

*スケジューラー*<br/>
登録`IScheduler`するスケジューラへのインターフェイス。

*version*<br/>
スケジューラがリソース マネージャーと通信するために使用している通信インターフェイスのバージョン。 バージョンを使用すると、スケジューラが古い機能にアクセスできるように、リソース マネージャーは通信インターフェイスを進化させることができます。 Visual Studio 2010 でリソース マネージャーの機能を使用するスケジューラは、`CONCRT_RM_VERSION_1`バージョンを使用する必要があります。

### <a name="return-value"></a>戻り値

リソース`ISchedulerProxy`マネージャーがスケジューラに関連付けられているインターフェイス。 スケジューラは、この時点からリソース マネージャーと通信するために、このインターフェイスを使用する必要があります。

### <a name="remarks"></a>解説

このメソッドは、リソース マネージャーとの通信を開始するために使います。 このメソッドは、スケジューラ`IScheduler`のインターフェイスを`ISchedulerProxy`インターフェイスに関連付け、それを返します。 返されたインターフェイスを使用して、スケジューラで使用する実行リソースを要求したり、リソース マネージャーでスレッドをサブスクライブしたりできます。 リソース マネージャーは[、IScheduler::GetPolicy](ischeduler-structure.md#getpolicy)メソッドによって返されるスケジューラ ポリシーのポリシー要素を使用して、スケジューラが作業を実行する必要があるスレッドの種類を決定します。 `SchedulerKind`ポリシー キーに`UmsThreadDefault`値があり、値がポリシーから値`UmsThreadDefault`として読み取り戻される場合、メソッド`IScheduler`に渡されるインターフェイスは`IUMSScheduler`インターフェイスである必要があります。

パラメーター`invalid_argument`に値`pScheduler``NULL`がある場合、またはパラメーター`version`が通信インターフェースの有効なバージョンでない場合、このメソッドは例外をスローします。

## <a name="iresourcemanagerrelease-method"></a><a name="release"></a>メソッドのリリース

リソース マネージャー インスタンスの参照カウントをデクリメントします。 リソース マネージャの参照カウントが に行くと`0`、リソース マネージャは破棄されます。

```cpp
virtual unsigned int Release() = 0;
```

### <a name="return-value"></a>戻り値

結果の参照カウント。

## <a name="see-also"></a>関連項目

[同時実行名前空間](concurrency-namespace.md)<br/>
[ISchedulerProxy 構造体](ischedulerproxy-structure.md)<br/>
[IScheduler 構造体](ischeduler-structure.md)

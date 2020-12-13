---
description: 詳細については、「IUMSScheduler 構造体」を参照してください。
title: IUMSScheduler 構造体
ms.date: 11/04/2016
f1_keywords:
- IUMSScheduler
- CONCRTRM/concurrency::IUMSScheduler
- CONCRTRM/concurrency::IUMSScheduler::IUMSScheduler::SetCompletionList
helpviewer_keywords:
- IUMSScheduler structure
ms.assetid: 3a500225-4e02-4849-bb56-d744865f5870
ms.openlocfilehash: e42a2e3d39e568ba12cd681053406ce88c7b5dba
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97334342"
---
# <a name="iumsscheduler-structure"></a>IUMSScheduler 構造体

コンカレンシー ランタイムのリソース マネージャーによってユーザー モード スケジュール可能 (UMS) スレッドが渡される必要がある作業スケジューラの抽象化のインターフェイスです。 リソース マネージャーでは、このインターフェイスを使用して UMS スレッド スケジューラと通信します。 `IUMSScheduler` インターフェイスは `IScheduler` インターフェイスを継承します。

## <a name="syntax"></a>構文

```cpp
struct IUMSScheduler : public IScheduler;
```

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[IUMSScheduler:: Set補完リスト](#setcompletionlist)|`IUMSCompletionList`UMS スレッドスケジューラにインターフェイスを割り当てます。|

## <a name="remarks"></a>解説

リソースマネージャーと通信するカスタムスケジューラを実装していて、通常の Win32 スレッドではなく、UMS スレッドをスケジューラに渡す必要がある場合は、インターフェイスの実装を提供する必要があり `IUMSScheduler` ます。 また、scheduler ポリシーキーのポリシー値をに設定する必要があり `SchedulerKind` `UmsThreadDefault` ます。 ポリシーで UMS スレッドが指定されている場合、 `IScheduler` [iresourcemanager:: registerscheduler](iresourcemanager-structure.md#registerscheduler) メソッドにパラメーターとして渡されるインターフェイスはインターフェイスである必要があり `IUMSScheduler` ます。

リソースマネージャーは、UMS 機能を持つオペレーティングシステムでのみ、UMS スレッドを渡すことができます。 Windows 7 以降のバージョンの64ビットオペレーティングシステムでは、UMS スレッドがサポートされています。 キーが値に設定されたスケジューラポリシーを作成 `SchedulerKind` `UmsThreadDefault` し、基になるプラットフォームで UMS がサポートされていない場合は、 `SchedulerKind` そのポリシーのキーの値が値に変更され `ThreadScheduler` ます。 UMS スレッドを受け取ることが予想される前に、常にこのポリシー値を読み取る必要があります。

この `IUMSScheduler` インターフェイスは、スケジューラとリソースマネージャーの間の通信の双方向チャネルの一端です。 もう一方の端は、 `IResourceManager` `ISchedulerProxy` リソースマネージャーによって実装されるインターフェイスとインターフェイスによって表されます。

## <a name="inheritance-hierarchy"></a>継承階層

[IScheduler](ischeduler-structure.md)

`IUMSScheduler`

## <a name="requirements"></a>要件

**ヘッダー:** concrtrm. h

**名前空間:** concurrency

## <a name="iumsschedulersetcompletionlist-method"></a><a name="setcompletionlist"></a> IUMSScheduler:: Set補完リストメソッド

`IUMSCompletionList`UMS スレッドスケジューラにインターフェイスを割り当てます。

```cpp
virtual void SetCompletionList(_Inout_ IUMSCompletionList* pCompletionList) = 0;
```

### <a name="parameters"></a>パラメーター

*P補完の一覧*<br/>
スケジューラの入力候補一覧のインターフェイス。 スケジューラごとにリストが1つあります。

### <a name="remarks"></a>解説

リソースマネージャーは、スケジューラがリソースの初期割り当てを要求した後に、UMS スレッドを必要とすることを指定するスケジューラでこのメソッドを呼び出します。 スケジューラは、インターフェイスを使用して、 `IUMSCompletionList` UMS スレッドプロキシがブロック解除されたタイミングを判断できます。 このインターフェイスにアクセスできるのは、UMS スケジューラに割り当てられている仮想プロセッサルートで実行されているスレッドプロキシからだけです。

## <a name="see-also"></a>関連項目

[concurrency 名前空間](concurrency-namespace.md)<br/>
[PolicyElementKey](concurrency-namespace-enums.md)<br/>
[IScheduler 構造体](ischeduler-structure.md)<br/>
[IUMSCompletionList 構造体](iumscompletionlist-structure.md)<br/>
[IResourceManager 構造体](iresourcemanager-structure.md)

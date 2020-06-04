---
title: IUMSScheduler 構造体
ms.date: 11/04/2016
f1_keywords:
- IUMSScheduler
- CONCRTRM/concurrency::IUMSScheduler
- CONCRTRM/concurrency::IUMSScheduler::IUMSScheduler::SetCompletionList
helpviewer_keywords:
- IUMSScheduler structure
ms.assetid: 3a500225-4e02-4849-bb56-d744865f5870
ms.openlocfilehash: 70954906122c048e5199a801632626d35a8e3f18
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81368094"
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
|[アウムスケジューラ::セットコンプリートリスト](#setcompletionlist)|インターフェイスを`IUMSCompletionList`UMS スレッド スケジューラに割り当てます。|

## <a name="remarks"></a>解説

リソース マネージャーと通信するカスタム スケジューラを実装する場合、通常の Win32 スレッドではなく、UMS スレッドをスケジューラに渡す必要があります、 インターフェイスの実装を提供`IUMSScheduler`する必要があります。 また、スケジューラ ポリシー キー`SchedulerKind`のポリシー値を に設定する必要`UmsThreadDefault`があります。 ポリシーで UMS スレッドを指定`IScheduler`する場合は、パラメーターとして[IResourceManager::RegisterScheduler](iresourcemanager-structure.md#registerscheduler)メソッドに渡される`IUMSScheduler`インターフェイスはインターフェイスである必要があります。

リソース マネージャーは、UMS 機能を持つオペレーティング システムでのみ UMS スレッドを渡します。 バージョン Windows 7 以上のバージョンの 64 ビット オペレーティング システムは、UMS スレッドをサポートします。 `SchedulerKind`キーを値`UmsThreadDefault`に設定してスケジューラ ポリシーを作成し、基になるプラットフォームが UMS をサポートしていない場合、その`SchedulerKind`ポリシーのキーの値は 値`ThreadScheduler`に変更されます。 UMS スレッドを受信する前に、このポリシー値を常に読み取る必要があります。

この`IUMSScheduler`インターフェイスは、スケジューラとリソース マネージャー間の双方向通信チャネルの一方の端です。 もう一方の端は、 `IResourceManager` `ISchedulerProxy`と インターフェイスによって表され、リソース マネージャーによって実装されます。

## <a name="inheritance-hierarchy"></a>継承階層

[Iスケジューラ](ischeduler-structure.md)

`IUMSScheduler`

## <a name="requirements"></a>必要条件

**ヘッダー:** concrtrm.h

**名前空間:** 同時実行

## <a name="iumsschedulersetcompletionlist-method"></a><a name="setcompletionlist"></a>メソッドを設定します。

インターフェイスを`IUMSCompletionList`UMS スレッド スケジューラに割り当てます。

```cpp
virtual void SetCompletionList(_Inout_ IUMSCompletionList* pCompletionList) = 0;
```

### <a name="parameters"></a>パラメーター

*完了リスト*<br/>
スケジューラの完了リスト インターフェイス。 スケジューラごとに 1 つのリストがあります。

### <a name="remarks"></a>解説

リソース マネージャーは、リソースの初期割り当てを要求した後、UMS スレッドを要求するスケジューラでこのメソッドを呼び出します。 スケジューラは、インターフェイスを`IUMSCompletionList`使用して、UMS スレッド プロキシがブロック解除されたタイミングを判断できます。 UMS スケジューラに割り当てられた仮想プロセッサ ルートで実行されているスレッド プロキシからこのインターフェイスにアクセスする場合にのみ有効です。

## <a name="see-also"></a>関連項目

[同時実行名前空間](concurrency-namespace.md)<br/>
[キー](concurrency-namespace-enums.md)<br/>
[IScheduler 構造体](ischeduler-structure.md)<br/>
[IUMSCompletionList 構造体](iumscompletionlist-structure.md)<br/>
[IResourceManager 構造体](iresourcemanager-structure.md)

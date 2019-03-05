---
title: IUMSThreadProxy 構造体
ms.date: 11/04/2016
f1_keywords:
- IUMSThreadProxy
- CONCRTRM/concurrency::IUMSThreadProxy
- CONCRTRM/concurrency::IUMSThreadProxy::IUMSThreadProxy::EnterCriticalRegion
- CONCRTRM/concurrency::IUMSThreadProxy::IUMSThreadProxy::EnterHyperCriticalRegion
- CONCRTRM/concurrency::IUMSThreadProxy::IUMSThreadProxy::ExitCriticalRegion
- CONCRTRM/concurrency::IUMSThreadProxy::IUMSThreadProxy::ExitHyperCriticalRegion
- CONCRTRM/concurrency::IUMSThreadProxy::IUMSThreadProxy::GetCriticalRegionType
helpviewer_keywords:
- IUMSThreadProxy structure
ms.assetid: 61c69b7e-5c37-4048-bcb4-e75c536afd86
ms.openlocfilehash: 258f249aa178b73da2080cca888409dc07f63dbb
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/04/2019
ms.locfileid: "57263036"
---
# <a name="iumsthreadproxy-structure"></a>IUMSThreadProxy 構造体

実行スレッドの抽象化です。 ユーザー モード スケジュール可能 (UMS) スレッドをスケジューラに付与するには、スケジューラ ポリシー要素 `SchedulerKind` の値を `UmsThreadDefault` に設定し、さらに `IUMSScheduler` インターフェイスを実装する必要があります。 UMS スレッドは、Windows 7 以上のバージョンの 64 ビット オペレーティング システムでのみサポートされます。

## <a name="syntax"></a>構文

```
struct IUMSThreadProxy : public IThreadProxy;
```

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[IUMSThreadProxy::EnterCriticalRegion](#entercriticalregion)|重要な領域を入力するために呼び出されます。 クリティカル領域内で、スケジューラは、リージョンの中に発生する非同期のブロック操作を確認しません。 これは、スケジューラがページ フォールトやスレッドの中断、カーネルの非同期プロシージャ コール (Apc) など、UMS スレッドの再入力しないはことを意味します。|
|[IUMSThreadProxy::EnterHyperCriticalRegion](#enterhypercriticalregion)|ハイパー クリティカル領域を入力するために呼び出されます。 Hyper クリティカル領域内で、スケジューラは、リージョンの中に発生するブロッキング操作を確認しません。 これは、スケジューラが関数呼び出し、ブロック、ページ フォールト、スレッドの中断、カーネルの非同期プロシージャ コール (Apc) となど、UMS スレッドのロック獲得の試行をブロックするため再入力するはないことを意味します。|
|[IUMSThreadProxy::ExitCriticalRegion](#exitcriticalregion)|重要な領域を終了するために呼び出されます。|
|[IUMSThreadProxy::ExitHyperCriticalRegion](#exithypercriticalregion)|ハイパー クリティカル領域を終了するために呼び出されます。|
|[IUMSThreadProxy::GetCriticalRegionType](#getcriticalregiontype)|内のスレッド プロキシは、クリティカル領域の種類を返します。 クリティカル領域とし、ハイパー クリティカル領域では、コードを入力した場合、ハイパー クリティカル領域はクリティカル領域は、のスーパー セットであるため`InsideHyperCriticalRegion`が返されます。|

## <a name="inheritance-hierarchy"></a>継承階層

[IThreadProxy](ithreadproxy-structure.md)

`IUMSThreadProxy`

## <a name="requirements"></a>必要条件

**ヘッダー:** concrtrm.h

**名前空間:** concurrency

##  <a name="entercriticalregion"></a>  Iumsthreadproxy::entercriticalregion メソッド

重要な領域を入力するために呼び出されます。 クリティカル領域内で、スケジューラは、リージョンの中に発生する非同期のブロック操作を確認しません。 これは、スケジューラがページ フォールトやスレッドの中断、カーネルの非同期プロシージャ コール (Apc) など、UMS スレッドの再入力しないはことを意味します。

```
virtual int EnterCriticalRegion() = 0;
```

### <a name="return-value"></a>戻り値

クリティカル領域の新しい深度。 クリティカル領域は再入可能です。

##  <a name="enterhypercriticalregion"></a>  IUMSThreadProxy::EnterHyperCriticalRegion Method

ハイパー クリティカル領域を入力するために呼び出されます。 Hyper クリティカル領域内で、スケジューラは、リージョンの中に発生するブロッキング操作を確認しません。 これは、スケジューラが関数呼び出し、ブロック、ページ フォールト、スレッドの中断、カーネルの非同期プロシージャ コール (Apc) となど、UMS スレッドのロック獲得の試行をブロックするため再入力するはないことを意味します。

```
virtual int EnterHyperCriticalRegion() = 0;
```

### <a name="return-value"></a>戻り値

ハイパー クリティカル領域の新しい深度。 ハイパースレッディング クリティカル領域は再入可能です。

### <a name="remarks"></a>Remarks

スケジューラは、このようなリージョンで呼び出すメソッドとロックが獲得する何について十分に注意である必要があります。 このようなリージョン内のコードをスケジューラをスケジュールするためのものに保持されているロックでブロックする場合は、デッドロックが発生したりします。

##  <a name="exitcriticalregion"></a>  Iumsthreadproxy::exitcriticalregion メソッド

重要な領域を終了するために呼び出されます。

```
virtual int ExitCriticalRegion() = 0;
```

### <a name="return-value"></a>戻り値

クリティカル領域の新しい深度。 クリティカル領域は再入可能です。

##  <a name="exithypercriticalregion"></a>  Iumsthreadproxy::exithypercriticalregion メソッド

ハイパー クリティカル領域を終了するために呼び出されます。

```
virtual int ExitHyperCriticalRegion() = 0;
```

### <a name="return-value"></a>戻り値

ハイパー クリティカル領域の新しい深度。 ハイパースレッディング クリティカル領域は再入可能です。

##  <a name="getcriticalregiontype"></a>  Iumsthreadproxy::getcriticalregiontype メソッド

内のスレッド プロキシは、クリティカル領域の種類を返します。 クリティカル領域とし、ハイパー クリティカル領域では、コードを入力した場合、ハイパー クリティカル領域はクリティカル領域は、のスーパー セットであるため`InsideHyperCriticalRegion`が返されます。

```
virtual CriticalRegionType GetCriticalRegionType() const = 0;
```

### <a name="return-value"></a>戻り値

内のスレッド プロキシは、クリティカル領域の種類。

## <a name="see-also"></a>関連項目

[コンカレンシー名前空間](concurrency-namespace.md)<br/>
[IUMSScheduler 構造体](iumsscheduler-structure.md)

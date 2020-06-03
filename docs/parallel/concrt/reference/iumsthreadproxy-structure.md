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
ms.openlocfilehash: 2e748b1da02394e1f70afd8b92947e1291957c62
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81368080"
---
# <a name="iumsthreadproxy-structure"></a>IUMSThreadProxy 構造体

実行スレッドの抽象化です。 ユーザー モード スケジュール可能 (UMS) スレッドをスケジューラに付与するには、スケジューラ ポリシー要素 `SchedulerKind` の値を `UmsThreadDefault` に設定し、さらに `IUMSScheduler` インターフェイスを実装する必要があります。 UMS スレッドは、Windows 7 以上のバージョンの 64 ビット オペレーティング システムでのみサポートされます。

## <a name="syntax"></a>構文

```cpp
struct IUMSThreadProxy : public IThreadProxy;
```

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[を指定します。](#entercriticalregion)|クリティカル領域に入るために呼び出されます。 重要な領域内では、スケジューラは、その領域で発生する非同期ブロッキング操作を監視しません。 つまり、ページ フォールト、スレッドの中断、カーネル非同期プロシージャ呼び出し (Apc) などの場合、UMS スレッドのスケジューラは再入力されません。|
|[を使用します。](#enterhypercriticalregion)|ハイパー クリティカル領域に入るために呼び出されます。 ハイパークリティカル領域内では、スケジューラはリージョン中に発生するブロック操作を監視しません。 つまり、スケジューラは、ブロック、ページ フォールト、スレッドの中断、カーネル非同期プロシージャ呼び出し (APC) などの UMS スレッドのロック取得の試行をブロックするために再入力されません。|
|[を指定します。](#exitcriticalregion)|クリティカル領域を終了するために呼び出されます。|
|[を使用します。](#exithypercriticalregion)|ハイパークリティカル領域を終了するために呼び出されます。|
|[を使用します。](#getcriticalregiontype)|スレッド プロキシが存在する重要領域の種類を返します。 ハイパークリティカル領域は重要領域のスーパーセットであるため、コードがクリティカル領域に入り、ハイパークリティカル領域に入った場合は、`InsideHyperCriticalRegion`そのリージョンが返されます。|

## <a name="inheritance-hierarchy"></a>継承階層

[プロキシ](ithreadproxy-structure.md)

`IUMSThreadProxy`

## <a name="requirements"></a>必要条件

**ヘッダー:** concrtrm.h

**名前空間:** 同時実行

## <a name="iumsthreadproxyentercriticalregion-method"></a><a name="entercriticalregion"></a>メソッドを入力します。

クリティカル領域に入るために呼び出されます。 重要な領域内では、スケジューラは、その領域で発生する非同期ブロッキング操作を監視しません。 つまり、ページ フォールト、スレッドの中断、カーネル非同期プロシージャ呼び出し (Apc) などの場合、UMS スレッドのスケジューラは再入力されません。

```cpp
virtual int EnterCriticalRegion() = 0;
```

### <a name="return-value"></a>戻り値

臨界領域の新しい深さ。 重要な領域は再入可能です。

## <a name="iumsthreadproxyenterhypercriticalregion-method"></a><a name="enterhypercriticalregion"></a>メソッドを入力します。

ハイパー クリティカル領域に入るために呼び出されます。 ハイパークリティカル領域内では、スケジューラはリージョン中に発生するブロック操作を監視しません。 つまり、スケジューラは、ブロック、ページ フォールト、スレッドの中断、カーネル非同期プロシージャ呼び出し (APC) などの UMS スレッドのロック取得の試行をブロックするために再入力されません。

```cpp
virtual int EnterHyperCriticalRegion() = 0;
```

### <a name="return-value"></a>戻り値

超臨界領域の新しい深さ。 超重要領域は再入可能です。

### <a name="remarks"></a>解説

スケジューラは、どのメソッドを呼び出し、どのロックをその領域で取得するかについて、非常に注意する必要があります。 スケジューラーがスケジュールを担当するロック上で、このような領域内のコードがブロックされると、デッドロックが発生する可能性があります。

## <a name="iumsthreadproxyexitcriticalregion-method"></a><a name="exitcriticalregion"></a>メソッドを終了します。

クリティカル領域を終了するために呼び出されます。

```cpp
virtual int ExitCriticalRegion() = 0;
```

### <a name="return-value"></a>戻り値

臨界領域の新しい深さ。 重要な領域は再入可能です。

## <a name="iumsthreadproxyexithypercriticalregion-method"></a><a name="exithypercriticalregion"></a>メソッドを終了します。

ハイパークリティカル領域を終了するために呼び出されます。

```cpp
virtual int ExitHyperCriticalRegion() = 0;
```

### <a name="return-value"></a>戻り値

超臨界領域の新しい深さ。 超重要領域は再入可能です。

## <a name="iumsthreadproxygetcriticalregiontype-method"></a><a name="getcriticalregiontype"></a>メソッドの種類を指定します。

スレッド プロキシが存在する重要領域の種類を返します。 ハイパークリティカル領域は重要領域のスーパーセットであるため、コードがクリティカル領域に入り、ハイパークリティカル領域に入った場合は、`InsideHyperCriticalRegion`そのリージョンが返されます。

```cpp
virtual CriticalRegionType GetCriticalRegionType() const = 0;
```

### <a name="return-value"></a>戻り値

スレッド プロキシが存在する重要領域の型。

## <a name="see-also"></a>関連項目

[同時実行名前空間](concurrency-namespace.md)<br/>
[IUMSScheduler 構造体](iumsscheduler-structure.md)

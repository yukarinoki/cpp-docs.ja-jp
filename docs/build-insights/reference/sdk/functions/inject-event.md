---
title: InjectEvent
description: C++ Build Insights SDK の InjectEvent 関数のリファレンス。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- InjectEvent
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: b4d85f17a6d553d9dffa727824e6d4de94518645
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/29/2020
ms.locfileid: "92922848"
---
# <a name="injectevent"></a>InjectEvent

::: moniker range="<=msvc-140"

C++ Build Insights SDK は、Visual Studio 2017 以降と互換性があります。 これらのバージョンのドキュメントを表示するには、この記事の Visual Studio **Version** セレクター コントロールを Visual Studio 2017 または Visual Studio 2019 に設定します。 このページの目次の一番上にあります。

::: moniker-end
::: moniker range=">=msvc-150"

`InjectEvent` 関数は、[IRelogger](../other-types/irelogger-class.md) インターフェイスが実装されているリロガー内で呼び出されます。 再ログ記録セッションの出力トレース ファイルに Event Tracing for Windows (ETW) イベントを書き込むために使用されます。

## <a name="syntax"></a>構文

```cpp
void InjectEvent(
    const void* relogSession,
    LPCGUID providerId,
    PCEVENT_DESCRIPTOR eventDescriptor,
    unsigned long processId,
    unsigned long threadId,
    unsigned short processorIndex,
    long long timestamp,
    unsigned char* data,
    unsigned long byteCount);
```

### <a name="parameters"></a>パラメーター

*relogSession*\
再ログ記録セッションへのポインター。 再ログ記録セッションは、`IRelogger` インターフェイスが実装されているリロガーに提供されます。 詳細については、[IRelogger](../other-types/irelogger-class.md) に関する記事を参照してください。

*providerId*\
ETW イベントが再ログ記録される Tracing for Windows (ETW) プロバイダー GUID。

*eventDescriptor*\
再ログ記録される ETW イベントの ETW イベント記述子。

*processId*\
再ログ記録される ETW イベントのプロセス識別子 (PID)。

*threadId*\
再ログ記録される ETW イベントのスレッド識別子 (TID)。

*processorIndex*\
再ログ記録される ETW イベントのプロセッサ インデックス。

*timestamp*\
再ログ記録される ETW イベントのタイムスタンプ。

*data*\
再ログ記録される ETW イベントに含める必要があるデータへのポインター。

*byteCount*\
*data* によって示されるデータのサイズ (バイト単位)。

## <a name="remarks"></a>注釈

" *プロバイダー GUID* " や " *イベント記述子* " などの ETW の概念の詳細については、[ETW のドキュメント](/windows/win32/etw/about-event-tracing)を参照してください。 C++ Build Insights SDK を使用して再ログ記録セッションを開始する方法の詳細については、「[Relog](relog.md)」を参照してください。

::: moniker-end

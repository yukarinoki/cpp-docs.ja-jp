---
title: イベントを注入する
description: C++ ビルド インサイト SDK インジェクトイベント関数リファレンス。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- InjectEvent
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: c82aad5923eff60e5c72ceccaa39aa136f942665
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81324038"
---
# <a name="injectevent"></a>イベントを注入する

::: moniker range="<=vs-2015"

C++ ビルド インサイト SDK は、Visual Studio 2017 以降と互換性があります。 これらのバージョンのドキュメントを参照するには、この記事の Visual Studio**バージョン**セレクター コントロールを Visual Studio 2017 または Visual Studio 2019 に設定します。 このページの目次の上部に表示されます。

::: moniker-end
::: moniker range=">=vs-2017"

関数`InjectEvent`は[、IRelogger](../other-types/irelogger-class.md)インターフェイスを実装するリロガー内で呼び出されます。 再ロギング セッションの出力トレース ファイルに Windows イベント トレース (ETW) イベントを書き込むために使用されます。

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

*セッションを再ログします。*\
再ロギング セッションへのポインター。 再ロギング セッションは、インターフェイスを実装するリロガーに`IRelogger`提供されます。 詳細については[、IRelogger](../other-types/irelogger-class.md)を参照してください。

*プロバイダ Id*\
ETW イベントが再ログされる Windows (ETW) プロバイダー GUID のイベント トレース。

*イベント記述子*\
再ログに記録される ETW イベントの ETW イベント記述子。

*プロセスId*\
再ログに記録される ETW イベントのプロセス識別子 (PID)。

*Threadid*\
再ログに記録される ETW イベントのスレッド識別子 (TID)。

*プロセッサインデックス*\
再ログに記録される ETW イベントのプロセッサ インデックス。

*タイムスタンプ*\
再ログに記録された ETW イベントのタイムスタンプ。

*データ*\
ログに記録された ETW イベントに含める必要があるデータへのポインター。

*バイト数*\
データが指すデータのサイズ (バイト*単位)。*

## <a name="remarks"></a>解説

*プロバイダの GUID*や*イベント記述子*などの ETW の概念の詳細については、 [ETW のドキュメントを参照してください](/windows/win32/etw/about-event-tracing)。 C++ ビルド インサイト SDK で再ロギング セッションを開始する方法の詳細については[、「Relog」](relog.md)を参照してください。

::: moniker-end

---
title: IRelogger クラス
description: C++ Build Insights SDK の IRelogger クラスのリファレンス。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- IRelogger
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: e504ece95529f7279650062145f3ac0914449c98
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/29/2020
ms.locfileid: "92922520"
---
# <a name="irelogger-class"></a>IRelogger クラス

::: moniker range="<=msvc-140"

C++ Build Insights SDK は、Visual Studio 2017 以降と互換性があります。 これらのバージョンのドキュメントを表示するには、この記事の Visual Studio **Version** セレクター コントロールを Visual Studio 2017 または Visual Studio 2019 に設定します。 このページの目次の一番上にあります。

::: moniker-end
::: moniker range=">=msvc-150"

`IRelogger` クラスにより、Event Tracing for Windows (ETW) トレースの再ログ記録を行うためのインターフェイスが提供されます。 [MakeDynamicReloggerGroup](../functions/make-dynamic-relogger-group.md) 関数と [MakeStaticReloggerGroup](../functions/make-static-analyzer-group.md) 関数で使用されます。 リロガー グループの一部にできる独自のリロガーを作成するための基底クラスとしては、`IRelogger` を使用します。

## <a name="syntax"></a>構文

```cpp
class IRelogger
{
public:
    virtual AnalysisControl OnStartActivity(const EventStack& eventStack,
        const void* relogSession);

    virtual AnalysisControl OnStopActivity(const EventStack& eventStack,
        const void* relogSession);

    virtual AnalysisControl OnSimpleEvent(const EventStack& eventStack,
        const void* relogSession);

    virtual AnalysisControl OnTraceInfo(const TraceInfo& traceInfo);
    virtual AnalysisControl OnBeginRelogging();
    virtual AnalysisControl OnEndRelogging();
    virtual AnalysisControl OnBeginReloggingPass();
    virtual AnalysisControl OnEndReloggingPass() ;

    virtual ~IRelogger();
};
```

## <a name="remarks"></a>解説

オーバーライドされていないすべての関数の既定の戻り値は `AnalysisControl::CONTINUE` です。 詳細については、[AnalysisControl](analysis-control-enum-class.md) に関する記事を参照してください。

## <a name="members"></a>メンバー

### <a name="destructor"></a>デストラクターです。

[~IRelogger](#irelogger-destructor)

### <a name="functions"></a>機能

[OnBeginRelogging](#on-begin-relogging)\
[OnBeginReloggingPass](#on-begin-relogging-pass)\
[OnEndRelogging](#on-end-relogging)\
[OnEndReloggingPass](#on-end-relogging-pass)\
[OnSimpleEvent](#on-simple-event)\
[OnStartActivity](#on-start-activity)\
[OnStopActivity](#on-stop-activity)\
[OnTraceInfo](#on-trace-info)

## <a name="irelogger"></a><a name="irelogger-destructor"></a> ~IRelogger

IRelogger クラスを破棄します。

```cpp
virtual ~IRelogger();
```

## <a name="onbeginrelogging"></a><a name="on-begin-relogging"></a> OnBeginRelogging

この関数は、再ログ記録パスが開始される前に呼び出されます。

```cpp
virtual AnalysisControl OnBeginRelogging();
```

### <a name="return-value"></a>戻り値

次に行う必要があることが記述されている [AnalysisControl](analysis-control-enum-class.md) コード。

## <a name="onbeginreloggingpass"></a><a name="on-begin-relogging-pass"></a> OnBeginReloggingPass

この関数は、再ログ記録パスの開始時に呼び出されます。

```cpp
virtual AnalysisControl OnBeginReloggingPass();
```

### <a name="return-value"></a>戻り値

次に行う必要があることが記述されている [AnalysisControl](analysis-control-enum-class.md) コード。

## <a name="onendrelogging"></a><a name="on-end-relogging"></a> OnEndRelogging

この関数は、再ログ記録パスが終了した後で呼び出されます。

```cpp
virtual AnalysisControl OnEndRelogging();
```

### <a name="return-value"></a>戻り値

次に行う必要があることが記述されている [AnalysisControl](analysis-control-enum-class.md) コード。

## <a name="onendreloggingpass"></a><a name="on-end-relogging-pass"></a> OnEndReloggingPass

この関数は、再ログ記録パスの終了時に呼び出されます。

```cpp
virtual AnalysisControl OnEndReloggingPass();
```

### <a name="return-value"></a>戻り値

次に行う必要があることが記述されている [AnalysisControl](analysis-control-enum-class.md) コード。

## <a name="onsimpleevent"></a><a name="on-simple-event"></a> OnSimpleEvent

```cpp
virtual AnalysisControl OnSimpleEvent(const EventStack& eventStack);
```

この関数は、簡易イベントが処理されるときに呼び出されます。

### <a name="parameters"></a>パラメーター

*eventStack*\
この簡易イベントのイベント スタック。 イベント スタックの詳細については、[イベント](../event-table.md)に関するページを参照してください。

### <a name="return-value"></a>戻り値

次に行う必要があることが記述されている [AnalysisControl](analysis-control-enum-class.md) コード。

## <a name="onstartactivity"></a><a name="on-start-activity"></a> OnStartActivity

```cpp
virtual AnalysisControl OnStartActivity(const EventStack& eventStack);
```

この関数は、アクティビティ開始イベントが処理されるときに呼び出されます。

### <a name="parameters"></a>パラメーター

*eventStack*\
このアクティビティ開始イベントのイベント スタック。 イベント スタックの詳細については、[イベント](../event-table.md)に関するページを参照してください。

### <a name="return-value"></a>戻り値

次に行う必要があることが記述されている [AnalysisControl](analysis-control-enum-class.md) コード。

## <a name="onstopactivity"></a><a name="on-stop-activity"></a> OnStopActivity

この関数は、アクティビティ停止イベントが処理されるときに呼び出されます。

```cpp
virtual AnalysisControl OnStopActivity(const EventStack& eventStack);
```

### <a name="parameters"></a>パラメーター

*eventStack*\
このアクティビティ停止イベントのイベント スタック。 イベント スタックの詳細については、[イベント](../event-table.md)に関するページを参照してください。

### <a name="return-value"></a>戻り値

次に行う必要があることが記述されている [AnalysisControl](analysis-control-enum-class.md) コード。

## <a name="ontraceinfo"></a><a name="on-trace-info"></a> OnTraceInfo

```cpp
virtual AnalysisControl OnTraceInfo(const TraceInfo& traceInfo);
```

この関数は、すべての分析パスまたは再ログ記録パスの開始時に 1 回呼び出されます。

### <a name="parameters"></a>パラメーター

*traceInfo*\
使用されているトレースに関する有用なプロパティが格納される [TraceInfo](../cpp-event-data-types/trace-info.md) オブジェクト。

### <a name="return-value"></a>戻り値

次に行う必要があることが記述されている [AnalysisControl](analysis-control-enum-class.md) コード。

::: moniker-end

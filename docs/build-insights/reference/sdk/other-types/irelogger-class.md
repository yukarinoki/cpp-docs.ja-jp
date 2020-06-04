---
title: IRelogger クラス
description: C++ ビルド インサイト SDK IRelogger クラス リファレンス。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- IRelogger
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 146377b2b44df43ed4b2f749efd9fb614a2a09c9
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81329155"
---
# <a name="irelogger-class"></a>IRelogger クラス

::: moniker range="<=vs-2015"

C++ ビルド インサイト SDK は、Visual Studio 2017 以降と互換性があります。 これらのバージョンのドキュメントを参照するには、この記事の Visual Studio**バージョン**セレクター コントロールを Visual Studio 2017 または Visual Studio 2019 に設定します。 このページの目次の上部に表示されます。

::: moniker-end
::: moniker range=">=vs-2017"

この`IRelogger`クラスは、Windows イベント トレース (ETW) トレースを再ログするためのインターフェイスを提供します。 これは、[関数](../functions/make-dynamic-relogger-group.md)と共に使用[されます](../functions/make-static-analyzer-group.md)。 リ`IRelogger`ロガーグループの一部にすることができる独自のリロガーを作成する基本クラスとして使用します。

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

オーバーライドされないすべての関数の既定の戻り値は`AnalysisControl::CONTINUE`です。 詳細については、「[分析コントロール](analysis-control-enum-class.md)」を参照してください。

## <a name="members"></a>メンバー

### <a name="destructor"></a>デストラクターです。

[~IRelogger](#irelogger-destructor)

### <a name="functions"></a>関数

[オンビギンリロギング](#on-begin-relogging)\
[オンビギンリロギングパス](#on-begin-relogging-pass)\
[オンエンドリロギング](#on-end-relogging)\
[オンエンドレロギングパス](#on-end-relogging-pass)\
[オンシンプルイベント](#on-simple-event)\
[オンスタートアクティビティ](#on-start-activity)\
[オンストップアクティビティ](#on-stop-activity)\
[オントレース情報](#on-trace-info)

## <a name="irelogger"></a><a name="irelogger-destructor"></a>~IRelogger

IRelogger クラスを破棄します。

```cpp
virtual ~IRelogger();
```

## <a name="onbeginrelogging"></a><a name="on-begin-relogging"></a>オンビギンリロギング

この関数は、再ロギングパスが開始される前に呼び出されます。

```cpp
virtual AnalysisControl OnBeginRelogging();
```

### <a name="return-value"></a>戻り値

次に何が起こるかを記述する[分析コントロール](analysis-control-enum-class.md)コード。

## <a name="onbeginreloggingpass"></a><a name="on-begin-relogging-pass"></a>オンビギンリロギングパス

この関数は、再ロギングパスの先頭で呼び出されます。

```cpp
virtual AnalysisControl OnBeginReloggingPass();
```

### <a name="return-value"></a>戻り値

次に何が起こるかを記述する[分析コントロール](analysis-control-enum-class.md)コード。

## <a name="onendrelogging"></a><a name="on-end-relogging"></a>オンエンドリロギング

この関数は、再ロギングパスが終了した後に呼び出されます。

```cpp
virtual AnalysisControl OnEndRelogging();
```

### <a name="return-value"></a>戻り値

次に何が起こるかを記述する[分析コントロール](analysis-control-enum-class.md)コード。

## <a name="onendreloggingpass"></a><a name="on-end-relogging-pass"></a>オンエンドレロギングパス

この関数は、再ロギングパスの最後に呼び出されます。

```cpp
virtual AnalysisControl OnEndReloggingPass();
```

### <a name="return-value"></a>戻り値

次に何が起こるかを記述する[分析コントロール](analysis-control-enum-class.md)コード。

## <a name="onsimpleevent"></a><a name="on-simple-event"></a>オンシンプルイベント

```cpp
virtual AnalysisControl OnSimpleEvent(const EventStack& eventStack);
```

この関数は、単純なイベントが処理されるときに呼び出されます。

### <a name="parameters"></a>パラメーター

*イベントスタック*\
この単純なイベントのイベント スタック。 イベント スタックの詳細については、「[イベント](../event-table.md)」を参照してください。

### <a name="return-value"></a>戻り値

次に何が起こるかを記述する[分析コントロール](analysis-control-enum-class.md)コード。

## <a name="onstartactivity"></a><a name="on-start-activity"></a>オンスタートアクティビティ

```cpp
virtual AnalysisControl OnStartActivity(const EventStack& eventStack);
```

この関数は、アクティビティ開始イベントが処理されるときに呼び出されます。

### <a name="parameters"></a>パラメーター

*イベントスタック*\
このアクティビティ開始イベントのイベント スタック。 イベント スタックの詳細については、「[イベント](../event-table.md)」を参照してください。

### <a name="return-value"></a>戻り値

次に何が起こるかを記述する[分析コントロール](analysis-control-enum-class.md)コード。

## <a name="onstopactivity"></a><a name="on-stop-activity"></a>オンストップアクティビティ

この関数は、アクティビティ停止イベントが処理されるときに呼び出されます。

```cpp
virtual AnalysisControl OnStopActivity(const EventStack& eventStack);
```

### <a name="parameters"></a>パラメーター

*イベントスタック*\
このアクティビティ停止イベントのイベント スタック。 イベント スタックの詳細については、「[イベント](../event-table.md)」を参照してください。

### <a name="return-value"></a>戻り値

次に何が起こるかを記述する[分析コントロール](analysis-control-enum-class.md)コード。

## <a name="ontraceinfo"></a><a name="on-trace-info"></a>オントレース情報

```cpp
virtual AnalysisControl OnTraceInfo(const TraceInfo& traceInfo);
```

この関数は、すべての分析または再ロギングパスの開始時に 1 回呼び出されます。

### <a name="parameters"></a>パラメーター

*トレース情報*\
使用されるトレースに関する有用なプロパティを格納する[TraceInfo](../cpp-event-data-types/trace-info.md)オブジェクト。

### <a name="return-value"></a>戻り値

次に何が起こるかを記述する[分析コントロール](analysis-control-enum-class.md)コード。

::: moniker-end

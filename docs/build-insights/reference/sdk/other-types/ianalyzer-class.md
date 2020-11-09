---
title: IAnalyzer クラス
description: C++ Build Insights SDK の IAnalyzer クラスのリファレンス。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- IAnalyzer
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 2514dd305a186d1153e9f9d1711bb774ea70cdf9
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/29/2020
ms.locfileid: "92919814"
---
# <a name="ianalyzer-class"></a>IAnalyzer クラス

::: moniker range="<=msvc-140"

C++ Build Insights SDK は、Visual Studio 2017 以降と互換性があります。 これらのバージョンのドキュメントを表示するには、この記事の Visual Studio **Version** セレクター コントロールを Visual Studio 2017 または Visual Studio 2019 に設定します。 このページの目次の一番上にあります。

::: moniker-end
::: moniker range=">=msvc-150"

`IAnalyzer` クラスにより、Event Tracing for Windows (ETW) トレースの分析を行うためのインターフェイスが提供されます。 これは、[MakeDynamicAnalyzerGroup](../functions/make-dynamic-analyzer-group.md)、[MakeDynamicReloggerGroup](../functions/make-dynamic-relogger-group.md)、[MakeStaticAnalyzerGroup](../functions/make-dynamic-analyzer-group.md)、および [MakeStaticReloggerGroup](../functions/make-static-analyzer-group.md) 関数で使用されます。 アナライザーまたはリロガー グループの一部にできる独自のアナライザーを作成するための基底クラスとしては、`IAnalyzer` を使用します。

## <a name="syntax"></a>構文

```cpp
class IAnalyzer : public IRelogger
{
public:
    virtual AnalysisControl OnStartActivity(const EventStack& eventStack);
    virtual AnalysisControl OnStopActivity(const EventStack& eventStack)
    virtual AnalysisControl OnSimpleEvent(const EventStack& eventStack);
    virtual AnalysisControl OnBeginAnalysis();
    virtual AnalysisControl OnEndAnalysis();
    virtual AnalysisControl OnBeginAnalysisPass();
    virtual AnalysisControl OnEndAnalysisPass();

    AnalysisControl OnStartActivity(const EventStack& eventStack,
        const void* relogSession) final;

    AnalysisControl OnStopActivity(const EventStack& eventStack,
        const void* relogSession) final;

    AnalysisControl OnSimpleEvent(const EventStack& eventStack,
        const void* relogSession) final;

    AnalysisControl OnBeginRelogging() final;
    AnalysisControl OnEndRelogging() final;
    AnalysisControl OnBeginReloggingPass() final;
    AnalysisControl OnEndReloggingPass() final;

    virtual ~IAnalyzer();
};
```

## <a name="remarks"></a>解説

`IAnalyzer` から派生したクラスは、アナライザーとしても、リロガーとしても使用できます。 リロガーとして使用する場合、リロガー固有の関数は同等のアナライザーの関数にリダイレクトされます。 その逆は当てはまりません。つまり、`IRelogger` から派生したクラスをアナライザーとして使用することはできません。 リロガー グループでアナライザーを使用するのは一般的なパターンです。 リロガー グループの早い位置に配置されたアナライザーによって、情報を事前に計算し、より後の位置にあるリロガーが使用できるようにすることができます。

オーバーライドされていないすべての関数の既定の戻り値は `AnalysisControl::CONTINUE` です。 詳細については、[AnalysisControl](analysis-control-enum-class.md) に関する記事をご覧ください。

## <a name="members"></a>メンバー

`IRelogger` インターフェイスの [OnTraceInfo](irelogger-class.md#on-trace-info) メンバーに加えて、`IAnalyzer` クラスには次のメンバーが含まれています。

### <a name="destructor"></a>デストラクターです。

[~IAnalyzer](#ianalyzer-destructor)

### <a name="functions"></a>機能

[OnBeginAnalysis](#on-begin-analysis)\
[OnBeginAnalysisPass](#on-begin-analysis-pass)\
[OnBeginRelogging](#on-begin-relogging)\
[OnBeginReloggingPass](#on-begin-relogging-pass)\
[OnEndAnalysis](#on-end-analysis)\
[OnEndAnalysisPass](#on-end-analysis-pass)\
[OnEndRelogging](#on-end-relogging)\
[OnEndReloggingPass](#on-end-relogging-pass)\
[OnSimpleEvent](#on-simple-event)\
[OnStartActivity](#on-start-activity)\
[OnStopActivity](#on-stop-activity)

## <a name="ianalyzer"></a><a name="ianalyzer-destructor"></a> ~IAnalyzer

IAnalyzer クラスを破棄します。

```cpp
virtual ~IAnalyzer();
```

## <a name="onbeginanalysis"></a><a name="on-begin-analysis"></a> OnBeginAnalysis

アナライザー グループのアナライザーの部分では、最初の分析パスが開始される前に、この関数が呼び出されます。 リロガー グループのアナライザーの部分では、再ログ記録パスが開始される前に、この関数が呼び出されます。 同じ再ログ記録セッションのアナライザーおよびリロガー グループ両方のアナライザーの部分では、最初の分析パスが開始される前に、この関数が 2 回呼び出されます。

```cpp
virtual AnalysisControl OnBeginAnalysis();
```

### <a name="return-value"></a>戻り値

次に行う必要があることが記述されている [AnalysisControl](analysis-control-enum-class.md) コード。

## <a name="onbeginanalysispass"></a><a name="on-begin-analysis-pass"></a> OnBeginAnalysisPass

アナライザー グループのアナライザーの部分では、すべての分析パスの開始時にこの関数が呼び出されます。 リロガー グループのアナライザーの部分では、リロガー パスの開始時にこの関数が呼び出されます。 同じ再ログ記録セッションのアナライザーおよびリロガー グループ両方のアナライザーの部分では、すべての分析パスの開始時、およびリロガー パスの開始時にこの関数が呼び出されます。

```cpp
virtual AnalysisControl OnBeginAnalysisPass();
```

### <a name="return-value"></a>戻り値

次に行う必要があることが記述されている [AnalysisControl](analysis-control-enum-class.md) コード。

## <a name="onbeginrelogging"></a><a name="on-begin-relogging"></a> OnBeginRelogging

```cpp
AnalysisControl OnBeginRelogging() final;
```

この関数をオーバーライドすることはできません。 これは、アナライザーがリロガー グループの一部である場合、C++ Build Insights SDK によって呼び出されます。 この関数によって [OnBeginAnalysis](#on-begin-analysis) への呼び出しがリダイレクトされます。

### <a name="return-value"></a>戻り値

[OnBeginAnalysis](#on-begin-analysis) 呼び出しの結果です。

## <a name="onbeginreloggingpass"></a><a name="on-begin-relogging-pass"></a> OnBeginReloggingPass

この関数をオーバーライドすることはできません。 これは、アナライザーがリロガー グループの一部である場合、C++ Build Insights SDK によって呼び出されます。 この関数によって [OnBeginAnalysisPass](#on-begin-analysis-pass) への呼び出しがリダイレクトされます。

```cpp
AnalysisControl OnBeginReloggingPass() final;
```

### <a name="return-value"></a>戻り値

[OnBeginAnalysisPass](#on-begin-analysis-pass) 呼び出しの結果です。

## <a name="onendanalysis"></a><a name="on-end-analysis"></a> OnEndAnalysis

アナライザー グループの一部であるアナライザーでは、最後の分析パスが終了した後に、この関数が呼び出されます。 リロガー グループの一部であるアナライザーでは、再ログ記録パスが終了した後に、この関数が呼び出されます。 同じ再ログ記録セッションのアナライザーおよびリロガー グループ両方の一部であるアナライザーの場合、この関数は 2 回呼び出されます。

1. すべての分析パスが終了した後、再ログ記録パスが開始される前。および
1. 再ログ記録パスが終了した後。

```cpp
virtual AnalysisControl OnEndAnalysis();
```

### <a name="return-value"></a>戻り値

次に行う必要があることが記述されている [AnalysisControl](analysis-control-enum-class.md) コード。

## <a name="onendanalysispass"></a><a name="on-end-analysis-pass"></a> OnEndAnalysisPass

アナライザー グループのアナライザーの部分では、すべての分析パスの終了時にこの関数が呼び出されます。 リロガー グループのアナライザーの部分では、リロガー パスの終了時にこの関数が呼び出されます。 同じ再ログ記録セッションのアナライザーおよびリロガー グループ両方のアナライザーの部分では、すべての分析パスの終了時、およびリロガー パスの終了時にこの関数が呼び出されます。

```cpp
virtual AnalysisControl OnEndAnalysisPass();
```

### <a name="return-value"></a>戻り値

次に行う必要があることが記述されている [AnalysisControl](analysis-control-enum-class.md) コード。

## <a name="onendrelogging"></a><a name="on-end-relogging"></a> OnEndRelogging

この関数をオーバーライドすることはできません。 これは、アナライザーがリロガー グループの一部である場合、C++ Build Insights SDK によって呼び出されます。 この関数によって [OnEndAnalysis](#on-end-analysis) への呼び出しがリダイレクトされます。

```cpp
AnalysisControl OnEndRelogging() final;
```

### <a name="return-value"></a>戻り値

[OnEndAnalysis](#on-end-analysis) 呼び出しの結果です。

## <a name="onendreloggingpass"></a><a name="on-end-relogging-pass"></a> OnEndReloggingPass

この関数をオーバーライドすることはできません。 これは、アナライザーがリロガー グループの一部である場合、C++ Build Insights SDK によって呼び出されます。 この関数によって [OnEndAnalysisPass](#on-end-analysis-pass) への呼び出しがリダイレクトされます。

```cpp
AnalysisControl OnEndReloggingPass() final;
```

### <a name="return-value"></a>戻り値

[OnEndAnalysisPass](#on-end-analysis-pass) 呼び出しの結果です。

## <a name="onsimpleevent"></a><a name="on-simple-event"></a> OnSimpleEvent

この関数は、簡易イベントが処理されるときに呼び出されます。 この関数の 2 番目のバージョンをオーバーライドすることはできません。 これは、アナライザーがリロガー グループの一部である場合、C++ Build Insights SDK によって呼び出されます。 バージョン 2 へのすべての呼び出しは、バージョン 1 にリダイレクトされます。

### <a name="version-1"></a>Version 1

```cpp
virtual AnalysisControl OnSimpleEvent(const EventStack& eventStack);
```

### <a name="version-2"></a>Version 2

```cpp
AnalysisControl OnSimpleEvent(const EventStack& eventStack,
        const void* relogSession) final;
```

### <a name="parameters"></a>パラメーター

*eventStack*\
この簡易イベントのイベント スタック。 イベント スタックの詳細については、[イベント](../event-table.md)に関するページを参照してください。

*relogSession*\
このパラメーターは使用されません。

### <a name="return-value"></a>戻り値

次に行う必要があることが記述されている [AnalysisControl](analysis-control-enum-class.md) コード。

## <a name="onstartactivity"></a><a name="on-start-activity"></a> OnStartActivity

この関数は、アクティビティ開始イベントが処理されるときに呼び出されます。 この関数の 2 番目のバージョンをオーバーライドすることはできません。 これは、アナライザーがリロガー グループの一部である場合、C++ Build Insights SDK によって呼び出されます。 バージョン 2 へのすべての呼び出しは、バージョン 1 にリダイレクトされます。

### <a name="version-1"></a>Version 1

```cpp
virtual AnalysisControl OnStartActivity(const EventStack& eventStack);
```

### <a name="version-2"></a>Version 2

```cpp
AnalysisControl OnStartActivity(const EventStack& eventStack,
        const void* relogSession) final;
```

### <a name="parameters"></a>パラメーター

*eventStack*\
このアクティビティ開始イベントのイベント スタック。 イベント スタックの詳細については、[イベント](../event-table.md)に関するページを参照してください。

*relogSession*\
このパラメーターは使用されません。

### <a name="return-value"></a>戻り値

次に行う必要があることが記述されている [AnalysisControl](analysis-control-enum-class.md) コード。

## <a name="onstopactivity"></a><a name="on-stop-activity"></a> OnStopActivity

この関数は、アクティビティ停止イベントが処理されるときに呼び出されます。 この関数の 2 番目のバージョンをオーバーライドすることはできません。 これは、アナライザーがリロガー グループの一部である場合、C++ Build Insights SDK によって呼び出されます。 バージョン 2 へのすべての呼び出しは、バージョン 1 にリダイレクトされます。

### <a name="version-1"></a>Version 1

```cpp
virtual AnalysisControl OnStopActivity(const EventStack& eventStack);
```

### <a name="version-2"></a>Version 2

```cpp
AnalysisControl OnStopActivity(const EventStack& eventStack,
        const void* relogSession) final;
```

### <a name="parameters"></a>パラメーター

*eventStack*\
このアクティビティ停止イベントのイベント スタック。 イベント スタックの詳細については、[イベント](../event-table.md)に関するページを参照してください。

*relogSession*\
このパラメーターは使用されません。

### <a name="return-value"></a>戻り値

次に行う必要があることが記述されている [AnalysisControl](analysis-control-enum-class.md) コード。

::: moniker-end

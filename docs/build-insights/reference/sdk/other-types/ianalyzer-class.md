---
title: Iアナライザクラス
description: C++ ビルド インサイト SDK IAnalyzer クラスリファレンス。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- IAnalyzer
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: be9d80bb94450458c73fd6ce8d908985ba6f293d
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81329170"
---
# <a name="ianalyzer-class"></a>Iアナライザクラス

::: moniker range="<=vs-2015"

C++ ビルド インサイト SDK は、Visual Studio 2017 以降と互換性があります。 これらのバージョンのドキュメントを参照するには、この記事の Visual Studio**バージョン**セレクター コントロールを Visual Studio 2017 または Visual Studio 2019 に設定します。 このページの目次の上部に表示されます。

::: moniker-end
::: moniker range=">=vs-2017"

この`IAnalyzer`クラスは、Windows (ETW) トレースのイベント トレースを分析するためのインターフェイスを提供します。 これは、関数、ダイナミック[アナライザグループ](../functions/make-dynamic-analyzer-group.md)、[メイクダイナミックリロガーグループ](../functions/make-dynamic-relogger-group.md)、[メイクスタティックアナライザグループ](../functions/make-dynamic-analyzer-group.md)、および[メイクスタティックリロガーグループ](../functions/make-static-analyzer-group.md)関数で使用されます。 アナライザ`IAnalyzer`ーまたはリロガー グループの一部にすることができる独自のアナライザーを作成する基本クラスとして使用します。

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

派生`IAnalyzer`元のクラスは、アナライザーとリロガーの両方として使用できます。 リロガーとして使用する場合, リロガー固有の関数は、同等のアナライザーにリダイレクトします。 その逆は真実ではなく、派生`IRelogger`元のクラスをアナライザーとして使用することはできません。 リロガー グループでアナライザーを使用することは一般的なパターンです。 リロガーグループの早期位置に置かれた場合、アナライザーは情報を事前に計算し、後の位置でリロガーに利用できるようにします。

オーバーライドされないすべての関数の既定の戻り値は`AnalysisControl::CONTINUE`です。 詳細については、「[分析コントロール](analysis-control-enum-class.md)」を参照してください。

## <a name="members"></a>メンバー

インターフェイスの[OnTraceInfo](irelogger-class.md#on-trace-info)メンバーに加えて、`IAnalyzer`クラスには次のメンバーが含まれています。 `IRelogger`

### <a name="destructor"></a>デストラクターです。

[~Iアナライザ](#ianalyzer-destructor)

### <a name="functions"></a>関数

[分析の開始](#on-begin-analysis)\
[オンビギン分析パス](#on-begin-analysis-pass)\
[オンビギンリロギング](#on-begin-relogging)\
[オンビギンリロギングパス](#on-begin-relogging-pass)\
[オンエンド分析](#on-end-analysis)\
[オンエンド分析パス](#on-end-analysis-pass)\
[オンエンドリロギング](#on-end-relogging)\
[オンエンドレロギングパス](#on-end-relogging-pass)\
[オンシンプルイベント](#on-simple-event)\
[オンスタートアクティビティ](#on-start-activity)\
[オンストップアクティビティ](#on-stop-activity)

## <a name="ianalyzer"></a><a name="ianalyzer-destructor"></a>~Iアナライザ

IAnalyzer クラスを破棄します。

```cpp
virtual ~IAnalyzer();
```

## <a name="onbeginanalysis"></a><a name="on-begin-analysis"></a>分析の開始

アナライザ グループのアナライザーの一部の場合、この関数は最初の分析パスが開始される前に呼び出されます。 リロガー グループのアナライザーの一部の場合、この関数は再ロギングパスが開始する前に呼び出されます。 アナライザーと同じ再ロギングセッションのリロガーグループの両方の部分のアナライザーの場合、この関数は最初の分析パスが開始される前に2回呼び出されます。

```cpp
virtual AnalysisControl OnBeginAnalysis();
```

### <a name="return-value"></a>戻り値

次に何が起こるかを記述する[分析コントロール](analysis-control-enum-class.md)コード。

## <a name="onbeginanalysispass"></a><a name="on-begin-analysis-pass"></a>オンビギン分析パス

アナライザ グループのアナライザーの一部の場合、この関数は、すべての分析パスの先頭で呼び出されます。 リロガー グループのアナライザーの一部の場合、この関数はリロガー パスの先頭で呼び出されます。 アナライザーのアナライザーと同じ再ロギングセッションのリロガーグループの両方の部分の場合、この関数は、すべての分析パスの先頭に、リロガーパスの先頭に呼び出されます。

```cpp
virtual AnalysisControl OnBeginAnalysisPass();
```

### <a name="return-value"></a>戻り値

次に何が起こるかを記述する[分析コントロール](analysis-control-enum-class.md)コード。

## <a name="onbeginrelogging"></a><a name="on-begin-relogging"></a>オンビギンリロギング

```cpp
AnalysisControl OnBeginRelogging() final;
```

この関数はオーバーライドできません。 アナライザーがリロガー グループの一部である場合、C++ ビルド インサイト SDK によって呼び出されます。 この関数は、呼び出しを[OnBeginAnalysis](#on-begin-analysis)にリダイレクトします。

### <a name="return-value"></a>戻り値

呼び出し[の](#on-begin-analysis)結果。

## <a name="onbeginreloggingpass"></a><a name="on-begin-relogging-pass"></a>オンビギンリロギングパス

この関数はオーバーライドできません。 アナライザーがリロガー グループの一部である場合、C++ ビルド インサイト SDK によって呼び出されます。 この関数は、呼び出しを[OnBeginAnalysisPass](#on-begin-analysis-pass)にリダイレクトします。

```cpp
AnalysisControl OnBeginReloggingPass() final;
```

### <a name="return-value"></a>戻り値

呼び出し[の](#on-begin-analysis-pass)結果。

## <a name="onendanalysis"></a><a name="on-end-analysis"></a>オンエンド分析

アナライザー グループの一部であるアナライザーの場合、この関数は最後の分析パスが終了した後に呼び出されます。 リロガー グループの一部であるアナライザーの場合、この関数は、再ロギング パスが終了した後に呼び出されます。 同じ再ロギング セッションのアナライザーとリロガー グループの両方の一部であるアナライザーの場合、この関数は 2 回呼び出されます。

1. すべての解析パスが終了した後、再ロギングパスが開始される前に、
1. 再ロギングパスが終了した後。

```cpp
virtual AnalysisControl OnEndAnalysis();
```

### <a name="return-value"></a>戻り値

次に何が起こるかを記述する[分析コントロール](analysis-control-enum-class.md)コード。

## <a name="onendanalysispass"></a><a name="on-end-analysis-pass"></a>オンエンド分析パス

アナライザ グループのアナライザーの一部の場合、この関数は、すべての分析パスの最後に呼び出されます。 リロガー グループのアナライザーの一部の場合、この関数はリロガー パスの最後に呼び出されます。 アナライザーのアナライザーと同じ再ロギングセッションのリロガーグループの両方の部分の場合、この関数は、すべての分析パスの最後に、リロガーパスの最後に呼び出されます。

```cpp
virtual AnalysisControl OnEndAnalysisPass();
```

### <a name="return-value"></a>戻り値

次に何が起こるかを記述する[分析コントロール](analysis-control-enum-class.md)コード。

## <a name="onendrelogging"></a><a name="on-end-relogging"></a>オンエンドリロギング

この関数はオーバーライドできません。 アナライザーがリロガー グループの一部である場合、C++ ビルド インサイト SDK によって呼び出されます。 この関数は、呼び出しを[OnEndAnalysis](#on-end-analysis)にリダイレクトします。

```cpp
AnalysisControl OnEndRelogging() final;
```

### <a name="return-value"></a>戻り値

[OnEnd 分析](#on-end-analysis)呼び出しの結果。

## <a name="onendreloggingpass"></a><a name="on-end-relogging-pass"></a>オンエンドレロギングパス

この関数はオーバーライドできません。 アナライザーがリロガー グループの一部である場合、C++ ビルド インサイト SDK によって呼び出されます。 この関数は、呼び出しを[OnEndAnalysisPass](#on-end-analysis-pass)にリダイレクトします。

```cpp
AnalysisControl OnEndReloggingPass() final;
```

### <a name="return-value"></a>戻り値

[オンエンド分析パス](#on-end-analysis-pass)呼び出しの結果。

## <a name="onsimpleevent"></a><a name="on-simple-event"></a>オンシンプルイベント

この関数は、単純なイベントが処理されるときに呼び出されます。 この関数の 2 番目のバージョンはオーバーライドできません。 アナライザーがリロガー グループの一部である場合、C++ ビルド インサイト SDK によって呼び出されます。 バージョン 2 へのすべての呼び出しはバージョン 1 にリダイレクトされます。

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

*イベントスタック*\
この単純なイベントのイベント スタック。 イベント スタックの詳細については、「[イベント](../event-table.md)」を参照してください。

*セッションを再ログします。*\
このパラメーターは使用されません。

### <a name="return-value"></a>戻り値

次に何が起こるかを記述する[分析コントロール](analysis-control-enum-class.md)コード。

## <a name="onstartactivity"></a><a name="on-start-activity"></a>オンスタートアクティビティ

この関数は、アクティビティ開始イベントが処理されるときに呼び出されます。 この関数の 2 番目のバージョンはオーバーライドできません。 アナライザーがリロガー グループの一部である場合、C++ ビルド インサイト SDK によって呼び出されます。 バージョン 2 へのすべての呼び出しはバージョン 1 にリダイレクトされます。

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

*イベントスタック*\
このアクティビティ開始イベントのイベント スタック。 イベント スタックの詳細については、「[イベント](../event-table.md)」を参照してください。

*セッションを再ログします。*\
このパラメーターは使用されません。

### <a name="return-value"></a>戻り値

次に何が起こるかを記述する[分析コントロール](analysis-control-enum-class.md)コード。

## <a name="onstopactivity"></a><a name="on-stop-activity"></a>オンストップアクティビティ

この関数は、アクティビティ停止イベントが処理されるときに呼び出されます。 この関数の 2 番目のバージョンはオーバーライドできません。 アナライザーがリロガー グループの一部である場合、C++ ビルド インサイト SDK によって呼び出されます。 バージョン 2 へのすべての呼び出しはバージョン 1 にリダイレクトされます。

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

*イベントスタック*\
このアクティビティ停止イベントのイベント スタック。 イベント スタックの詳細については、「[イベント](../event-table.md)」を参照してください。

*セッションを再ログします。*\
このパラメーターは使用されません。

### <a name="return-value"></a>戻り値

次に何が起こるかを記述する[分析コントロール](analysis-control-enum-class.md)コード。

::: moniker-end

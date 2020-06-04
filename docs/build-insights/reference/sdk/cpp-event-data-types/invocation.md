---
title: 呼び出しクラス
description: C++ ビルド インサイト SDK 呼び出しクラスのリファレンス。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- Invocation
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: fcb087d46ea445251b0108f811545a44c26f421e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81324637"
---
# <a name="invocation-class"></a>呼び出しクラス

::: moniker range="<=vs-2015"

C++ ビルド インサイト SDK は、Visual Studio 2017 以降と互換性があります。 これらのバージョンのドキュメントを参照するには、この記事の Visual Studio**バージョン**セレクター コントロールを Visual Studio 2017 または Visual Studio 2019 に設定します。 このページの目次の上部に表示されます。

::: moniker-end
::: moniker range=">=vs-2017"

クラス`Invocation`[は、](../functions/match-event-in-member-function.md)[関数](../functions/match-event.md)で使用されます。 [MatchEventStack](../functions/match-event-stack.md) [MatchEventStackInMemberFunction](../functions/match-event-stack-in-member-function.md) このイベントは[、コンパイラ](../event-table.md#compiler)ーまたは[リンカー](../event-table.md#linker) ・イベントと一致させるために使用します。

## <a name="syntax"></a>構文

```cpp
class Invocation : public Activity
{
    const INVOCATION_DATA* data_;

public:
    enum class Type
    {
        CL      = MSVC_TOOL_CODE_CL,
        LINK    = MSVC_TOOL_CODE_LINK
    };

    Invocation(const RawEvent& event);

    Type             Type() const;
    const char*      ToolVersionString() const;
    const wchar_t*   WorkingDirectory() const;
    const wchar_t*   ToolPath() const;

    const INVOCATION_VERSION_DATA& ToolVersion() const;
};
```

## <a name="members"></a>メンバー

クラスには、[その Activity](activity.md)基本クラスから継承された`Invocation`メンバーと共に、次のメンバーが含まれます。

### <a name="constructors"></a>コンストラクター

[[呼び出し]](#invocation)

### <a name="functions"></a>関数

[ツールパス](#tool-path)
[ツールバージョン](#tool-version)
[ツールバージョン文字列](#tool-version-string)
[タイプ](#type)
[ワーキングディレクトリ](#working-directory)

## <a name="invocation"></a><a name="invocation"></a>呼び出し

```cpp
Invocation(const RawEvent& event);
```

### <a name="parameters"></a>パラメーター

*イベント*\
[コンパイラ](../event-table.md#compiler)ーまたは[リンカー](../event-table.md#linker) ・イベント。

## <a name="toolpath"></a><a name="tool-path"></a>ツールパス

```cpp
const wchar_t* ToolPath() const;
```

### <a name="return-value"></a>戻り値

呼び出されたツールへの絶対パス。

## <a name="toolversion"></a><a name="tool-version"></a>ツールバージョン

```cpp
const INVOCATION_VERSION_DATA& ToolVersion() const;
```

### <a name="return-value"></a>戻り値

[INVOCATION_VERSION_DATA](../c-event-data-types/invocation-version-data-struct.md)参照として呼び出されたツールのバージョン。

## <a name="toolversionstring"></a><a name="tool-version-string"></a>ツールバージョン文字列

```cpp
const char* ToolVersionString() const;
```

### <a name="return-value"></a>戻り値

ANSI 文字列として呼び出されたツールのバージョン。

## <a name="type"></a><a name="type"></a> の型

```cpp
Type Type() const;
```

### <a name="return-value"></a>戻り値

呼び出されたツールを示すコード。

## <a name="workingdirectory"></a><a name="working-directory"></a>ワーキングディレクトリ

```cpp
const wchar_t* WorkingDirectory() const;
```

### <a name="return-value"></a>戻り値

ツールが呼び出されたディレクトリへの絶対パス。

::: moniker-end

---
title: Invocation クラス
description: C++ Build Insights SDK の Invocation クラスのリファレンス。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- Invocation
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: dfd463c7b9ca72dc14ad74b3759fdd1e3730d5a9
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/29/2020
ms.locfileid: "92923137"
---
# <a name="invocation-class"></a>Invocation クラス

::: moniker range="<=msvc-140"

C++ Build Insights SDK は、Visual Studio 2017 以降と互換性があります。 これらのバージョンのドキュメントを表示するには、この記事の Visual Studio **Version** セレクター コントロールを Visual Studio 2017 または Visual Studio 2019 に設定します。 このページの目次の一番上にあります。

::: moniker-end
::: moniker range=">=msvc-150"

`Invocation` クラスは、[MatchEvent](../functions/match-event.md)、[MatchEventInMemberFunction](../functions/match-event-in-member-function.md)、[MatchEventStack](../functions/match-event-stack.md)、および [MatchEventStackInMemberFunction](../functions/match-event-stack-in-member-function.md) 関数と共に使用されます。 [COMPILER](../event-table.md#compiler) または [LINKER](../event-table.md#linker) イベントを照合するために使用します。

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

その基底クラス [Activity](activity.md) から継承されたメンバーに加えて、`Invocation` クラスには以下のメンバーが含まれます。

### <a name="constructors"></a>コンストラクター

[[呼び出し]](#invocation)

### <a name="functions"></a>機能

[ToolPath](#tool-path)
[ToolVersion](#tool-version)
[ToolVersionString](#tool-version-string)
[Type](#type)
[WorkingDirectory](#working-directory)

## <a name="invocation"></a><a name="invocation"></a> Invocation

```cpp
Invocation(const RawEvent& event);
```

### <a name="parameters"></a>パラメーター

*event*\
[COMPILER](../event-table.md#compiler) または [LINKER](../event-table.md#linker) イベント。

## <a name="toolpath"></a><a name="tool-path"></a> ToolPath

```cpp
const wchar_t* ToolPath() const;
```

### <a name="return-value"></a>戻り値

呼び出されたツールへの絶対パス。

## <a name="toolversion"></a><a name="tool-version"></a> ToolVersion

```cpp
const INVOCATION_VERSION_DATA& ToolVersion() const;
```

### <a name="return-value"></a>戻り値

[INVOCATION_VERSION_DATA](../c-event-data-types/invocation-version-data-struct.md) 参照としての、呼び出されたツールのバージョン。

## <a name="toolversionstring"></a><a name="tool-version-string"></a> ToolVersionString

```cpp
const char* ToolVersionString() const;
```

### <a name="return-value"></a>戻り値

ANSI 文字列としての、呼び出されたツールのバージョン。

## <a name="type"></a><a name="type"></a> の型

```cpp
Type Type() const;
```

### <a name="return-value"></a>戻り値

呼び出されたツールを示すコード。

## <a name="workingdirectory"></a><a name="working-directory"></a> WorkingDirectory

```cpp
const wchar_t* WorkingDirectory() const;
```

### <a name="return-value"></a>戻り値

ツールが呼び出されたディレクトリへの絶対パス。

::: moniker-end

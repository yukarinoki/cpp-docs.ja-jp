---
title: FileInput クラス
description: C++ Build Insights SDK の FileInput クラスのリファレンス。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- FileInput
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 6e12336c10347f00ea2663116f2f308658775e0d
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/29/2020
ms.locfileid: "92920685"
---
# <a name="fileinput-class"></a>FileInput クラス

::: moniker range="<=msvc-140"

C++ Build Insights SDK は、Visual Studio 2017 以降と互換性があります。 これらのバージョンのドキュメントを表示するには、この記事の Visual Studio **Version** セレクター コントロールを Visual Studio 2017 または Visual Studio 2019 に設定します。 このページの目次の一番上にあります。

::: moniker-end
::: moniker range=">=msvc-150"

`FileInput` クラスは、[MatchEvent](../functions/match-event.md)、[MatchEventInMemberFunction](../functions/match-event-in-member-function.md)、[MatchEventStack](../functions/match-event-stack.md)、および [MatchEventStackInMemberFunction](../functions/match-event-stack-in-member-function.md) 関数と共に使用されます。 [FILE_INPUT](../event-table.md#file-input) イベントを照合するために使用します。

## <a name="syntax"></a>構文

```cpp
class FileInput : public SimpleEvent
{
public:
    enum class Type
    {
        OTHER               = FILE_TYPE_CODE_OTHER,
        OBJ                 = FILE_TYPE_CODE_OBJ,
        EXECUTABLE_IMAGE    = FILE_TYPE_CODE_EXECUTABLE_IMAGE,
        LIB                 = FILE_TYPE_CODE_LIB,
        IMP_LIB             = FILE_TYPE_CODE_IMP_LIB,
        EXP                 = FILE_TYPE_CODE_EXP
    };

    FileInput(const RawEvent& event);

    const wchar_t* Path() const;
    Type           Type() const;
};
```

## <a name="members"></a>メンバー

その基底クラス [SimpleEvent](simple-event.md) から継承されたメンバーに加えて、`FileInput` クラスには以下のメンバーが含まれます。

### <a name="constructors"></a>コンストラクター

[FileInput](#file-input)

### <a name="functions"></a>機能

[Path](#path)
[Type](#type)

## <a name="fileinput"></a><a name="file-input"></a> FileInput

```cpp
FileInput(const RawEvent& event);
```

### <a name="parameters"></a>パラメーター

*event*\
[FILE_INPUT](../event-table.md#file-input) イベントです。

## <a name="path"></a><a name="path"></a> Path

```cpp
const wchar_t Path() const;
```

### <a name="return-value"></a>戻り値

入力ファイルへの絶対パス。

## <a name="type"></a><a name="type"></a> の型

```cpp
Type Type() const;
```

### <a name="return-value"></a>戻り値

入力ファイルの種類を表すコード。

::: moniker-end

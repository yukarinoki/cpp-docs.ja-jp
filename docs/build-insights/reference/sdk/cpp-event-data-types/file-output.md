---
title: FileOutput クラス
description: C++ Build Insights SDK の FileOutput クラスのリファレンス。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- FileOutput
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 65e23715d8ac47a8653215e8bd3ee7a43bbe80a3
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/29/2020
ms.locfileid: "92923246"
---
# <a name="fileoutput-class"></a>FileOutput クラス

::: moniker range="<=msvc-140"

C++ Build Insights SDK は、Visual Studio 2017 以降と互換性があります。 これらのバージョンのドキュメントを表示するには、この記事の Visual Studio **Version** セレクター コントロールを Visual Studio 2017 または Visual Studio 2019 に設定します。 このページの目次の一番上にあります。

::: moniker-end
::: moniker range=">=msvc-150"

`FileOutput` クラスは、[MatchEvent](../functions/match-event.md)、[MatchEventInMemberFunction](../functions/match-event-in-member-function.md)、[MatchEventStack](../functions/match-event-stack.md)、および [MatchEventStackInMemberFunction](../functions/match-event-stack-in-member-function.md) 関数と共に使用されます。 [EXECUTABLE_IMAGE_OUTPUT](../event-table.md#executable-image-output)、[EXP_OUTPUT](../event-table.md#exp-output)、[IMP_LIB_OUTPUT](../event-table.md#imp-lib-output)、[LIB_OUTPUT](../event-table.md#lib-output)、または [OBJ_OUTPUT](../event-table.md#obj-output) イベントを照合するために使用します。

## <a name="syntax"></a>構文

```cpp
class FileOutput : public SimpleEvent
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

    FileOutput(const RawEvent& event);

    const wchar_t* Path() const;
    Type           Type() const;
};
```

## <a name="members"></a>メンバー

その基底クラス [SimpleEvent](simple-event.md) から継承されたメンバーに加えて、`FileOutput` クラスには以下のメンバーが含まれます。

### <a name="constructors"></a>コンストラクター

[FileOutput](#file-output)

### <a name="functions"></a>機能

[Path](#path)
[Type](#type)

## <a name="fileoutput"></a><a name="file-output"></a> FileOutput

```cpp
FileOutput(const RawEvent& event);
```

### <a name="parameters"></a>パラメーター

*event*\
[EXECUTABLE_IMAGE_OUTPUT](../event-table.md#executable-image-output)、[EXP_OUTPUT](../event-table.md#exp-output)、[IMP_LIB_OUTPUT](../event-table.md#imp-lib-output)、[LIB_OUTPUT](../event-table.md#lib-output)、または [OBJ_OUTPUT](../event-table.md#obj-output) イベント。

## <a name="path"></a><a name="path"></a> Path

```cpp
const wchar_t Path() const;
```

### <a name="return-value"></a>戻り値

出力ファイルへの絶対パス。

## <a name="type"></a><a name="type"></a> の型

```cpp
Type Type() const;
```

### <a name="return-value"></a>戻り値

出力ファイルの種類を表すコード。

::: moniker-end

---
title: ファイル入力クラス
description: C++ ビルド インサイト SDK ファイル入力クラスリファレンス。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- FileInput
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 642236d3e67465ed38508cb24c8cd698ae880065
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81324793"
---
# <a name="fileinput-class"></a>ファイル入力クラス

::: moniker range="<=vs-2015"

C++ ビルド インサイト SDK は、Visual Studio 2017 以降と互換性があります。 これらのバージョンのドキュメントを参照するには、この記事の Visual Studio**バージョン**セレクター コントロールを Visual Studio 2017 または Visual Studio 2019 に設定します。 このページの目次の上部に表示されます。

::: moniker-end
::: moniker range=">=vs-2017"

クラス`FileInput`[は、](../functions/match-event-in-member-function.md)[関数](../functions/match-event.md)で使用されます。 [MatchEventStack](../functions/match-event-stack.md) [MatchEventStackInMemberFunction](../functions/match-event-stack-in-member-function.md) [FILE_INPUT](../event-table.md#file-input)イベントに一致させるために使用します。

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

[クラスには、SimpleEvent](simple-event.md)基本クラスから継承されたメンバーと`FileInput`共に、次のメンバーが含まれます。

### <a name="constructors"></a>コンストラクター

[ファイル入力](#file-input)

### <a name="functions"></a>関数

[パス](#path)
[の種類](#type)

## <a name="fileinput"></a><a name="file-input"></a>ファイル入力

```cpp
FileInput(const RawEvent& event);
```

### <a name="parameters"></a>パラメーター

*イベント*\
[FILE_INPUT](../event-table.md#file-input)イベント。

## <a name="path"></a><a name="path"></a>パス

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

入力ファイルの種類を記述するコード。

::: moniker-end

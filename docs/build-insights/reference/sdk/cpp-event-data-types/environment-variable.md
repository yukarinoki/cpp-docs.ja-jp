---
title: 環境変数クラス
description: C++ ビルド インサイト SDK 環境変数クラスリファレンス。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- EnvironmentVariable
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 963c52e0ea9e048448c6f2b3ac62d9938817467e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81325017"
---
# <a name="environmentvariable-class"></a>環境変数クラス

::: moniker range="<=vs-2015"

C++ ビルド インサイト SDK は、Visual Studio 2017 以降と互換性があります。 これらのバージョンのドキュメントを参照するには、この記事の Visual Studio**バージョン**セレクター コントロールを Visual Studio 2017 または Visual Studio 2019 に設定します。 このページの目次の上部に表示されます。

::: moniker-end
::: moniker range=">=vs-2017"

クラス`EnvironmentVariable`[は、](../functions/match-event-in-member-function.md)[関数](../functions/match-event.md)で使用されます。 [MatchEventStack](../functions/match-event-stack.md) [MatchEventStackInMemberFunction](../functions/match-event-stack-in-member-function.md) [ENVIRONMENT_VARIABLE](../event-table.md#environment-variable)イベントと一致させるために使用します。

## <a name="syntax"></a>構文

```cpp
class EnvironmentVariable : public SimpleEvent
{
public:
    EnvironmentVariable(const RawEvent& event);

    const wchar_t* Name() const;
    const wchar_t* Value() const;
};
```

## <a name="members"></a>メンバー

[クラスには、SimpleEvent](simple-event.md)基本クラスから継承されたメンバーと`EnvironmentVariable`共に、次のメンバーが含まれます。

### <a name="constructors"></a>コンストラクター

[EnvironmentVariable](#environment-variable)

### <a name="functions"></a>関数

[名前の](#name)
[値](#value)

## <a name="environmentvariable"></a><a name="environment-variable"></a>環境変数

```cpp
EnvironmentVariable(const RawEvent& event);
```

### <a name="parameters"></a>パラメーター

*イベント*\
[ENVIRONMENT_VARIABLE](../event-table.md#environment-variable)イベント。

## <a name="name"></a><a name="name"></a>名前

```cpp
const wchar_t Name() const;
```

### <a name="return-value"></a>戻り値

環境変数の名前。

## <a name="value"></a><a name="value"></a> の値

```cpp
const wchar_t Value() const;
```

### <a name="return-value"></a>戻り値

環境変数の値。

::: moniker-end

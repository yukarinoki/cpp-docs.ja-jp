---
title: フォースインリネクラス
description: C++ ビルド インサイト SDK ForceInlinee クラス リファレンス。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- ForceInlinee
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: c6a1af0384197a0a3b6062ad9ef30537c348190d
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81324780"
---
# <a name="forceinlinee-class"></a>フォースインリネクラス

::: moniker range="<=vs-2015"

C++ ビルド インサイト SDK は、Visual Studio 2017 以降と互換性があります。 これらのバージョンのドキュメントを参照するには、この記事の Visual Studio**バージョン**セレクター コントロールを Visual Studio 2017 または Visual Studio 2019 に設定します。 このページの目次の上部に表示されます。

::: moniker-end
::: moniker range=">=vs-2017"

クラス`ForceInlinee`[は、](../functions/match-event-in-member-function.md)[関数](../functions/match-event.md)で使用されます。 [MatchEventStack](../functions/match-event-stack.md) [MatchEventStackInMemberFunction](../functions/match-event-stack-in-member-function.md) [FORCE_INLINEE](../event-table.md#force-inlinee)イベントに一致させるために使用します。

## <a name="syntax"></a>構文

```cpp
class ForceInlinee : public SimpleEvent
{
public:
    ForceInlinee(const RawEvent& event);

    const char*             Name() const;
    const unsigned short&   Size() const;
};
```

## <a name="members"></a>メンバー

[クラスには、SimpleEvent](simple-event.md)基本クラスから継承されたメンバーと`ForceInlinee`共に、次のメンバーが含まれます。

### <a name="constructors"></a>コンストラクター

[フォースインリネ](#force-inlinee)

### <a name="functions"></a>関数

[名前の](#name)
[サイズ](#size)

## <a name="forceinlinee"></a><a name="force-inlinee"></a>フォースインリネ

```cpp
ForceInlinee(const RawEvent& event);
```

### <a name="parameters"></a>パラメーター

*イベント*\
[FORCE_INLINEE](../event-table.md#force-inlinee)イベント。

## <a name="name"></a><a name="name"></a>名前

```cpp
const char* Name() const;
```

### <a name="return-value"></a>戻り値

強制インライン化関数の名前で、UTF-8 でエンコードされます。

## <a name="size"></a><a name="size"></a> サイズ

```cpp
const unsigned short& Size() const;
```

### <a name="return-value"></a>戻り値

強制インライン化関数のサイズを中間命令数として指定します。

::: moniker-end

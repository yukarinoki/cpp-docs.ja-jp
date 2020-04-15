---
title: 関数クラス
description: C++ ビルド インサイト SDK 関数クラスリファレンス。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- Function
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 69acbe4d6630de37120aec89a24a9f33d447009e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81324720"
---
# <a name="function-class"></a>関数クラス

::: moniker range="<=vs-2015"

C++ ビルド インサイト SDK は、Visual Studio 2017 以降と互換性があります。 これらのバージョンのドキュメントを参照するには、この記事の Visual Studio**バージョン**セレクター コントロールを Visual Studio 2017 または Visual Studio 2019 に設定します。 このページの目次の上部に表示されます。

::: moniker-end
::: moniker range=">=vs-2017"

クラス`Function`[は、](../functions/match-event-in-member-function.md)[関数](../functions/match-event.md)で使用されます。 [MatchEventStack](../functions/match-event-stack.md) [MatchEventStackInMemberFunction](../functions/match-event-stack-in-member-function.md) この関数は[、FUNCTION](../event-table.md#function)イベントと一致させるために使用します。

## <a name="syntax"></a>構文

```cpp
class Function : public Activity
{
public:
    Function(const RawEvent& event);

    const char* Name() const;
};
```

## <a name="members"></a>メンバー

クラスには、[その Activity](activity.md)基本クラスから継承された`Function`メンバーと共に、次のメンバーが含まれます。

### <a name="constructors"></a>コンストラクター

[関数](#function)

### <a name="functions"></a>関数

[名前](#name)

## <a name="function"></a><a name="function"></a>関数

```cpp
Function(const RawEvent& event);
```

### <a name="parameters"></a>パラメーター

*イベント*\
[関数](../event-table.md#function)イベント。

## <a name="name"></a><a name="name"></a>名前

```cpp
const char* Name() const;
```

### <a name="return-value"></a>戻り値

UTF-8 でエンコードされた関数の名前。

::: moniker-end

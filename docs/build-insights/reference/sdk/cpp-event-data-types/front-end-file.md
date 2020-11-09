---
title: FrontEndFile クラス
description: C++ Build Insights SDK の FrontEndFile クラスのリファレンスです。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- FrontEndFile
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 7715a153df538eab94b8de5281a91d4f6b439ff9
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/29/2020
ms.locfileid: "92920659"
---
# <a name="frontendfile-class"></a>FrontEndFile クラス

::: moniker range="<=msvc-140"

C++ Build Insights SDK は、Visual Studio 2017 以降と互換性があります。 これらのバージョンのドキュメントを表示するには、この記事の Visual Studio **Version** セレクター コントロールを Visual Studio 2017 または Visual Studio 2019 に設定します。 このページの目次の一番上にあります。

::: moniker-end
::: moniker range=">=msvc-150"

`FrontEndFile` クラスは、[MatchEvent](../functions/match-event.md)、[MatchEventInMemberFunction](../functions/match-event-in-member-function.md)、[MatchEventStack](../functions/match-event-stack.md)、および [MatchEventStackInMemberFunction](../functions/match-event-stack-in-member-function.md) 関数と共に使用されます。 [FRONT_END_FILE](../event-table.md#front-end-file) イベントを照合するために使用します。

## <a name="syntax"></a>構文

```cpp
class FrontEndFile : public Activity
{
public:
    FrontEndFile(const RawEvent& event);

    const char* Path() const;
};
```

## <a name="members"></a>メンバー

その基底クラス [Activity](activity.md) から継承されたメンバーに加えて、`FrontEndFile` クラスには以下のメンバーが含まれます。

### <a name="constructors"></a>コンストラクター

[FrontEndFile](#front-end-file)

### <a name="functions"></a>機能

[パス](#path)

## <a name="frontendfile"></a><a name="front-end-file"></a> FrontEndFile

```cpp
FrontEndFile(const RawEvent& event);
```

### <a name="parameters"></a>パラメーター

*event*\
[FRONT_END_FILE](../event-table.md#front-end-file) イベント。

## <a name="path"></a><a name="path"></a> Path

```cpp
const char* Path() const;
```

### <a name="return-value"></a>戻り値

ファイルへの絶対パス。UTF-8 でエンコードされます。

::: moniker-end

---
title: クラス
description: C++ ビルド インサイト SDK フロントエンドファイル クラスリファレンス。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- FrontEndFile
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: c40137724279ea2fd615729db39f0ac5c907b79e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81324756"
---
# <a name="frontendfile-class"></a>クラス

::: moniker range="<=vs-2015"

C++ ビルド インサイト SDK は、Visual Studio 2017 以降と互換性があります。 これらのバージョンのドキュメントを参照するには、この記事の Visual Studio**バージョン**セレクター コントロールを Visual Studio 2017 または Visual Studio 2019 に設定します。 このページの目次の上部に表示されます。

::: moniker-end
::: moniker range=">=vs-2017"

クラス`FrontEndFile`[は、](../functions/match-event-in-member-function.md)[関数](../functions/match-event.md)で使用されます。 [MatchEventStack](../functions/match-event-stack.md) [MatchEventStackInMemberFunction](../functions/match-event-stack-in-member-function.md) [FRONT_END_FILE](../event-table.md#front-end-file)イベントに一致させるために使用します。

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

クラスには、[その Activity](activity.md)基本クラスから継承された`FrontEndFile`メンバーと共に、次のメンバーが含まれます。

### <a name="constructors"></a>コンストラクター

[フロントエンドファイル](#front-end-file)

### <a name="functions"></a>関数

[パス](#path)

## <a name="frontendfile"></a><a name="front-end-file"></a>フロントエンドファイル

```cpp
FrontEndFile(const RawEvent& event);
```

### <a name="parameters"></a>パラメーター

*イベント*\
[FRONT_END_FILE](../event-table.md#front-end-file)イベント。

## <a name="path"></a><a name="path"></a>パス

```cpp
const char* Path() const;
```

### <a name="return-value"></a>戻り値

ファイルへの絶対パスを UTF-8 でエンコードします。

::: moniker-end

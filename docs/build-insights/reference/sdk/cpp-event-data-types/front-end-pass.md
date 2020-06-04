---
title: フロントエンドパスクラス
description: C++ ビルド インサイト SDK フロントエンドパス クラスリファレンス。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- FrontEndPass
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 137f553f1e495b7658ae89e69a48cec6b1988a81
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81324726"
---
# <a name="frontendpass-class"></a>フロントエンドパスクラス

::: moniker range="<=vs-2015"

C++ ビルド インサイト SDK は、Visual Studio 2017 以降と互換性があります。 これらのバージョンのドキュメントを参照するには、この記事の Visual Studio**バージョン**セレクター コントロールを Visual Studio 2017 または Visual Studio 2019 に設定します。 このページの目次の上部に表示されます。

::: moniker-end
::: moniker range=">=vs-2017"

クラス`FrontEndPass`[は、](../functions/match-event-in-member-function.md)[関数](../functions/match-event.md)で使用されます。 [MatchEventStack](../functions/match-event-stack.md) [MatchEventStackInMemberFunction](../functions/match-event-stack-in-member-function.md) [FRONT_END_PASS](../event-table.md#front-end-pass)イベントに一致させるために使用します。

## <a name="syntax"></a>構文

```cpp
class FrontEndPass : public CompilerPass
{
public:
    FrontEndPass(const RawEvent& event);
};
```

## <a name="members"></a>メンバー

クラスには、継承されたメンバーが[CompilerPass](compiler-pass.md)基本クラス`FrontEndPass`から継承されたメンバーと共に、次のメンバーが含まれます。

### <a name="constructors"></a>コンストラクター

[フロントエンドパス](#front-end-pass)

## <a name="frontendpass"></a><a name="front-end-pass"></a>フロントエンドパス

```cpp
FrontEndPass(const RawEvent& event);
```

### <a name="parameters"></a>パラメーター

*イベント*\
[FRONT_END_PASS](../event-table.md#front-end-pass)イベント。

::: moniker-end

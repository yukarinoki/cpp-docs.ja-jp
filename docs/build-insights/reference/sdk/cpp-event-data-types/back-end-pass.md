---
title: バックエンドパスクラス
description: C++ ビルド インサイト SDK バックエンドパス クラスリファレンス。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- BackEndPass
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 2b4b1a219abdbe418efaab4537f1c6dc9a22afb3
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81325234"
---
# <a name="backendpass-class"></a>バックエンドパスクラス

::: moniker range="<=vs-2015"

C++ ビルド インサイト SDK は、Visual Studio 2017 以降と互換性があります。 これらのバージョンのドキュメントを参照するには、この記事の Visual Studio**バージョン**セレクター コントロールを Visual Studio 2017 または Visual Studio 2019 に設定します。 このページの目次の上部に表示されます。

::: moniker-end
::: moniker range=">=vs-2017"

クラス`BackEndPass`[は、](../functions/match-event-in-member-function.md)[関数](../functions/match-event.md)で使用されます。 [MatchEventStack](../functions/match-event-stack.md) [MatchEventStackInMemberFunction](../functions/match-event-stack-in-member-function.md) [BACK_END_PASS](../event-table.md#back-end-pass)イベントに一致させるために使用します。

## <a name="syntax"></a>構文

```cpp
class BackEndPass : public CompilerPass
{
public:
    BackEndPass(const RawEvent& event);
};
```

## <a name="members"></a>メンバー

クラスには、継承されたメンバーが[CompilerPass](compiler-pass.md)基本クラス`BackEndPass`から継承されたメンバーと共に、次のメンバーが含まれます。

### <a name="constructors"></a>コンストラクター

[バックエンドパス](#back-end-pass)

## <a name="backendpass"></a><a name="back-end-pass"></a>バックエンドパス

```cpp
BackEndPass(const RawEvent& event);
```

### <a name="parameters"></a>パラメーター

*イベント*\
[BACK_END_PASS](../event-table.md#back-end-pass)イベント。

::: moniker-end

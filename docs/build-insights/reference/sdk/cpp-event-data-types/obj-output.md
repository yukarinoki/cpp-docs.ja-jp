---
title: クラスを出力します。
description: C++ ビルド インサイト SDK ObjOutput クラスリファレンス。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- ObjOutput
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 194253e8995401114e2529b868b36c9823510a4f
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81324490"
---
# <a name="objoutput-class"></a>クラスを出力します。

::: moniker range="<=vs-2015"

C++ ビルド インサイト SDK は、Visual Studio 2017 以降と互換性があります。 これらのバージョンのドキュメントを参照するには、この記事の Visual Studio**バージョン**セレクター コントロールを Visual Studio 2017 または Visual Studio 2019 に設定します。 このページの目次の上部に表示されます。

::: moniker-end
::: moniker range=">=vs-2017"

クラス`ObjOutput`[は、](../functions/match-event-in-member-function.md)[関数](../functions/match-event.md)で使用されます。 [MatchEventStack](../functions/match-event-stack.md) [MatchEventStackInMemberFunction](../functions/match-event-stack-in-member-function.md) [OBJ_OUTPUT](../event-table.md#obj-output)イベントに一致させるために使用します。

## <a name="syntax"></a>構文

```cpp
class ObjOutput : public FileOutput
{
public:
    ObjOutput(const RawEvent& event);
};
```

## <a name="members"></a>メンバー

クラスには、[その FileOutput](file-output.md)基本クラスから継承された`ObjOutput`メンバーと共に、次のメンバーが含まれます。

### <a name="constructors"></a>コンストラクター

[出力](#obj-output)

## <a name="objoutput"></a><a name="obj-output"></a>出力

```cpp
ObjOutput(const RawEvent& event);
```

### <a name="parameters"></a>パラメーター

*イベント*\
[OBJ_OUTPUT](../event-table.md#obj-output)イベント。

::: moniker-end

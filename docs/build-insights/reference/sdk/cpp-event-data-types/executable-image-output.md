---
title: クラスをイメージします。
description: クラスリファレンスを構築します。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- ExecutableImageOutput
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 834689a3605b729260f2d4c925396ee1af1bb705
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81324955"
---
# <a name="executableimageoutput-class"></a>クラスをイメージします。

::: moniker range="<=vs-2015"

C++ ビルド インサイト SDK は、Visual Studio 2017 以降と互換性があります。 これらのバージョンのドキュメントを参照するには、この記事の Visual Studio**バージョン**セレクター コントロールを Visual Studio 2017 または Visual Studio 2019 に設定します。 このページの目次の上部に表示されます。

::: moniker-end
::: moniker range=">=vs-2017"

クラス`ExecutableImageOutput`[は、](../functions/match-event-in-member-function.md)[関数](../functions/match-event.md)で使用されます。 [MatchEventStack](../functions/match-event-stack.md) [MatchEventStackInMemberFunction](../functions/match-event-stack-in-member-function.md) [EXECUTABLE_IMAGE_OUTPUT](../event-table.md#executable-image-output)イベントに一致させるために使用します。

## <a name="syntax"></a>構文

```cpp
class ExecutableImageOutput : public FileOutput
{
public:
    ExecutableImageOutput(const RawEvent& event);
};
```

## <a name="members"></a>メンバー

クラスには、[その FileOutput](file-output.md)基本クラスから継承された`ExecutableImageOutput`メンバーと共に、次のメンバーが含まれます。

### <a name="constructors"></a>コンストラクター

[イメージ出力](#executable-image-output)

## <a name="executableimageoutput"></a><a name="executable-image-output"></a>イメージ出力

```cpp
ExecutableImageOutput(const RawEvent& event);
```

### <a name="parameters"></a>パラメーター

*イベント*\
[EXECUTABLE_IMAGE_OUTPUT](../event-table.md#executable-image-output)イベント。

::: moniker-end

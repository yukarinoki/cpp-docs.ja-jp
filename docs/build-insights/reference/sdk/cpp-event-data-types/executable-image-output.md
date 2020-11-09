---
title: ExecutableImageOutput クラス
description: C++ Build Insights SDK の ExecutableImageOutput クラスのリファレンス。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- ExecutableImageOutput
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: bf6bb9790dabc39d1ed6baa417d5dc3bf72ed5e6
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/29/2020
ms.locfileid: "92920724"
---
# <a name="executableimageoutput-class"></a>ExecutableImageOutput クラス

::: moniker range="<=msvc-140"

C++ Build Insights SDK は、Visual Studio 2017 以降と互換性があります。 これらのバージョンのドキュメントを表示するには、この記事の Visual Studio **Version** セレクター コントロールを Visual Studio 2017 または Visual Studio 2019 に設定します。 このページの目次の一番上にあります。

::: moniker-end
::: moniker range=">=msvc-150"

`ExecutableImageOutput` クラスは、[MatchEvent](../functions/match-event.md)、[MatchEventInMemberFunction](../functions/match-event-in-member-function.md)、[MatchEventStack](../functions/match-event-stack.md)、および [MatchEventStackInMemberFunction](../functions/match-event-stack-in-member-function.md) 関数と共に使用されます。 [EXECUTABLE_IMAGE_OUTPUT](../event-table.md#executable-image-output) イベントを照合するために使用します。

## <a name="syntax"></a>構文

```cpp
class ExecutableImageOutput : public FileOutput
{
public:
    ExecutableImageOutput(const RawEvent& event);
};
```

## <a name="members"></a>メンバー

その基底クラス [FileOutput](file-output.md) から継承されたメンバーに加えて、`ExecutableImageOutput` クラスには以下のメンバーが含まれます。

### <a name="constructors"></a>コンストラクター

[ExecutableImageOutput](#executable-image-output)

## <a name="executableimageoutput"></a><a name="executable-image-output"></a> ExecutableImageOutput

```cpp
ExecutableImageOutput(const RawEvent& event);
```

### <a name="parameters"></a>パラメーター

*event*\
[EXECUTABLE_IMAGE_OUTPUT](../event-table.md#executable-image-output) イベント。

::: moniker-end

---
title: RelogW
description: C++ Build Insights SDK の RelogW 関数のリファレンス。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- RelogW
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: e01cf7ca769c60761999ca320a7f9a65b41a8ed6
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/29/2020
ms.locfileid: "92920061"
---
# <a name="relogw"></a>RelogW

::: moniker range="<=msvc-140"

C++ Build Insights SDK は、Visual Studio 2017 以降と互換性があります。 これらのバージョンのドキュメントを表示するには、この記事の Visual Studio **Version** セレクター コントロールを Visual Studio 2017 または Visual Studio 2019 に設定します。 このページの目次の一番上にあります。

::: moniker-end
::: moniker range=">=msvc-150"

`RelogW` 関数は、入力 Event Tracing for Windows (ETW) トレースから MSVC イベントを読み取り、それを新しい変更された ETW トレースに書き込むために使用されます。

## <a name="syntax"></a>構文

```cpp
enum RESULT_CODE RelogW(
    const wchar_t*          inputLogFile,
    const wchar_t*          outputLogFile,
    const RELOG_DESCRIPTOR* relogDescriptor);
```

### <a name="parameters"></a>パラメーター

*inputLogFile*\
イベントの読み取り元の入力 ETW トレース。

*outputLogFile*\
新しいイベントを書き込むファイル。

*relogDescriptor*\
[RELOG_DESCRIPTOR](../other-types/relog-descriptor-struct.md) オブジェクトへのポインター。 再ログ記録セッションを構成するには、このオブジェクトを使用します。

### <a name="return-value"></a>戻り値

[RESULT_CODE](../other-types/result-code-enum.md) 列挙型の結果コード。

::: moniker-end

---
title: 分析W
description: C++ ビルド インサイト SDK 分析関数リファレンス。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- AnalyzeW
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 64d68e4c10c0b77c3e6b08b1ec23735e38a377a1
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81324155"
---
# <a name="analyzew"></a>分析W

::: moniker range="<=vs-2015"

C++ ビルド インサイト SDK は、Visual Studio 2017 以降と互換性があります。 これらのバージョンのドキュメントを参照するには、この記事の Visual Studio**バージョン**セレクター コントロールを Visual Studio 2017 または Visual Studio 2019 に設定します。 このページの目次の上部に表示されます。

::: moniker-end
::: moniker range=">=vs-2017"

この`AnalyzeW`関数は、Windows (ETW) トレースの入力イベント・トレースから読み取られた MSVC イベントを分析するために使用されます。

## <a name="syntax"></a>構文

```cpp
enum RESULT_CODE AnalyzeW(
    const wchar_t*             inputLogFile,
    const ANALYSIS_DESCRIPTOR* analysisDescriptor);
```

### <a name="parameters"></a>パラメーター

*入力ログファイル*\
イベントの読み取りを行う入力 ETW トレース。

*分析記述子*\
[ANALYSIS_DESCRIPTOR](../other-types/analysis-descriptor-struct.md)オブジェクトへのポインター。 このオブジェクトを使用して、分析を構成します。

### <a name="return-value"></a>戻り値

[RESULT_CODE](../other-types/result-code-enum.md)列挙型からの結果コード。

::: moniker-end

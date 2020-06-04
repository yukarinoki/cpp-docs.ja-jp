---
title: 分析A
description: C++ ビルド インサイト SDK 分析関数リファレンス。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- AnalyzeA
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 7c7602c49ab5f3ce67693424019e253727563293
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81324143"
---
# <a name="analyzea"></a>分析A

::: moniker range="<=vs-2015"

C++ ビルド インサイト SDK は、Visual Studio 2017 以降と互換性があります。 これらのバージョンのドキュメントを参照するには、この記事の Visual Studio**バージョン**セレクター コントロールを Visual Studio 2017 または Visual Studio 2019 に設定します。 このページの目次の上部に表示されます。

::: moniker-end
::: moniker range=">=vs-2017"

この`AnalyzeA`関数は、Windows (ETW) トレースの入力イベント・トレースから読み取られた MSVC イベントを分析するために使用されます。

## <a name="syntax"></a>構文

```cpp
enum RESULT_CODE AnalyzeA(
    const char*                inputLogFile,
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

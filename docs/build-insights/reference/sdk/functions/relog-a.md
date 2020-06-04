---
title: リロガ
description: C++ ビルド インサイト SDK RelogA 関数リファレンス。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- RelogA
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 5a772b1156fc69eeef39514afe401c549c3b7c38
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81323843"
---
# <a name="reloga"></a>リロガ

::: moniker range="<=vs-2015"

C++ ビルド インサイト SDK は、Visual Studio 2017 以降と互換性があります。 これらのバージョンのドキュメントを参照するには、この記事の Visual Studio**バージョン**セレクター コントロールを Visual Studio 2017 または Visual Studio 2019 に設定します。 このページの目次の上部に表示されます。

::: moniker-end
::: moniker range=">=vs-2017"

この`RelogA`関数は、Windows イベント・トレース (ETW) トレースから MSVC イベントを読み取り、新しい変更された ETW トレースに書き込むために使用されます。

## <a name="syntax"></a>構文

```cpp
enum RESULT_CODE RelogA(
    const char*             inputLogFile,
    const char*             outputLogFile,
    const RELOG_DESCRIPTOR* relogDescriptor);
```

### <a name="parameters"></a>パラメーター

*入力ログファイル*\
イベントの読み取りを行う入力 ETW トレース。

*出力ログファイル*\
新しいイベントを書き込むファイル。

*記述子を再ログします。*\
[RELOG_DESCRIPTOR](../other-types/relog-descriptor-struct.md)オブジェクトへのポインター。 このオブジェクトは、再ロギング セッションを構成するために使用します。

### <a name="return-value"></a>戻り値

[RESULT_CODE](../other-types/result-code-enum.md)列挙型からの結果コード。

::: moniker-end

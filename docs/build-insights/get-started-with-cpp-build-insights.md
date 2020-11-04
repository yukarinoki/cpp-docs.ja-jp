---
title: C++ Build Insights を使ってみる
description: C++ Build Insights ツールの概要。
ms.date: 11/03/2019
helpviewer_keywords:
- C++ Build Insights
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: c4ebbb280a5cccaa35b5efc7f90e9b570600c47b
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/29/2020
ms.locfileid: "92923629"
---
# <a name="get-started-with-c-build-insights"></a>C++ Build Insights を使ってみる

::: moniker range="<=msvc-150"

C++ Build Insights ツールは、Visual Studio 2019 で使用できます。 このバージョンのドキュメントを表示するには、この記事の Visual Studio の **[バージョン]** セレクター コントロールを Visual Studio 2019 に設定してください。 このページの目次の一番上にあります。

::: moniker-end
::: moniker range="msvc-160"

C++ Build Insights は、Microsoft Visual C++ (MSVC) ツール チェーンの可視性を向上させるツールのコレクションです。 これらのツールを使用すると、C++ ビルドに関するデータが収集され、次のような一般的な質問の答えを確認できます。

- ビルドは十分に並列化されていますか。
- プリコンパイル済みヘッダー (PCH) には何を含める必要がありますか。
- ビルドの速度を向上させるために、特に注目する必要のあるボトルネックはありますか。

このテクノロジの主要なコンポーネントは次のとおりです。

- ビルドのトレースを収集するために使用できるコマンドライン ユーティリティである *vcperf.exe* 、
- Windows パフォーマンス アナライザー (WPA) でビルド トレースを表示できる WPA 拡張機能、および
- C++ Build Insights データを使用する独自のツールを作成するためのソフトウェア開発キットである C++ Build Insights SDK。

## <a name="documentation-sections"></a>ドキュメントのセクション

[チュートリアル: vcperf および Windows パフォーマンス アナライザー](tutorials/vcperf-and-wpa.md)\
C++ プロジェクトのビルド トレースを収集する方法と、WPA でそれらを表示する方法について説明します。

[チュートリアル: Windows パフォーマンスの基本](tutorials/wpa-basics.md)\
ビルド トレースの分析に役立つ WPA のヒントが掲載されています。

[C++ Build Insights SDK](reference/sdk/overview.md)\
C++ Build Insights SDK の概要。

## <a name="articles"></a>記事

C++ Build Insights の詳細については、C++ チームの公式ブログから次の記事を参照してください。

[C++ Build Insights の概要](https://devblogs.microsoft.com/cppblog/introducing-c-build-insights/)

[C++ Build Insights SDK を使用してプログラムでビルドを分析する](https://devblogs.microsoft.com/cppblog/analyze-your-builds-programmatically-with-the-c-build-insights-sdk/)

[C++ Build Insights を使用してビルドのボトルネックを見つける](https://devblogs.microsoft.com/cppblog/finding-build-bottlenecks-with-cpp-build-insights/)

[C++ Build Insights からの PCH の提案を使用してビルドを高速化する](https://devblogs.microsoft.com/cppblog/faster-builds-with-pch-suggestions-from-c-build-insights/)

::: moniker-end

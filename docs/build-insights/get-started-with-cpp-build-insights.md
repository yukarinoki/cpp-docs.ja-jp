---
title: C++ Build Insights を使ってみる
description: C++ ビルド インサイトの概要。
ms.date: 11/03/2019
helpviewer_keywords:
- C++ Build Insights
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 3a75dfe3bf1263cce53d70b764607cad4eec86d5
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81325716"
---
# <a name="get-started-with-c-build-insights"></a>C++ Build Insights を使ってみる

::: moniker range="<=vs-2017"

C++ ビルドインサイト ツールは、Visual Studio 2019 で使用できます。 そのバージョンのドキュメントを参照するには、この記事の Visual Studio**バージョン**セレクター コントロールを Visual Studio 2019 に設定します。 このページの目次の上部に表示されます。

::: moniker-end
::: moniker range="vs-2019"

C++ ビルド インサイトは、Microsoft Visual C++ (MSVC) ツール チェーンの可視性を向上させるツールのコレクションです。 これらのツールは、C++ ビルドに関するデータを収集し、次のような一般的な質問に答える際に役立つ形式で表示します。

- ビルドは十分に並列化されていますか?
- プリコンパイル済みヘッダー (PCH) には何を含める必要がありますか?
- ビルド速度を上げるために、特定のボトルネックに重点を置く必要がありますか。

この技術の主なコンポーネントは次のとおりです。

- *vcperf.exe*は、ビルドのトレースを収集するために使用できるコマンド ライン ユーティリティです。
- WPA でビルド トレースを表示できる Windows パフォーマンス アナライザ (WPA) 拡張機能
- C++ ビルド インサイト SDK は、C++ ビルド インサイト データを使用する独自のツールを作成するためのソフトウェア開発キットです。

次のリンクをクリックすると、これらのコンポーネントをすぐに使用できます。

[チュートリアル: vcperf と Windows パフォーマンス アナライザ](tutorials/vcperf-and-wpa.md)\
C++ プロジェクトのビルド トレースを収集する方法と、WPA で表示する方法について説明します。

[チュートリアル: Windows パフォーマンスの基本](tutorials/wpa-basics.md)\
ビルド トレースを分析するための便利な WPA ヒントをご覧ください。

[C++ ビルド インサイト SDK](reference/sdk/overview.md)\
C++ ビルド インサイト SDK の概要。

::: moniker-end

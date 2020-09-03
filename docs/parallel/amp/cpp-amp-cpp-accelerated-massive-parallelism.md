---
title: C++ AMP (C++ Accelerated Massive Parallelism)
ms.date: 11/04/2016
helpviewer_keywords:
- C++ AMP (see C++ Accelerated Massive Parallelism)
- C++ Accelerated Massive Parallelism, getting started
ms.assetid: e27824cb-3167-409b-8c3f-a0e476d8f349
ms.openlocfilehash: 243c476b6536278eb09b26b24becb65276d6e48a
ms.sourcegitcommit: 093f49b8b69daf86661adc125b1d2d7b1f0e0650
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/03/2020
ms.locfileid: "89427635"
---
# <a name="c-amp-c-accelerated-massive-parallelism"></a>C++ AMP (C++ Accelerated Massive Parallelism)

C++ AMP (C++ Accelerated Massive Parallelism) は、独立したグラフィックス カードの GPU (graphics processing unit) などの一般的なデータ並列ハードウェアを活用して、C++ コードの実行を高速化します。 C++ AMP のプログラミング モデルには、多次元配列、インデックス作成、メモリ転送、およびタイルのサポートが含まれています。 また、数学関数ライブラリも含まれています。 C++ AMP の言語拡張機能を使用して、データを CPU から GPU へ、また GPU から CPU へどのように移動するかを制御できます。

## <a name="related-topics"></a>関連トピック

|Title|説明|
|-----------|-----------------|
|[C++ AMP の概要](../../parallel/amp/cpp-amp-overview.md)|C++ AMP および数値演算ライブラリの主な機能について説明します。|
|[ラムダ、関数オブジェクト、および制限関数の使用](../../parallel/amp/using-lambdas-function-objects-and-restricted-functions.md)|[Parallel_for_each](reference/concurrency-namespace-functions-amp.md#parallel_for_each)メソッドの呼び出しでラムダ式、関数オブジェクト、および制限された関数を使用する方法について説明します。|
|[タイルの使用](../../parallel/amp/using-tiles.md)|タイルを使用して C++ AMP コードを高速化する方法について説明します。|
|[Accelerator オブジェクトと accelerator_view オブジェクトの使用](../../parallel/amp/using-accelerator-and-accelerator-view-objects.md)|アクセラレータを使用して GPU でのコードの実行をカスタマイズする方法について説明します。|
|[UWP アプリでの C++ AMP の使用](../../parallel/amp/using-cpp-amp-in-windows-store-apps.md)|Windows ランタイムの種類を使用するユニバーサル Windows プラットフォーム (UWP) アプリで C++ AMP を使用する方法について説明します。|
|[グラフィックス (C++ AMP)](../../parallel/amp/graphics-cpp-amp.md)|C++ AMP のグラフィックス ライブラリを使用する方法について説明します。|
|[チュートリアル: 行列乗算](../../parallel/amp/walkthrough-matrix-multiplication.md)|C++ AMP コードとタイルを使用した行列乗算を示します。|
|[チュートリアル: C++ AMP アプリケーションのデバッグ](../../parallel/amp/walkthrough-debugging-a-cpp-amp-application.md)|並列リダクションを使用して整数の大きな配列を合計するアプリケーションを作成してデバッグする方法について説明します。|

## <a name="reference"></a>リファレンス

[リファレンス (C++ AMP)](../../parallel/amp/reference/reference-cpp-amp.md)<br/>
[tile_static キーワード](../../cpp/tile-static-keyword.md)<br/>
[restrict (C++ AMP)](../../cpp/restrict-cpp-amp.md)

## <a name="other-resources"></a>その他の参照情報

[ネイティブコードでの並列プログラミングに関するブログ](/archive/blogs/nativeconcurrency/)<br/>
[ダウンロード用のサンプルプロジェクトの C++ AMP](/archive/blogs/nativeconcurrency/c-amp-sample-projects-for-download)<br/>
[同時実行ビジュアライザーを使用した C++ AMP コードの分析](/archive/blogs/nativeconcurrency/analyzing-c-amp-code-with-the-concurrency-visualizer)

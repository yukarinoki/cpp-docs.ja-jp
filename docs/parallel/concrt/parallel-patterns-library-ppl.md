---
description: 詳細については、並列パターンライブラリ (PPL) に関するページを参照してください。
title: 並列パターン ライブラリ (PPL)
ms.date: 11/04/2016
helpviewer_keywords:
- Parallel Patterns Library (PPL)
ms.assetid: 40fd86b2-69fa-45e5-93d8-98a75636c242
ms.openlocfilehash: ea5719e8ebaacf8f181678ef7af8aae9c900fbe6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97172350"
---
# <a name="parallel-patterns-library-ppl"></a>並列パターン ライブラリ (PPL)

並列パターン ライブラリ (PPL: Parallel Patterns Library) は、同時実行アプリケーションの開発に不可欠な、スケーラビリティが高く使いやすいプログラミング モデルを提供します。 PPL は、コンカレンシー ランタイムのスケジューリング コンポーネントとリソース管理コンポーネントに基づいています。 PPL には、データを並列的に操作する、タイプ セーフのジェネリックなアルゴリズムとコンテナーが用意されています。これらを使用すると、アプリケーション コードと基になるスレッド処理機構の間で抽象化のレベルを引き上げることができます。 また、PPL には共有状態に代わる手段が用意されているため、規模の変更に対応したアプリケーションの開発にも役立ちます。

PPL には次の機能があります。

- *タスクの並列* 化: Windows ThreadPool 上で動作し、複数の作業項目 (タスク) を並行して実行するメカニズム

- *並列アルゴリズム*: データのコレクションを並列処理するために同時実行ランタイム上で動作する汎用アルゴリズム

- *並列コンテナーとオブジェクト*: 要素への安全な同時アクセスを提供するジェネリックコンテナー型

## <a name="example"></a>例

PPL には、C++ 標準ライブラリに似たプログラミングモデルが用意されています。 次の例では、PPL のさまざまな機能を示します。 複数のフィボナッチの数列を逐次的および並列的に計算します。 どちらの計算も [std:: array](../../standard-library/array-class-stl.md) オブジェクトに対して動作します。 また、それぞれの計算に要する時間もコンソールに出力します。

シリアルバージョンでは、C++ 標準ライブラリの [std:: for_each](../../standard-library/algorithm-functions.md#for_each) アルゴリズムを使用して配列を走査し、結果を [std:: vector](../../standard-library/vector-class.md) オブジェクトに格納します。 並列バージョンは同じタスクを実行しますが、PPL [concurrency::p arallel_for_each](reference/concurrency-namespace-functions.md#parallel_for_each) アルゴリズムを使用して、結果を [concurrency:: concurrent_vector](../../parallel/concrt/reference/concurrent-vector-class.md) オブジェクトに格納します。 `concurrent_vector` クラスを使用することで、コンテナーへの書き込みアクセスを同期しなくても各ループ反復で要素を同時に追加できます。

`parallel_for_each` は同時に処理を行うため、この例の並列バージョンでは、`concurrent_vector` オブジェクトを並べ替え、逐次バージョンと同じ結果を生成する必要があります。

この例では、素朴な方法を使用してフィボナッチの数列を計算しています。ただし、この方法で示しているのは、コンカレンシー ランタイムによって長い計算のパフォーマンスが向上するしくみです。

[!code-cpp[concrt-parallel-fibonacci#1](../../parallel/concrt/codesnippet/cpp/parallel-patterns-library-ppl_1.cpp)]

4 つのプロセッサを備えたコンピューターを使用したときのサンプル出力を次に示します。

```Output
serial time: 9250 ms
parallel time: 5726 ms

fib(24): 46368
fib(26): 121393
fib(41): 165580141
fib(42): 267914296
```

終了までに要する時間は、ループ反復ごとに異なります。 `parallel_for_each` のパフォーマンスは最後に終了した操作に関係してくるため、 この例の逐次バージョンと並列バージョンを比べても、パフォーマンスのリニアな向上は期待できません。

## <a name="related-topics"></a>関連トピック

|Title|説明|
|-----------|-----------------|
|[タスクの並列処理](../../parallel/concrt/task-parallelism-concurrency-runtime.md)|PPL でのタスクおよびタスク グループの役割について説明します。|
|[並列アルゴリズム](../../parallel/concrt/parallel-algorithms.md)|`parallel_for` や `parallel_for_each` などの並列アルゴリズムの使用方法について説明します。|
|[並列コンテナーと並列オブジェクト](../../parallel/concrt/parallel-containers-and-objects.md)|PPL に用意されているさまざまな並列コンテナーと並列オブジェクトについて説明します。|
|[PPL における取り消し処理](cancellation-in-the-ppl.md)|並列アルゴリズムによって行われている処理を取り消す方法について説明します。|
|[コンカレンシー ランタイム](../../parallel/concrt/concurrency-runtime.md)|並列プログラミングを容易にするコンカレンシー ランタイムについて説明します。また、関連トピックへのリンクを示します。|

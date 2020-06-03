---
title: 自動並行化と自動ベクター化
ms.date: 11/04/2016
ms.assetid: ec71583a-287b-4599-8767-1d255e080fe3
ms.openlocfilehash: adc0dd9346cc2850b02e01804e26044c367f2d14
ms.sourcegitcommit: fcc3aeb271449f8be80348740cffef39ba543407
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/29/2020
ms.locfileid: "82538617"
---
# <a name="auto-parallelization-and-auto-vectorization"></a>自動並行化と自動ベクター化

自動並行化と自動ベクター化は、コード内のループのパフォーマンスが自動的に向上するように設計されています。

## <a name="auto-parallelizer"></a>自動並行化

[/Qpar](../build/reference/qpar-auto-parallelizer.md)コンパイラスイッチを使用すると、コード内のループの*自動並列*化が有効になります。 既存のコードを変更せずにこのフラグを指定すると、並行化の利点を達成できる可能性があるループを見つける観点で、コンパイラがコードを評価します。 つまり、処理量がそれほど多くなく、したがって並行化の利点が多くないループを見つける可能性があります。また、不必要な並行化はいずれも、パフォーマンスの向上ではなく低下につながる可能性のあるスレッド プール、余分な同期、または他のプロセスの発生源になる可能性があります。したがって、コンパイラは並行化するループを保守的な基準で選択します。 たとえば、コンパイル時にループの上限が不明である次の例について考えてみましょう。

```cpp
void loop_test(int u) {
   for (int i=0; i<u; ++i)
      A[i] = B[i] * C[i];
}
```

`u` は小さい値という可能性があるため、コンパイラは自動的にこのループを並行化することはありません。 ただし、`u` が必ず大きいことを把握している場合は、開発者が並行化を希望することもあります。 自動並列化を有効にするには、 [#pragma ループ (hint_parallel (n))](../preprocessor/loop.md)を指定します。 `n`は、並列化するスレッドの数です。 次の例では、コンパイラは 8 つのスレッドにまたがるループの並行化を試みます。

```cpp
void loop_test(int u) {
#pragma loop(hint_parallel(8))
   for (int i=0; i<u; ++i)
      A[i] = B[i] * C[i];
}
```

すべての[プラグマディレクティブ](../preprocessor/pragma-directives-and-the-pragma-keyword.md)と同様に、代替`__pragma(loop(hint_parallel(n)))`プラグマ構文もサポートされています。

開発者が希望しても、コンパイラが並行化できないループが存在します。 次に例を示します。

```cpp
#pragma loop(hint_parallel(8))
for (int i=0; i<upper_bound(); ++i)
    A[i] = B[i] * C[i];
```

関数の `upper_bound()` が、呼び出されるたびに変化する可能性がある場合。 上限を特定できないため、コンパイラはこのループを並行化できない理由を説明する診断メッセージを生成できます。 次の例では、並行化できるループ、並行化できないループ、コマンド プロンプトで使用するためのコンパイラの構文、および各コマンド ライン オプションに対応するコンパイラ出力を示します。

```cpp
int A[1000];
void test() {
#pragma loop(hint_parallel(0))
    for (int i=0; i<1000; ++i) {
        A[i] = A[i] + 1;
    }

    for (int i=1000; i<2000; ++i) {
        A[i] = A[i] + 1;
    }
}
```

次のコマンドを使用してコンパイル:

`cl d:\myproject\mylooptest.cpp /O2 /Qpar /Qpar-report:1`

生成される出力:

```Output
--- Analyzing function: void __cdecl test(void)
d:\myproject\mytest.cpp(4) : loop parallelized
```

次のコマンドを使用してコンパイル:

`cl d:\myproject\mylooptest.cpp /O2 /Qpar /Qpar-report:2`

生成される出力:

```Output
--- Analyzing function: void __cdecl test(void)
d:\myproject\mytest.cpp(4) : loop parallelized
d:\myproject\mytest.cpp(4) : loop not parallelized due to reason '1008'
```

2つの異なる[/Qpar-report (自動並行化レポートレベル)](../build/reference/qpar-report-auto-parallelizer-reporting-level.md)オプションの出力の違いに注意してください。 `/Qpar-report:1` を指定した場合は、正常に並行化されたループのみに関する並行化メッセージが出力されます。 `/Qpar-report:2` を指定した場合は、並行化したループと並行化しなかったループの両方に関する並行化メッセージが出力されます。

理由コードとメッセージの詳細については、「[ベクター化 And 並行化 messages](../error-messages/tool-errors/vectorizer-and-parallelizer-messages.md)」を参照してください。

## <a name="auto-vectorizer"></a>自動ベクター化

自動ベクター化機能は、コード内のループを分析し、可能な場合は、ターゲット コンピューター上のベクター レジスタとベクター命令を使用してそれらのループを実行します。 この方法により、コードのパフォーマンスが向上する可能性があります。 コンパイラは、Intel または AMD プロセッサの SSE2、AVX、AVX2 命令、または[/arch](../build/reference/arch-minimum-cpu-architecture.md)スイッチによる ARM プロセッサのネオン命令を対象としています。

自動ベクター化機能は、`/arch` スイッチで指定されていない命令を生成することもあります。 これらの命令は、実行時チェックによって保護され、引き続きコードが正しく実行されることが確認されます。 たとえば、`/arch:SSE2` のコンパイル時に SSE4.2 命令が送出されることがあります。 実行時チェックによって、ターゲット プロセッサで SSE4.2 を使用できるかが確認され、プロセッサがそれらの命令をサポートしていない場合は SSE4.2 でないバージョンのループにジャンプします。

既定では、自動ベクター化が有効になります。 ベクター化の下でコードのパフォーマンスを比較する場合は、 [#pragma ループ (no_vector)](../preprocessor/loop.md)を使用して、任意のループのベクター化を無効にすることができます。

```cpp
#pragma loop(no_vector)
for (int i = 0; i < 1000; ++i)
   A[i] = B[i] + C[i];
```

すべての[プラグマディレクティブ](../preprocessor/pragma-directives-and-the-pragma-keyword.md)と同様に、代替`__pragma(loop(no_vector))`プラグマ構文もサポートされています。

自動並行化の場合と同様に、 [/Qvec-report (自動ベクター化レポートレベル)](../build/reference/qvec-report-auto-vectorizer-reporting-level.md)コマンドラインオプションを指定して、正常にベクター化ループのみ`/Qvec-report:1`を報告するか、成功と失敗の両方のベクター化`/Qvec-report:2`ループ) を報告することができます。

理由コードとメッセージの詳細については、「[ベクター化 And 並行化 messages](../error-messages/tool-errors/vectorizer-and-parallelizer-messages.md)」を参照してください。

ベクター化が実際にどのように動作するかを示す例については、「 [Project オースティン第2部: ページ Curling](https://devblogs.microsoft.com/cppblog/project-austin-part-2-of-6-page-curling/) 」を参照してください。

## <a name="see-also"></a>関連項目

[ループ](../preprocessor/loop.md)<br/>
[ネイティブコードでの並列プログラミング](/archive/blogs/nativeconcurrency)<br/>
[/Qpar (自動並行化)](../build/reference/qpar-auto-parallelizer.md)<br/>
[/Qpar-report (自動並行化レポート作成レベル)](../build/reference/qpar-report-auto-parallelizer-reporting-level.md)<br/>
[/Qvec-report (自動ベクター化レポート作成レベル)](../build/reference/qvec-report-auto-vectorizer-reporting-level.md)<br/>
[ベクター化と並列化のメッセージ ](../error-messages/tool-errors/vectorizer-and-parallelizer-messages.md)

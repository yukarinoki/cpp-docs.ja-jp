---
description: '詳細情報: コードの最適化'
title: コードの最適化
ms.date: 05/06/2019
helpviewer_keywords:
- performance, optimizing code
- optimization
- cl.exe compiler, performance
- optimization, C++ code
- code, optimizing
- performance, compiler
ms.openlocfilehash: 893e3dce64400d47026e478b081283e3f1d82262
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97179799"
---
# <a name="optimizing-your-code"></a>コードの最適化

実行可能ファイルを最適化することで、実行の高速化とコード サイズの縮小の間でバランスを取ることができます。 このトピックでは、コードを最適化するために Visual Studio に用意されているいくつかのメカニズムについて説明します。

## <a name="language-features"></a>言語機能

次のトピックでは、C/C++ 言語のいくつかの最適化機能について説明します。

[最適化に影響するプラグマおよびキーワード](optimization-pragmas-and-keywords.md) \
パフォーマンスを向上させるためにコードで使用できるキーワードとプラグマの一覧。

[カテゴリ別のコンパイラ オプション](reference/compiler-options-listed-by-category.md) \
実行速度またはコード サイズに特に影響を与える **/O** コンパイラ オプションの一覧。

[右辺値参照宣言子: &&](../cpp/rvalue-reference-declarator-amp-amp.md) \
右辺値参照では、*移動セマンティクス* の実装がサポートされます。 移動セマンティクスを使用してテンプレート ライブラリを実装すると、これらのテンプレートを使用するアプリケーションのパフォーマンスが大幅に向上する可能性があります。

### <a name="the-optimize-pragma"></a>optimize プラグマ

コードの最適化されたセクションによってエラーまたは遅延が発生する場合は、[optimize](../preprocessor/optimize.md) プラグマを使用して、そのセクションの最適化をオフにすることができます。

次に示すように、2 つのプラグマでコードを囲みます。

```cpp
#pragma optimize("", off)
// some code here
#pragma optimize("", on)
```

## <a name="programming-practices"></a>プログラミング プラクティス

最適化を使用してコードをコンパイルしたときに、追加の警告メッセージが表示されることがあります。 いくつかの警告は最適化されたコードのみに関係しているため、これは想定されている動作です。 これらの警告に従うと、多くの最適化の問題を回避できます。

逆説的ですが、プログラムの速度を最適化すると、コードの実行速度が低下する可能性があります。 これは、速度の最適化の中には、コード サイズを増加させるものがあるためです。 たとえば、関数のインライン化によって、関数呼び出しのオーバーヘッドが除外されます。 ただし、多数のコードをインライン化するとプログラムが大きくなり、仮想メモリのページ フォールトの数が増加する可能性があります。 そのため、関数呼び出しの除外によって得られる速度が、メモリ スワップによって失われる可能性があります。

次のトピックでは、適切なプログラミング ラクティスについて説明します。

[タイムクリティカルなコードを高速化するためのヒント](tips-for-improving-time-critical-code.md) \
コーディング技法が優れていると、パフォーマンスが向上します。 このトピックでは、タイムクリティカルなコード部分が問題なく実行されるようにするためのコーディング技法について説明します。

[最適化のベスト プラクティス](optimization-best-practices.md) \
アプリケーションを最適化するための最善の方法に関する一般的なガイドラインを示します。

## <a name="debugging-optimized-code"></a>最適化されたコードのデバッグ

コンパイラによって作成されたコードが最適化によって変更される可能性があるため、アプリケーションをデバッグし、パフォーマンスを測定した後、コードを最適化することをお勧めします。

以下のトピックでは、リリース ビルドのデバッグに関する情報を提供します。

- [Visual Studio でのデバッグ](/visualstudio/debugger/debugging-in-visual-studio)

- [方法: 最適化されたコードをデバッグする](/visualstudio/debugger/how-to-debug-optimized-code)

- [浮動小数点数の精度の低下](why-floating-point-numbers-may-lose-precision.md)

以下のトピックでは、コードのビルド、読み込み、および実行を最適化する方法についての情報を提供します。

- [コンパイラのスループットの向上](improving-compiler-throughput.md)

- [() のない関数名とコードの生成](using-function-name-without-parens-produces-no-code.md)

- [インライン アセンブリの最適化](../assembler/inline/optimizing-inline-assembly.md)

- [ATL プロジェクトのコンパイラ最適化の指定](../atl/reference/specifying-compiler-optimization-for-an-atl-project.md)

- [読み込み時にクライアント アプリケーションのパフォーマンスを向上するための最適化技法](../build/dll-frequently-asked-questions.md#mfc_optimization)

## <a name="in-this-section"></a>このセクションの内容

[最適化に影響するプラグマおよびキーワード](optimization-pragmas-and-keywords.md) \
[コンパイラのスループットの向上](improving-compiler-throughput.md) \
[浮動小数点数の精度が低下する理由](why-floating-point-numbers-may-lose-precision.md) \
[IEEE 浮動小数点表現](ieee-floating-point-representation.md) \
[タイムクリティカルなコードを高速化するためのヒント](tips-for-improving-time-critical-code.md) \
["()" のない関数名とコードの生成](using-function-name-without-parens-produces-no-code.md) \
[最適化のベスト プラクティス](optimization-best-practices.md) \
[プロファイルに基づく最適化](profile-guided-optimizations.md) \
[プロファイルに基づく最適化の環境変数](environment-variables-for-profile-guided-optimizations.md) \
[PgoAutoSweep](pgoautosweep.md) \
[pgomgr](pgomgr.md) \
[pgosweep](pgosweep.md) \
[方法: 複数の PGO プロファイルを単一のプロファイルにマージする](how-to-merge-multiple-pgo-profiles-into-a-single-profile.md)

## <a name="see-also"></a>関連項目

[C/C++ ビルドのリファレンス](reference/c-cpp-building-reference.md)

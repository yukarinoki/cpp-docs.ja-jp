---
title: コードの最適化
ms.date: 05/06/2019
helpviewer_keywords:
- performance, optimizing code
- optimization
- cl.exe compiler, performance
- optimization, C++ code
- code, optimizing
- performance, compiler
ms.openlocfilehash: 00356cf50ca8e50c80e8a1142adf654816490c9b
ms.sourcegitcommit: 8e285a766523e653aeeb34d412dc6f615ef7b17b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/21/2020
ms.locfileid: "80078490"
---
# <a name="optimizing-your-code"></a>コードの最適化

実行可能ファイルを最適化することで、高速実行速度と小さいコードサイズとのバランスを取ることができます。 このトピックでは、コードを最適化するために Visual Studio に用意されているいくつかのメカニズムについて説明します。

## <a name="language-features"></a>言語機能

次のトピックでは、C/C++言語の一部の最適化機能について説明します。

[最適化のプラグマとキーワード](optimization-pragmas-and-keywords.md) \
パフォーマンスを向上させるためにコードで使用できるキーワードとプラグマの一覧。

[カテゴリ別に一覧表示されたコンパイラオプション](reference/compiler-options-listed-by-category.md) \
実行速度またはコードサイズに特に影響を与える **/o**コンパイラオプションの一覧。

[右辺値参照宣言子: & &](../cpp/rvalue-reference-declarator-amp-amp.md) \
右辺値参照は、*移動セマンティクス*の実装をサポートします。 移動セマンティクスを使用してテンプレートライブラリを実装すると、これらのテンプレートを使用するアプリケーションのパフォーマンスが大幅に向上する可能性があります。

### <a name="the-optimize-pragma"></a>Optimize プラグマ

コードの最適化されたセクションによってエラーまたは遅延が発生する場合は、 [optimize](../preprocessor/optimize.md)プラグマを使用してそのセクションの最適化をオフにすることができます。

次に示すように、2つのプラグマの間でコードを囲みます。

```cpp
#pragma optimize("", off)
// some code here
#pragma optimize("", on)
```

## <a name="programming-practices"></a>プログラミングプラクティス

最適化を使用してコードをコンパイルすると、追加の警告メッセージが表示されることがあります。 この動作は、最適化されたコードのみに関連する警告があるため、予想されます。 これらの警告を確認すると、多くの最適化の問題を回避できます。

逆説的を使用すると、プログラムの速度を最適化することで、コードの実行速度が低下する可能性があります。 これは、速度の最適化によってコードサイズが増加するためです。 たとえば、関数のインライン展開により、関数呼び出しのオーバーヘッドが解消されます。 ただし、コードが過剰にインライン展開されると、プログラムが大きくなり、仮想メモリのページフォールトの数が増加する可能性があります。 そのため、関数呼び出しの削除によって得られる速度が、メモリスワップに失われる可能性があります。

次のトピックでは、適切なプログラミング手法について説明します。

[タイムクリティカルなコード \ を向上させるためのヒント](tips-for-improving-time-critical-code.md)
コーディング手法が優れていると、パフォーマンスが向上します。 このトピックでは、コードの時間の重要な部分が確実に実行されるようにするためのコーディング技法について説明します。

[最適化のベストプラクティス](optimization-best-practices.md) \
アプリケーションの最適化に最適な方法に関する一般的なガイドラインを示します。

## <a name="debugging-optimized-code"></a>最適化されたコードのデバッグ

最適化によってコンパイラによって作成されたコードが変更される可能性があるため、アプリケーションをデバッグし、パフォーマンスを測定して、コードを最適化することをお勧めします。

次のトピックでは、リリースビルドをデバッグする方法について説明します。

- [Visual Studio でのデバッグ](/visualstudio/debugger/debugging-in-visual-studio)

- [方法 : 最適化されたコードをデバッグする](/visualstudio/debugger/how-to-debug-optimized-code)

- [浮動小数点数の精度の低下](why-floating-point-numbers-may-lose-precision.md)

次のトピックでは、コードのビルド、読み込み、および実行を最適化する方法について説明します。

- [コンパイラのスループットの向上](improving-compiler-throughput.md)

- [() のない関数名とコードの生成](using-function-name-without-parens-produces-no-code.md)

- [インライン アセンブリの最適化](../assembler/inline/optimizing-inline-assembly.md)

- [ATL プロジェクトのコンパイラ最適化の指定](../atl/reference/specifying-compiler-optimization-for-an-atl-project.md)

- [読み込み時にクライアントアプリケーションのパフォーマンスを向上させるためにどのような最適化手法を使用する必要がありますか。](../build/dll-frequently-asked-questions.md#mfc_optimization)

## <a name="in-this-section"></a>このセクションの内容

[最適化のプラグマとキーワード](optimization-pragmas-and-keywords.md) \
[コンパイラスループットの向上](improving-compiler-throughput.md) \
[浮動小数点数の精度が失われる理由](why-floating-point-numbers-may-lose-precision.md) \
[IEEE 浮動小数点表現の](ieee-floating-point-representation.md) \
[タイムクリティカルなコード \ を向上させるためのヒント](tips-for-improving-time-critical-code.md)
[() を指定せずに関数名を使用すると、コードが生成](using-function-name-without-parens-produces-no-code.md)され \
[最適化のベストプラクティス](optimization-best-practices.md) \
[ガイド付き最適化のプロファイルの](profile-guided-optimizations.md) \
[ガイド付き最適化のプロファイルの環境変数](environment-variables-for-profile-guided-optimizations.md) \
[PgoAutoSweep](pgoautosweep.md) \
[pgomgr](pgomgr.md) \
[pgosweep](pgosweep.md) \
[方法: 複数の PGO プロファイルを単一のプロファイルにマージする](how-to-merge-multiple-pgo-profiles-into-a-single-profile.md)

## <a name="see-also"></a>参照

[C/C++ ビルドのリファレンス](reference/c-cpp-building-reference.md)

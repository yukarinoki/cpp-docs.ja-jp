---
title: コードの最適化
ms.date: 12/10/2018
helpviewer_keywords:
- performance, optimizing code
- optimization
- cl.exe compiler, performance
- optimization, C++ code
- code, optimizing
- performance, compiler
ms.openlocfilehash: ae60070959c683a6365992e7b6cc510fd4111b36
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2019
ms.locfileid: "57828101"
---
# <a name="optimizing-your-code"></a>コードの最適化

実行可能ファイルを最適化することによって、高速に実行速度とサイズの小さなコード間のバランスを実現できます。 このトピックでは、Visual C は、コードを最適化するためのメカニズムの一部について説明します。

## <a name="language-features"></a>言語機能

次のトピックでは、C と C++ 言語の最適化機能の一部について説明します。

[最適化に影響するプラグマおよびキーワード](optimization-pragmas-and-keywords.md)<br/>
一連のキーワードとプラグマのパフォーマンスを向上させるために、コードで使用できます。

[カテゴリ別のコンパイラ オプション](reference/compiler-options-listed-by-category.md)<br/>
一連の **/O**コンパイラ オプションが具体的には実行の速度やコードのサイズに影響します。

[右辺値参照宣言子: &&](../cpp/rvalue-reference-declarator-amp-amp.md)<br/>
右辺値参照の実装をサポートする*移動セマンティクス*します。 移動セマンティクスをテンプレート ライブラリでは、これらのテンプレートを使用するアプリケーションのパフォーマンスを実装するために使用が大幅に向上させることができます。 場合、

### <a name="the-optimize-pragma"></a>Optimize プラグマ

コードの最適化のセクションでは、エラーやパフォーマンスが低下が発生する場合は使用できます、[最適化](../preprocessor/optimize.md)プラグマに、そのセクションの最適化をオフにします。

次に示すように、2 つのプラグマ コードを囲みます。

```cpp
#pragma optimize("", off)
// some code here
#pragma optimize("", on)
```

## <a name="programming-practices"></a>プログラミング手法

最適化したコードをコンパイルするときに、追加の警告メッセージがわかります。 いくつかの警告が最適化されたコードにのみ関連しているために、この動作が必要です。 これらの警告の注意を払わない場合は、多くの最適化問題を回避できます。

皮肉にも、速度のためのプログラムを最適化することにより、実行速度が低下するためのコード。 これは、最適化の方法によっては、コードのサイズを増やすためです。 たとえば、関数をインライン展開関数呼び出しのオーバーヘッドがなくなります。 ただし、インライン コードが多すぎることは、プログラム非常に大きいため、仮想メモリのページの数が増加をフォールトします。 そのため、関数呼び出しを排除することから得られた速度は、メモリ スワップ失わ可能性があります。

次のトピックでは、適切なプログラミング方法について説明します。

[タイム クリティカルなコードを高速化するためのヒント](tips-for-improving-time-critical-code.md)<br/>
適切なコーディング テクニックと、パフォーマンスを向上できます。 このトピックでは、コーディング、コードの時間が重要な部分が満足することを確認するのに役立つ手法を提案します。

[最適化の推奨事項](optimization-best-practices.md)<br/>
アプリケーションを最適化する最善の方法に関する一般的なガイドラインを提供します。

## <a name="debugging-optimized-code"></a>最適化されたコードのデバッグ

最適化は、コンパイラによって作成されたコードに変わる可能性がある、アプリケーションをデバッグして、パフォーマンスの測定をコードを最適化し、お勧めします。

次のトピックでは、ビルドのリリースをデバッグする方法についての情報を提供します。

- [Visual Studio でのデバッグ](/visualstudio/debugger/debugging-in-visual-studio)

- [方法: 最適化されたコードをデバッグする](/visualstudio/debugger/how-to-debug-optimized-code)

- [浮動小数点数の精度の低下](why-floating-point-numbers-may-lose-precision.md)


次のトピックでは、構築、読み込み、およびコードの実行を最適化する方法に関する情報を提供します。

- [コンパイラのスループットの向上](improving-compiler-throughput.md)

- [() のない関数名とコードの生成](using-function-name-without-parens-produces-no-code.md)

- [インライン アセンブリの最適化](../assembler/inline/optimizing-inline-assembly.md)

- [ATL プロジェクトのコンパイラ最適化の指定](../atl/reference/specifying-compiler-optimization-for-an-atl-project.md)

- [どのような最適化手法を読み込むときに、クライアント アプリケーションのパフォーマンスを向上させるために使用する必要がありますか。](../build/dll-frequently-asked-questions.md#mfc_optimization)


## <a name="in-this-section"></a>このセクションの内容

[最適化に影響するプラグマおよびキーワード](optimization-pragmas-and-keywords.md)<br/>
[コンパイラのスループットの向上](improving-compiler-throughput.md)<br/>
[浮動小数点数の精度の低下](why-floating-point-numbers-may-lose-precision.md)<br/>
[IEEE 浮動小数点表現](ieee-floating-point-representation.md)<br/>
[タイム クリティカルなコードを高速化するためのヒント](tips-for-improving-time-critical-code.md)<br/>
[() のない関数名とコードの生成](using-function-name-without-parens-produces-no-code.md)<br/>
[最適化の推奨事項](optimization-best-practices.md)<br/>
[ガイド付き最適化のプロファイル](profile-guided-optimizations.md)<br/>
[ガイド付き最適化のプロファイルの環境変数](environment-variables-for-profile-guided-optimizations.md)<br/>
[PgoAutoSweep](pgoautosweep.md)<br/>
[pgomgr](pgomgr.md)<br/>
[pgosweep](pgosweep.md)<br/>
[方法: 複数の PGO プロファイルを単一のプロファイルにマージする](how-to-merge-multiple-pgo-profiles-into-a-single-profile.md)<br/>
[パフォーマンスと診断ハブでの Visual Studio 2013 PGO アドイン](profile-guided-optimization-in-the-performance-and-diagnostics-hub.md)<br/>

## <a name="see-also"></a>関連項目

[C/C++ ビルドのリファレンス](reference/c-cpp-building-reference.md)

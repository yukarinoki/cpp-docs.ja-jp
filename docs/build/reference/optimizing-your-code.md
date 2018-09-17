---
title: コードの最適化 |Microsoft Docs
ms.custom: ''
ms.date: 12/28/2017
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- performance, optimizing code
- optimization
- cl.exe compiler, performance
- optimization, C++ code
- code, optimizing
- performance, compiler
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 180586f55ea57100286c3c598ac62eb83107d7c9
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2018
ms.locfileid: "45714377"
---
# <a name="optimizing-your-code"></a>コードの最適化

実行可能ファイルを最適化することによって、高速に実行速度とサイズの小さなコード間のバランスを実現できます。 このトピックでは、Visual C は、コードを最適化するためのメカニズムの一部について説明します。

## <a name="language-features"></a>言語機能

次のトピックでは、C と C++ 言語の最適化機能の一部について説明します。

[最適化のプラグマおよびキーワード](../../build/reference/optimization-pragmas-and-keywords.md)一連のキーワードとプラグマのパフォーマンスを向上させるために、コードで使用できます。

[コンパイラの Options Listed by Category](../../build/reference/compiler-options-listed-by-category.md)一連の **/O**具体的には実行の速度やコードのサイズに影響を与えるコンパイラ オプション。

[右辺値参照宣言子: & &](../../cpp/rvalue-reference-declarator-amp-amp.md)右辺値参照の実装をサポートする*移動セマンティクス*します。 移動セマンティクスをテンプレート ライブラリでは、これらのテンプレートを使用するアプリケーションのパフォーマンスを実装するために使用が大幅に向上させることができます。 場合、

### <a name="the-optimize-pragma"></a>Optimize プラグマ

コードの最適化のセクションでは、エラーやパフォーマンスが低下が発生する場合は使用できます、[最適化](../../preprocessor/optimize.md)プラグマに、そのセクションの最適化をオフにします。

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

[タイム クリティカル コードを改善するためのヒント](../../build/reference/tips-for-improving-time-critical-code.md)コーディング手法を効率化、パフォーマンスを向上できます。 このトピックでは、コーディング、コードの時間が重要な部分が満足することを確認するのに役立つ手法を提案します。

[最適化のベスト プラクティス](../../build/reference/optimization-best-practices.md)アプリケーションを最適化する最善の方法に関する一般的なガイドラインを提供します。

## <a name="debugging-optimized-code"></a>最適化されたコードのデバッグ

最適化は、コンパイラによって作成されたコードに変わる可能性がある、アプリケーションをデバッグして、パフォーマンスの測定をコードを最適化し、お勧めします。

次のトピックでは、デバッグする方法についての基本的な情報を説明します。

- [Visual Studio でのデバッグ](/visualstudio/debugger/debugging-in-visual-studio)

- [リリース ビルド作成時によくある問題](../../build/reference/common-problems-when-creating-a-release-build.md)

次のトピックでは、デバッグする方法についてより高度な情報を提供します。

- [方法 : 最適化されたコードをデバッグする](/visualstudio/debugger/how-to-debug-optimized-code)

- [浮動小数点数の精度の低下](../../build/reference/why-floating-point-numbers-may-lose-precision.md)

次のトピックでは、構築、読み込み、およびコードの実行を最適化する方法に関する情報を提供します。

- [コンパイラのスループットの向上](../../build/reference/improving-compiler-throughput.md)

- [() のない関数名とコードの生成](../../build/reference/using-function-name-without-parens-produces-no-code.md)

- [インライン アセンブリの最適化](../../assembler/inline/optimizing-inline-assembly.md)

- [ATL プロジェクトのコンパイラ最適化の指定](../../atl/reference/specifying-compiler-optimization-for-an-atl-project.md)

- [どのような最適化手法を読み込むときに、クライアント アプリケーションのパフォーマンスを向上させるために使用する必要がありますか。](../../build/dll-frequently-asked-questions.md#mfc_optimization)

## <a name="see-also"></a>関連項目

[C/C++ ビルドのリファレンス](../../build/reference/c-cpp-building-reference.md)

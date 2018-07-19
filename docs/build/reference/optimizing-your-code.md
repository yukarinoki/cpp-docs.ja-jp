---
title: コードの最適化 |Microsoft ドキュメント
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
ms.openlocfilehash: a8b18ba4ce00eb751d8f30debbab3e87b9cce53e
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32378978"
---
# <a name="optimizing-your-code"></a>コードの最適化

実行可能ファイルを最適化して、高速に実行速度とサイズの小さいコード間のバランスを実現できます。 このトピックでは、Visual C ではコードを最適化するためのメカニズムについて説明します。

## <a name="language-features"></a>言語機能

次のトピックでは、一部の C と C++ 言語での最適化機能について説明します。

[最適化に影響するプラグマおよびキーワード](../../build/reference/optimization-pragmas-and-keywords.md)  
一連のキーワードとプラグマのパフォーマンスを向上させるために、コードで使用できます。

[カテゴリ別のコンパイラ オプション](../../build/reference/compiler-options-listed-by-category.md)  
一連の **/O**コンパイラ オプションが具体的には実行速度またはコードのサイズに影響します。

[右辺値参照宣言子: &&](../../cpp/rvalue-reference-declarator-amp-amp.md)  
右辺値参照の実装をサポートする*移動セマンティクス*です。 移動セマンティクスを使用して、これらのテンプレートを使用するアプリケーションのパフォーマンスのテンプレート ライブラリを実装するが大幅に向上させることができます。 場合、

### <a name="the-optimize-pragma"></a>Optimize プラグマ

コードの最適化のセクション発生エラーやパフォーマンスが低下すると、行うこともできます、[最適化](../../preprocessor/optimize.md)プラグマをそのセクションの最適化をオフにします。

次に示すように、2 つのプラグマの間のコードを囲みます。

```cpp
#pragma optimize("", off)
// some code here
#pragma optimize("", on)
```

## <a name="programming-practices"></a>プログラミング手法

最適化を使用してコードをコンパイルするときに関連する警告メッセージに注意してください可能性があります。 この動作がいくつかの警告が最適化されたコードにのみ関連付けるために必要です。 これらの警告をよく確認する場合は、多くの最適化の問題を回避できます。

皮肉にも、速度のためのプログラムを最適化するには、コード実行速度が低下する可能性があります。 これは、最適化の方法によっては、コードのサイズを増やすため。 たとえば、関数をインライン展開関数呼び出しのオーバーヘッドを排除します。 ただし、インライン コードが多すぎる可能性がある、プログラム非常に大きいため、仮想メモリのページの数が増加をフォールトします。 したがって、関数呼び出しを排除することから得られた速度は、メモリ スワップが失われた可能性があります。

次のトピックでは、推奨されるプログラミング方法について説明します。

[タイム クリティカルなコードを高速化するためのヒント](../../build/reference/tips-for-improving-time-critical-code.md)  
適切なコーディング テクニックと、パフォーマンスを向上できます。 このトピックでは、コーディング、コードの時間が重要な部分を実行する十分に表せないことを確認するのに役立つ手法を提案します。

[最適化の推奨事項](../../build/reference/optimization-best-practices.md)  
アプリケーションを最適化する最善の方法に関する一般的なガイドラインを提供します。

## <a name="debugging-optimized-code"></a>最適化されたコードのデバッグ

最適化は、コンパイラによって作成されたコードに変わる可能性がある、アプリケーションをデバッグして、パフォーマンスの測定をコードを最適化お勧めします。

次のトピックでは、デバッグする方法に関する基本情報を説明します。

- [Visual Studio でのデバッグ](/visualstudio/debugger/debugging-in-visual-studio)

- [リリース ビルド作成時によくある問題](../../build/reference/common-problems-when-creating-a-release-build.md)

次のトピックより高度な情報をデバッグする方法を説明します。

- [方法 : 最適化されたコードをデバッグする](/visualstudio/debugger/how-to-debug-optimized-code)

- [浮動小数点数の精度の低下](../../build/reference/why-floating-point-numbers-may-lose-precision.md)

次のトピックでは、構築、読み込み、およびコードの実行を最適化する方法に関する情報を提供します。

- [コンパイラのスループットの向上](../../build/reference/improving-compiler-throughput.md)

- [() のない関数名とコードの生成](../../build/reference/using-function-name-without-parens-produces-no-code.md)

- [インライン アセンブリの最適化](../../assembler/inline/optimizing-inline-assembly.md)

- [ATL プロジェクトのコンパイラ最適化の指定](../../atl/reference/specifying-compiler-optimization-for-an-atl-project.md)

- [どのような最適化の手法を読み込むときに、クライアント アプリケーションのパフォーマンスを向上させるために使用する必要がありますか。](../../build/dll-frequently-asked-questions.md#mfc_optimization)

## <a name="see-also"></a>関連項目

[C/C++ ビルドのリファレンス](../../build/reference/c-cpp-building-reference.md)  

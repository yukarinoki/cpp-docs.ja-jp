---
title: 自動並行化と自動ベクター化 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: ec71583a-287b-4599-8767-1d255e080fe3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 0b1ec19065647f78b4d9b2665003c0aa3a2795ba
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
---
# <a name="auto-parallelization-and-auto-vectorization"></a>自動並行化と自動ベクター化
自動並行化と自動ベクター化は、コード内のループのパフォーマンスが自動的に向上するように設計されています。  
  
## <a name="auto-parallelizer"></a>自動並行化  
 [/Qpar](../build/reference/qpar-auto-parallelizer.md)コンパイラ スイッチにより*自動並列化*コード内のループのです。 既存のコードを変更せずにこのフラグを指定すると、並行化の利点を達成できる可能性があるループを見つける観点で、コンパイラがコードを評価します。 つまり、処理量がそれほど多くなく、したがって並行化の利点が多くないループを見つける可能性があります。また、不必要な並行化はいずれも、パフォーマンスの向上ではなく低下につながる可能性のあるスレッド プール、余分の同期、または他のプロセスの発生源になる可能性があります。したがって、コンパイラは並行化するループを保守的な基準で選択します。 たとえば、コンパイル時にループの上限が不明である次の例について考えてみましょう。  
  
```cpp  
void loop_test(int u) {  
   for (int i=0; i<u; ++i)  
      A[i] = B[i] * C[i];  
}  
```  
  
 `u` は小さい値という可能性があるため、コンパイラは自動的にこのループを並行化することはありません。 ただし、`u` が必ず大きいことを把握している場合は、開発者が並行化を希望することもあります。 自動並行化を有効にするには指定[#pragma loop(hint_parallel(n))](../preprocessor/loop.md)ここで、`n`並行化するスレッドの数です。 次の例では、コンパイラは 8 つのスレッドにまたがるループの並行化を試みます。  
  
```cpp  
void loop_test(int u) {  
#pragma loop(hint_parallel(8))  
   for (int i=0; i<u; ++i)  
      A[i] = B[i] * C[i];  
}  
```  
  
 すべてのと同様[プラグマ ディレクティブ](../preprocessor/pragma-directives-and-the-pragma-keyword.md)、代替 pragma 構文`__pragma(loop(hint_parallel(n)))`もサポートされています。  
  
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
  
 **cl d:\myproject\mylooptest.cpp/O2/Qpar/Qpar-レポート: 1**  
  
 生成される出力:  
  
 **---分析関数: _ _cdecl test(void) を無効にします。**   
 **d:\myproject\mytest.cpp(4): ループは並列化**  
  
 次のコマンドを使用してコンパイル:  
  
 **cl d:\myproject\mylooptest.cpp/O2/Qpar/Qpar-レポート: 2**  
  
 生成される出力:  
  
 **---分析関数: _ _cdecl test(void) を無効にします。**   
 **d:\myproject\mytest.cpp(4): ループは並列化**   
 **d:\myproject\mytest.cpp(4): ループは理由 '1008' により並列化されません**  
  
 異なる 2 つの出力に違いが見つかる[/Qpar-report (自動並行化レポート作成レベル)](../build/reference/qpar-report-auto-parallelizer-reporting-level.md)オプション。 **/Qpar-レポート: 1**は正常に並行化されたループのみに関する並行化メッセージを出力します。 **/Qpar-レポート: 2**成功と失敗のループを両方指定に関する並行化メッセージを出力します。  
  
 理由コードとメッセージの詳細については、次を参照してください。[ベクター化と並行化メッセージ](../error-messages/tool-errors/vectorizer-and-parallelizer-messages.md)です。  
  
## <a name="auto-vectorizer"></a>自動ベクター化  
 自動ベクター化機能は、コード内のループを分析し、可能な場合は、ターゲット コンピューター上のベクター レジスタとベクター命令を使用してそれらのループを実行します。 この方法により、コードのパフォーマンスが向上する可能性があります。 コンパイラは、Intel または AMD プロセッサの SSE2、AVX、AVX2 命令または ARM プロセッサの NEON 命令をターゲットによると、 [/arch](../build/reference/arch-minimum-cpu-architecture.md)スイッチします。  
  
 指定されたよりも、自動ベクター化が命令を生成する可能性があります、 **/arch**スイッチします。 これらの命令は、実行時チェックによって保護され、引き続きコードが正しく実行されることが確認されます。 たとえば、コンパイル **/arch:sse2 以上**、SSE4.2 命令を生成する可能性があります。 実行時チェックによって、ターゲット プロセッサで SSE4.2 を使用できるかが確認され、プロセッサがそれらの命令をサポートしていない場合は SSE4.2 でないバージョンのループにジャンプします。  
  
 既定では、自動ベクター化が有効になります。 ベクター化対象のコードのパフォーマンスを比較する場合は、使用[#pragma loop (no_vector)](../preprocessor/loop.md)を指定されたループのベクター化を無効にします。  
  
```  
  
      #pragma loop(no_vector)  
for (int i = 0; i < 1000; ++i)  
   A[i] = B[i] + C[i];  
  
```  
  
 すべてのと同様[プラグマ ディレクティブ](../preprocessor/pragma-directives-and-the-pragma-keyword.md)、代替 pragma 構文`__pragma(loop(no_vector))`もサポートされています。  
  
 ようは自動並列化を指定できます、 [/Qvec-report (自動ベクター化レポート作成レベル)](../build/reference/qvec-report-auto-vectorizer-reporting-level.md)ベクター化したループのみを正常にいずれかを報告するコマンド ライン オプション:**/Qvec-レポート: 1**— または正常と失敗の両方にループがベクター化-**/Qvec-レポート: 2**)。  
  
 理由コードとメッセージの詳細については、次を参照してください。[ベクター化と並行化メッセージ](../error-messages/tool-errors/vectorizer-and-parallelizer-messages.md)です。  
  
 実際にはベクター化のしくみを示す例は、次を参照してください[Project Austin Part 2 of 6: Page Curling。](http://blogs.msdn.com/b/vcblog/archive/2012/09/27/10348494.aspx)  
  
## <a name="see-also"></a>関連項目  
 [ループ](../preprocessor/loop.md)   
 [ネイティブ コードでの並列プログラミング](http://go.microsoft.com/fwlink/p/?linkid=263662)   
 [/Qpar (自動並行化)](../build/reference/qpar-auto-parallelizer.md)   
 [/Qpar-report (自動並行化レポート作成レベル)](../build/reference/qpar-report-auto-parallelizer-reporting-level.md)   
 [/Qvec-report (自動ベクター化レポート作成レベル)](../build/reference/qvec-report-auto-vectorizer-reporting-level.md)   
 [ベクター化と並列化のメッセージ](../error-messages/tool-errors/vectorizer-and-parallelizer-messages.md)
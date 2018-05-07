---
title: 致命的なエラー C1001 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1001
dev_langs:
- C++
helpviewer_keywords:
- C1001
ms.assetid: 5736cdb3-22c8-4fad-aa85-d5e0d2b232f4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f605dd7e4892c4a8b57e544ed857257be72f020d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="fatal-error-c1001"></a>致命的なエラー C1001

> 内部コンパイラ ERROR(compiler file *file*, line *number*)  
  
解析中に特定の式と最適化オプション、または問題の組み合わせにより多くの場合、構成用の正しいコードを生成することはできません。 示されているコンパイラ ファイルに utc または C2 パス セグメントがある場合は、これはほとんど最適化エラーです。 ファイルが cxxfe または c1xx のパス セグメントや msc1.cpp をはおそらくパーサー エラーです。 という名前のファイルは、cl.exe は、存在がない場合その他の情報です。  

多くの場合、1 つまたは複数の最適化オプションを削除することによって最適化の問題を修正できます。 どちらのオプションに問題を特定するには、エラー メッセージがなくなるまで時および再コンパイルに 1 つのオプションを削除します。 最もよく担当のオプションは[/Og (グローバルの最適化)](../../build/reference/og-global-optimizations.md)と[/Oi (組み込み関数の生成)](../../build/reference/oi-generate-intrinsic-functions.md)です。 担当な最適化オプションを確認した後は無効にできます関数を使用してエラーが発生、[最適化](../../preprocessor/optimize.md)プラグマ、モジュールの残りのオプションを使用し、続けます。 最適化オプションの詳細については、次を参照してください。[最適化の推奨事項](../../build/reference/optimization-best-practices.md)です。

最適化がエラーの原因でない場合は、エラーが報告された行または数行のコードをその前後の再書き換えを再試行してください。 コードのように、コンパイラが参照する前処理した後、使用することができます、 [/P (プリプロセス出力ファイルへの)](../../build/reference/p-preprocess-to-a-file.md)オプション。

内部コンパイラ エラーを Microsoft に報告する方法と、エラーの原因を特定する方法の詳細については、次を参照してください。 [Visual c ツールセットで問題を報告する方法](../../how-to-report-a-problem-with-the-visual-cpp-toolset.md)です。
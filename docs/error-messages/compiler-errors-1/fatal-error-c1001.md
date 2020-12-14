---
description: '詳細情報: 致命的なエラー C1001'
title: 致命的なエラー C1001
ms.date: 11/04/2016
f1_keywords:
- C1001
helpviewer_keywords:
- C1001
ms.assetid: 5736cdb3-22c8-4fad-aa85-d5e0d2b232f4
ms.openlocfilehash: a00e8bc2fe79201f77f67eac6f0756e90eba462b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97262829"
---
# <a name="fatal-error-c1001"></a>致命的なエラー C1001

> 内部コンパイラエラー (コンパイラファイル *ファイル*、行 *番号*)

コンパイラはコンストラクトの正しいコードを生成できません。多くの場合、特定の式と最適化オプションの組み合わせが原因であるか、解析中に問題が発生しています。 一覧に表示されているコンパイラファイルに utc または C2 パスセグメントが含まれている場合は、最適化エラーであると想定されます。 ファイルに cxxfe または c1xx パスセグメントがある場合、またはが msc1 の場合は、パーサーエラーの場合があります。 という名前のファイルが cl.exe 場合、他の情報は利用できません。

最適化の問題は、多くの場合、1つまたは複数の最適化オプションを削除することによって修正できます。 障害が発生しているオプションを特定するには、一度に1つずつオプションを削除し、エラーメッセージが表示されるまで再コンパイルします。 最も一般的に行われるオプションは、 [/og (グローバルな最適化)](../../build/reference/og-global-optimizations.md) と [/Oi (組み込み関数の生成)](../../build/reference/oi-generate-intrinsic-functions.md)です。 どの最適化オプションが関係しているかを判断したら、 [optimize](../../preprocessor/optimize.md) プラグマを使用してエラーが発生した関数の周囲で無効にして、残りのモジュールに対してオプションを使用し続けることができます。 最適化オプションの詳細については、「 [最適化のベストプラクティス](../../build/optimization-best-practices.md)」を参照してください。

最適化によってエラーが発生しない場合は、エラーが報告された行を書き直すか、その行を囲む数行のコードを書き直してください。 プリプロセスの実行後にコンパイラが認識する方法を確認するには、 [/p (ファイルを前処理する)](../../build/reference/p-preprocess-to-a-file.md) オプションを使用します。

エラーの原因を特定する方法と、内部コンパイラエラーを Microsoft に報告する方法の詳細については、「 [Visual C++ ツールセットで問題を報告する方法](../../overview/how-to-report-a-problem-with-the-visual-cpp-toolset.md)」を参照してください。

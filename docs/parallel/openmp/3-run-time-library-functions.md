---
title: 3. ランタイム ライブラリ関数 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: b226e512-6822-4cbe-a2ca-74cc2bb7e880
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d747f775509c6b3b2b95be51d95ea937816d3cd1
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
---
# <a name="3-run-time-library-functions"></a>3.ランタイム ライブラリ関数
このセクションでは、OpenMP C および C++ ランタイム ライブラリ関数について説明します。 ヘッダー  **\<omp.h >** 2 つの型が、制御およびクエリを並列実行環境とロック データへのアクセスを同期するために使用できる関数を使用できるいくつかの関数を宣言します。  
  
 型**omp_lock_t**オブジェクトの種類は、ロックが使用できる、ことを表現すること、またはスレッドがロックを所有しています。 これらのロックをいいます*単純ロック*です。  
  
 型**omp_nest_lock_t**はオブジェクトの種類を表すいずれかの可能なロックを使用、またはロックを所有するスレッドの両方の id と*入れ子カウント*(下記参照)。 これらのロックをいいます*入れ子にできるロック*です。  
  
 ライブラリ関数は、"C"リンケージを持つ外部関数です。  
  
 この章の説明は、次のトピックに分かれています。  
  
-   実行環境関数 (を参照してください[セクション 3.1](../../parallel/openmp/3-1-execution-environment-functions.md)ページ 35)。  
  
-   ロック関数 (を参照してください[セクション 3.2](../../parallel/openmp/3-2-lock-functions.md) 41 ページ上)。
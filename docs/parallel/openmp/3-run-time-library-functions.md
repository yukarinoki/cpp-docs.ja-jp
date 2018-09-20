---
title: 3. ランタイム ライブラリ関数 |Microsoft Docs
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
ms.openlocfilehash: 5c1a05df3b47c2bbf345bc0101f30ffb83b84967
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46401850"
---
# <a name="3-run-time-library-functions"></a>3.ランタイム ライブラリ関数

このセクションでは、OpenMP C および C++ ランタイム ライブラリ関数について説明します。 ヘッダー  **\<omp.h >** 2 つの型は、制御およびクエリの並列実行環境とロック データへのアクセスを同期するために使用する関数を使用できるいくつかの関数を宣言します。

型**omp_lock_t**オブジェクトの種類は、ロックが使用可能なことを表すことができる、またはスレッドがロックを所有しています。 これらのロックと呼びます*単純ロック*します。

型**omp_nest_lock_t**するかを表すことができるオブジェクトの種類のロックが使用可能なまたはスレッド id、ロックを所有しているが、*入れ子カウント*(下記参照)。 これらのロックと呼びます*入れ子にできるロック*します。

ライブラリ関数は、"C"リンケージを持つ外部関数です。

この章の説明は、次のトピックに分かれています。

- 実行環境関数 (を参照してください[セクション 3.1](../../parallel/openmp/3-1-execution-environment-functions.md) 35 ページ)。

- ロック関数 (を参照してください[セクション 3.2](../../parallel/openmp/3-2-lock-functions.md) 41 ページ上)。
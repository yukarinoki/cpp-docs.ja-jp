---
title: 2.7 データ環境 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 74e44b3c-e18c-4773-8e78-cd6c4413ae57
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d1b0f253ce14ffc5d3740e582a9a51feea56ad32
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
ms.locfileid: "33690066"
---
# <a name="27-data-environment"></a>2.7 データ環境
このセクションでは、ディレクティブと次のように、並行領域の実行中に、データの環境を制御するためのいくつかの句が表示されます。  
  
-   A **threadprivate**するため、ファイル スコープ、名前空間スコープ、または静的ブロック スコープ変数をこのスレッドにローカル ディレクティブのものは (次のセクションを参照してください)。  
  
-   属性を制御、共有変数の並列または work-sharing コンス トラクターの実行中のディレクティブで指定できる句は「[セクション 2.7.2](../../parallel/openmp/2-7-2-data-sharing-attribute-clauses.md) 25 ページ。
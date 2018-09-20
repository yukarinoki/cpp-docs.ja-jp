---
title: 2.7 データ環境 |Microsoft Docs
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
ms.openlocfilehash: 17c60c621defa15c034f57d0af8f14637db54f03
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46378138"
---
# <a name="27-data-environment"></a>2.7 データ環境

このセクションでは、ディレクティブと次のように、並行領域の実行中にデータ環境を制御するためのいくつかの句では。

- A **threadprivate**ディレクティブは、作成、ファイル スコープ、名前空間スコープ、または静的のブロック スコープ変数をこのスレッドにローカルに提供されます (次のセクションを参照してください)。

- 並列または動作共有のコンストラクトの実行中の変数の共有の属性を制御するディレクティブで指定できる句が記載されて[セクション 2.7.2](../../parallel/openmp/2-7-2-data-sharing-attribute-clauses.md) 25 ページにします。
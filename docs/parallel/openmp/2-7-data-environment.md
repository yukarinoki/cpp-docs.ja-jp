---
title: 2.7 データ環境
ms.date: 11/04/2016
ms.assetid: 74e44b3c-e18c-4773-8e78-cd6c4413ae57
ms.openlocfilehash: b65dfc7d7694b36ef4f89351579cd73e07ab537c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50491970"
---
# <a name="27-data-environment"></a>2.7 データ環境

このセクションでは、ディレクティブと次のように、並行領域の実行中にデータ環境を制御するためのいくつかの句では。

- A **threadprivate**ディレクティブは、作成、ファイル スコープ、名前空間スコープ、または静的のブロック スコープ変数をこのスレッドにローカルに提供されます (次のセクションを参照してください)。

- 並列または動作共有のコンストラクトの実行中の変数の共有の属性を制御するディレクティブで指定できる句が記載されて[セクション 2.7.2](../../parallel/openmp/2-7-2-data-sharing-attribute-clauses.md) 25 ページにします。
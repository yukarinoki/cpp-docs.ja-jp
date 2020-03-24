---
title: 致命的なエラー C1307
ms.date: 11/04/2016
f1_keywords:
- C1307
helpviewer_keywords:
- C1307
ms.assetid: 6f77d3d4-ba8a-476c-b540-aff19eb4efc4
ms.openlocfilehash: c7eb90c8e17408f6898ef7ff1a9d9e5efcafb4fa
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80203347"
---
# <a name="fatal-error-c1307"></a>致命的なエラー C1307

プロファイル データが集められてからプログラムが編集されました。

[/Ltcg: PGOPTIMIZE](../../build/reference/ltcg-link-time-code-generation.md)を使用する場合、リンカーは、/LTCG: pgoptimize の後に再コンパイルされた入力モジュールを検出し、既存のプロファイルデータが関連付けられていない時点にモジュールが変更されたことを検出しました。 たとえば、再コンパイルされたモジュールで呼び出しグラフが変更された場合、コンパイラは C1307 を生成します。

このエラーを解決するには、/LTCG: PGINSTRUMENT を実行し、すべてのテストの実行をやり直し、/LTCG: PGINSTRUMENT を実行します。 /LTCG: PGINSTRUMENT を実行できず、すべてのテストの実行をやり直すことができない場合は、/LTCG: PGINSTRUMENT ではなく/LTCG: PGINSTRUMENT を使用して最適化されたイメージを作成します。

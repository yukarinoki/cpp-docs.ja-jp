---
title: '経過時間: 汎用クラス'
ms.date: 11/04/2016
helpviewer_keywords:
- adding dates
- calculating dates and times
- dates, calculating intervals
- elapsed time, calculating
- elapsed time
- time, elapsed
- intervals, date and time
- calculations, date and time
ms.assetid: e5c5d3d2-ce1d-409e-875c-98848434e716
ms.openlocfilehash: ebaf77b34411cd55cb3a028bcce9109613b63ed9
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50676743"
---
# <a name="elapsed-time-general-purpose-classes"></a>経過時間: 汎用クラス

次の手順は、2 つの差を計算する方法を示しています。`CTime`オブジェクトを取得、`CTimeSpan`結果。 使用して、`CTime`と`CTimeSpan`の経過時間を次のように計算するオブジェクト。

   [!code-cpp[NVC_ATLMFC_Utilities#174](../atl-mfc-shared/codesnippet/cpp/elapsed-time-general-purpose-classes_1.cpp)]

計算した後`elapsedTime`のメンバー関数を使用する`CTimeSpan`経過時間の値のコンポーネントを抽出します。


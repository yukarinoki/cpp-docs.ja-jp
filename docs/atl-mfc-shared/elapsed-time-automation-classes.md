---
title: 経過時間:オートメーション クラス
ms.date: 11/04/2016
helpviewer_keywords:
- adding dates
- calculating dates and times
- dates, calculating intervals
- elapsed time, calculating in Automation
- Automation classes, elapsed time
- time, elapsed
- intervals, date and time
- calculations, date and time
ms.assetid: 26b34b37-c10e-4b91-82c3-1dc5ffb5361f
ms.openlocfilehash: d6a77d57a88166354fcb222c0da09690426108e9
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/11/2019
ms.locfileid: "57750050"
---
# <a name="elapsed-time-automation-classes"></a>経過時間:オートメーション クラス

この手順は、2 つの差を計算する方法を示しています。`CTime`オブジェクトを取得、`CTimeSpan`結果。

## <a name="to-calculate-elapsed-time"></a>経過時間を計算するには

1. 2 つ作成`COleDateTime`オブジェクト。

1. 1 つの設定、`COleDateTime`オブジェクトを現在の時刻。

1. いくつかの時間のかかるタスクを実行します。

1. 他の設定`COleDateTime`オブジェクトを現在の時刻。

1. 2 つの時刻の差を取得します。

   [!code-cpp[NVC_ATLMFC_Utilities#178](../atl-mfc-shared/codesnippet/cpp/elapsed-time-automation-classes_1.cpp)]

## <a name="see-also"></a>関連項目

[日付と時刻:オートメーションのサポート](../atl-mfc-shared/date-and-time-automation-support.md)

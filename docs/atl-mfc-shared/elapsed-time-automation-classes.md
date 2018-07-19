---
title: '経過時間: オートメーション クラス |Microsoft ドキュメント'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c1abf6274137ae67b159ad43612d24020a0d14e9
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32354969"
---
# <a name="elapsed-time-automation-classes"></a>経過時間: オートメーション クラス
この手順は、2 つの差を計算する方法を示しています。`CTime`オブジェクトを取得、`CTimeSpan`結果。  
  
#### <a name="to-calculate-elapsed-time"></a>経過時間を計算するには  
  
1.  2 つ作成`COleDateTime`オブジェクト。  
  
2.  いずれかの設定、`COleDateTime`を現在の時刻のオブジェクト。  
  
3.  時間のかかるタスクを実行します。  
  
4.  他の設定`COleDateTime`を現在の時刻のオブジェクト。  
  
5.  2 つの時刻の差を取得します。  
  
     [!code-cpp[NVC_ATLMFC_Utilities#178](../atl-mfc-shared/codesnippet/cpp/elapsed-time-automation-classes_1.cpp)]  
  
## <a name="see-also"></a>関連項目  
 [日付と時刻: オートメーション サポート](../atl-mfc-shared/date-and-time-automation-support.md)


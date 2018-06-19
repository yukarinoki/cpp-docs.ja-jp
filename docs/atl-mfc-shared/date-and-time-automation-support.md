---
title: '日付と時刻: オートメーション サポート |Microsoft ドキュメント'
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
- formatting [Visual Studio], dates
- dates, Automation support
- elapsed time, calculating in Automation
- COleDateTime class, Automation date/time support
- COleDateTimeSpan class, Automation date/time support
- Automation, date and time support
- formatting [Visual Studio], time
- calculations, date and time
- time [Visual Studio], Automation support
ms.assetid: 6eee94c4-943d-4ffc-bf7c-bdda89337ab0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 915bcd5487f423b6240061a0e85f5554a3224397
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32357595"
---
# <a name="date-and-time-automation-support"></a>日付と時刻: オートメーションのサポート
この記事では、日付と時刻の管理に関連するクラス ライブラリのサービスを活用する方法について説明します。 説明する手順は次のとおりです。  
  
-   [現在の時刻を取得します。](../atl-mfc-shared/current-time-automation-classes.md)  
  
-   [経過時間の計算](../atl-mfc-shared/elapsed-time-automation-classes.md)  
  
-   [日付/時刻の文字列形式の書式設定](../atl-mfc-shared/formatting-time-automation-classes.md)  
  
 [COleDateTime](../atl-mfc-shared/reference/coledatetime-class.md)クラスには、日付と時刻の情報を表す方法が用意されています。 提供する粒度よりも広い範囲、 [CTime](../atl-mfc-shared/reference/ctime-class.md)クラスです。 [メンバー](../atl-mfc-shared/reference/coledatetimespan-class.md)クラスは、2 つの違いなど、経過時間を表す`COleDateTime`オブジェクト。  
  
 `COleDateTime`と`COleDateTimeSpan`クラスで使用するように設計されています、`COleVariant`オートメーションで使用されるクラスです。 `COleDateTime` `COleDateTimeSpan`も、MFC データベース プログラミングに便利ですが、日付と時刻の値を操作するときに使用することができます。 `COleDateTime`クラスの値と粒度よりも大きい範囲には、`CTime`よりオブジェクトごとの複数の記憶域が必要です、クラス、`CTime`です。 特別な考慮事項と、基になる操作するときに**日付**型です。 参照してください[DATE 型](../atl-mfc-shared/date-type.md)の実装の詳細については**日付**です。  
  
 `COleDateTime` 9999 100 年 1 月 1 日と 12 月 31 日間の日付を表すオブジェクトを使用できます。 `COleDateTime` オブジェクトには浮動小数点、おおよその解像度が 1 ミリ秒を指定します。 `COleDateTime` 基づく、**日付**MFC のドキュメントで定義されたデータ型[COleDateTime::operator 日付](../atl-mfc-shared/reference/coledatetime-class.md#operator_date)です。 実際の実装**日付**より広い範囲を拡張します。 `COleDateTime`実装では、これらの境界がクラスを使用した作業を容易になります。  
  
 `COleDateTime` ユリウス暦をサポートしていません。 構成のグレゴリオ暦カレンダーは、「時間を戻す 100 年 1 月 1 日に拡張すると見なされます。  
  
 `COleDateTime` 夏時間 (DST) は無視されます。 次のコード例を比較する時間間隔を越える DST 切り替え日付を計算する 2 つの方法: CRT を使用して 1 つと、その他を使用して、`COleDateTime`です。 DST は、4 月の第 2 週と 10 月の 3 つ目のほとんどのロケールに切り替えます。  
  
 最初のメソッドは、2 を設定`CTime`オブジェクト、 *time1*と*time2*、5 年 4 月と年 4 月 6日 standard C 型の構造体を使用して、それぞれ**tm**と`time_t`. 表示されます。 *time1*と*time2*とそれらの間の時間間隔。  
  
 2 番目のメソッドでは、2 つ作成されます`COleDateTime`オブジェクト、`oletime1`と`oletime2`、として同じ日に設定および*time1*と*time2*です。 表示`oletime1`と`oletime2`とそれらの間の時間間隔。  
  
 CRT は正しく 23 時間の差を計算します。 `COleDateTimeSpan` 24 時間の差を計算します。  
  
 正しく使用する日付を表示する例では、末尾付近の回避策が使用されることに注意してください`COleDateTime::Format`です。 サポート技術情報の記事を参照してください"バグ: Format("%D") が失敗した`COleDateTime`と`COleDateTimeSpan`"(Q167338)。  
  
 [!code-cpp[NVC_ATLMFC_Utilities#176](../atl-mfc-shared/codesnippet/cpp/date-and-time-automation-support_1.cpp)]  
  
## <a name="see-also"></a>関連項目  
 [日付と時刻](../atl-mfc-shared/date-and-time.md)


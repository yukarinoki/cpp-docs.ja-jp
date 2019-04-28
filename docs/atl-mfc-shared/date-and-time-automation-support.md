---
title: 日付と時刻:オートメーションのサポート
ms.date: 11/04/2016
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
ms.openlocfilehash: c26534189c7b6f904611e78c5d2d6d0b1d6d7382
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62235915"
---
# <a name="date-and-time-automation-support"></a>日付と時刻:オートメーションのサポート

この記事では、日付と時刻の管理に関連するクラス ライブラリのサービスを活用する方法について説明します。 説明する手順は次のとおりです。

- [現在の時刻を取得します。](../atl-mfc-shared/current-time-automation-classes.md)

- [経過時間の計算](../atl-mfc-shared/elapsed-time-automation-classes.md)

- [日付/時刻の文字列表現の書式設定](../atl-mfc-shared/formatting-time-automation-classes.md)

[COleDateTime](../atl-mfc-shared/reference/coledatetime-class.md)クラスには、日付と時刻の情報を表す方法が用意されています。 粒度の細かいおよびよりも広い範囲を提供します、 [CTime](../atl-mfc-shared/reference/ctime-class.md)クラス。 [COleDateTimeSpan](../atl-mfc-shared/reference/coledatetimespan-class.md)クラスは、2 つの違いなど、経過時間を表します`COleDateTime`オブジェクト。

`COleDateTime`と`COleDateTimeSpan`で使用するクラスが設計されています、`COleVariant`オートメーションで使用されるクラス。 `COleDateTime` `COleDateTimeSpan`も、MFC データベース プログラミングに便利ですが、日付と時刻の値を操作するときに使用することができます。 `COleDateTime`クラスが値よりも細かい粒度の大きい範囲、`CTime`クラスより多くのストレージよりもオブジェクトごとに要する`CTime`します。 特別な考慮事項、基になる日付型を使用する場合。 参照してください[日付型](../atl-mfc-shared/date-type.md)日付の実装の詳細についてはします。

`COleDateTime` 100 年 1 月 1 日と年 12 月 31 日間の日付から 9999 を表すには、オブジェクトを使用できます。 `COleDateTime` オブジェクトには浮動小数点、おおよその解像度が 1 ミリ秒を指定します。 `COleDateTime` MFC のドキュメントで定義されている、日付データ型に基づいて[COleDateTime::operator 日付](../atl-mfc-shared/reference/coledatetime-class.md#operator_date)します。 日付の実際の実装は、これらの境界を超えて拡張します。 `COleDateTime`実装では、これらの境界をクラスを使用して作業を容易にします。

`COleDateTime` ユリウス暦はサポートされません。 構成のグレゴリオ暦カレンダーは、100 年 1 月 1 日にさかのぼって拡張と見なされます。

`COleDateTime` 夏時間 (DST) は無視されます。 次のコード例は、DST 切り替えの日付と交差するまでの時間を計算する 2 つの方法を比較します: 1 つに、CRT を使用して、他の使用`COleDateTime`します。 DST は、4 月に第 2 週、10 月の第 3 のほとんどのロケールで、スイッチします。

最初のメソッドが 2 つを設定`CTime`オブジェクト、 *time1*と*time2*年 4 月 5日および 6 年 4 月に、それぞれ、標準の C 型の構造体を使用して`tm`と`time_t`。 コードを表示*time1*と*time2*とそれらの間のタイム スパン。

2 番目のメソッドでは、2 つ作成されます`COleDateTime`オブジェクト、`oletime1`と`oletime2`、同じ日付として設定しますが、 *time1*と*time2*します。 表示`oletime1`と`oletime2`とそれらの間のタイム スパン。

CRT は正しく 23 時間の差を計算します。 `COleDateTimeSpan` 24 時間の差を計算します。

[!code-cpp[NVC_ATLMFC_Utilities#176](../atl-mfc-shared/codesnippet/cpp/date-and-time-automation-support_1.cpp)]

## <a name="see-also"></a>関連項目

[日付と時刻](../atl-mfc-shared/date-and-time.md)

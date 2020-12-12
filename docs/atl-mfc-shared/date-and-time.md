---
description: '詳細情報: 日付と時刻'
title: 日時
ms.date: 08/13/2019
helpviewer_keywords:
- time, MFC programming
- time
- MFC, date and time
- dates, MFC
ms.assetid: ecf56dc5-d418-4603-ad3e-af7e205a6403
ms.openlocfilehash: 4a8f2d5c9537f07c5d410361e79bf14a12778bc8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97167033"
---
# <a name="date-and-time"></a>日時

MFC では、日付と時刻を操作するためのさまざまな方法がサポートされています。

- Automation [DATE データ型](../atl-mfc-shared/date-type.md)のサポート。 日付、時刻、および日付/時刻の値がサポートされています。 [COleDateTime](../atl-mfc-shared/reference/coledatetime-class.md)クラスと[COleDateTimeSpan](../atl-mfc-shared/reference/coledatetimespan-class.md)クラスは、この機能をカプセル化します。 これらは、オートメーションサポートを使用して [COleVariant](../mfc/reference/colevariant-class.md) クラスで動作します。

- 汎用の時間クラス。 [CTime](../atl-mfc-shared/reference/ctime-class.md)クラスと[CTimeSpan](../atl-mfc-shared/reference/ctimespan-class.md)クラスは、time. H で宣言されている、ANSI 標準時ライブラリに関連付けられている機能の大部分をカプセル化します。

- システムクロックのサポート。 MFC バージョン3.0 では、 `CTime` Win32 `SYSTEMTIME` とデータ型のサポートがに追加されました `FILETIME` 。

## <a name="date-and-time-automation-support"></a>日付と時刻: オートメーションのサポート

[COleDateTime](../atl-mfc-shared/reference/coledatetime-class.md)クラスは、日付と時刻の情報を表す方法を提供します。 より細かい粒度と、 [CTime](../atl-mfc-shared/reference/ctime-class.md) クラスよりも広い範囲を提供します。 [COleDateTimeSpan](../atl-mfc-shared/reference/coledatetimespan-class.md)クラスは、2つのオブジェクトの差など、経過時間を表し `COleDateTime` ます。

クラスとクラスは、 `COleDateTime` `COleDateTimeSpan` クラスで使用するように設計されてい `COleVariant` ます。 `COleDateTime` と `COleDateTimeSpan` は MFC データベースプログラミングにも役立ちますが、日付と時刻の値を操作するときに使用できます。 クラスに `COleDateTime` は、クラスよりも大きな値の範囲と粒度があるクラスがあり `CTime` ますが、オブジェクトごとにより多くのストレージを必要と `CTime` します。 基になる日付型を操作する際には、いくつかの特別な考慮事項もあります。 日付の実装の詳細については、 [日付型](../atl-mfc-shared/date-type.md)を参照してください。

`COleDateTime` オブジェクトを使用して、100年1月1日から9999年12月31日までの日付を表すことができます。 `COleDateTime` オブジェクトは浮動小数点値であり、おおよその解像度は1ミリ秒です。 `COleDateTime` は、MFC ドキュメント「 [COleDateTime:: OPERATOR DATE](../atl-mfc-shared/reference/coledatetime-class.md#operator_date)」で定義されている日付データ型に基づいています。 実際の日付の実装は、これらの範囲を超えて拡張されます。 実装では、 `COleDateTime` クラスの操作を容易にするために、これらの境界が設定されています。

`COleDateTime` ユリウス暦の日付はサポートされていません。 グレゴリオ暦は、時間を100年1月1日に延長することを前提としています。

`COleDateTime` 夏時間 (DST) を無視します。 次のコード例では、2つのメソッドを比較して、DST の切り替え日を超える時間範囲を計算します。1つは CRT を使用し、もう1つはを使用し `COleDateTime` ます。

最初のメソッドは、 `CTime` 標準の C 型構造体とを使用して、 *time1* と *で time2 より* の2つのオブジェクトをそれぞれ4月5日と4月6日に設定し `tm` `time_t` ます。 このコードは、 *time1* と *で time2 より* 、およびそれらの間の時間間隔を表示します。

2番目のメソッドは、とという2つのオブジェクトを作成 `COleDateTime` `oletime1` し、 `oletime2` *time1* および *で time2 より* と同じ日付に設定します。 とと `oletime1` の `oletime2` 間の時間が表示されます。

CRT では、23時間の差が正しく計算されます。 `COleDateTimeSpan` 24時間の差を計算します。

[!code-cpp[NVC_ATLMFC_Utilities#176](../atl-mfc-shared/codesnippet/cpp/date-and-time-automation-support_1.cpp)]

### <a name="get-the-current-time"></a>現在の時刻を取得します。

次の手順は、オブジェクトを作成し、現在の時刻で初期化する方法を示して `COleDateTime` います。

#### <a name="to-get-the-current-time"></a>現在の時刻を取得するには

1. `COleDateTime` オブジェクトを作成します。

1. `GetCurrentTime` を呼び出します。

   [!code-cpp[NVC_ATLMFC_Utilities#177](../atl-mfc-shared/codesnippet/cpp/current-time-automation-classes_1.cpp)]

### <a name="calculate-elapsed-time"></a>経過時間の計算

この手順では、2つのオブジェクトの差を計算し、結果を取得する方法を示し `COleDateTime` `COleDateTimeSpan` ます。

#### <a name="to-calculate-elapsed-time"></a>経過時間を計算するには

1. 2つ `COleDateTime` のオブジェクトを作成します。

1. オブジェクトの1つ `COleDateTime` を現在の時刻に設定します。

1. 時間のかかるタスクを実行します。

1. もう一方の `COleDateTime` オブジェクトを現在の時刻に設定します。

1. 2つの時刻の差を取得します。

   [!code-cpp[NVC_ATLMFC_Utilities#178](../atl-mfc-shared/codesnippet/cpp/elapsed-time-automation-classes_1.cpp)]

### <a name="format-a-time"></a>時刻の書式設定

#### <a name="to-format-a-time"></a>時刻を書式設定するには

`Format` [COleDateTime](../atl-mfc-shared/reference/coledatetime-class.md)または[COleDateTimeSpan](../atl-mfc-shared/reference/coledatetimespan-class.md)のメンバー関数を使用して、時刻または経過時間を表す文字列を作成します。

   [!code-cpp[NVC_ATLMFC_Utilities#179](../atl-mfc-shared/codesnippet/cpp/formatting-time-automation-classes_1.cpp)]

詳細については、「クラス [COleVariant](../mfc/reference/colevariant-class.md)」を参照してください。

## <a name="date-and-time-database-support"></a>日付と時刻: データベース サポート

バージョン4.0 以降では、MFC データベースプログラミングは、日付と時刻のデータを表すために、 [COleDateTime](../atl-mfc-shared/reference/coledatetime-class.md) クラスと [COleDateTimeSpan](../atl-mfc-shared/reference/coledatetimespan-class.md) クラスを使用します。 これらのクラスは、オートメーションでも使用され、 [COleVariant](../mfc/reference/colevariant-class.md)クラスから派生します。 これは、 [CTime](../atl-mfc-shared/reference/ctime-class.md) や [CTimeSpan](../atl-mfc-shared/reference/ctimespan-class.md)よりも、日付と時刻のデータを管理するためのより優れたサポートを提供します。

## <a name="date-and-time-systemtime-support"></a>日付と時刻: SYSTEMTIME サポート

[COleDateTime](../atl-mfc-shared/reference/coledatetime-class.md)クラスには、Win32 からシステム時刻とファイル時刻を受け取るコンストラクターがあります。

Win32 `FILETIME` 構造体は、時間を64ビット値として表します。 これは、構造体よりも内部ストレージの方が便利な形式で `SYSTEMTIME` あり、ファイル作成の時間を表すために Win32 によって使用される形式です。 SYSTEMTIME 構造の詳細については、「 [systemtime](/windows/desktop/api/minwinbase/ns-minwinbase-systemtime)」を参照してください。 FILETIME 構造体の詳細については、「 [filetime](/windows/desktop/api/minwinbase/ns-minwinbase-filetime)」を参照してください。

## <a name="see-also"></a>関連項目

[いう](../mfc/mfc-concepts.md)\
[MFC の一般的なトピック](../mfc/general-mfc-topics.md)

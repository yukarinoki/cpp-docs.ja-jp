---
title: CFileTime クラス
ms.date: 10/18/2018
f1_keywords:
- CFileTime
- ATLTIME/ATL::CFileTime
- ATLTIME/ATL::CFileTime::CFileTime
- ATLTIME/ATL::CFileTime::GetCurrentTime
- ATLTIME/ATL::CFileTime::GetTime
- ATLTIME/ATL::CFileTime::LocalToUTC
- ATLTIME/ATL::CFileTime::SetTime
- ATLTIME/ATL::CFileTime::UTCToLocal
- ATLTIME/ATL::CFileTime::Day
- ATLTIME/ATL::CFileTime::Hour
- ATLTIME/ATL::CFileTime::Millisecond
- ATLTIME/ATL::CFileTime::Minute
- ATLTIME/ATL::CFileTime::Second
- ATLTIME/ATL::CFileTime::Week
helpviewer_keywords:
- CFileTime class
- shared classes, CFileTime
ms.assetid: 1a358a65-1383-4124-b0d4-59b026e6860f
ms.openlocfilehash: bc9fe752898a5dfde2631352abd8c3cf5f8b378c
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81317892"
---
# <a name="cfiletime-class"></a>CFileTime クラス

このクラスには、ファイルに関連付けられた日付と時刻の値を管理するためのメソッドが用意されています。

## <a name="syntax"></a>構文

```
class CFileTime :  public FILETIME
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[ファイルタイム::Cファイルタイム](#cfiletime)|コンストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[ファイルタイム::ゲットカレントタイム](#getcurrenttime)|現在のシステムの日付と時刻`CFileTime`を表すオブジェクトを取得します。|
|[ファイルタイム::ゲットタイム](#gettime)|`CFileTime`オブジェクトから時刻を取得します。|
|[ファイルタイム::ローカルトフ](#localtoutc)|世界協定時刻 (UTC) に基づいて、ローカル ファイルの時刻をファイル時刻に変換します。|
|[ファイルタイム::セットタイム](#settime)|`CFileTime`オブジェクトによって格納される日付と時刻を設定します。|
|[ファイルタイム::UTCローカル](#utctolocal)|世界協定時刻 (UTC) に基づく時刻をローカル ファイル時刻に変換します。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[Cファイルタイム::演算子 -](#operator_-)|この演算子は、 オブジェクト`CFileTime``CFileTimeSpan`に対して減算を実行するために使用されます。|
|[Cファイルタイム::演算子 !=](#operator_neq)|この演算子は、2`CFileTime`つのオブジェクトが不等比較を行います。|
|[Cファイルタイム::演算子 +](#operator_add)|この演算子は、`CFileTimeSpan` オブジェクトで加算を実行するために使用します。|
|[Cファイルタイム::演算子 +=](#operator_add_eq)|この演算子は、`CFileTimeSpan` オブジェクトで加算を実行し、結果を現在のオブジェクトに代入するために使用します。|
|[Cファイルタイム::演算子&lt;](#operator_lt)|この演算子は、2 つの `CFileTime` オブジェクトを比較して、小さい方を決定します。|
|[Cファイルタイム::演算子&lt;=](#operator_lt_eq)|この演算子では、2 つの `CFileTime` オブジェクトを比較して、等しいかどうか、または小さい方を決定します。|
|[Cファイルタイム::演算子 =](#operator_eq)|代入演算子。|
|[Cファイルタイム::演算子 -=](#operator_-_eq)|この演算子は、オブジェクトに対して減算`CFileTimeSpan`を実行し、その結果を現在のオブジェクトに割り当てる場合に使用します。|
|[Cファイルタイム::演算子 ==](#operator_eq_eq)|この演算子は、2 つの `CFileTime` オブジェクトが等しいかどうかを比較します。|
|[Cファイルタイム::演算子&gt;](#operator_gt)|この演算子は、2 つの `CFileTime` オブジェクトを比較して、大きい方を決定します。|
|[Cファイルタイム::演算子&gt;=](#operator_gt_eq)|この演算子は、2 つの `CFileTime` オブジェクトを比較して、等しいかどうか、または大きい方を決定します。|

### <a name="public-constants"></a>パブリック定数

|名前|説明|
|----------|-----------------|
|[ファイルタイム::D](#day)|1 日を構成する 100 ナノ秒の間隔の数を格納する静的データ メンバー。|
|[ファイルタイム::時間](#hour)|1 時間を構成する 100 ナノ秒間隔の数を格納する静的データ メンバー。|
|[Cファイル時間::ミリ秒](#millisecond)|1 ミリ秒を構成する 100 ナノ秒の間隔の数を格納する静的データ メンバー。|
|[ファイルタイム::分](#minute)|1 分を構成する 100 ナノ秒間隔の数を格納する静的データ メンバー。|
|[ファイルタイム::2番目](#second)|1 秒を構成する 100 ナノ秒の間隔の数を格納する静的データ メンバー。|
|[ファイルタイム::週](#week)|1 週間を構成する 100 ナノ秒間隔の数を格納する静的データ メンバー。|

## <a name="remarks"></a>解説

このクラスは、ファイルの作成、アクセス、および変更に関連付けられた日付と時刻の値を管理するためのメソッドを提供します。 このクラスのメソッドとデータは、相対時間値を扱`CFileTimeSpan`うオブジェクトと組み合わせて頻繁に使用されます。

日付と時刻の値は、1601 年 1 月 1 日以降の 100 ナノ秒間隔の数を表す 64 ビット値として格納されます。 これは世界協定時刻 (UTC) 形式です。

計算を簡略化するために、次の静的 const メンバー変数が提供されています。

|メンバー変数|100ナノ秒の間隔の数|
|---------------------|-----------------------------------------|
|Millisecond|10,000|
|秒|ミリ\*秒 1,000|
|分|セカンド\*60|
|時|ミニ\*ッツ 60|
|日|24時間\*|
|Week|7\*日目|

**注**すべてのファイルシステムが作成時刻と最終アクセス時刻を記録できるわけではありません。 たとえば、Windows NT FAT ファイル システムでは、作成時間の解像度は 10 ミリ秒、書き込み時間の解像度は 2 秒、アクセス時間の解像度は 1 日 (アクセス日) です。 NTFS では、アクセス時間の解像度は 1 時間です。 さらに、FAT は時刻をディスク上のローカル時刻に記録しますが、NTFS では時刻が UTC でディスクに記録されます。 詳細については、「[ファイル時間」を](/windows/win32/SysInfo/file-times)参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

`FILETIME`

`CFileTime`

## <a name="requirements"></a>必要条件

**ヘッダー:** atltime.h

## <a name="cfiletimecfiletime"></a><a name="cfiletime"></a>ファイルタイム::Cファイルタイム

コンストラクターです。

```
CFileTime() throw();
CFileTime(const FILETIME& ft) throw();
CFileTime(ULONGLONG nTime) throw();
```

### <a name="parameters"></a>パラメーター

*フィート*<br/>
[ファイルタイム](/windows/win32/api/minwinbase/ns-minwinbase-filetime)構造体。

*n時間*<br/>
64 ビット値で表される日付と時刻。

### <a name="remarks"></a>解説

オブジェクト`CFileTime`は、`FILETIME`構造体の既存の日付と時刻を使用して作成することも、64 ビット値 (ローカルまたは協定世界時 (UTC) の時刻形式) で表すこともできます。 既定のコンストラクターは、時刻を 0 に設定します。

## <a name="cfiletimeday"></a><a name="day"></a>ファイルタイム::D

1 日を構成する 100 ナノ秒の間隔の数を格納する静的データ メンバー。

```
static const ULONGLONG Day = Hour* 24;
```

### <a name="example"></a>例

[「CFileTime::ミリ秒](#millisecond)」の例を参照してください。

## <a name="cfiletimegetcurrenttime"></a><a name="getcurrenttime"></a>ファイルタイム::ゲットカレントタイム

現在のシステムの日付と時刻`CFileTime`を表すオブジェクトを取得します。

```
static CFileTime GetCurrentTime() throw();
```

### <a name="return-value"></a>戻り値

現在のシステムの日付と時刻を世界協定時刻 (UTC) 形式で返します。

### <a name="example"></a>例

[!code-cpp[NVC_MFCFiles#41](../../atl-mfc-shared/reference/codesnippet/cpp/cfiletime-class_1.cpp)]

## <a name="cfiletimegettime"></a><a name="gettime"></a>ファイルタイム::ゲットタイム

`CFileTime`オブジェクトから時刻を取得します。

```
ULONGLONG GetTime() const throw();
```

### <a name="return-value"></a>戻り値

日付と時刻を 64 ビットの数値で返します。

## <a name="cfiletimehour"></a><a name="hour"></a>ファイルタイム::時間

1 時間を構成する 100 ナノ秒間隔の数を格納する静的データ メンバー。

```
static const ULONGLONG Hour = Minute* 60;
```

### <a name="example"></a>例

[「CFileTime::ミリ秒](#millisecond)」の例を参照してください。

## <a name="cfiletimelocaltoutc"></a><a name="localtoutc"></a>ファイルタイム::ローカルトフ

世界協定時刻 (UTC) に基づいて、ローカル ファイルの時刻をファイル時刻に変換します。

```
CFileTime LocalToUTC() const throw();
```

### <a name="return-value"></a>戻り値

時刻を`CFileTime`含むオブジェクトを UTC 形式で返します。

### <a name="example"></a>例

[CFileTime::UTCToLocal](#utctolocal)の例を参照してください。

## <a name="cfiletimemillisecond"></a><a name="millisecond"></a>Cファイル時間::ミリ秒

1 ミリ秒を構成する 100 ナノ秒の間隔の数を格納する静的データ メンバー。

```
static const ULONGLONG Millisecond = 10000;
```

### <a name="example"></a>例

[!code-cpp[NVC_MFCFiles#44](../../atl-mfc-shared/reference/codesnippet/cpp/cfiletime-class_2.cpp)]

## <a name="cfiletimeminute"></a><a name="minute"></a>ファイルタイム::分

1 分を構成する 100 ナノ秒間隔の数を格納する静的データ メンバー。

```
static const ULONGLONG Minute = Second* 60;
```

### <a name="example"></a>例

[「CFileTime::ミリ秒](#millisecond)」の例を参照してください。

## <a name="cfiletimeoperator--"></a><a name="operator_-"></a>Cファイルタイム::演算子 -

この演算子は、 オブジェクト`CFileTime``CFileTimeSpan`に対して減算を実行するために使用されます。

```
CFileTime operator-(CFileTimeSpan span) const throw();
CFileTimeSpan operator-(CFileTime ft) const throw();
```

### <a name="parameters"></a>パラメーター

*スパン*<br/>
`CFileTimeSpan` オブジェクト。

*フィート*<br/>
`CFileTime` オブジェクト。

### <a name="return-value"></a>戻り値

2`CFileTime`つのオブジェクトの`CFileTimeSpan`時間差の結果を表すオブジェクトまたはオブジェクトを返します。

## <a name="cfiletimeoperator-"></a><a name="operator_neq"></a>Cファイルタイム::演算子 !=

この演算子は、2`CFileTime`つのオブジェクトが不等比較を行います。

```
bool operator!=(CFileTime ft) const throw();
```

### <a name="parameters"></a>パラメーター

*フィート*<br/>
比較される `CFileTime` オブジェクト。

### <a name="return-value"></a>戻り値

比較対象の項目がオブジェクトと等しくない場合は`CFileTime`TRUE を返し、それ以外の場合は FALSE を返します。

## <a name="cfiletimeoperator-"></a><a name="operator_add"></a>Cファイルタイム::演算子 +

この演算子は、`CFileTimeSpan` オブジェクトで加算を実行するために使用します。

```
CFileTime operator+(CFileTimeSpan span) const throw();
```

### <a name="parameters"></a>パラメーター

*スパン*<br/>
`CFileTimeSpan` オブジェクト。

### <a name="return-value"></a>戻り値

元の`CFileTime`時刻の結果に相対時刻を加算したオブジェクトを返します。

## <a name="cfiletimeoperator-"></a><a name="operator_add_eq"></a>Cファイルタイム::演算子 +=

この演算子は、`CFileTimeSpan` オブジェクトで加算を実行し、結果を現在のオブジェクトに代入するために使用します。

```
CFileTime& operator+=(CFileTimeSpan span) throw();
```

### <a name="parameters"></a>パラメーター

*スパン*<br/>
`CFileTimeSpan` オブジェクト。

### <a name="return-value"></a>戻り値

元の時刻`CFileTime`と相対時刻の結果を表す、更新されたオブジェクトを返します。

## <a name="cfiletimeoperator-lt"></a><a name="operator_lt"></a>Cファイルタイム::演算子&lt;

この演算子は、2 つの `CFileTime` オブジェクトを比較して、小さい方を決定します。

```
bool operator<(CFileTime ft) const throw();
```

### <a name="parameters"></a>パラメーター

*フィート*<br/>
比較される `CFileTime` オブジェクト。

### <a name="return-value"></a>戻り値

1 番目のオブジェクトが 2 番目のオブジェクトより少ない場合 (時間の前に) TRUE を返し、それ以外の場合は FALSE を返します。

### <a name="example"></a>例

[!code-cpp[NVC_MFCFiles#43](../../atl-mfc-shared/reference/codesnippet/cpp/cfiletime-class_3.cpp)]

## <a name="cfiletimeoperator-lt"></a><a name="operator_lt_eq"></a>Cファイルタイム::演算子&lt;=

この演算子では、2 つの `CFileTime` オブジェクトを比較して、等しいかどうか、または小さい方を決定します。

```
bool operator<=(CFileTime ft) const throw();
```

### <a name="parameters"></a>パラメーター

*フィート*<br/>
比較される `CFileTime` オブジェクト。

### <a name="return-value"></a>戻り値

最初のオブジェクトが 2 番目のオブジェクトより小さい場合 (時刻の前) または 2 番目のオブジェクトと等しい場合は TRUE を返し、それ以外の場合は FALSE を返します。

## <a name="cfiletimeoperator-"></a><a name="operator_eq"></a>Cファイルタイム::演算子 =

代入演算子。

```
CFileTime& operator=(const FILETIME& ft) throw();
```

### <a name="parameters"></a>パラメーター

*フィート*<br/>
新`CFileTime`しい日時を含むオブジェクト。

### <a name="return-value"></a>戻り値

更新された`CFileTime`オブジェクトを返します。

## <a name="cfiletimeoperator--"></a><a name="operator_-_eq"></a>Cファイルタイム::演算子 -=

この演算子は、オブジェクトに対して減算`CFileTimeSpan`を実行し、その結果を現在のオブジェクトに割り当てる場合に使用します。

```
CFileTime& operator-=(CFileTimeSpan span) throw();
```

### <a name="parameters"></a>パラメーター

*スパン*<br/>
減`CFileTimeSpan`算する相対時間を含むオブジェクト。

### <a name="return-value"></a>戻り値

更新された`CFileTime`オブジェクトを返します。

## <a name="cfiletimeoperator-"></a><a name="operator_eq_eq"></a>Cファイルタイム::演算子 ==

この演算子は、2 つの `CFileTime` オブジェクトが等しいかどうかを比較します。

```
bool operator==(CFileTime ft) const throw();
```

### <a name="parameters"></a>パラメーター

*フィート*<br/>
比較対象の `CFileTime` オブジェクト。

### <a name="return-value"></a>戻り値

オブジェクトが等しい場合は TRUE を返し、それ以外の場合は FALSE を返します。

## <a name="cfiletimeoperator-gt"></a><a name="operator_gt"></a>Cファイルタイム::演算子&gt;

この演算子は、2 つの `CFileTime` オブジェクトを比較して、大きい方を決定します。

```
bool operator>(CFileTime ft) const throw();
```

### <a name="parameters"></a>パラメーター

*フィート*<br/>
比較される `CFileTime` オブジェクト。

### <a name="return-value"></a>戻り値

最初のオブジェクトが 2 番目のオブジェクトより大きい場合 (後で) FALSE を返します。

## <a name="cfiletimeoperator-gt"></a><a name="operator_gt_eq"></a>Cファイルタイム::演算子&gt;=

この演算子は、2 つの `CFileTime` オブジェクトを比較して、等しいかどうか、または大きい方を決定します。

```
bool operator>=(CFileTime ft) const throw();
```

### <a name="parameters"></a>パラメーター

*フィート*<br/>
比較される `CFileTime` オブジェクト。

### <a name="return-value"></a>戻り値

最初のオブジェクトが 2 番目のオブジェクトより大きいか、2 番目のオブジェクトと等しい場合は TRUE を返し、それ以外の場合は FALSE を返します。

## <a name="cfiletimesecond"></a><a name="second"></a>ファイルタイム::2番目

1 日を構成する 100 ナノ秒の間隔の数を格納する静的データ メンバー。

```
static const ULONGLONG Second = Millisecond* 1000;
```

### <a name="example"></a>例

[「CFileTime::ミリ秒](#millisecond)」の例を参照してください。

## <a name="cfiletimesettime"></a><a name="settime"></a>ファイルタイム::セットタイム

`CFileTime`オブジェクトによって格納される日付と時刻を設定します。

```
void SetTime(ULONGLONG nTime) throw();
```

### <a name="parameters"></a>パラメーター

*n時間*<br/>
日付と時刻を表す 64 ビット値 (ローカルまたは協定世界時 (UTC) 形式)。

## <a name="cfiletimeutctolocal"></a><a name="utctolocal"></a>ファイルタイム::UTCローカル

世界協定時刻 (UTC) に基づく時刻をローカル ファイル時刻に変換します。

```
CFileTime UTCToLocal() const throw();
```

### <a name="return-value"></a>戻り値

時刻を`CFileTime`格納しているオブジェクトをローカル ファイル時刻形式で返します。

### <a name="example"></a>例

[!code-cpp[NVC_MFCFiles#42](../../atl-mfc-shared/reference/codesnippet/cpp/cfiletime-class_4.cpp)]

## <a name="cfiletimeweek"></a><a name="week"></a>ファイルタイム::週

1 週間を構成する 100 ナノ秒間隔の数を格納する静的データ メンバー。

```
static const ULONGLONG Week = Day* 7;
```

### <a name="example"></a>例

[「CFileTime::ミリ秒](#millisecond)」の例を参照してください。

## <a name="see-also"></a>関連項目

[FILETIME](/windows/win32/api/minwinbase/ns-minwinbase-filetime)<br/>
[クラス](../../atl-mfc-shared/reference/cfiletimespan-class.md)<br/>
[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[ATL/MFC 共有クラス](../../atl-mfc-shared/atl-mfc-shared-classes.md)

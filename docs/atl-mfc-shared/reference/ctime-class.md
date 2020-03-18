---
title: CTime クラス
ms.date: 10/18/2018
f1_keywords:
- ATLTIME/ATL::CTime
- ATLTIME/ATL::CTime::CTime
- ATLTIME/ATL::CTime::Format
- ATLTIME/ATL::CTime::FormatGmt
- ATLTIME/ATL::CTime::GetAsDBTIMESTAMP
- ATLTIME/ATL::CTime::GetAsSystemTime
- ATLTIME/ATL::CTime::GetCurrentTime
- ATLTIME/ATL::CTime::GetDay
- ATLTIME/ATL::CTime::GetDayOfWeek
- ATLTIME/ATL::CTime::GetGmtTm
- ATLTIME/ATL::CTime::GetHour
- ATLTIME/ATL::CTime::GetLocalTm
- ATLTIME/ATL::CTime::GetMinute
- ATLTIME/ATL::CTime::GetMonth
- ATLTIME/ATL::CTime::GetSecond
- ATLTIME/ATL::CTime::GetTime
- ATLTIME/ATL::CTime::GetYear
- ATLTIME/ATL::CTime::Serialize64
helpviewer_keywords:
- CTime class
- shared classes, CTime
ms.assetid: 0a299544-485b-48dc-9d3c-fdc30f57d612
ms.openlocfilehash: a1d62cca42e3110974b07dae143bafcf807fed7e
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/17/2020
ms.locfileid: "79440484"
---
# <a name="ctime-class"></a>CTime クラス

絶対時刻と日付を表します。

## <a name="syntax"></a>構文

```
class CTime
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|Name|説明|
|----------|-----------------|
|[CTime:: CTime](#ctime)|`CTime` オブジェクトをさまざまな方法で構築します。|

### <a name="public-methods"></a>パブリック メソッド

|Name|説明|
|----------|-----------------|
|[CTime:: 形式](#format)|ローカルタイムゾーンに基づいて、`CTime` オブジェクトを書式設定された文字列に変換します。|
|[CTime:: FormatGmt](#formatgmt)|`CTime` オブジェクトを UTC に基づいて書式設定された文字列に変換します。|
|[CTime:: GetAsDBTIMESTAMP](#getasdbtimestamp)|`CTime` オブジェクトに格納されている時刻情報を、Win32 と互換性のある DBTIMESTAMP 構造体に変換します。|
|[CTime:: GetAsSystemTime](#getassystemtime)|`CTime` オブジェクトに格納されている時刻情報を、Win32 互換の[SYSTEMTIME](/windows/win32/api/minwinbase/ns-minwinbase-systemtime)構造体に変換します。|
|[CTime:: GetCurrentTime](#getcurrenttime)|現在の時刻 (静的メンバー関数) を表す `CTime` オブジェクトを作成します。|
|[CTime:: GetDay](#getday)|`CTime` オブジェクトによって表される日を返します。|
|[CTime:: GetDayOfWeek](#getdayofweek)|`CTime` オブジェクトで表される曜日を返します。|
|[CTime:: GetGmtTm](#getgmttm)|UTC に基づいて、`CTime` オブジェクトをコンポーネントに分割します。|
|[CTime:: Gethour:](#gethour)|`CTime` オブジェクトで表される時間を返します。|
|[CTime:: GetLocalTm](#getlocaltm)|ローカルタイムゾーンに基づいて、`CTime` オブジェクトをコンポーネントに分割します。|
|[CTime:: GetMinute](#getminute)|`CTime` オブジェクトによって表される分を返します。|
|[CTime:: GetMonth](#getmonth)|`CTime` オブジェクトで表される月を返します。|
|[CTime:: GetSecond](#getsecond)|`CTime` オブジェクトによって表される秒の値を返します。|
|[CTime:: GetTime](#gettime)|指定された `CTime` オブジェクトの **__time64_t**値を返します。|
|[CTime:: GetYear](#getyear)|`CTime` オブジェクトによって表される年を返します。|
|[CTime:: Serialize64](#serialize64)|アーカイブとの間でデータをシリアル化します。|

### <a name="operators"></a>演算子

|||
|-|-|
|[演算子 +-](#operator_add_-)|これらの演算子は、`CTimeSpan` オブジェクトと `CTime` オブジェクトを加算および減算します。|
|[operator + =、-=](#operator_add_eq_-_eq)|これらの演算子は、この `CTime` オブジェクトとの間で `CTimeSpan` オブジェクトを加算および減算します。|
|[operator =](#operator_eq)|代入演算子。|
|[operator = =、< など](#ctime_comparison_operators)|比較演算子。|

## <a name="remarks"></a>コメント

`CTime` には基底クラスがありません。

`CTime` 値は世界協定時刻 (UTC) に基づいています。協定世界時 (グリニッジ標準時、GMT) と同等です。 タイムゾーンの決定方法については、「[時間管理](../../c-runtime-library/time-management.md)」を参照してください。

`CTime` オブジェクトを作成する場合は、`nDST` パラメーターを0に設定して、標準時間が有効であることを示します。または、夏時間が有効であることを示す0より大きい値を指定するか、または標準時間と夏時間のどちらを使用するかを C ランタイムライブラリコードで計算するには0より大きい値を設定します。 `tm_isdst` は必須フィールドです。 値が設定されていない場合、その値は未定義で、 [mktime](../../c-runtime-library/reference/mktime-mktime32-mktime64.md)からの戻り値は予測できません。 `timeptr` が[asctime_s](../../c-runtime-library/reference/asctime-s-wasctime-s.md)、 [_gmtime_s](../../c-runtime-library/reference/gmtime-s-gmtime32-s-gmtime64-s.md)、または[localtime_s](../../c-runtime-library/reference/localtime-s-localtime32-s-localtime64-s.md)の前回の呼び出しによって返された tm 構造体を指している場合、`tm_isdst` フィールドには正しい値が格納されます。

コンパニオンクラス[CTimeSpan](../../atl-mfc-shared/reference/ctimespan-class.md)は、時間間隔を表します。

`CTime` クラスと `CTimeSpan` クラスは、派生用には設計されていません。 仮想関数がないため、`CTime` オブジェクトと `CTimeSpan` オブジェクトのサイズは完全に8バイトになります。 ほとんどのメンバー関数はインラインです。

> [!NOTE]
>  上限の日付は12/31/3000 です。 下限は 1/1/1970 12:00:00 AM GMT です。

`CTime`の使用方法の詳細については、「ランタイムライブラリリファレンス」の「[日付と時刻](../../atl-mfc-shared/date-and-time.md)」および「[時刻管理](../../c-runtime-library/time-management.md)」を参照してください。

> [!NOTE]
>  `CTime` 構造が MFC 7.1 から MFC 8.0 に変更されました。 MFC 8.0 以降のバージョンで**演算子 < <** を使用して `CTime` 構造をシリアル化した場合、その結果のファイルは以前のバージョンの mfc では読み取ることができません。

## <a name="requirements"></a>要件

**ヘッダー:** atltime. h

##  <a name="ctime_comparison_operators"></a>CTime 比較演算子

比較演算子。

```
bool operator==(CTime time) const throw();
bool operator!=(CTime time) const throw();
bool operator<(CTime time) const throw();
bool operator>(CTime time) const throw();
bool operator<=(CTime time) const throw();
bool operator>=(CTime time) const throw();
```

### <a name="parameters"></a>パラメーター

*time*<br/>
比較される `CTime` オブジェクト。

### <a name="return-value"></a>戻り値

これらの演算子は2つの絶対時刻を比較し、条件が true の場合は TRUE を返します。それ以外の場合は FALSE。

### <a name="example"></a>例

[!code-cpp[NVC_ATLMFC_Utilities#161](../../atl-mfc-shared/codesnippet/cpp/ctime-class_1.cpp)]

##  <a name="ctime"></a>CTime:: CTime

指定した時間で初期化された新しい `CTime` オブジェクトを作成します。

```
CTime() throw();
CTime(__time64_t time) throw();
CTime(int nYear, int nMonth, int nDay,
      int nHour, int nMin, int nSec, int nDST = -1);
CTime(WORD wDosDate, WORD wDosTime, int nDST = -1);
CTime(const SYSTEMTIME& st, int nDST = - 1) throw();
CTime(const FILETIME& ft, int nDST = - 1);
CTime(const DBTIMESTAMP& dbts, int nDST = -1) throw();
```

### <a name="parameters"></a>パラメーター

*timeSrc*<br/>
既に存在する `CTime` オブジェクトを示します。

*time*<br/>
UTC 1970 年1月1日以降の秒数で `__time64_t` 時刻値。 これは、現地時刻に調整されることに注意してください。 たとえば、ニューヨークにいて、パラメーター0を渡すことによって `CTime` オブジェクトを作成した場合、 [CTime:: GetMonth](#getmonth)は12を返します。

*Nyear*、 *nyear*、 *nyear*、 *nyear*、 *nyear*、 *nSec*<br/>
新しい `CTime` オブジェクトにコピーする日付と時刻の値を示します。

*nDST*<br/>
夏時間が有効かどうかを示します。 次の3つの値のいずれかを指定できます。

- *nDST*を 0standard time に設定すると有効になります。

- *nDST*は、0より大きな値に設定されています。

- *NDST*は既定値の0未満の値に設定されます。 標準時間と夏時間のどちらを有効にするかを自動的に計算します。

*Wdosdate*、 *wDosTime*<br/>
日付/時刻値に変換され、新しい `CTime` オブジェクトにコピーされる MS-DOS の日付と時刻の値。

*&*<br/>
日付/時刻値に変換され、新しい `CTime` オブジェクトにコピーされる[SYSTEMTIME](/windows/win32/api/minwinbase/ns-minwinbase-systemtime)構造体。

*cm*<br/>
日付/時刻値に変換され、新しい `CTime` オブジェクトにコピーされる[FILETIME](/windows/win32/api/minwinbase/ns-minwinbase-filetime)構造体。

*dbts*<br/>
現在の現地時刻を格納している DBTIMESTAMP 構造体への参照。

### <a name="remarks"></a>コメント

各コンストラクターについて以下に説明します。

- `CTime();` は、初期化されていない `CTime` オブジェクトを構築します。 このコンストラクターを使用すると `CTime` オブジェクト配列を定義できます。 を使用する前に、有効な時刻でこのような配列を初期化する必要があります。

- `CTime( const CTime& );` 別の `CTime` 値から `CTime` オブジェクトを構築します。

- `CTime( __time64_t );` は、 **__time64_t**型から `CTime` オブジェクトを構築します。 このコンストラクターは UTC 時刻を想定し、結果を格納する前に結果を現地時刻に変換します。

- `CTime( int, int, ...);` は、各コンポーネントが次の範囲に制限されているローカルタイムコンポーネントから `CTime` オブジェクトを構築します。

   |コンポーネント|[範囲]|
   |---------------|-----------|
   |*nYear*|1970-3000|
   |*nMonth*|1-12|
   |*nDay*|1-31|
   |*nHour*|0-23|
   |*N1 日*|0-59|
   |*nSec*|0-59|

   このコンストラクターは、UTC への適切な変換を行います。 1つ以上の時間コンポーネントが範囲外の場合、Microsoft Foundation Class ライブラリのデバッグバージョンはアサートします。 を呼び出す前に、引数を検証する必要があります。 このコンストラクターには、ローカル時刻が必要です。

- `CTime( WORD, WORD );` は、指定された MS-DOS 日時値から `CTime` オブジェクトを構築します。 このコンストラクターには、ローカル時刻が必要です。

- `CTime( const SYSTEMTIME& );` は、`SYSTEMTIME` 構造体から `CTime` オブジェクトを構築します。 このコンストラクターには、ローカル時刻が必要です。

- `CTime( const FILETIME& );` は、`FILETIME` 構造体から `CTime` オブジェクトを構築します。 `CTime FILETIME` 初期化を直接使用しない可能性があります。 `CFile` オブジェクトを使用してファイルを操作する場合、`CFile::GetStatus` は `FILETIME` 構造で初期化された `CTime` オブジェクトを介してファイルのタイムスタンプを取得します。 このコンストラクターは、UTC に基づく時間を想定しており、結果を格納する前に、値を自動的に現地時刻に変換します。

   > [!NOTE]
   > `DBTIMESTAMP` パラメーターを使用するコンストラクターは、OLEDB. h が含まれている場合にのみ使用できます。

詳細については、Windows SDK の「 [SYSTEMTIME](/windows/win32/api/minwinbase/ns-minwinbase-systemtime)と[FILETIME](/windows/win32/api/minwinbase/ns-minwinbase-filetime)の構造」を参照してください。 Windows SDK にある[MS-DOS の日付と時刻](/windows/win32/SysInfo/ms-dos-date-and-time)のエントリも参照してください。

### <a name="example"></a>例

[!code-cpp[NVC_ATLMFC_Utilities#148](../../atl-mfc-shared/codesnippet/cpp/ctime-class_2.cpp)]

##  <a name="format"></a>CTime:: 形式

日付/時刻値の書式設定された表現を作成するには、このメンバー関数を呼び出します。

```
CString Format(LPCTSTR pszFormat) const;
CString Format(UINT nFormatID) const;
```

### <a name="parameters"></a>パラメーター

*pszFormat*<br/>
`printf` 書式設定文字列に類似した書式設定文字列。 先頭にパーセント (`%`) 記号が付いた書式指定コードは、対応する `CTime` コンポーネントに置き換えられます。 書式設定文字列内のその他の文字は、返された文字列にそのままコピーされます。 書式設定コードの一覧については、「ランタイム関数[strftime](../../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md) 」を参照してください。

*nFormatID*<br/>
この形式を識別する文字列の ID。

### <a name="return-value"></a>戻り値

書式設定された時刻を格納している[CString](../../atl-mfc-shared/reference/cstringt-class.md) 。

### <a name="remarks"></a>コメント

この `CTime` オブジェクトの状態が null の場合、戻り値は空の文字列になります。

このメソッドは、書式設定する日付/時刻の値が、1970年1月1日午前0時 (UTC) の3000世界協定時刻 (UTC) からの範囲外である場合に、例外をスローします。

### <a name="example"></a>例

[!code-cpp[NVC_ATLMFC_Utilities#149](../../atl-mfc-shared/codesnippet/cpp/ctime-class_3.cpp)]

##  <a name="formatgmt"></a>CTime:: FormatGmt

この `CTime` オブジェクトに対応する書式設定された文字列を生成します。

```
CString FormatGmt(LPCTSTR pszFormat) const;
CString FormatGmt(UINT nFormatID) const;
```

### <a name="parameters"></a>パラメーター

*pszFormat*<br/>
`printf` 書式設定文字列に類似した書式設定文字列を指定します。 詳細については、ランタイム関数[strftime](../../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md)を参照してください。

*nFormatID*<br/>
この形式を識別する文字列の ID。

### <a name="return-value"></a>戻り値

書式設定された時刻を格納している[CString](../../atl-mfc-shared/reference/cstringt-class.md) 。

### <a name="remarks"></a>コメント

時刻値は変換されないため、UTC が反映されます。

このメソッドは、書式設定する日付/時刻の値が、1970年1月1日午前0時 (UTC) の3000世界協定時刻 (UTC) からの範囲外である場合に、例外をスローします。

### <a name="example"></a>例

[CTime:: Format](#format)の例を参照してください。

##  <a name="getasdbtimestamp"></a>CTime:: GetAsDBTIMESTAMP

このメンバー関数を呼び出して、`CTime` オブジェクトに格納されている時刻情報を Win32 互換の DBTIMESTAMP 構造体に変換します。

```
bool GetAsDBTIMESTAMP(DBTIMESTAMP& dbts) const throw();
```

### <a name="parameters"></a>パラメーター

*dbts*<br/>
現在の現地時刻を格納している DBTIMESTAMP 構造体への参照。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>コメント

結果として得られた時間を参照された*dbts*構造体に格納します。 この関数によって初期化される `DBTIMESTAMP` データ構造体は、`fraction` メンバーが0に設定されます。

### <a name="example"></a>例

[!code-cpp[NVC_ATLMFC_Utilities#150](../../atl-mfc-shared/codesnippet/cpp/ctime-class_4.cpp)]

##  <a name="getassystemtime"></a>CTime:: GetAsSystemTime

このメンバー関数を呼び出して、`CTime` オブジェクトに格納されている時刻情報を Win32 互換の[SYSTEMTIME](/windows/win32/api/minwinbase/ns-minwinbase-systemtime)構造体に変換します。

```
bool GetAsSystemTime(SYSTEMTIME& st) const throw();
```

### <a name="parameters"></a>パラメーター

*timeDest*<br/>
`CTime` オブジェクトの変換された日付/時刻値を保持する[SYSTEMTIME](/windows/win32/api/minwinbase/ns-minwinbase-systemtime)構造体への参照。

### <a name="return-value"></a>戻り値

成功した場合は TRUE、それ以外の場合は FALSE。

### <a name="remarks"></a>コメント

`GetAsSystemTime` は、参照された*Timedest*構造体に結果の時間を格納します。 この関数によって初期化される `SYSTEMTIME` データ構造体は、`wMilliseconds` メンバーが0に設定されます。

### <a name="example"></a>例

[!code-cpp[NVC_ATLMFC_Utilities#151](../../atl-mfc-shared/codesnippet/cpp/ctime-class_5.cpp)]

##  <a name="getcurrenttime"></a>CTime:: GetCurrentTime

現在の時刻を表す `CTime` オブジェクトを返します。

```
static CTime WINAPI GetCurrentTime() throw();
```

### <a name="remarks"></a>コメント

現在のシステム日付と時刻を世界協定時刻 (UTC) で返します。

### <a name="example"></a>例

[!code-cpp[NVC_ATLMFC_Utilities#152](../../atl-mfc-shared/codesnippet/cpp/ctime-class_6.cpp)]

##  <a name="getday"></a>CTime:: GetDay

`CTime` オブジェクトによって表される日を返します。

```
int GetDay() const throw();
```

### <a name="return-value"></a>戻り値

現地時刻に基づいて1から31までの日付を返します。

### <a name="remarks"></a>コメント

この関数は、静的に割り当てられた内部バッファーを使用する `GetLocalTm`を呼び出します。 このバッファー内のデータは、他の `CTime` メンバー関数の呼び出しによって上書きされます。

### <a name="example"></a>例

[!code-cpp[NVC_ATLMFC_Utilities#153](../../atl-mfc-shared/codesnippet/cpp/ctime-class_7.cpp)]

##  <a name="getdayofweek"></a>CTime:: GetDayOfWeek

`CTime` オブジェクトで表される曜日を返します。

```
int GetDayOfWeek() const throw();
```

### <a name="return-value"></a>戻り値

現地時刻に基づいて曜日を返します。1 = 日曜日、2 = 月曜日、7 = 土曜日。

### <a name="remarks"></a>コメント

この関数は、静的に割り当てられた内部バッファーを使用する `GetLocalTm`を呼び出します。 このバッファー内のデータは、他の `CTime` メンバー関数の呼び出しによって上書きされます。

### <a name="example"></a>例

[!code-cpp[NVC_ATLMFC_Utilities#154](../../atl-mfc-shared/codesnippet/cpp/ctime-class_8.cpp)]

##  <a name="getgmttm"></a>CTime:: GetGmtTm

この `CTime` オブジェクトに格納されている時間の分解を格納している**構造体 tm**を取得します。

```
struct tm* GetGmtTm(struct tm* ptm) const;
```

### <a name="parameters"></a>パラメーター

*ptm*<br/>
時刻データを受け取るバッファーを指します。 このポインターが NULL の場合、例外がスローされます。

### <a name="return-value"></a>戻り値

インクルードファイル時刻に定義されている、埋め込まれた**構造体 tm**へのポインター。始め. 構造体のレイアウトについては、「 [gmtime、_gmtime32、_gmtime64](../../c-runtime-library/reference/gmtime-gmtime32-gmtime64.md) 」を参照してください。

### <a name="remarks"></a>コメント

`GetGmtTm` は UTC を返します。

*ptm*を NULL にすることはできません。 以前の動作に戻す場合は、 *ptm*を NULL にして、静的に割り当てられた内部バッファーを使用する必要があることを示すには、_SECURE_ATL を未定義にします。

### <a name="example"></a>例

[!code-cpp[NVC_ATLMFC_Utilities#155](../../atl-mfc-shared/codesnippet/cpp/ctime-class_9.cpp)]

##  <a name="gethour"></a>CTime:: Gethour:

`CTime` オブジェクトで表される時間を返します。

```
int GetHour() const throw();
```

### <a name="return-value"></a>戻り値

0 ~ 23 の範囲の現地時刻に基づいて時間を返します。

### <a name="remarks"></a>コメント

この関数は、静的に割り当てられた内部バッファーを使用する `GetLocalTm`を呼び出します。 このバッファー内のデータは、他の `CTime` メンバー関数の呼び出しによって上書きされます。

### <a name="example"></a>例

[!code-cpp[NVC_ATLMFC_Utilities#156](../../atl-mfc-shared/codesnippet/cpp/ctime-class_10.cpp)]

##  <a name="getlocaltm"></a>CTime:: GetLocalTm

この `CTime` オブジェクトに格納されている時間の分解を格納している**構造体 tm**を取得します。

```
struct tm* GetLocalTm(struct tm* ptm) const;
```

### <a name="parameters"></a>パラメーター

*ptm*<br/>
時刻データを受け取るバッファーを指します。 このポインターが NULL の場合、例外がスローされます。

### <a name="return-value"></a>戻り値

インクルードファイル時刻に定義されている、埋め込まれた**構造体 tm**へのポインター。始め. 構造体のレイアウトについては、「 [gmtime、_gmtime32、_gmtime64](../../c-runtime-library/reference/gmtime-gmtime32-gmtime64.md) 」を参照してください。

### <a name="remarks"></a>コメント

`GetLocalTm` は、現地時刻を返します。

*ptm*を NULL にすることはできません。 以前の動作に戻す場合は、 *ptm*を NULL にして、静的に割り当てられた内部バッファーを使用する必要があることを示すには、_SECURE_ATL を未定義にします。

### <a name="example"></a>例

[!code-cpp[NVC_ATLMFC_Utilities#157](../../atl-mfc-shared/codesnippet/cpp/ctime-class_11.cpp)]

##  <a name="getminute"></a>CTime:: GetMinute

`CTime` オブジェクトによって表される分を返します。

```
int GetMinute() const throw();
```

### <a name="return-value"></a>戻り値

0 ~ 59 の範囲の現地時刻に基づいて分を返します。

### <a name="remarks"></a>コメント

この関数は、静的に割り当てられた内部バッファーを使用する `GetLocalTm`を呼び出します。 このバッファー内のデータは、他の `CTime` メンバー関数の呼び出しによって上書きされます。

### <a name="example"></a>例

[Gethour:](#gethour)の例を参照してください。

##  <a name="getmonth"></a>CTime:: GetMonth

`CTime` オブジェクトで表される月を返します。

```
int GetMonth() const throw();
```

### <a name="return-value"></a>戻り値

現地時刻に基づいて1から12までの月を返します (1 から1月)。

### <a name="remarks"></a>コメント

この関数は、静的に割り当てられた内部バッファーを使用する `GetLocalTm`を呼び出します。 このバッファー内のデータは、他の `CTime` メンバー関数の呼び出しによって上書きされます。

### <a name="example"></a>例

[Getday](#getday)の例を参照してください。

##  <a name="getsecond"></a>CTime:: GetSecond

`CTime` オブジェクトによって表される秒の値を返します。

```
int GetSecond() const throw();
```

### <a name="return-value"></a>戻り値

0 ~ 59 の範囲で、現地時刻に基づいて2番目のを返します。

### <a name="remarks"></a>コメント

この関数は、静的に割り当てられた内部バッファーを使用する `GetLocalTm`を呼び出します。 このバッファー内のデータは、他の `CTime` メンバー関数の呼び出しによって上書きされます。

### <a name="example"></a>例

[Gethour:](#gethour)の例を参照してください。

##  <a name="gettime"></a>CTime:: GetTime

指定された `CTime` オブジェクトの **__time64_t**値を返します。

```
__time64_t GetTime() const throw();
```

### <a name="return-value"></a>戻り値

`GetTime` は、現在の `CTime` オブジェクトと1970年1月1日の間の秒数を返します。

### <a name="example"></a>例

[!code-cpp[NVC_ATLMFC_Utilities#158](../../atl-mfc-shared/codesnippet/cpp/ctime-class_12.cpp)]

##  <a name="getyear"></a>CTime:: GetYear

`CTime` オブジェクトによって表される年を返します。

```
int GetYear();
```

### <a name="return-value"></a>戻り値

1970年1月1日から2038年1月18日までの範囲で、現地時刻に基づいて年を返します。

### <a name="remarks"></a>コメント

この関数は、静的に割り当てられた内部バッファーを使用する `GetLocalTm`を呼び出します。 このバッファー内のデータは、他の `CTime` メンバー関数の呼び出しによって上書きされます。

### <a name="example"></a>例

[Getday](#getday)の例を参照してください。

##  <a name="operator_eq"></a>CTime:: operator =

代入演算子。

```
CTime& operator=(__time64_t time) throw();
```

### <a name="parameters"></a>パラメーター

*time*<br/>
新しい日付/時刻値。

### <a name="return-value"></a>戻り値

更新された `CTime` オブジェクト。

### <a name="remarks"></a>コメント

このオーバーロードされた代入演算子は、この `CTime` オブジェクトにソース時間をコピーします。 `CTime` オブジェクトの内部時間の格納は、タイムゾーンに依存しません。 タイムゾーンの変換は、割り当て時には必要ありません。

##  <a name="operator_add_-"></a>CTime:: operator +、-

これらの演算子は、`CTimeSpan` オブジェクトと `CTime` オブジェクトを加算および減算します。

```
CTime operator+(CTimeSpan timeSpan) const throw();
CTime operator-(CTimeSpan timeSpan) const throw();
CTimeSpan operator-(CTime time) const throw();
```

### <a name="parameters"></a>パラメーター

*timeSpan*<br/>
加算または減算する `CTimeSpan` オブジェクト。

*time*<br/>
減算される `CTime` オブジェクト。

### <a name="return-value"></a>戻り値

操作の結果を表す `CTime` または `CTimeSpan` オブジェクト。

### <a name="remarks"></a>コメント

`CTime` オブジェクトは絶対時間を表し、`CTimeSpan` オブジェクトは相対時間を表します。 最初の2つの演算子を使用すると、`CTime` オブジェクトに対して `CTimeSpan` オブジェクトの追加と削除を行うことができます。 3番目の演算子を使用すると、1つの `CTime` オブジェクトを別のオブジェクトから減算して、`CTimeSpan` オブジェクトを生成することができます。

### <a name="example"></a>例

[!code-cpp[NVC_ATLMFC_Utilities#159](../../atl-mfc-shared/codesnippet/cpp/ctime-class_13.cpp)]

##  <a name="operator_add_eq_-_eq"></a>CTime:: operator + =、-=

これらの演算子は、この `CTime` オブジェクトとの間で `CTimeSpan` オブジェクトを加算および減算します。

```
CTime& operator+=(CTimeSpan span) throw();
CTime& operator-=(CTimeSpan span) throw();
```

### <a name="parameters"></a>パラメーター

*スパン*<br/>
加算または減算する `CTimeSpan` オブジェクト。

### <a name="return-value"></a>戻り値

更新された `CTime` オブジェクト。

### <a name="remarks"></a>コメント

これらの演算子を使用すると、この `CTime` オブジェクトとの間で `CTimeSpan` オブジェクトを追加および削除できます。

### <a name="example"></a>例

[!code-cpp[NVC_ATLMFC_Utilities#160](../../atl-mfc-shared/codesnippet/cpp/ctime-class_14.cpp)]

##  <a name="serialize64"></a>CTime:: Serialize64

> [!NOTE]
> このメソッドは、MFC プロジェクトでのみ使用できます。

メンバー変数に関連付けられたデータをアーカイブにシリアル化します。

```
CArchive& Serialize64(CArchive& ar);
```

### <a name="parameters"></a>パラメーター

*金*<br/>
更新する `CArchive` オブジェクト。

### <a name="return-value"></a>戻り値

更新された `CArchive` オブジェクト。

## <a name="see-also"></a>参照

[asctime_s、_wasctime_s](../../c-runtime-library/reference/asctime-s-wasctime-s.md)<br/>
[_ftime_s、_ftime32_s、_ftime64_s](../../c-runtime-library/reference/ftime-s-ftime32-s-ftime64-s.md)<br/>
[gmtime_s、_gmtime32_s、_gmtime64_s](../../c-runtime-library/reference/gmtime-s-gmtime32-s-gmtime64-s.md)<br/>
[localtime_s、_localtime32_s、_localtime64_s](../../c-runtime-library/reference/localtime-s-localtime32-s-localtime64-s.md)<br/>
[strftime、wcsftime、_strftime_l、_wcsftime_l](../../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md)<br/>
[time、_time32、_time64](../../c-runtime-library/reference/time-time32-time64.md)<br/>
[CTimeSpan クラス](../../atl-mfc-shared/reference/ctimespan-class.md)<br/>
[階層図](../../mfc/hierarchy-chart.md)<br/>
[ATL/MFC 共有クラス](../../atl-mfc-shared/atl-mfc-shared-classes.md)

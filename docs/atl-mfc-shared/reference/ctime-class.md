---
title: CTimeクラス
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
ms.openlocfilehash: e6e471fe648c5fa370cce750e8569e158eb1ffe4
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81317570"
---
# <a name="ctime-class"></a>CTimeクラス

絶対時刻と日付を表します。

## <a name="syntax"></a>構文

```
class CTime
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[タイム::タイム](#ctime)|さまざまな方法`CTime`でオブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[時間::フォーマット](#format)|ローカル タイム`CTime`ゾーンに基づいて、オブジェクトを書式指定された文字列に変換します。|
|[タイム::フォーマットGmt](#formatgmt)|オブジェクトを`CTime`UTC に基づいて、書式設定された文字列に変換します。|
|[タイム::ゲタスデータベースタイムスタンプ](#getasdbtimestamp)|オブジェクトに格納されている時刻情報を`CTime`Win32 互換 DBTIMESTAMP 構造体に変換します。|
|[タイム::システムタイムを取得します。](#getassystemtime)|オブジェクトに格納されている時刻情報を`CTime`Win32 互換の[SYSTEMTIME](/windows/win32/api/minwinbase/ns-minwinbase-systemtime)構造体に変換します。|
|[時間::ゲットカレントタイム](#getcurrenttime)|現在の`CTime`時刻 (静的メンバー関数) を表すオブジェクトを作成します。|
|[タイム::ゲットデイ](#getday)|オブジェクトによって表される日を`CTime`返します。|
|[タイム::ゲットデイオブウィーク](#getdayofweek)|オブジェクトによって表される曜日を`CTime`返します。|
|[タイム::ゲットGmtTm](#getgmttm)|オブジェクトを`CTime`UTC に基づいてコンポーネントに分解します。|
|[時間::ゲットアワー](#gethour)|オブジェクトによって表される時間を`CTime`返します。|
|[タイム::ゲットローカルTm](#getlocaltm)|ローカル タイム`CTime`ゾーンに基づいて、オブジェクトをコンポーネントに分割します。|
|[タイム::ゲットミニット](#getminute)|オブジェクトによって表される分を`CTime`返します。|
|[時間::ゲットマン](#getmonth)|オブジェクトによって表される月を`CTime`返します。|
|[タイム::ゲットセカンド](#getsecond)|オブジェクトによって表される 2`CTime`番目の値を返します。|
|[タイム::ゲットタイム](#gettime)|指定した **__time64_t**`CTime`オブジェクトの__time64_t値を返します。|
|[タイム::ゲットイヤー](#getyear)|オブジェクトによって表される年を`CTime`返します。|
|[CTime::シリアライズ64](#serialize64)|アーカイブとの間でデータをシリアル化します。|

### <a name="operators"></a>オペレーター

|||
|-|-|
|[演算子 + -](#operator_add_-)|これらの演算子は、加算`CTimeSpan`および`CTime`減算およびオブジェクトです。|
|[演算子 +=、-=](#operator_add_eq_-_eq)|これらの演算子は、このオブジェクト`CTimeSpan`に対してオブジェクトを`CTime`加算したり、オブジェクトからオブジェクトを減算したりします。|
|[演算子 =](#operator_eq)|代入演算子。|
|[演算子 ==、< など](#ctime_comparison_operators)|比較演算子。|

## <a name="remarks"></a>解説

`CTime`は基本クラスを持っていません。

`CTime`値は協定世界時 (UTC) に基づいており、これは協定世界時 (グリニッジ標準時、GMT) に相当します。 タイム ゾーンの決定方法については、「[時間管理](../../c-runtime-library/time-management.md)」を参照してください。

オブジェクトを`CTime`作成する場合は、`nDST`標準時間が有効であることを示す場合は 0、夏時間が有効であることを示す場合は 0 より大きい値、C ランタイム ライブラリ コードが標準時間または夏時間のどちらが有効であるかを計算するには 0 未満の値をパラメーターに設定します。 `tm_isdst` は必須フィールドです。 設定されていない場合、その値は未定義であり[、mktime](../../c-runtime-library/reference/mktime-mktime32-mktime64.md)からの戻り値は予測不能です。 asctime_s `timeptr` [、](../../c-runtime-library/reference/asctime-s-wasctime-s.md) [_gmtime_s](../../c-runtime-library/reference/gmtime-s-gmtime32-s-gmtime64-s.md)、または[localtime_s](../../c-runtime-library/reference/localtime-s-localtime32-s-localtime64-s.md)に対する以前の呼び出しによって`tm_isdst`返された tm 構造体を指す場合、フィールドには正しい値が含まれます。

コンパニオン クラス[CTimeSpan](../../atl-mfc-shared/reference/ctimespan-class.md)は、時間間隔を表します。

クラス`CTime`と`CTimeSpan`クラスは派生用に設計されていません。 仮想関数がないため、オブジェクトと`CTime``CTimeSpan`オブジェクトのサイズは正確に 8 バイトです。 ほとんどのメンバー関数はインラインです。

> [!NOTE]
> 上限日の制限は 12/31/3000 です。 下限は1/1/1970 12:00:00 AM GMTです。

の使用方法`CTime`の詳細については、『ランタイム ライブラリ リファレンス』の「[日付と時刻](../../atl-mfc-shared/date-and-time.md)」および「[時間管理](../../c-runtime-library/time-management.md)」を参照してください。

> [!NOTE]
> 構造体`CTime`が MFC 7.1 から MFC 8.0 に変更されました。 MFC 8.0`CTime`以降のバージョンで**演算子 <<** を使用して構造体をシリアル化する場合、結果のファイルは、古いバージョンの MFC では読み取りできません。

## <a name="requirements"></a>必要条件

**ヘッダー:** atltime.h

## <a name="ctime-comparison-operators"></a><a name="ctime_comparison_operators"></a>CTime 比較演算子

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

これらの演算子は 2 つの絶対時間を比較し、条件が真の場合は TRUE を返します。それ以外の場合は FALSE。

### <a name="example"></a>例

[!code-cpp[NVC_ATLMFC_Utilities#161](../../atl-mfc-shared/codesnippet/cpp/ctime-class_1.cpp)]

## <a name="ctimectime"></a><a name="ctime"></a>タイム::タイム

指定した時刻`CTime`で初期化された新しいオブジェクトを作成します。

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

*タイムスrc*<br/>
既に`CTime`存在するオブジェクトを示します。

*time*<br/>
時刻`__time64_t`値は、1970 年 1 月 1 日 (UTC) 以降の秒数です。 これはローカル時刻に合わせて調整されます。 たとえば、ニューヨークで 0 のパラメータを渡して`CTime`オブジェクトを作成すると[、CTime::GetMonth](#getmonth)は 12 を返します。

*年*, *nMonth*, *nDay*, *nHour*, *nMin*, *nSec*<br/>
新しい`CTime`オブジェクトにコピーする日付と時刻の値を示します。

*nDST*<br/>
夏時間が有効かどうかを示します。 次の 3 つの値のいずれかを指定できます。

- *nDST*が 0 に設定されている標準時刻が有効です。

- *nDST*が 0 より大きい値に設定された場合、時間節約時間が有効です。

- *nDST*は 0 より小さい値に設定されます。 標準時間または夏時間のどちらが有効であるかを自動的に計算します。

*を指定*します *。*<br/>
日付/時刻値に変換され、新しい`CTime`オブジェクトにコピーされる MS-DOS の日付と時刻の値。

*聖*<br/>
日付/時刻値に変換され、新しい`CTime`オブジェクトにコピーされる[SYSTEMTIME](/windows/win32/api/minwinbase/ns-minwinbase-systemtime)構造体。

*フィート*<br/>
日付/時刻値に変換され、新しい`CTime`オブジェクトにコピーされる[FILETIME](/windows/win32/api/minwinbase/ns-minwinbase-filetime)構造体。

*dbts*<br/>
現在のローカル時間を含む DBTIMESTAMP 構造体への参照。

### <a name="remarks"></a>解説

各コンストラクターについて、以下に説明します。

- `CTime();`初期化`CTime`されていないオブジェクトを構築します。 このコンストラクターを使用すると、`CTime`オブジェクト配列を定義できます。 使用する前に、このような配列を有効な時刻で初期化する必要があります。

- `CTime( const CTime& );`別`CTime`の値`CTime`からオブジェクトを構築します。

- `CTime( __time64_t );`__time64_t型から`CTime`オブジェクトを構築 **__time64_t**します。 このコンストラクターは、UTC 時刻を想定し、結果を格納する前に結果をローカル時刻に変換します。

- `CTime( int, int, ...);`ローカル時間コンポーネント`CTime`からオブジェクトを構築し、各コンポーネントを次の範囲に拘束します。

   |コンポーネント|範囲|
   |---------------|-----------|
   |*n年*|1970-3000|
   |*nMonth*|1-12|
   |*nDay*|1-31|
   |*nアワー*|0-23|
   |*nMin*|0-59|
   |*Nsec*|0-59|

   このコンストラクターは、適切な変換を UTC にします。 1 つ以上の時間コンポーネントが範囲外にある場合、Microsoft Foundation クラス ライブラリのデバッグ バージョンがアサートします。 呼び出す前に引数を検証する必要があります。 このコンストラクターは、ローカル時刻を想定しています。

- `CTime( WORD, WORD );`指定した`CTime`MS-DOS の日付と時刻の値からオブジェクトを構築します。 このコンストラクターは、ローカル時刻を想定しています。

- `CTime( const SYSTEMTIME& );`構造体からオブジェクト`CTime`を構築します`SYSTEMTIME`。 このコンストラクターは、ローカル時刻を想定しています。

- `CTime( const FILETIME& );`構造体からオブジェクト`CTime`を構築します`FILETIME`。 初期化は直接使用`CTime FILETIME`しない可能性が高いです。 オブジェクトを`CFile`使用してファイルを操作する場合は`CFile::GetStatus`、構造体で初期化された`CTime`オブジェクトを通じてファイルのタイムスタンプを`FILETIME`取得します。 このコンストラクターは、UTC に基づく時刻を想定し、結果を格納する前に値を自動的にローカル時刻に変換します。

   > [!NOTE]
   > パラメーターを使用`DBTIMESTAMP`するコンストラクターは、OLEDB.h が含まれている場合にのみ使用できます。

詳細については、Windows SDK の[システム時刻](/windows/win32/api/minwinbase/ns-minwinbase-systemtime)と[ファイルタイム](/windows/win32/api/minwinbase/ns-minwinbase-filetime)の構造体を参照してください。 また、Windows SDK の[MS-DOS の日付と時刻](/windows/win32/SysInfo/ms-dos-date-and-time)のエントリも参照してください。

### <a name="example"></a>例

[!code-cpp[NVC_ATLMFC_Utilities#148](../../atl-mfc-shared/codesnippet/cpp/ctime-class_2.cpp)]

## <a name="ctimeformat"></a><a name="format"></a>時間::フォーマット

日時値の書式化された表現を作成します。

```
CString Format(LPCTSTR pszFormat) const;
CString Format(UINT nFormatID) const;
```

### <a name="parameters"></a>パラメーター

*フォーマット*<br/>
書式指定文字列に似た`printf`書式指定文字列。 フォーマット コードの前にパーセント記号`%`() が付いた書式コード`CTime`は、対応するコンポーネントに置き換えられます。 書式指定文字列内の他の文字は、変更されずに返された文字列にコピーされます。 フォーマットコードのリストについては、実行時関数[strftime](../../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md)を参照してください。

*データを持つ*<br/>
この形式を識別する文字列の ID。

### <a name="return-value"></a>戻り値

書式指定された時刻を含む[CString。](../../atl-mfc-shared/reference/cstringt-class.md)

### <a name="remarks"></a>解説

この`CTime`オブジェクトの状態が null の場合、戻り値は空の文字列です。

このメソッドは、形式を設定する日時の値が、1970 年 1 月 1 日午前 0 時から 3000 年 12 月 31 日 (UTC) の範囲にない場合に例外をスローします。

### <a name="example"></a>例

[!code-cpp[NVC_ATLMFC_Utilities#149](../../atl-mfc-shared/codesnippet/cpp/ctime-class_3.cpp)]

## <a name="ctimeformatgmt"></a><a name="formatgmt"></a>タイム::フォーマットGmt

この`CTime`オブジェクトに対応する書式付き文字列を生成します。

```
CString FormatGmt(LPCTSTR pszFormat) const;
CString FormatGmt(UINT nFormatID) const;
```

### <a name="parameters"></a>パラメーター

*フォーマット*<br/>
書式指定文字列に似た書式`printf`指定文字列を指定します。 詳細については、実行時関数[strftime](../../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md)を参照してください。

*データを持つ*<br/>
この形式を識別する文字列の ID。

### <a name="return-value"></a>戻り値

書式指定された時刻を含む[CString。](../../atl-mfc-shared/reference/cstringt-class.md)

### <a name="remarks"></a>解説

時刻の値は変換されないため、UTC が反映されます。

このメソッドは、形式を設定する日時の値が、1970 年 1 月 1 日午前 0 時から 3000 年 12 月 31 日 (UTC) の範囲にない場合に例外をスローします。

### <a name="example"></a>例

[「CTime::フォーマット](#format)」の例を参照してください。

## <a name="ctimegetasdbtimestamp"></a><a name="getasdbtimestamp"></a>タイム::ゲタスデータベースタイムスタンプ

`CTime`オブジェクトに格納されている時刻情報を Win32 互換 DBTIMESTAMP 構造体に変換します。

```
bool GetAsDBTIMESTAMP(DBTIMESTAMP& dbts) const throw();
```

### <a name="parameters"></a>パラメーター

*dbts*<br/>
現在のローカル時間を含む DBTIMESTAMP 構造体への参照。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>解説

参照された*dbts*構造体に結果の時刻を格納します。 この`DBTIMESTAMP`関数で初期化されるデータ構造体の`fraction`メンバは 0 に設定されます。

### <a name="example"></a>例

[!code-cpp[NVC_ATLMFC_Utilities#150](../../atl-mfc-shared/codesnippet/cpp/ctime-class_4.cpp)]

## <a name="ctimegetassystemtime"></a><a name="getassystemtime"></a>タイム::システムタイムを取得します。

`CTime`オブジェクトに格納されている時刻情報を Win32 互換[の SYSTEMTIME](/windows/win32/api/minwinbase/ns-minwinbase-systemtime)構造体に変換します。

```
bool GetAsSystemTime(SYSTEMTIME& st) const throw();
```

### <a name="parameters"></a>パラメーター

*タイムデスト*<br/>
オブジェクトの変換された日付/時刻値を保持する[SYSTEMTIME](/windows/win32/api/minwinbase/ns-minwinbase-systemtime)構造体への`CTime`参照。

### <a name="return-value"></a>戻り値

成功した場合は TRUE、それ以外の場合は FALSE。

### <a name="remarks"></a>解説

`GetAsSystemTime`参照された*timeDest*構造体に結果の時間を格納します。 この`SYSTEMTIME`関数で初期化されるデータ構造体の`wMilliseconds`メンバは 0 に設定されます。

### <a name="example"></a>例

[!code-cpp[NVC_ATLMFC_Utilities#151](../../atl-mfc-shared/codesnippet/cpp/ctime-class_5.cpp)]

## <a name="ctimegetcurrenttime"></a><a name="getcurrenttime"></a>時間::ゲットカレントタイム

現在の`CTime`時刻を表すオブジェクトを返します。

```
static CTime WINAPI GetCurrentTime() throw();
```

### <a name="remarks"></a>解説

現在のシステムの日付と時刻を世界協定時刻 (UTC) で返します。

### <a name="example"></a>例

[!code-cpp[NVC_ATLMFC_Utilities#152](../../atl-mfc-shared/codesnippet/cpp/ctime-class_6.cpp)]

## <a name="ctimegetday"></a><a name="getday"></a>タイム::ゲットデイ

オブジェクトによって表される日を`CTime`返します。

```
int GetDay() const throw();
```

### <a name="return-value"></a>戻り値

1 ~ 31 の範囲で、現地時間に基づいて、月の日を返します。

### <a name="remarks"></a>解説

この関数は`GetLocalTm`、静的に割り当てられた内部バッファを使用する を呼び出します。 このバッファー内のデータは、他`CTime`のメンバー関数の呼び出しにより上書きされます。

### <a name="example"></a>例

[!code-cpp[NVC_ATLMFC_Utilities#153](../../atl-mfc-shared/codesnippet/cpp/ctime-class_7.cpp)]

## <a name="ctimegetdayofweek"></a><a name="getdayofweek"></a>タイム::ゲットデイオブウィーク

オブジェクトによって表される曜日を`CTime`返します。

```
int GetDayOfWeek() const throw();
```

### <a name="return-value"></a>戻り値

現地時間に基づいて曜日を返します。1 = 日曜日、2 = 月曜日、7 = 土曜日。

### <a name="remarks"></a>解説

この関数は`GetLocalTm`、静的に割り当てられた内部バッファを使用する を呼び出します。 このバッファー内のデータは、他`CTime`のメンバー関数の呼び出しにより上書きされます。

### <a name="example"></a>例

[!code-cpp[NVC_ATLMFC_Utilities#154](../../atl-mfc-shared/codesnippet/cpp/ctime-class_8.cpp)]

## <a name="ctimegetgmttm"></a><a name="getgmttm"></a>タイム::ゲットGmtTm

この`CTime`オブジェクトに含まれる時間の分解を含む**構造体の tm**を取得します。

```
struct tm* GetGmtTm(struct tm* ptm) const;
```

### <a name="parameters"></a>パラメーター

*Ptm*<br/>
時刻データを受け取るバッファーへのポイント。 このポインターが NULL の場合、例外がスローされます。

### <a name="return-value"></a>戻り値

インクルード ファイル TIME で定義されている、入力された**構造体 tm**へのポインター。H。 構造レイアウトについては[、gmtime、_gmtime32、_gmtime64](../../c-runtime-library/reference/gmtime-gmtime32-gmtime64.md)を参照してください。

### <a name="remarks"></a>解説

`GetGmtTm`は UTC を返します。

*ptm*を NULL にすることはできません。 ptm が NULL である可能性がある古い*ptm*動作に戻して、内部の静的に割り当てられたバッファを使用することを示す場合は、_SECURE_ATL定義を解除します。

### <a name="example"></a>例

[!code-cpp[NVC_ATLMFC_Utilities#155](../../atl-mfc-shared/codesnippet/cpp/ctime-class_9.cpp)]

## <a name="ctimegethour"></a><a name="gethour"></a>時間::ゲットアワー

オブジェクトによって表される時間を`CTime`返します。

```
int GetHour() const throw();
```

### <a name="return-value"></a>戻り値

0 ~ 23 の範囲の、現地時間に基づいて時間を返します。

### <a name="remarks"></a>解説

この関数は`GetLocalTm`、静的に割り当てられた内部バッファを使用する を呼び出します。 このバッファー内のデータは、他`CTime`のメンバー関数の呼び出しにより上書きされます。

### <a name="example"></a>例

[!code-cpp[NVC_ATLMFC_Utilities#156](../../atl-mfc-shared/codesnippet/cpp/ctime-class_10.cpp)]

## <a name="ctimegetlocaltm"></a><a name="getlocaltm"></a>タイム::ゲットローカルTm

この`CTime`オブジェクトに含まれる時間の分解を含む**構造体の tm**を取得します。

```
struct tm* GetLocalTm(struct tm* ptm) const;
```

### <a name="parameters"></a>パラメーター

*Ptm*<br/>
時刻データを受け取るバッファーへのポイント。 このポインターが NULL の場合、例外がスローされます。

### <a name="return-value"></a>戻り値

インクルード ファイル TIME で定義されている、入力された**構造体 tm**へのポインター。H。 構造レイアウトについては[、gmtime、_gmtime32、_gmtime64](../../c-runtime-library/reference/gmtime-gmtime32-gmtime64.md)を参照してください。

### <a name="remarks"></a>解説

`GetLocalTm`は、ローカル時刻を返します。

*ptm*を NULL にすることはできません。 ptm が NULL である可能性がある古い*ptm*動作に戻して、内部の静的に割り当てられたバッファを使用することを示す場合は、_SECURE_ATL定義を解除します。

### <a name="example"></a>例

[!code-cpp[NVC_ATLMFC_Utilities#157](../../atl-mfc-shared/codesnippet/cpp/ctime-class_11.cpp)]

## <a name="ctimegetminute"></a><a name="getminute"></a>タイム::ゲットミニット

オブジェクトによって表される分を`CTime`返します。

```
int GetMinute() const throw();
```

### <a name="return-value"></a>戻り値

0 ~ 59 の範囲で、ローカル時刻に基づいて分を返します。

### <a name="remarks"></a>解説

この関数は`GetLocalTm`、静的に割り当てられた内部バッファを使用する を呼び出します。 このバッファー内のデータは、他`CTime`のメンバー関数の呼び出しにより上書きされます。

### <a name="example"></a>例

[GetHour](#gethour)の例を参照してください。

## <a name="ctimegetmonth"></a><a name="getmonth"></a>時間::ゲットマン

オブジェクトによって表される月を`CTime`返します。

```
int GetMonth() const throw();
```

### <a name="return-value"></a>戻り値

1 ~ 12 (1 月) の範囲で、現地時間に基づいて月を返します。

### <a name="remarks"></a>解説

この関数は`GetLocalTm`、静的に割り当てられた内部バッファを使用する を呼び出します。 このバッファー内のデータは、他`CTime`のメンバー関数の呼び出しにより上書きされます。

### <a name="example"></a>例

[GetDay](#getday)の例を参照してください。

## <a name="ctimegetsecond"></a><a name="getsecond"></a>タイム::ゲットセカンド

オブジェクトによって表される 2`CTime`番目の値を返します。

```
int GetSecond() const throw();
```

### <a name="return-value"></a>戻り値

0 ~ 59 の範囲で、ローカル時刻に基づいて秒を返します。

### <a name="remarks"></a>解説

この関数は`GetLocalTm`、静的に割り当てられた内部バッファを使用する を呼び出します。 このバッファー内のデータは、他`CTime`のメンバー関数の呼び出しにより上書きされます。

### <a name="example"></a>例

[GetHour](#gethour)の例を参照してください。

## <a name="ctimegettime"></a><a name="gettime"></a>タイム::ゲットタイム

指定した **__time64_t**`CTime`オブジェクトの__time64_t値を返します。

```
__time64_t GetTime() const throw();
```

### <a name="return-value"></a>戻り値

`GetTime`現在`CTime`のオブジェクトと 1970 年 1 月 1 日の間の秒数を返します。

### <a name="example"></a>例

[!code-cpp[NVC_ATLMFC_Utilities#158](../../atl-mfc-shared/codesnippet/cpp/ctime-class_12.cpp)]

## <a name="ctimegetyear"></a><a name="getyear"></a>タイム::ゲットイヤー

オブジェクトによって表される年を`CTime`返します。

```
int GetYear();
```

### <a name="return-value"></a>戻り値

1970 年 1 月 1 日から 2038 年 1 月 18 日までの範囲の、ローカル時刻に基づいて年を返します 。

### <a name="remarks"></a>解説

この関数は`GetLocalTm`、静的に割り当てられた内部バッファを使用する を呼び出します。 このバッファー内のデータは、他`CTime`のメンバー関数の呼び出しにより上書きされます。

### <a name="example"></a>例

[GetDay](#getday)の例を参照してください。

## <a name="ctimeoperator-"></a><a name="operator_eq"></a>時間::演算子 =

代入演算子。

```
CTime& operator=(__time64_t time) throw();
```

### <a name="parameters"></a>パラメーター

*time*<br/>
新しい日付/時刻の値。

### <a name="return-value"></a>戻り値

更新された`CTime`オブジェクト。

### <a name="remarks"></a>解説

このオーバーロードされた代入演算子は、ソース時間をこの`CTime`オブジェクトにコピーします。 `CTime`オブジェクト内の内部時間ストレージは、タイム ゾーンとは無関係です。 割り当て時にタイム ゾーン変換は必要ありません。

## <a name="ctimeoperator---"></a><a name="operator_add_-"></a>時間::演算子 +、 -

これらの演算子は、加算`CTimeSpan`および`CTime`減算およびオブジェクトです。

```
CTime operator+(CTimeSpan timeSpan) const throw();
CTime operator-(CTimeSpan timeSpan) const throw();
CTimeSpan operator-(CTime time) const throw();
```

### <a name="parameters"></a>パラメーター

*Timespan*<br/>
加算`CTimeSpan`または減算するオブジェクト。

*time*<br/>
減`CTime`算するオブジェクト。

### <a name="return-value"></a>戻り値

操作`CTime`の`CTimeSpan`結果を表すオブジェクトまたはオブジェクト。

### <a name="remarks"></a>解説

`CTime`オブジェクトは絶対時間を`CTimeSpan`表し、オブジェクトは相対時間を表します。 最初の 2 つの演算子を使用すると`CTimeSpan`、オブジェクトのオブジェクト`CTime`の追加とオブジェクトの間でのオブジェクトの減算を行うことができます。 3 番目の演算子を使用すると`CTime`、オブジェクトを別のオブジェクト`CTimeSpan`から減算してオブジェクトを生成できます。

### <a name="example"></a>例

[!code-cpp[NVC_ATLMFC_Utilities#159](../../atl-mfc-shared/codesnippet/cpp/ctime-class_13.cpp)]

## <a name="ctimeoperator---"></a><a name="operator_add_eq_-_eq"></a>時間::演算子 +=、-=

これらの演算子は、このオブジェクト`CTimeSpan`に対してオブジェクトを`CTime`加算したり、オブジェクトからオブジェクトを減算したりします。

```
CTime& operator+=(CTimeSpan span) throw();
CTime& operator-=(CTimeSpan span) throw();
```

### <a name="parameters"></a>パラメーター

*スパン*<br/>
加算`CTimeSpan`または減算するオブジェクト。

### <a name="return-value"></a>戻り値

更新された`CTime`オブジェクト。

### <a name="remarks"></a>解説

これらの演算子を使用すると、この`CTimeSpan``CTime`オブジェクトに対してオブジェクトを追加したり、オブジェクトからオブジェクトを減算したりできます。

### <a name="example"></a>例

[!code-cpp[NVC_ATLMFC_Utilities#160](../../atl-mfc-shared/codesnippet/cpp/ctime-class_14.cpp)]

## <a name="ctimeserialize64"></a><a name="serialize64"></a>CTime::シリアライズ64

> [!NOTE]
> このメソッドは、MFC プロジェクトでのみ使用できます。

アーカイブとの間でメンバー変数に関連付けられたデータをシリアル化します。

```
CArchive& Serialize64(CArchive& ar);
```

### <a name="parameters"></a>パラメーター

*ar*<br/>
更新`CArchive`するオブジェクト。

### <a name="return-value"></a>戻り値

更新された`CArchive`オブジェクト。

## <a name="see-also"></a>関連項目

[asctime_s、_wasctime_s](../../c-runtime-library/reference/asctime-s-wasctime-s.md)<br/>
[_ftime_s、_ftime32_s、_ftime64_s](../../c-runtime-library/reference/ftime-s-ftime32-s-ftime64-s.md)<br/>
[gmtime_s、_gmtime32_s、_gmtime64_s](../../c-runtime-library/reference/gmtime-s-gmtime32-s-gmtime64-s.md)<br/>
[localtime_s、_localtime32_s、_localtime64_s](../../c-runtime-library/reference/localtime-s-localtime32-s-localtime64-s.md)<br/>
[strftime、wcsftime、_strftime_l、_wcsftime_l](../../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md)<br/>
[time、_time32、_time64](../../c-runtime-library/reference/time-time32-time64.md)<br/>
[クラス](../../atl-mfc-shared/reference/ctimespan-class.md)<br/>
[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[ATL/MFC 共有クラス](../../atl-mfc-shared/atl-mfc-shared-classes.md)

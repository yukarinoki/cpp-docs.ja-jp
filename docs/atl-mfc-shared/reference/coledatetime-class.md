---
title: COleDateTime クラス
ms.date: 03/27/2019
f1_keywords:
- COleDateTime
- ATLCOMTIME/ATL::COleDateTime
- ATLCOMTIME/ATL::COleDateTime::COleDateTime
- ATLCOMTIME/ATL::COleDateTime::Format
- ATLCOMTIME/ATL::COleDateTime::GetAsDBTIMESTAMP
- ATLCOMTIME/ATL::COleDateTime::GetAsSystemTime
- ATLCOMTIME/ATL::COleDateTime::GetAsUDATE
- ATLCOMTIME/ATL::COleDateTime::GetCurrentTime
- ATLCOMTIME/ATL::COleDateTime::GetDay
- ATLCOMTIME/ATL::COleDateTime::GetDayOfWeek
- ATLCOMTIME/ATL::COleDateTime::GetDayOfYear
- ATLCOMTIME/ATL::COleDateTime::GetHour
- ATLCOMTIME/ATL::COleDateTime::GetMinute
- ATLCOMTIME/ATL::COleDateTime::GetMonth
- ATLCOMTIME/ATL::COleDateTime::GetSecond
- ATLCOMTIME/ATL::COleDateTime::GetStatus
- ATLCOMTIME/ATL::COleDateTime::GetYear
- ATLCOMTIME/ATL::COleDateTime::ParseDateTime
- ATLCOMTIME/ATL::COleDateTime::SetDate
- ATLCOMTIME/ATL::COleDateTime::SetDateTime
- ATLCOMTIME/ATL::COleDateTime::SetStatus
- ATLCOMTIME/ATL::COleDateTime::SetTime
- ATLCOMTIME/ATL::COleDateTime::m_dt
- ATLCOMTIME/ATL::COleDateTime::m_status
helpviewer_keywords:
- shared classes, COleDateTime
- time-only values
- Date data type, MFC encapsulation of
- COleDateTime class
- dates, handling in MFC
- time, handling in MFC
ms.assetid: e718f294-16ec-4649-88b6-a4dbae5178fb
ms.openlocfilehash: 5cbc131a81afef1ee94069f39e79f22ce7addfcb
ms.sourcegitcommit: 1839405b97036891b6e4d37c99def044d6f37eff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/18/2020
ms.locfileid: "88562468"
---
# <a name="coledatetime-class"></a>COleDateTime クラス

`DATE`OLE オートメーションで使用されるデータ型をカプセル化します。

## <a name="syntax"></a>構文

```
class COleDateTime
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[COleDateTime:: COleDateTime](#coledatetime)|`COleDateTime` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[COleDateTime:: Format](#format)|オブジェクトの書式設定された文字列形式を生成 `COleDateTime` します。|
|[COleDateTime:: GetAsDBTIMESTAMP](#getasdbtimestamp)|オブジェクトの時刻を `COleDateTime` データ構造体として取得するには、このメソッドを呼び出し `DBTIMESTAMP` ます。|
|[COleDateTime:: GetAsSystemTime](#getassystemtime)|このメソッドを呼び出して、オブジェクトの時刻を `COleDateTime` [SYSTEMTIME](/windows/win32/api/minwinbase/ns-minwinbase-systemtime) データ構造体として取得します。|
|[COleDateTime:: GetAsUDATE](#getasudate)|`COleDateTime`データ構造体としての時間を取得するには、このメソッドを呼び出し `UDATE` ます。|
|[COleDateTime:: GetCurrentTime](#getcurrenttime)|`COleDateTime`現在の時刻 (静的メンバー関数) を表すオブジェクトを作成します。|
|[COleDateTime:: GetDay](#getday)|この `COleDateTime` オブジェクトが表す日 (1-31) を返します。|
|[COleDateTime:: GetDayOfWeek](#getdayofweek)|この `COleDateTime` オブジェクトが表す曜日 (日曜日 = 1) を返します。|
|[COleDateTime:: GetDayOfYear](#getdayofyear)|このオブジェクトが表す年の日付を返し `COleDateTime` ます (1 月1日 = 1)。|
|[COleDateTime:: Gethour:](#gethour)|この `COleDateTime` オブジェクトが表す時間 (0-23) を返します。|
|[COleDateTime:: GetMinute](#getminute)|この `COleDateTime` オブジェクトが表す分 (0-59) を返します。|
|[COleDateTime:: GetMonth](#getmonth)|このオブジェクトが表す月を返し `COleDateTime` ます (1-12)。|
|[COleDateTime:: GetSecond](#getsecond)|このオブジェクトが表す2番目の `COleDateTime` オブジェクト (0-59) を返します。|
|[COleDateTime:: GetStatus](#getstatus)|このオブジェクトの状態 (有効) を取得し `COleDateTime` ます。|
|[COleDateTime:: GetYear](#getyear)|このオブジェクトが表す年を返し `COleDateTime` ます。|
|[COleDateTime::P arseDateTime](#parsedatetime)|文字列から日付/時刻値を読み取り、の値を設定し `COleDateTime` ます。|
|[COleDateTime:: SetDate](#setdate)|このオブジェクトの値 `COleDateTime` を、指定した日付専用の値に設定します。|
|[COleDateTime:: SetDateTime](#setdatetime)|このオブジェクトの値 `COleDateTime` を、指定した日付/時刻値に設定します。|
|[COleDateTime:: SetStatus](#setstatus)|このオブジェクトの状態 (有効性) を設定し `COleDateTime` ます。|
|[COleDateTime:: SetTime](#settime)|このオブジェクトの値 `COleDateTime` を、指定した時間専用の値に設定します。|

### <a name="public-operators"></a>パブリック演算子

|Name|説明|
|----------|-----------------|
|[COleDateTime:: operator = =、COleDateTime:: operator < など。](#coledatetime_relational_operators)|2つ `COleDateTime` の値を比較します。|
|[COleDateTime:: operator +, COleDateTime:: operator-](#operator_add_-)|値を加算および減算 `COleDateTime` します。|
|[COleDateTime:: operator + =、COleDateTime:: operator-=](#operator_add_eq_-_eq)|`COleDateTime`このオブジェクトの値を加算および減算 `COleDateTime` します。|
|[COleDateTime:: operator =](#operator_eq)|値をコピー `COleDateTime` します。|
|[COleDateTime:: operator DATE、COleDateTime:: operator Date *](#operator_date)|値を `COleDateTime` `DATE` またはに変換 `DATE*` します。|

### <a name="public-data-members"></a>パブリック データ メンバー

|Name|説明|
|----------|-----------------|
|[COleDateTime:: m_dt](#m_dt)|このオブジェクトの基になるを格納 `DATE` `COleDateTime` します。|
|[COleDateTime:: m_status](#m_status)|このオブジェクトの状態を格納 `COleDateTime` します。|

## <a name="remarks"></a>解説

`COleDateTime` に基底クラスがありません。

これは、OLE オートメーションの [VARIANT](/windows/win32/api/oaidl/ns-oaidl-variant) データ型に使用できる型の1つです。 値は、 `COleDateTime` 絶対日付と時刻の値を表します。

型は、 `DATE` 浮動小数点値として実装されます。 日数は、1899年12月30日午前0時に測定されます。 次の表に、日付とそれに関連付けられた値を示します。

|Date|値|
|----------|-----------|
|1899年12月29日午前0時|-1.0|
|1899年12月29日、6. M|-1.25|
|1899年12月30日午前0時|0.0|
|1899年12月31日午前0時|1.0|
|1900年1月1日、午前6時|2.25|

> [!CAUTION]
> 上の表では、日の値が1899年12月30日の午前0時よりも負の値になりますが、時刻の値にはなりません。 たとえば、日付を表す整数が正 (12 月 1899 30 日以降) または負 (12 月 1899 30 日より前) であるかどうかにかかわらず、6:00 AM は常に小数値0.25 によって表されます。 これは、単純な浮動小数点比較では、 `COleDateTime` 12/29/1899 上の 6:00 am を表すを、同じ日に 7:00 AM を表すものとして誤って並べ替えられることを **意味し** ます。

クラスは、 `COleDateTime` 100 年1月1日から9999年12月31日までの日付を処理します。 クラスはグレゴリオ暦を使用します。ユリウス暦はサポートして `COleDateTime` いません。 `COleDateTime` 夏時間を無視します。 (「 [日付と時刻: オートメーションサポート」を](../../atl-mfc-shared/date-and-time-automation-support.md)参照してください)。

> [!NOTE]
> 形式を使用すると、 `%y` 1900 から始まる日付の場合にのみ、2桁の年を取得できます。 `%y`1900 より前の日付で形式を使用すると、コードによってアサートエラーが生成されます。

この型は、日付のみまたは時間専用の値を表すためにも使用されます。 慣例により、日付 0 (1899 年12月30日) が時間のみの値に使用され、時刻 00:00 (午前0時) が日付専用の値に使用されます。

100未満の日付を使用してオブジェクトを作成した場合、その `COleDateTime` 日付は受け入れられますが、、、、、、およびへの後続の呼び出しは `GetYear` `GetMonth` `GetDay` `GetHour` `GetMinute` `GetSecond` 失敗し、-1 を返します。 以前は、2桁の日付を使用できましたが、MFC 4.2 以降では、日付は100以上である必要があります。

問題を回避するには、4桁の日付を指定します。 次に例を示します。

[!code-cpp[NVC_ATLMFC_Utilities#1](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_1.cpp)]

値の基本算術演算で `COleDateTime` は、コンパニオンクラス [COleDateTimeSpan](../../atl-mfc-shared/reference/coledatetimespan-class.md)が使用されます。 `COleDateTimeSpan` 値は時間間隔を定義します。 これらのクラス間のリレーションシップは、 [CTime](../../atl-mfc-shared/reference/ctime-class.md) と [CTimeSpan](../../atl-mfc-shared/reference/ctimespan-class.md)の間の関係に似ています。

クラスとクラスの詳細については、 `COleDateTime` `COleDateTimeSpan` 「 [日付と時刻: オートメーションサポート](../../atl-mfc-shared/date-and-time-automation-support.md)」を参照してください。

## <a name="requirements"></a>必要条件

**ヘッダー:** ATLComTime .h

## <a name="coledatetime-relational-operators"></a><a name="coledatetime_relational_operators"></a> COleDateTime 関係演算子

比較演算子。

```
bool operator==(const COleDateTime& date) const throw();
bool operator!=(const COleDateTime& date) const throw();
bool operator<(const COleDateTime& date) const throw();
bool operator>(const COleDateTime& date) const throw();
bool operator<=(const COleDateTime& date) const throw();
bool operator>=(const COleDateTime& date) const throw();
```

### <a name="parameters"></a>パラメーター

*date*<br/>
比較される `COleDateTime` オブジェクト。

### <a name="remarks"></a>解説

> [!NOTE]
> 2つのオペランドのいずれかが無効な場合、ATLASSERT が発生します。

### <a name="example"></a>例

[!code-cpp[NVC_ATLMFC_Utilities#13](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_2.cpp)]

### <a name="example"></a>例

**>=** **\<=**, **>** **<** オブジェクトが null に設定されている場合、、、およびの各演算子はアサートし `COleDateTime` ます。

[!code-cpp[NVC_ATLMFC_Utilities#170](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_3.cpp)]

## <a name="coledatetimecoledatetime"></a><a name="coledatetime"></a> COleDateTime:: COleDateTime

`COleDateTime` オブジェクトを構築します。

```
COleDateTime() throw();
COleDateTime(const VARIANT& varSrc) throw();
COleDateTime(DATE dtSrc) throw();
COleDateTime(time_t timeSrc) throw();
COleDateTime(__time64_t timeSrc) throw();
COleDateTime(const SYSTEMTIME& systimeSrc) throw();
COleDateTime(const FILETIME& filetimeSrc) throw();

COleDateTime(int nYear,
    int nMonth,
    int nDay,
    int nHour,
    int nMin,
    int nSec) throw();

COleDateTime(WORD wDosDate,
    WORD wDosTime) throw();
COleDateTime(const DBTIMESTAMP& timeStamp) throw();
```

### <a name="parameters"></a>パラメーター

*日 Rc*<br/>
`COleDateTime`新しいオブジェクトにコピーされる既存のオブジェクト `COleDateTime` 。

*varSrc*<br/>
`VARIANT` `COleVariant` 日付/時刻値 (VT_DATE) に変換して新しいオブジェクトにコピーする既存のデータ構造 (場合によってはオブジェクト) `COleDateTime` 。

*dtSrc*<br/>
`DATE`新しいオブジェクトにコピーされる日付/時刻 () 値 `COleDateTime` 。

*timeSrc*<br/>
`time_t` `__time64_t` 日付/時刻値に変換され、新しいオブジェクトにコピーされる値または値 `COleDateTime` 。

*systimeSrc*<br/>
`SYSTEMTIME`日付/時刻値に変換され、新しいオブジェクトにコピーされる構造体 `COleDateTime` 。

*filetimeSrc*<br/>
`FILETIME`日付/時刻値に変換され、新しいオブジェクトにコピーされる構造体 `COleDateTime` 。 は世界 `FILETIME` 協定時刻 (UTC) を使用するため、構造体にローカル時刻を渡すと、結果は正しくありません。 詳細については、「Windows SDK の [ファイル時刻](/windows/win32/SysInfo/file-times) 」を参照してください。

*Nyear*、 *nyear*、 *nyear*、 *nyear*、 *nyear*、 *nSec*<br/>
新しいオブジェクトにコピーする日付と時刻の値を示し `COleDateTime` ます。

*Wdosdate*、 *wDosTime*<br/>
日付/時刻値に変換され、新しいオブジェクトにコピーされる MS-DOS の日付と時刻の値 `COleDateTime` 。

*タイムスタンプ*<br/>
現在の現地時刻を格納している [Dbtimestamp](/dotnet/api/system.data.oledb.oledbtype) 構造体への参照。

### <a name="remarks"></a>解説

これらのすべてのコンストラクター `COleDateTime` は、指定された値に初期化された新しいオブジェクトを作成します。 次の表は、各日付と時刻のコンポーネントの有効な範囲を示しています。

|日付/時刻コンポーネント|有効な範囲|
|--------------------------|-----------------|
|year|100 ~ 9999|
|month|0 - 12|
|day|0 - 31|
|hour|0 - 23|
|minute|0 - 59|
|second|0 - 59|

日の部分の実際の上限は、月と年のコンポーネントによって異なることに注意してください。 詳細については、「」 `SetDate` または「メンバー関数」を参照してください `SetDateTime` 。

各コンストラクターの簡単な説明を次に示します。

- `COleDateTime(`**)** `COleDateTime` 0 に初期化されたオブジェクトを構築します (1899 年12月30日午前0時)。

- `COleDateTime(``dateSrc` **)** 既存の `COleDateTime` オブジェクトからオブジェクトを構築 `COleDateTime` します。

- `COleDateTime(`*varsrc* **)** オブジェクトを構築 `COleDateTime` します。 `VARIANT`構造体または[COleVariant](../../mfc/reference/colevariant-class.md)オブジェクトから日付/時刻 () 値への変換を試み `VT_DATE` ます。 この変換が成功した場合は、変換後の値が新しいオブジェクトにコピーされ `COleDateTime` ます。 そうでない場合、オブジェクトの値 `COleDateTime` は 0 (午前0時、1899年12月30日) に設定され、その状態は無効になります。

- `COleDateTime(``dtSrc` **)**`COleDateTime`値からオブジェクトを構築 `DATE` します。

- `COleDateTime(``timeSrc` **)**`COleDateTime`値からオブジェクトを構築 `time_t` します。

- `COleDateTime(`*systimeSrc* **)** `COleDateTime` 値からオブジェクトを構築 `SYSTEMTIME` します。

- `COleDateTime(``filetimeSrc` **)**`COleDateTime`値からオブジェクトを構築 `FILETIME` します。 . は世界 `FILETIME` 協定時刻 (UTC) を使用するため、構造体にローカル時刻を渡すと、結果は正しくありません。 詳細については、「Windows SDK の [ファイル時間](/windows/win32/SysInfo/file-times) 」を参照してください。

- `COleDateTime(``nYear`、 `nMonth` 、 `nDay` 、 `nHour` 、 `nMin` 、 `nSec` **)** は、 `COleDateTime` 指定された数値からオブジェクトを構築します。

- `COleDateTime(``wDosDate`、 `wDosTime` **)** `COleDateTime` 指定した MS-DOS の日付と時刻の値からオブジェクトを構築します。

データ型の詳細については、 `time_t` 「ランタイム*ライブラリリファレンス*」の「 [time](../../c-runtime-library/reference/time-time32-time64.md)関数」を参照してください。

詳細については、Windows SDK の「 [SYSTEMTIME](/windows/win32/api/minwinbase/ns-minwinbase-systemtime) および [FILETIME](/windows/win32/api/minwinbase/ns-minwinbase-filetime) 構造体」を参照してください。

値の境界の詳細については `COleDateTime` 、「 [日付と時刻: オートメーションサポート](../../atl-mfc-shared/date-and-time-automation-support.md)」を参照してください。

> [!NOTE]
> パラメーターを使用するコンストラクターは、 `DBTIMESTAMP` OLEDB が含まれている場合にのみ使用できます。

### <a name="example"></a>例

[!code-cpp[NVC_ATLMFC_Utilities#2](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_4.cpp)]

## <a name="coledatetimeformat"></a><a name="format"></a> COleDateTime:: Format

日付/時刻値の書式設定された表現を作成します。

```
CString Format(DWORD dwFlags = 0,  LCID lcid = LANG_USER_DEFAULT) const;
CString Format(LPCTSTR lpszFormat) const;
CString Format(UINT nFormatID) const;
```

### <a name="parameters"></a>パラメーター

*dwFlags*<br/>
次のいずれかのロケールフラグを示します。

- LOCALE_NOUSEROVERRIDE カスタムユーザー設定ではなく、システムの既定のロケール設定を使用します。

- 解析中に日付部分を無視 VAR_TIMEVALUEONLY ます。

- 解析中に時間部分を無視 VAR_DATEVALUEONLY ます。

*lcid*<br/>
変換に使用するロケール ID を示します。 言語識別子の詳細については、「 [言語識別子](/windows/win32/Intl/language-identifiers)」を参照してください。

*lpszFormat*<br/>
書式設定文字列に類似した書式設定文字列 `printf` 。 各書式指定コードは、前にパーセント () 記号を付けて、 `%` 対応するコンポーネントに置き換えられ `COleDateTime` ます。 書式設定文字列内のその他の文字は、返された文字列にそのままコピーされます。 詳細については、「ランタイム関数 [strftime](../../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md)」を参照してください。 の書式設定コードの値と意味 `Format` は次のとおりです。

- `%H` 現在の日の時間

- `%M` 現在の時間 (分)

- `%S` 現在の1分間の秒数

- `%%` パーセント記号

*nFormatID*<br/>
書式制御文字列のリソース ID。

### <a name="return-value"></a>戻り値

`CString`書式設定された日付/時刻値を格納している。

### <a name="remarks"></a>解説

このオブジェクトの状態 `COleDateTime` が null の場合、戻り値は空の文字列になります。 状態が無効である場合は、文字列リソース ATL_IDS_DATETIME_INVALID によって返される文字列が指定されます。

この関数の3つの形式の簡単な説明を次に示します。

`Format`( *dwFlags*、 *lcid*)<br/>
このフォームでは、日付と時刻の言語仕様 (ロケール Id) を使用して値の書式を設定します。 このフォームでは、既定のパラメーターを使用して日付と時刻を出力します。ただし、時刻部分が 0 (深夜) である場合は、日付のみが出力されます。日付部分が 0 (1899 12 月30日) の場合は、時刻だけが出力されます。 日付/時刻値が 0 (1899 年12月30日午前0時) の場合、既定のパラメーターを持つこのフォームは午前0時に印刷されます。

`Format`( *Lpszformat*)<br/>
このフォームでは、書式設定文字列を使用して値の書式を設定します。書式指定コードの前には、パーセント記号 (%) が付き `printf` ます。 書式設定文字列は、パラメーターとして関数に渡されます。 書式設定コードの詳細については、「 [strftime, wcsftime](../../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md) In The ランタイム Library Reference」を参照してください。

`Format`( *nFormatID*)<br/>
このフォームでは、書式設定文字列を使用して値の書式を設定します。書式指定コードの前には、パーセント記号 (%) が付き `printf` ます。 書式設定文字列はリソースです。 この文字列リソースの ID は、パラメーターとして渡されます。 書式設定コードの詳細については、「 [strftime, wcsftime](../../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md) In The *ランタイム Library Reference*」を参照してください。

### <a name="example"></a>例

[!code-cpp[NVC_ATLMFC_Utilities#3](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_5.cpp)]

## <a name="coledatetimegetasdbtimestamp"></a><a name="getasdbtimestamp"></a> COleDateTime:: GetAsDBTIMESTAMP

オブジェクトの時刻を `COleDateTime` データ構造体として取得するには、このメソッドを呼び出し `DBTIMESTAMP` ます。

```
bool GetAsDBTIMESTAMP(DBTIMESTAMP& timeStamp) const throw();
```

### <a name="parameters"></a>パラメーター

*タイムスタンプ*<br/>
[Dbtimestamp](/dotnet/api/system.data.oledb.oledbtype)構造体への参照。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>解説

結果として得られた時間を参照された *タイムスタンプ* 構造体に格納します。 `DBTIMESTAMP`この関数によって初期化されるデータ構造体は、 `fraction` メンバーが0に設定されます。

### <a name="example"></a>例

[!code-cpp[NVC_ATLMFC_Utilities#4](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_6.cpp)]

## <a name="coledatetimegetassystemtime"></a><a name="getassystemtime"></a> COleDateTime:: GetAsSystemTime

オブジェクトの時刻を `COleDateTime` データ構造体として取得するには、このメソッドを呼び出し `SYSTEMTIME` ます。

```
bool GetAsSystemTime(SYSTEMTIME& sysTime) const throw();
```

### <a name="parameters"></a>パラメーター

*sysTime*<br/>
オブジェクトから変換された日付/時刻値を受け取るための[SYSTEMTIME](/windows/win32/api/minwinbase/ns-minwinbase-systemtime)構造体への参照。 `COleDateTime`

### <a name="return-value"></a>戻り値

成功した場合は TRUE を返します。変換に失敗した場合は FALSE `COleDateTime` 。オブジェクトが NULL または無効の場合は。

### <a name="remarks"></a>解説

`GetAsSystemTime` 結果として得られた時間を参照先の *sysTime* オブジェクトに格納します。 `SYSTEMTIME`この関数によって初期化されるデータ構造体は、 `wMilliseconds` メンバーが0に設定されます。

オブジェクトに保持されているステータス情報の詳細につい `COleDateTime` ては、「 [GetStatus](#getstatus)」を参照してください。

## <a name="coledatetimegetasudate"></a><a name="getasudate"></a> COleDateTime:: GetAsUDATE

オブジェクトの時刻を `COleDateTime` データ構造体として取得するには、このメソッドを呼び出し `UDATE` ます。

```
bool GetAsUDATE(UDATE& uDate) const throw();
```

### <a name="parameters"></a>パラメーター

*uDate*<br/>
`UDATE`オブジェクトから変換された日付/時刻値を受け取る構造体への参照 `COleDateTime` 。

### <a name="return-value"></a>戻り値

成功した場合は TRUE を返します。変換に失敗した場合は FALSE `COleDateTime` 。オブジェクトが NULL または無効の場合は。

### <a name="remarks"></a>解説

`UDATE`構造体は、"アンパック済み" の日付を表します。

## <a name="coledatetimegetcurrenttime"></a><a name="getcurrenttime"></a> COleDateTime:: GetCurrentTime

現在の日付/時刻値を返すには、この静的メンバー関数を呼び出します。

```
static COleDateTime WINAPI GetCurrentTime() throw();
```

### <a name="example"></a>例

[!code-cpp[NVC_ATLMFC_Utilities#5](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_7.cpp)]

## <a name="coledatetimegetday"></a><a name="getday"></a> COleDateTime:: GetDay

この日付/時刻値によって表される月の日付を取得します。

```
int GetDay() const throw();
```

### <a name="return-value"></a>戻り値

このオブジェクトの値で表される月の日付、 `COleDateTime` または `COleDateTime::error` 日を取得できなかった場合は。

### <a name="remarks"></a>解説

有効な戻り値の範囲は 1 ~ 31 です。

このオブジェクトの値を照会するその他のメンバー関数の詳細につい `COleDateTime` ては、次のメンバー関数を参照してください。

- [GetMonth](#getmonth)

- [GetYear](#getyear)

- [Gethour:](#gethour)

- [Getminute:](#getminute)

- [Getsecond:](#getsecond)

- [GetDayOfWeek](#getdayofweek)

- [GetDayOfYear](#getdayofyear)

### <a name="example"></a>例

[!code-cpp[NVC_ATLMFC_Utilities#6](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_8.cpp)]

## <a name="coledatetimegetdayofweek"></a><a name="getdayofweek"></a> COleDateTime:: GetDayOfWeek

この日付/時刻値によって表される月の日付を取得します。

```
int GetDayOfWeek() const throw();
```

### <a name="return-value"></a>戻り値

このオブジェクトの値で表される曜日、 `COleDateTime` または `COleDateTime::error` 曜日を取得できなかった場合は。

### <a name="remarks"></a>解説

有効な戻り値の範囲は 1 ~ 7 です。1は日曜日、2 = 月曜日のようになります。

このオブジェクトの値を照会するその他のメンバー関数の詳細につい `COleDateTime` ては、次のメンバー関数を参照してください。

- [GetDay](#getday)

- [GetMonth](#getmonth)

- [GetYear](#getyear)

- [Gethour:](#gethour)

- [Getminute:](#getminute)

- [Getsecond:](#getsecond)

- [GetDayOfYear](#getdayofyear)

### <a name="example"></a>例

[!code-cpp[NVC_ATLMFC_Utilities#7](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_9.cpp)]

## <a name="coledatetimegetdayofyear"></a><a name="getdayofyear"></a> COleDateTime:: GetDayOfYear

この日付/時刻値によって表される年の通算日を取得します。

```
int GetDayOfYear() const throw();
```

### <a name="return-value"></a>戻り値

このオブジェクトの値で表される年の日付、 `COleDateTime` または `COleDateTime::error` 年の通算日を取得できなかった場合は。

### <a name="remarks"></a>解説

有効な戻り値の範囲は 1 ~ 366 で、1月1日です。

このオブジェクトの値を照会するその他のメンバー関数の詳細につい `COleDateTime` ては、次のメンバー関数を参照してください。

- [GetDay](#getday)

- [GetMonth](#getmonth)

- [GetYear](#getyear)

- [Gethour:](#gethour)

- [Getminute:](#getminute)

- [Getsecond:](#getsecond)

- [GetDayOfWeek](#getdayofweek)

### <a name="example"></a>例

[!code-cpp[NVC_ATLMFC_Utilities#8](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_10.cpp)]

## <a name="coledatetimegethour"></a><a name="gethour"></a> COleDateTime:: Gethour:

この日付/時刻値によって表される時間を取得します。

```
int GetHour() const throw();
```

### <a name="return-value"></a>戻り値

このオブジェクトの値で表される時間 `COleDateTime` 。または `COleDateTime::error` 時間を取得できなかった場合は。

### <a name="remarks"></a>解説

有効な戻り値の範囲は 0 ~ 23 です。

このオブジェクトの値を照会するその他のメンバー関数の詳細につい `COleDateTime` ては、次のメンバー関数を参照してください。

- [GetDay](#getday)

- [GetMonth](#getmonth)

- [GetYear](#getyear)

- [Getminute:](#getminute)

- [Getsecond:](#getsecond)

- [GetDayOfWeek](#getdayofweek)

- [GetDayOfYear](#getdayofyear)

### <a name="example"></a>例

[!code-cpp[NVC_ATLMFC_Utilities#9](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_11.cpp)]

## <a name="coledatetimegetminute"></a><a name="getminute"></a> COleDateTime:: GetMinute

この日付/時刻値によって表される分を取得します。

```
int GetMinute() const throw();
```

### <a name="return-value"></a>戻り値

このオブジェクトの値で表される分、 `COleDateTime` または分を取得できなかった `COleDateTime::error` 場合は。

### <a name="remarks"></a>解説

有効な戻り値の範囲は 0 ~ 59 です。

このオブジェクトの値を照会するその他のメンバー関数の詳細につい `COleDateTime` ては、次のメンバー関数を参照してください。

- [GetDay](#getday)

- [GetMonth](#getmonth)

- [GetYear](#getyear)

- [Gethour:](#gethour)

- [Getsecond:](#getsecond)

- [GetDayOfWeek](#getdayofweek)

- [GetDayOfYear](#getdayofyear)

### <a name="example"></a>例

[Gethour:](#gethour)の例を参照してください。

## <a name="coledatetimegetmonth"></a><a name="getmonth"></a> COleDateTime:: GetMonth

この日付/時刻値によって表される月を取得します。

```
int GetMonth() const throw();
```

### <a name="return-value"></a>戻り値

このオブジェクトの値で表される月 `COleDateTime` `COleDateTime::error` 。月を取得できなかった場合は。

### <a name="remarks"></a>解説

有効な戻り値の範囲は 1 ~ 12 です。

このオブジェクトの値を照会するその他のメンバー関数の詳細につい `COleDateTime` ては、次のメンバー関数を参照してください。

- [GetDay](#getday)

- [GetYear](#getyear)

- [Gethour:](#gethour)

- [Getminute:](#getminute)

- [Getsecond:](#getsecond)

- [GetDayOfWeek](#getdayofweek)

- [GetDayOfYear](#getdayofyear)

### <a name="example"></a>例

[Getday](#getday)の例を参照してください。

## <a name="coledatetimegetsecond"></a><a name="getsecond"></a> COleDateTime:: GetSecond

この日付/時刻値によって表される秒を取得します。

```
int GetSecond() const throw();
```

### <a name="return-value"></a>戻り値

このオブジェクトの値で表される2番目の `COleDateTime` `COleDateTime::error` 。2番目のを取得できなかった場合は。

### <a name="remarks"></a>解説

有効な戻り値の範囲は 0 ~ 59 です。

> [!NOTE]
> クラスは、 `COleDateTime` うるう秒をサポートしていません。

の実装の詳細については `COleDateTime` 、「 [日付と時刻: オートメーションのサポート](../../atl-mfc-shared/date-and-time-automation-support.md)」を参照してください。

このオブジェクトの値を照会するその他のメンバー関数の詳細につい `COleDateTime` ては、次のメンバー関数を参照してください。

- [GetDay](#getday)

- [GetMonth](#getmonth)

- [GetYear](#getyear)

- [Gethour:](#gethour)

- [Getminute:](#getminute)

- [GetDayOfWeek](#getdayofweek)

- [GetDayOfYear](#getdayofyear)

### <a name="example"></a>例

[Gethour:](#gethour)の例を参照してください。

## <a name="coledatetimegetstatus"></a><a name="getstatus"></a> COleDateTime:: GetStatus

指定されたオブジェクトの状態 (有効性) を取得し `COleDateTime` ます。

```
DateTimeStatus GetStatus() const throw();
```

### <a name="return-value"></a>戻り値

この値の状態を返し `COleDateTime` ます。 `GetStatus`既定のを使用して構築されたオブジェクトでを呼び出すと `COleDateTime` 、有効なが返されます。 `GetStatus` `COleDateTime` コンストラクターを null に設定して初期化されたオブジェクトでを呼び出すと、 `GetStatus` は null を返します。

### <a name="remarks"></a>解説

戻り値は、クラス内で定義されている列挙型によって定義され `DateTimeStatus` `COleDateTime` ます。

```
enum DateTimeStatus
{
   error = -1,
   valid = 0,
   invalid = 1,    // Invalid date (out of range, etc.)
   null = 2,       // Literally has no value
};
```

これらの状態値の簡単な説明については、次の一覧を参照してください。

- `COleDateTime::error` 日付/時刻値の一部を取得しようとしているときにエラーが発生したことを示します。

- `COleDateTime::valid` このオブジェクトが有効であることを示し `COleDateTime` ます。

- `COleDateTime::invalid` このオブジェクトが無効であることを示します。つまり `COleDateTime` 、値が正しくない可能性があります。

- `COleDateTime::null` このオブジェクトが null であること、つまり `COleDateTime` 、このオブジェクトに値が指定されていないことを示します。 (これは、C++ NULL ではなく、"値がない" というデータベースの意味では "null" です)。

オブジェクトの状態 `COleDateTime` は、次の場合には無効です。

- 値が、 `VARIANT` `COleVariant` 日付/時刻値に変換できなかった値または値から設定されている場合は。

- `time_t` `SYSTEMTIME` `FILETIME` 有効な日付/時刻値に変換できない、、またはの値から値が設定されている場合は。

- 値が `SetDateTime` 無効なパラメーター値を使用して設定されている場合は。

- このオブジェクトの算術演算の実行中にオーバーフローまたはアンダーフローが発生した場合 (つまり、 `+=` または) `-=` 。

- 無効な値がこのオブジェクトに割り当てられた場合は。

- このオブジェクトの状態が、を使用して明示的に無効に設定された場合は `SetStatus` 。

状態が無効に設定されている可能性のある操作の詳細については、次のメンバー関数を参照してください。

- [COleDateTime](#coledatetime)

- [SetDateTime](#setdatetime)

- [演算子 +、-](#operator_add_-)

- [operator + =、-=](#operator_add_eq_-_eq)

値の境界の詳細については `COleDateTime` 、「 [日付と時刻: オートメーションサポート](../../atl-mfc-shared/date-and-time-automation-support.md)」を参照してください。

### <a name="example"></a>例

[!code-cpp[NVC_ATLMFC_Utilities#10](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_12.cpp)]

## <a name="coledatetimegetyear"></a><a name="getyear"></a> COleDateTime:: GetYear

この日付/時刻値によって表される年を取得します。

```
int GetYear() const throw();
```

### <a name="return-value"></a>戻り値

このオブジェクトの値で表される年 `COleDateTime` 。または `COleDateTime::error` 年を取得できなかった場合は。

### <a name="remarks"></a>解説

有効な戻り値の範囲は 100 ~ 9999 です。これには、世紀が含まれます。

このオブジェクトの値を照会するその他のメンバー関数の詳細につい `COleDateTime` ては、次のメンバー関数を参照してください。

- [GetDay](#getday)

- [GetMonth](#getmonth)

- [Gethour:](#gethour)

- [Getminute:](#getminute)

- [Getsecond:](#getsecond)

- [GetDayOfWeek](#getdayofweek)

- [GetDayOfYear](#getdayofyear)

値の境界の詳細については `COleDateTime` 、「 [日付と時刻: オートメーションサポート](../../atl-mfc-shared/date-and-time-automation-support.md)」を参照してください。

### <a name="example"></a>例

[Getday](#getday)の例を参照してください。

## <a name="coledatetimem_dt"></a><a name="m_dt"></a> COleDateTime:: m_dt

`DATE`このオブジェクトの基になる構造体 `COleDateTime` 。

```
DATE m_dt;
```

### <a name="remarks"></a>解説

> [!CAUTION]
> `DATE`この関数によって返されるポインターによってアクセスされるオブジェクトの値を変更すると、このオブジェクトの値が変更され `COleDateTime` ます。 このオブジェクトの状態は変更されません `COleDateTime` 。

オブジェクトの実装の詳細については `DATE` 、「 [日付と時刻: オートメーションのサポート](../../atl-mfc-shared/date-and-time-automation-support.md)」を参照してください。

## <a name="coledatetimem_status"></a><a name="m_status"></a> COleDateTime:: m_status

このオブジェクトの状態を格納 `COleDateTime` します。

```
DateTimeStatus m_status;
```

### <a name="remarks"></a>解説

このデータメンバーの型は列挙型であり `DateTimeStatus` 、クラス内で定義されてい `COleDateTime` ます。 詳細については、「 [COleDateTime:: GetStatus](#getstatus)」を参照してください。

> [!CAUTION]
> このデータメンバーは、高度なプログラミングの状況を対象としています。 インラインメンバー関数 [GetStatus](#getstatus) および [SetStatus](#setstatus)を使用する必要があります。 `SetStatus`このデータメンバーを明示的に設定する方法については、「」を参照してください。

## <a name="coledatetimeoperator-"></a><a name="operator_eq"></a> COleDateTime:: operator =

値をコピー `COleDateTime` します。

```
COleDateTime& operator=(const VARIANT& varSrc) throw();
COleDateTime& operator=(DATE dtSrc) throw();
COleDateTime& operator=(const time_t& timeSrc) throw();
COleDateTime& operator=(const __time64_t& timeSrc) throw();
COleDateTime& operator=(const SYSTEMTIME& systimeSrc) throw();
COleDateTime& operator=(const FILETIME& filetimeSrc) throw();
COleDateTime& operator=(const UDATE& uDate) throw();
```

### <a name="remarks"></a>解説

これらのオーバーロードされた代入演算子は、ソースの日付/時刻値をこのオブジェクトにコピー `COleDateTime` します。 これらのオーバーロードされた代入演算子の簡単な説明を次に示します。

- **operator = (** `dateSrc` **)** オペランドの値と状態がこのオブジェクトにコピーされ `COleDateTime` ます。

- **operator = (** *varsrc* **)**[バリアント](/windows/win32/api/oaidl/ns-oaidl-variant)値 (または[COleVariant](../../mfc/reference/colevariant-class.md)オブジェクト) から日付/時刻 (VT_DATE) への変換が成功すると、変換後の値がこのオブジェクトにコピーされ、 `COleDateTime` その状態が有効に設定されます。 変換が成功しなかった場合、このオブジェクトの値は 0 (1899 年12月30日午前0時) に設定され、その状態は無効になります。

- **operator = (** `dtSrc` **)** `DATE` このオブジェクトに値がコピーされ、 `COleDateTime` その状態が有効に設定されます。

- **operator = (** `timeSrc` **)** `time_t` `__time64_t` このオブジェクトには、値または値が変換されてコピーされ `COleDateTime` ます。 変換が成功した場合、このオブジェクトの状態は valid に設定されます。失敗した場合は、無効に設定されます。

- **operator = (** *systimeSrc* **)**[SYSTEMTIME](/windows/win32/api/minwinbase/ns-minwinbase-systemtime)値が変換され、このオブジェクトにコピーされ `COleDateTime` ます。 変換が成功した場合、このオブジェクトの状態は valid に設定されます。失敗した場合は、無効に設定されます。

- **operator = (** `uDate` **)** `UDATE` 値が変換され、このオブジェクトにコピーされ `COleDateTime` ます。 変換が成功した場合、このオブジェクトの状態は valid に設定されます。失敗した場合は、無効に設定されます。 `UDATE`構造体は、"アンパック済み" の日付を表します。 詳細については、「 [Vardatefromudate](/windows/win32/api/oleauto/nf-oleauto-vardatefromudate)関数」を参照してください。

- **operator = (** `filetimeSrc` **)** [FILETIME](/windows/win32/api/minwinbase/ns-minwinbase-filetime) 値が変換され、このオブジェクトにコピーされ `COleDateTime` ます。 変換が成功した場合、このオブジェクトの状態は valid に設定されます。それ以外の場合は、無効に設定されます。 `FILETIME` 世界協定時刻 (UTC) を使用します。そのため、構造体に UTC 時刻を渡すと、結果は UTC 時刻から現地時刻に変換され、バリアント時刻として格納されます。 この動作は、Visual C++ 6.0 および Visual C++ .NET 2003 SP2 と同じです。 詳細については、「Windows SDK の [ファイル時間](/windows/win32/SysInfo/file-times) 」を参照してください。

詳細については、Windows SDK の [バリアント](/windows/win32/api/oaidl/ns-oaidl-variant) エントリを参照してください。

データ型の詳細については、 `time_t` 「ランタイム*ライブラリリファレンス*」の「 [time](../../c-runtime-library/reference/time-time32-time64.md)関数」を参照してください。

詳細については、Windows SDK の「 [SYSTEMTIME](/windows/win32/api/minwinbase/ns-minwinbase-systemtime) および [FILETIME](/windows/win32/api/minwinbase/ns-minwinbase-filetime) 構造体」を参照してください。

値の境界の詳細については `COleDateTime` 、「 [日付と時刻: オートメーションサポート](../../atl-mfc-shared/date-and-time-automation-support.md)」を参照してください。

## <a name="coledatetimeoperator---"></a><a name="operator_add_-"></a> COleDateTime:: operator +、-

値を加算および減算 `ColeDateTime` します。

```
COleDateTime operator+(COleDateTimeSpan dateSpan) const throw();
COleDateTime operator-(COleDateTimeSpan dateSpan) const throw();
COleDateTimeSpan operator-(const COleDateTime& date) const throw();
```

### <a name="remarks"></a>解説

`COleDateTime` オブジェクトは絶対時刻を表します。 [COleDateTimeSpan](../../atl-mfc-shared/reference/coledatetimespan-class.md) オブジェクトは相対時刻を表します。 最初の2つの演算子を使用すると、値の値を加算および減算でき `COleDateTimeSpan` `COleDateTime` ます。 3番目の演算子を使用すると、ある `COleDateTime` 値を別の値から減算して値を生成することができ `COleDateTimeSpan` ます。

オペランドのいずれかが null の場合、結果の値の状態 `COleDateTime` は null になります。

結果の `COleDateTime` 値が許容される値の範囲外になる場合、その `COleDateTime` 値の状態は無効になります。

オペランドのいずれかが無効で、もう一方が null でない場合、結果の値の状態 `COleDateTime` は無効になります。

**+** **-** オブジェクトが null に設定されている場合、および演算子はアサートし `COleDateTime` ます。 例については、「 [COleDateTime 関係演算子](#coledatetime_relational_operators) 」を参照してください。

有効、無効、および null 状態の値の詳細については、 [m_status](#m_status) メンバー変数を参照してください。

値の境界の詳細については `COleDateTime` 、「 [日付と時刻: オートメーションサポート](../../atl-mfc-shared/date-and-time-automation-support.md)」を参照してください。

### <a name="example"></a>例

[!code-cpp[NVC_ATLMFC_Utilities#12](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_13.cpp)]

## <a name="coledatetimeoperator---"></a><a name="operator_add_eq_-_eq"></a> COleDateTime:: operator + =、-=

`ColeDateTime`このオブジェクトの値を加算および減算 `COleDateTime` します。

```
COleDateTime& operator+=(COleDateTimeSpan dateSpan) throw();
COleDateTime& operator-=(COleDateTimeSpan dateSpan) throw();
```

### <a name="remarks"></a>解説

これらの演算子を使用すると、 `COleDateTimeSpan` このに対して値を加算および減算でき `COleDateTime` ます。 オペランドのいずれかが null の場合、結果の値の状態 `COleDateTime` は null になります。

結果の `COleDateTime` 値が許容値の範囲外になる場合、この値の状態 `COleDateTime` は無効に設定されます。

オペランドのいずれかが無効で、その他のが null でない場合、結果の値の状態 `COleDateTime` は無効になります。

有効、無効、および null 状態の値の詳細については、 [m_status](#m_status) メンバー変数を参照してください。

**+=** **-=** オブジェクトが null に設定されている場合、および演算子はアサートし `COleDateTime` ます。 例については、「 [COleDateTime 関係演算子](#coledatetime_relational_operators) 」を参照してください。

値の境界の詳細については `COleDateTime` 、「 [日付と時刻: オートメーションサポート](../../atl-mfc-shared/date-and-time-automation-support.md)」を参照してください。

## <a name="coledatetimeoperator-date"></a><a name="operator_date"></a> COleDateTime:: operator DATE

値をに変換 `ColeDateTime` `DATE` します。

```
operator DATE() const throw();
```

### <a name="remarks"></a>解説

この演算子は、 `DATE` このオブジェクトから値がコピーされるオブジェクトを返し `COleDateTime` ます。 オブジェクトの実装の詳細については `DATE` 、「 [日付と時刻: オートメーションのサポート](../../atl-mfc-shared/date-and-time-automation-support.md)」を参照してください。

`DATE`オブジェクトが null に設定されている場合、演算子はをアサートし `COleDateTime` ます。 例については、「 [COleDateTime 関係演算子](#coledatetime_relational_operators) 」を参照してください。

## <a name="coledatetimeparsedatetime"></a><a name="parsedatetime"></a> COleDateTime::P arseDateTime

文字列を解析して、日付/時刻値を読み取ります。

```
bool ParseDateTime(
    LPCTSTR lpszDate,
    DWORD dwFlags = 0,
    LCID lcid = LANG_USER_DEFAULT) throw();
```

### <a name="parameters"></a>パラメーター

*lpszDate*<br/>
解析される null で終わる文字列へのポインター。 詳細については、「解説」を参照してください。

*dwFlags*<br/>
ロケール設定および解析のフラグを示します。 次のフラグの1つまたは複数を実行します。

- LOCALE_NOUSEROVERRIDE は、カスタムユーザー設定ではなく、システムの既定のロケール設定を使用します。

- 解析中に日付部分を無視 VAR_TIMEVALUEONLY ます。

- 解析中に時間部分を無視 VAR_DATEVALUEONLY ます。

*lcid*<br/>
変換に使用するロケール ID を示します。

### <a name="return-value"></a>戻り値

文字列が日付/時刻値に正常に変換された場合は TRUE を返し、それ以外の場合は FALSE を返します。

### <a name="remarks"></a>解説

文字列が日付/時刻値に正常に変換された場合、このオブジェクトの値 `COleDateTime` はその値に設定され、その状態が有効になります。

> [!NOTE]
> 年の値は、100 ~ 9999 の範囲で指定する必要があります。

*Lpszdate*パラメーターには、さまざまな形式を使用できます。 たとえば、次の文字列には、許容される日付/時刻書式が含まれています。

`"25 January 1996"`

`"8:30:00"`

`"20:30:00"`

`"January 25, 1996 8:30:00"`

`"8:30:00 Jan. 25, 1996"`

`"1/25/1996 8:30:00"  // always specify the full year, even in a 'short date' format`

ロケール ID は、文字列形式を日付/時刻値への変換に使用できるかどうかにも影響します。

VAR_DATEVALUEONLY の場合、時刻の値は時刻0または午前0時に設定されます。 VAR_TIMEVALUEONLY の場合、日付の値は date 0 に設定されます。つまり、1899年12月30日に設定されます。

文字列を日付/時刻値に変換できなかった場合、または数値のオーバーフローがあった場合、このオブジェクトの状態 `COleDateTime` は無効になります。

値の境界と実装の詳細については `COleDateTime` 、「 [日付と時刻: オートメーションサポート](../../atl-mfc-shared/date-and-time-automation-support.md)」を参照してください。

## <a name="coledatetimesetdate"></a><a name="setdate"></a> COleDateTime:: SetDate

このオブジェクトの日付を設定 `COleDateTime` します。

```
int SetDate(
    int nYear,
    int nMonth,
    int nDay) throw();
```

### <a name="parameters"></a>パラメーター

*nYear*\
このオブジェクトにコピーする年を示し `COleDateTime` ます。

*nMonth*\
このオブジェクトにコピーする月を指定 `COleDateTime` します。

*nDay*\
このオブジェクトにコピーする日を指定し `COleDateTime` ます。

### <a name="return-value"></a>戻り値

このオブジェクトの値が `COleDateTime` 正常に設定された場合は0。それ以外の場合は1。 この戻り値は、列挙型に基づいてい `DateTimeStatus` ます。 詳細については、「 [SetStatus](#setstatus) メンバー関数」を参照してください。

### <a name="remarks"></a>解説

日付は、指定した値に設定されます。 時刻は、時刻 0 (午前0時) に設定されます。

パラメーター値の境界については、次の表を参照してください。

|パラメーター|Bounds|
|---------------|------------|
|*nYear*|100 ~ 9999|
|*nMonth*|1 - 12|
|*nDay*|0 - 31|

月の日付がオーバーフローした場合は、翌月の正しい日付に変換され、それに応じて月や年が加算されます。 日の値が0の場合は、前月の最後の日を示します。 動作はと同じ `SystemTimeToVariantTime` です。

パラメーターで指定した日付値が有効でない場合、このオブジェクトの状態はに設定され `COleDateTime::invalid` ます。 [GetStatus](#getstatus)を使用して値の有効性を確認 `DATE` し、 [m_dt](#m_dt)の値が変更されないようにする必要があります。

日付値の例をいくつか次に示します。

|*nYear*|*nMonth*|*nDay*|値|
|-------------|--------------|------------|-----------|
|2000|2|29|2000年2月29日|
|1776|7|4|4 1776 年7月|
|1925|4|35|35年4月 1925 (無効な日付)|
|10000|1|1|1万年1月1日 (無効な日付)|

日付と時刻の両方を設定するには、「 [COleDateTime:: SetDateTime](#setdatetime)」を参照してください。

このオブジェクトの値に対してクエリを実行するメンバー関数の詳細につい `COleDateTime` ては、次のメンバー関数を参照してください。

- [GetDay](#getday)

- [GetMonth](#getmonth)

- [GetYear](#getyear)

- [Gethour:](#gethour)

- [Getminute:](#getminute)

- [Getsecond:](#getsecond)

- [GetDayOfWeek](#getdayofweek)

- [GetDayOfYear](#getdayofyear)

値の境界の詳細については `COleDateTime` 、「 [日付と時刻: オートメーションサポート](../../atl-mfc-shared/date-and-time-automation-support.md)」を参照してください。

### <a name="example"></a>例

[!code-cpp[NVC_ATLMFC_Utilities#11](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_14.cpp)]

## <a name="coledatetimesetdatetime"></a><a name="setdatetime"></a> COleDateTime:: SetDateTime

このオブジェクトの日付と時刻を設定 `COleDateTime` します。

```
int SetDateTime(
    int nYear,
    int nMonth,
    int nDay,
    int nHour,
    int nMin,
    int nSec) throw();
```

### <a name="parameters"></a>パラメーター

*Nyear*、 *nyear*、 *nyear*、 *nyear*、 *nyear*、 *nSec*<br/>
このオブジェクトにコピーする日付と時刻のコンポーネントを示し `COleDateTime` ます。

### <a name="return-value"></a>戻り値

このオブジェクトの値が `COleDateTime` 正常に設定された場合は0。それ以外の場合は1。 この戻り値は、列挙型に基づいてい `DateTimeStatus` ます。 詳細については、「 [SetStatus](#setstatus) メンバー関数」を参照してください。

### <a name="remarks"></a>解説

パラメーター値の境界については、次の表を参照してください。

|パラメーター|Bounds|
|---------------|------------|
|*nYear*|100 ~ 9999|
|*nMonth*|1 - 12|
|*nDay*|0 - 31|
|*nHour*|0 - 23|
|*N1 日*|0 - 59|
|*nSec*|0 - 59|

月の日付がオーバーフローした場合は、翌月の正しい日付に変換され、それに応じて月や年が加算されます。 日の値が0の場合は、前月の最後の日を示します。 動作は [SystemTimeToVariantTime](/windows/win32/api/oleauto/nf-oleauto-systemtimetovarianttime)と同じです。

パラメーターで指定した日付または時刻の値が無効である場合、このオブジェクトの状態は無効に設定され、このオブジェクトの値は変更されません。

次に、時刻値の例をいくつか示します。

|*nHour*|*N1 日*|*nSec*|値|
|-------------|------------|------------|-----------|
|1|3|3|01:03:03|
|23|45|0|23:45:00|
|25|30|0|無効|
|9|60|0|無効|

日付値の例をいくつか次に示します。

|*nYear*|*nMonth*|*nDay*|値|
|-------------|--------------|------------|-----------|
|1995|4|15|1995年4月15日|
|1789|7|14|1789年7月17日|
|1925|2|30|無効|
|10000|1|1|無効|

日付のみを設定するには、「 [COleDateTime:: SetDate](#setdate)」を参照してください。 時刻のみを設定するには、「 [COleDateTime:: SetTime](#settime)」を参照してください。

このオブジェクトの値に対してクエリを実行するメンバー関数の詳細につい `COleDateTime` ては、次のメンバー関数を参照してください。

- [GetDay](#getday)

- [GetMonth](#getmonth)

- [GetYear](#getyear)

- [Gethour:](#gethour)

- [Getminute:](#getminute)

- [Getsecond:](#getsecond)

- [GetDayOfWeek](#getdayofweek)

- [GetDayOfYear](#getdayofyear)

値の境界の詳細については `COleDateTime` 、「 [日付と時刻: オートメーションサポート](../../atl-mfc-shared/date-and-time-automation-support.md)」を参照してください。

### <a name="example"></a>例

[GetStatus](#getstatus)の例を参照してください。

## <a name="coledatetimesetstatus"></a><a name="setstatus"></a> COleDateTime:: SetStatus

このオブジェクトの状態を設定 `COleDateTime` します。

```cpp
void SetStatus(DateTimeStatus status) throw();
```

### <a name="parameters"></a>パラメーター

*status*<br/>
このオブジェクトの新しいステータス値 `COleDateTime` 。

### <a name="remarks"></a>解説

*Status*パラメーターの値は、クラス内で定義されている列挙型によって定義され `DateTimeStatus` `COleDateTime` ます。 詳細については、「 [COleDateTime:: GetStatus](#getstatus) 」を参照してください。

> [!CAUTION]
> この関数は、高度なプログラミングの状況に適しています。 この関数は、このオブジェクトのデータを変更しません。 この値は、通常、状態を **null** または **無効**に設定するために使用されます。 代入演算子 ([operator =](#operator_eq)) と [setdatetime](#setdatetime) は、ソース値に基づいてオブジェクトの状態を設定します。

### <a name="example"></a>例

[GetStatus](#getstatus)の例を参照してください。

## <a name="coledatetimesettime"></a><a name="settime"></a> COleDateTime:: SetTime

このオブジェクトの時刻を設定 `COleDateTime` します。

```
int SetTime(
    int nHour,
    int nMin,
    int nSec) throw();
```

### <a name="parameters"></a>パラメーター

*Nhour*、 *nhour*、 *nSec*<br/>
このオブジェクトにコピーされる時刻部分を示し `COleDateTime` ます。

### <a name="return-value"></a>戻り値

このオブジェクトの値が `COleDateTime` 正常に設定された場合は0。それ以外の場合は1。 この戻り値は、列挙型に基づいてい `DateTimeStatus` ます。 詳細については、「 [SetStatus](#setstatus) メンバー関数」を参照してください。

### <a name="remarks"></a>解説

時刻は、指定された値に設定されます。 日付は、1899年12月30日の日付0に設定されます。

パラメーター値の境界については、次の表を参照してください。

|パラメーター|Bounds|
|---------------|------------|
|*nHour*|0 - 23|
|*N1 日*|0 - 59|
|*nSec*|0 - 59|

パラメーターで指定した時刻値が有効でない場合、このオブジェクトの状態は無効に設定され、このオブジェクトの値は変更されません。

次に、時刻値の例をいくつか示します。

|*nHour*|*N1 日*|*nSec*|値|
|-------------|------------|------------|-----------|
|1|3|3|01:03:03|
|23|45|0|23:45:00|
|25|30|0|無効|
|9|60|0|無効|

日付と時刻の両方を設定するには、「 [COleDateTime:: SetDateTime](#setdatetime)」を参照してください。

このオブジェクトの値に対してクエリを実行するメンバー関数の詳細につい `COleDateTime` ては、次のメンバー関数を参照してください。

- [GetDay](#getday)

- [GetMonth](#getmonth)

- [GetYear](#getyear)

- [Gethour:](#gethour)

- [Getminute:](#getminute)

- [Getsecond:](#getsecond)

- [GetDayOfWeek](#getdayofweek)

- [GetDayOfYear](#getdayofyear)

値の境界の詳細については `COleDateTime` 、「 [日付と時刻: オートメーションサポート](../../atl-mfc-shared/date-and-time-automation-support.md)」を参照してください。

### <a name="example"></a>例

[SetDate](#setdate)の例を参照してください。

## <a name="see-also"></a>関連項目

[COleVariant クラス](../../mfc/reference/colevariant-class.md)<br/>
[CTime クラス](../../atl-mfc-shared/reference/ctime-class.md)<br/>
[CTimeSpan クラス](../../atl-mfc-shared/reference/ctimespan-class.md)<br/>
[階層図](../../mfc/hierarchy-chart.md)<br/>
[ATL/MFC 共有クラス](../../atl-mfc-shared/atl-mfc-shared-classes.md)

---
title: クラス
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
ms.openlocfilehash: 8ba09430427b6ece8ae5956912cbcc40fb33fcf2
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "81747158"
---
# <a name="coledatetime-class"></a>クラス

OLE オートメーション`DATE`で使用されるデータ型をカプセル化します。

## <a name="syntax"></a>構文

```
class COleDateTime
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[::コレデイトタイム](#coledatetime)|`COleDateTime` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[フォーマット](#format)|オブジェクトの書式付き文字列形式を`COleDateTime`生成します。|
|[を指定します。](#getasdbtimestamp)|`COleDateTime`オブジェクト内の時刻を`DBTIMESTAMP`データ構造体として取得します。|
|[システムタイムを取得します。](#getassystemtime)|オブジェクト内の時刻を`COleDateTime` [SYSTEMTIME](/windows/win32/api/minwinbase/ns-minwinbase-systemtime)データ構造体として取得します。|
|[コレデイトタイム::ゲタスデート](#getasudate)|データ構造体として`COleDateTime``UDATE`時刻を取得します。|
|[現在の時刻を取得します。](#getcurrenttime)|現在の`COleDateTime`時刻 (静的メンバー関数) を表すオブジェクトを作成します。|
|[コレデイトタイム::ゲットデイ](#getday)|この`COleDateTime`オブジェクトが表す日 (1 ~ 31) を返します。|
|[コレデイトタイム::ゲットデイオブウィーク](#getdayofweek)|この`COleDateTime`オブジェクトが表す曜日を返します (日曜日 = 1)。|
|[コレデイトタイム::ゲデイオブイヤー](#getdayofyear)|この`COleDateTime`オブジェクトが表す年の日を返します (Jan 1 = 1)。|
|[コレデイトタイム::ゲットアワー](#gethour)|この`COleDateTime`オブジェクトが表す時間 (0 ~ 23) を返します。|
|[コレデイトタイム::ゲットミニット](#getminute)|この`COleDateTime`オブジェクトが表す分 (0 ~ 59) を返します。|
|[コレデイトタイム::ゲットマン](#getmonth)|この`COleDateTime`オブジェクトが表す月を返します (1 ~ 12)。|
|[コレデイトタイム::ゲットセカンド](#getsecond)|この`COleDateTime`オブジェクトが表す 2 番目の値を返します (0 ~ 59)。|
|[を取得します。](#getstatus)|この`COleDateTime`オブジェクトの状態 (有効性) を取得します。|
|[コレデイトタイム::ゲットイヤー](#getyear)|このオブジェクトが表`COleDateTime`す年を返します。|
|[コレデイトタイム::P行日時間を指定します。](#parsedatetime)|文字列から日付/時刻値を読み取り、値を`COleDateTime`設定します。|
|[セットデイトタイム::セットデイト](#setdate)|この`COleDateTime`オブジェクトの値を指定した日付のみの値に設定します。|
|[を設定します。](#setdatetime)|この`COleDateTime`オブジェクトの値を指定した日付/時刻値に設定します。|
|[を設定します。](#setstatus)|この`COleDateTime`オブジェクトのステータス (有効性) を設定します。|
|[コレデイトタイム::セットタイム](#settime)|この`COleDateTime`オブジェクトの値を、指定した時間のみの値に設定します。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[::演算子 =、COleDateTime::演算子<など](#coledatetime_relational_operators)|2`COleDateTime`つの値を比較します。|
|[::演算子 +、COleDateTime::演算子 -](#operator_add_-)|値を加算`COleDateTime`および減算します。|
|[:演算子 +=、COleDateTime::演算子 -=](#operator_add_eq_-_eq)|この`COleDateTime`オブジェクトの値`COleDateTime`を加算および減算します。|
|[を指定します。](#operator_eq)|値を`COleDateTime`コピーします。|
|[::演算子日付、COleDateTime::演算子日付*](#operator_date)|値を`COleDateTime`に変換`DATE`します。 `DATE*`|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[コレデイトタイム::m_dt](#m_dt)|この`COleDateTime`オブジェクトの`DATE`基になるオブジェクトを格納します。|
|[コレデイトタイム::m_status](#m_status)|このオブジェクトの状態を`COleDateTime`格納します。|

## <a name="remarks"></a>解説

`COleDateTime`は基本クラスを持っていません。

これは、OLE オートメーションの[VARIANT](/windows/win32/api/oaidl/ns-oaidl-variant)データ型に使用できる型の 1 つです。 値`COleDateTime`は、日付と時刻の絶対値を表します。

型`DATE`は浮動小数点値として実装されます。 1899年12月30日午前0時から日数が測定されます。 次の表に、日付と関連する値を示します。

|Date|値|
|----------|-----------|
|1899年12月29日午前0時|-1.0|
|1899年12月29日 午前6時|-1.25|
|1899年12月30日深夜|0.0|
|1899年12月31日午前0時|1.0|
|1900年1月1日午前6時|2.25|

> [!CAUTION]
> 上の表では、日の値は 1899 年 12 月 30 日の午前 0 時より前に負になりますが、時刻の値は負ではありません。 たとえば、午前 6:00 は、日を表す整数が正 (1899 年 12 月 30 日より後) または負 (1899 年 12 月 30 日以前) のどちらであるかに関係なく、常に小数の値 0.25 で表されます。 これは、単純な浮動小数点比較では、1899 年`COleDateTime`12 月 29 日の午前 6 時を、同じ日の午前 7:00**以降に誤**って並べ替えることを意味します。

クラス`COleDateTime`は100日から9999年12月31日までの日付を処理します。 この`COleDateTime`クラスはグレゴリオ暦を使用します。ユリウス日付はサポートしていません。 `COleDateTime`夏時間を無視します。 ([日付と時刻: オートメーションサポート](../../atl-mfc-shared/date-and-time-automation-support.md)を参照してください。

> [!NOTE]
> この形式を`%y`使用して、1900 年から始まる日付の場合にのみ 2 桁の年を取得できます。 1900`%y`年より前の日付にこの形式を使用すると、ASSERT エラーが生成されます。

この型は、日付のみの値または時刻のみの値を表すためにも使用されます。 日付 0 (1899 年 12 月 30 日) は時刻のみの値に使用され、時刻 00:00 (真夜中) は日付のみの値に使用されます。

100`COleDateTime`未満の日付を使用してオブジェクトを作成した場合、日付は受け入れられますが`GetYear`、`GetMonth`その`GetDay`後`GetHour`に`GetMinute`、 `GetSecond` 、 、 、 、 、 、 、 を呼び出して 、-1 を返します。 以前は、2 桁の日付を使用で使用できますが、MFC 4.2 以降では 100 以上の日付を使用する必要があります。

問題を回避するには、4 桁の日付を指定します。 次に例を示します。

[!code-cpp[NVC_ATLMFC_Utilities#1](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_1.cpp)]

値の基本的な算術`COleDateTime`演算では、コンパニオン クラス[COleDateTimeSpan](../../atl-mfc-shared/reference/coledatetimespan-class.md)を使用します。 `COleDateTimeSpan`値は時間間隔を定義します。 これらのクラス間の関係は[、CTime](../../atl-mfc-shared/reference/ctime-class.md)と[CTimeSpan](../../atl-mfc-shared/reference/ctimespan-class.md)の間の関係と似ています。

クラスと クラスの`COleDateTime`詳細`COleDateTimeSpan`については、「[日付と時刻: オートメーション サポート](../../atl-mfc-shared/date-and-time-automation-support.md)」を参照してください。

## <a name="requirements"></a>必要条件

**ヘッダー:** アトルコムタイム.h

## <a name="coledatetime-relational-operators"></a><a name="coledatetime_relational_operators"></a>関係演算子

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
> ATLASSERT は、2 つのオペランドのいずれかが無効な場合に発生します。

### <a name="example"></a>例

[!code-cpp[NVC_ATLMFC_Utilities#13](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_2.cpp)]

### <a name="example"></a>例

演算子**>=** ** \< **、、**>** および**<** は、`COleDateTime`オブジェクトが null に設定されている場合にアサートします。

[!code-cpp[NVC_ATLMFC_Utilities#170](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_3.cpp)]

## <a name="coledatetimecoledatetime"></a><a name="coledatetime"></a>::コレデイトタイム

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

*日付Src*<br/>
新しい`COleDateTime``COleDateTime`オブジェクトにコピーされる既存のオブジェクト。

*varSrc*<br/>
日付/`VARIANT`時刻値 (VT_DATE) に変換され、新しい`COleVariant``COleDateTime`オブジェクトにコピーされる既存のデータ構造 (オブジェクトの場合があります)。

*dtSrc*<br/>
新しい`COleDateTime`オブジェクトにコピー`DATE`される日付/時刻 ( ) の値。

*タイムスrc*<br/>
日付`time_t`/`__time64_t`時刻値に変換され、新しい`COleDateTime`オブジェクトにコピーされる A または値。

*シスタイムスrc*<br/>
日付`SYSTEMTIME`/時刻値に変換され、新しい`COleDateTime`オブジェクトにコピーされる構造体。

*ファイルタイムスrc*<br/>
日付`FILETIME`/時刻値に変換され、新しい`COleDateTime`オブジェクトにコピーされる構造体。 は`FILETIME`世界協定時刻 (UTC) を使用するため、構造体にローカル時刻を渡すと、結果が正しくなれてしまいます。 詳細については、Windows SDK の[「ファイル時間](/windows/win32/SysInfo/file-times)」を参照してください。

*年*, *nMonth*, *nDay*, *nHour*, *nMin*, *nSec*<br/>
新しい`COleDateTime`オブジェクトにコピーする日付と時刻の値を指定します。

*を指定*します *。*<br/>
日付/時刻値に変換され、新しい`COleDateTime`オブジェクトにコピーされる MS-DOS の日付と時刻の値。

*タイムスタンプ*<br/>
現在のローカル時間を含む[DBTimeStamp](/dotnet/api/system.data.oledb.oledbtype)構造体への参照。

### <a name="remarks"></a>解説

これらのコンストラクターは、すべて、`COleDateTime`指定された値に初期化された新しいオブジェクトを作成します。 次の表は、各日付と時刻のコンポーネントの有効な範囲を示しています。

|日付/時刻コンポーネント|有効な範囲|
|--------------------------|-----------------|
|year|100 - 9999|
|month|0 - 12|
|day|0 - 31|
|hour|0 - 23|
|minute|0 - 59|
|second|0 - 59|

日のコンポーネントの実際の上限は、月と年のコンポーネントによって異なっています。 詳細については、 または`SetDate``SetDateTime`メンバー関数を参照してください。

各コンストラクターの簡単な説明を次に示します。

- `COleDateTime(`**)** 0 `COleDateTime` (1899 年 12 月 30 日午前 0 時) に初期化されたオブジェクトを構築します。

- `COleDateTime(``dateSrc` **)** 既存`COleDateTime`の`COleDateTime`オブジェクトからオブジェクトを構築します。

- `COleDateTime(`*varSrc* **)** オブジェクト`COleDateTime`を構築します。 構造体または[COleVariant](../../mfc/reference/colevariant-class.md)オブジェクトを`VT_DATE``VARIANT`日付/時刻 ( ) 値に変換しようとします。 この変換が成功すると、変換された値が新しい`COleDateTime`オブジェクトにコピーされます。 値が設定されていない場合、`COleDateTime`オブジェクトの値は 0 (1899 年 12 月 30 日午前 0 時) に設定され、状態は無効になります。

- `COleDateTime(``dtSrc` **)** 値から`COleDateTime`オブジェクトを構築`DATE`します。

- `COleDateTime(``timeSrc` **)** 値から`COleDateTime`オブジェクトを構築`time_t`します。

- `COleDateTime(`*systimeSrc* **)** 値`COleDateTime`からオブジェクトを`SYSTEMTIME`構築します。

- `COleDateTime(``filetimeSrc` **)** 値から`COleDateTime`オブジェクトを構築`FILETIME`します。 . は`FILETIME`世界協定時刻 (UTC) を使用するため、構造体にローカル時刻を渡すと、結果が正しくなれてしまいます。 詳細については、Windows SDK[の「ファイル時間](/windows/win32/SysInfo/file-times)」を参照してください。

- `COleDateTime(``nYear`、、、、、、、、、、、、、、`nMonth``nDay``nHour``nMin`指定`nSec`**)** された数値から`COleDateTime`オブジェクトを構築します。

- `COleDateTime(``wDosDate` `wDosTime` **、)** 指定した`COleDateTime`MS-DOS の日付と時刻の値からオブジェクトを構築します。

データ型の`time_t`詳細については、『*ランタイム ライブラリ リファレンス*』の[time](../../c-runtime-library/reference/time-time32-time64.md)関数を参照してください。

詳細については、Windows SDK の[システム時刻](/windows/win32/api/minwinbase/ns-minwinbase-systemtime)と[ファイルタイム](/windows/win32/api/minwinbase/ns-minwinbase-filetime)の構造体を参照してください。

`COleDateTime`値の境界の詳細については、「[日付と時刻: オートメーションのサポート](../../atl-mfc-shared/date-and-time-automation-support.md)」を参照してください。

> [!NOTE]
> パラメーターを使用`DBTIMESTAMP`するコンストラクターは、OLEDB.h が含まれている場合にのみ使用できます。

### <a name="example"></a>例

[!code-cpp[NVC_ATLMFC_Utilities#2](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_4.cpp)]

## <a name="coledatetimeformat"></a><a name="format"></a>フォーマット

日付/時刻値の書式付き表現を作成します。

```
CString Format(DWORD dwFlags = 0,  LCID lcid = LANG_USER_DEFAULT) const;
CString Format(LPCTSTR lpszFormat) const;
CString Format(UINT nFormatID) const;
```

### <a name="parameters"></a>パラメーター

*dwFlags*<br/>
次のいずれかのロケール フラグを示します。

- LOCALE_NOUSEROVERRIDE カスタム ユーザー設定ではなく、システムの既定のロケール設定を使用します。

- VAR_TIMEVALUEONLY 解析中に日付部分を無視します。

- VAR_DATEVALUEONLY 解析中に時間の部分を無視します。

*Lcid*<br/>
変換に使用するロケール ID を示します。 言語識別子の詳細については、「[言語識別子](/windows/win32/Intl/language-identifiers)」を参照してください。

*フォーマット*<br/>
書式指定文字列に似た`printf`書式指定文字列。 各書式設定コードの前にパーセント記号 ()`%`が付き、対応する`COleDateTime`コンポーネントに置き換えられます。 書式指定文字列内の他の文字は、変更されずに返された文字列にコピーされます。 詳細については、 ランタイム関数[strftime](../../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md)を参照してください。 フォーマットコードの値と意味`Format`は次のとおりです。

- `%H`現在の日の時間

- `%M`現在の時間の分

- `%S`現在の分の秒数

- `%%`パーセント記号

*データを持つ*<br/>
書式制御文字列のリソース ID。

### <a name="return-value"></a>戻り値

書式設定`CString`された日付/時刻値を含む A。

### <a name="remarks"></a>解説

この`COleDateTime`オブジェクトの状態が null の場合、戻り値は空の文字列です。 状態が無効な場合、戻り値の文字列は文字列リソース ATL_IDS_DATETIME_INVALIDによって指定されます。

この関数の 3 つの形式の簡単な説明を次に示します。

`Format`( *dwFlags ,* *lcid*)<br/>
このフォームは、日付と時刻の言語仕様 (ロケール ID) を使用して値を書式設定します。 デフォルトのパラメータを使用して、このフォームは、時刻部分が0(真夜中)でない限り、日付と時刻を印刷します。場合は日付だけを印刷するか、日付部分が0(1899年12月30日)で、その場合は時刻だけを印刷します。 日付/時刻の値が 0 (1899 年 12 月 30 日、午前 0 時) の場合、既定のパラメーターを持つこのフォームは深夜に印刷されます。

`Format`( *lpsz フォーマット*)<br/>
このフォームでは、値の書式を設定するには、前にパーセント記号 (%)が付いた特殊な書式指定コードを含`printf`む書式指定文字列を使用します。 書式指定文字列は、関数にパラメーターとして渡されます。 フォーマットコードの詳細については、『実行時ライブラリリファレンス』の[strftime.wcsftime](../../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md)を参照してください。

`Format`( *n 形式 )*<br/>
このフォームでは、値の書式を設定するには、前にパーセント記号 (%)が付いた特殊な書式指定コードを含`printf`む書式指定文字列を使用します。 書式指定文字列はリソースです。 この文字列リソースの ID は、パラメーターとして渡されます。 フォーマット コードの詳細については、『*実行時ライブラリ リファレンス*』[の strftime.](../../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md)

### <a name="example"></a>例

[!code-cpp[NVC_ATLMFC_Utilities#3](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_5.cpp)]

## <a name="coledatetimegetasdbtimestamp"></a><a name="getasdbtimestamp"></a>を指定します。

`COleDateTime`オブジェクト内の時刻を`DBTIMESTAMP`データ構造体として取得します。

```
bool GetAsDBTIMESTAMP(DBTIMESTAMP& timeStamp) const throw();
```

### <a name="parameters"></a>パラメーター

*タイムスタンプ*<br/>
[構造体](/dotnet/api/system.data.oledb.oledbtype)への参照。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>解説

参照された*timeStamp*構造体に結果の時刻を格納します。 この`DBTIMESTAMP`関数で初期化されるデータ構造体の`fraction`メンバは 0 に設定されます。

### <a name="example"></a>例

[!code-cpp[NVC_ATLMFC_Utilities#4](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_6.cpp)]

## <a name="coledatetimegetassystemtime"></a><a name="getassystemtime"></a>システムタイムを取得します。

`COleDateTime`オブジェクト内の時刻を`SYSTEMTIME`データ構造体として取得します。

```
bool GetAsSystemTime(SYSTEMTIME& sysTime) const throw();
```

### <a name="parameters"></a>パラメーター

*システムタイム*<br/>
オブジェクトから変換された日付/時刻値を受け取る[SYSTEMTIME](/windows/win32/api/minwinbase/ns-minwinbase-systemtime) `COleDateTime`構造体への参照。

### <a name="return-value"></a>戻り値

成功した場合は TRUE を返します。変換が失敗した場合、またはオブジェクトが`COleDateTime`NULL または無効の場合は FALSE。

### <a name="remarks"></a>解説

`GetAsSystemTime`は、参照される*sysTime*オブジェクトに結果の時刻を格納します。 この`SYSTEMTIME`関数で初期化されるデータ構造体の`wMilliseconds`メンバは 0 に設定されます。

`COleDateTime`オブジェクトに保持されている状態情報の詳細については、「 [GetStatus](#getstatus)」を参照してください。

## <a name="coledatetimegetasudate"></a><a name="getasudate"></a>コレデイトタイム::ゲタスデート

`COleDateTime`オブジェクト内の時刻を`UDATE`データ構造体として取得します。

```
bool GetAsUDATE(UDATE& uDate) const throw();
```

### <a name="parameters"></a>パラメーター

*u日付*<br/>
変換された日付/`UDATE`時刻値をオブジェクトから受け取る構造体への`COleDateTime`参照。

### <a name="return-value"></a>戻り値

成功した場合は TRUE を返します。変換が失敗した場合、またはオブジェクトが`COleDateTime`NULL または無効の場合は FALSE。

### <a name="remarks"></a>解説

構造体`UDATE`は「アンパック」日付を表します。

## <a name="coledatetimegetcurrenttime"></a><a name="getcurrenttime"></a>現在の時刻を取得します。

現在の日付/時刻値を返します。

```
static COleDateTime WINAPI GetCurrentTime() throw();
```

### <a name="example"></a>例

[!code-cpp[NVC_ATLMFC_Utilities#5](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_7.cpp)]

## <a name="coledatetimegetday"></a><a name="getday"></a>コレデイトタイム::ゲットデイ

この日付/時刻値で表される月の日を取得します。

```
int GetDay() const throw();
```

### <a name="return-value"></a>戻り値

この`COleDateTime`オブジェクトの値で表される月の日、または`COleDateTime::error`日が取得できなかった場合。

### <a name="remarks"></a>解説

有効な戻り値の範囲は 1 ~ 31 です。

この`COleDateTime`オブジェクトの値を照会するその他のメンバー関数については、次のメンバー関数を参照してください。

- [Getmonth](#getmonth)

- [ゲットイヤー](#getyear)

- [ゲットアワー](#gethour)

- [ゲットミニット](#getminute)

- [ゲットセカンド](#getsecond)

- [今週の週を取得します。](#getdayofweek)

- [ゲットデイオブイヤー](#getdayofyear)

### <a name="example"></a>例

[!code-cpp[NVC_ATLMFC_Utilities#6](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_8.cpp)]

## <a name="coledatetimegetdayofweek"></a><a name="getdayofweek"></a>コレデイトタイム::ゲットデイオブウィーク

この日付/時刻値で表される月の日を取得します。

```
int GetDayOfWeek() const throw();
```

### <a name="return-value"></a>戻り値

この`COleDateTime`オブジェクトの値で表される曜日、または`COleDateTime::error`曜日が取得できなかった場合。

### <a name="remarks"></a>解説

有効な戻り値の範囲は 1 ~ 7 で、1 = 日曜日、2 = 月曜日などです。

この`COleDateTime`オブジェクトの値を照会するその他のメンバー関数については、次のメンバー関数を参照してください。

- [ゲットデイ](#getday)

- [Getmonth](#getmonth)

- [ゲットイヤー](#getyear)

- [ゲットアワー](#gethour)

- [ゲットミニット](#getminute)

- [ゲットセカンド](#getsecond)

- [ゲットデイオブイヤー](#getdayofyear)

### <a name="example"></a>例

[!code-cpp[NVC_ATLMFC_Utilities#7](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_9.cpp)]

## <a name="coledatetimegetdayofyear"></a><a name="getdayofyear"></a>コレデイトタイム::ゲデイオブイヤー

この日付/時刻値で表される年の日を取得します。

```
int GetDayOfYear() const throw();
```

### <a name="return-value"></a>戻り値

この`COleDateTime`オブジェクトの値で表される年の日、または`COleDateTime::error`年の日が得られない場合。

### <a name="remarks"></a>解説

有効な戻り値の範囲は 1 ~ 366 で、1 月 1 日 = 1 です。

この`COleDateTime`オブジェクトの値を照会するその他のメンバー関数については、次のメンバー関数を参照してください。

- [ゲットデイ](#getday)

- [Getmonth](#getmonth)

- [ゲットイヤー](#getyear)

- [ゲットアワー](#gethour)

- [ゲットミニット](#getminute)

- [ゲットセカンド](#getsecond)

- [今週の週を取得します。](#getdayofweek)

### <a name="example"></a>例

[!code-cpp[NVC_ATLMFC_Utilities#8](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_10.cpp)]

## <a name="coledatetimegethour"></a><a name="gethour"></a>コレデイトタイム::ゲットアワー

この日付/時刻値で表される時間を取得します。

```
int GetHour() const throw();
```

### <a name="return-value"></a>戻り値

この`COleDateTime`オブジェクトの値で表される時間、または`COleDateTime::error`時間が取得できなかった場合。

### <a name="remarks"></a>解説

有効な戻り値の範囲は 0 ~ 23 です。

この`COleDateTime`オブジェクトの値を照会するその他のメンバー関数については、次のメンバー関数を参照してください。

- [ゲットデイ](#getday)

- [Getmonth](#getmonth)

- [ゲットイヤー](#getyear)

- [ゲットミニット](#getminute)

- [ゲットセカンド](#getsecond)

- [今週の週を取得します。](#getdayofweek)

- [ゲットデイオブイヤー](#getdayofyear)

### <a name="example"></a>例

[!code-cpp[NVC_ATLMFC_Utilities#9](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_11.cpp)]

## <a name="coledatetimegetminute"></a><a name="getminute"></a>コレデイトタイム::ゲットミニット

この日付/時刻値で表される分を取得します。

```
int GetMinute() const throw();
```

### <a name="return-value"></a>戻り値

この`COleDateTime`オブジェクトの値で表される分、または`COleDateTime::error`分を取得できなかった場合。

### <a name="remarks"></a>解説

有効な戻り値の範囲は 0 ~ 59 です。

この`COleDateTime`オブジェクトの値を照会するその他のメンバー関数については、次のメンバー関数を参照してください。

- [ゲットデイ](#getday)

- [Getmonth](#getmonth)

- [ゲットイヤー](#getyear)

- [ゲットアワー](#gethour)

- [ゲットセカンド](#getsecond)

- [今週の週を取得します。](#getdayofweek)

- [ゲットデイオブイヤー](#getdayofyear)

### <a name="example"></a>例

[GetHour](#gethour)の例を参照してください。

## <a name="coledatetimegetmonth"></a><a name="getmonth"></a>コレデイトタイム::ゲットマン

この日付/時刻値で表される月を取得します。

```
int GetMonth() const throw();
```

### <a name="return-value"></a>戻り値

この`COleDateTime`オブジェクトの値で表される月、または`COleDateTime::error`月が取得できなかった場合。

### <a name="remarks"></a>解説

有効な戻り値の範囲は 1 ~ 12 です。

この`COleDateTime`オブジェクトの値を照会するその他のメンバー関数については、次のメンバー関数を参照してください。

- [ゲットデイ](#getday)

- [ゲットイヤー](#getyear)

- [ゲットアワー](#gethour)

- [ゲットミニット](#getminute)

- [ゲットセカンド](#getsecond)

- [今週の週を取得します。](#getdayofweek)

- [ゲットデイオブイヤー](#getdayofyear)

### <a name="example"></a>例

[GetDay](#getday)の例を参照してください。

## <a name="coledatetimegetsecond"></a><a name="getsecond"></a>コレデイトタイム::ゲットセカンド

この日付/時刻値で表される 2 番目の値を取得します。

```
int GetSecond() const throw();
```

### <a name="return-value"></a>戻り値

この`COleDateTime`オブジェクトの値で表される 2`COleDateTime::error`番目の値、または 2 番目の値が取得できなかった場合。

### <a name="remarks"></a>解説

有効な戻り値の範囲は 0 ~ 59 です。

> [!NOTE]
> クラス`COleDateTime`はうるう秒をサポートしていません。

の`COleDateTime`実装の詳細については、「[日付と時刻: オートメーション サポート](../../atl-mfc-shared/date-and-time-automation-support.md)」を参照してください。

この`COleDateTime`オブジェクトの値を照会するその他のメンバー関数については、次のメンバー関数を参照してください。

- [ゲットデイ](#getday)

- [Getmonth](#getmonth)

- [ゲットイヤー](#getyear)

- [ゲットアワー](#gethour)

- [ゲットミニット](#getminute)

- [今週の週を取得します。](#getdayofweek)

- [ゲットデイオブイヤー](#getdayofyear)

### <a name="example"></a>例

[GetHour](#gethour)の例を参照してください。

## <a name="coledatetimegetstatus"></a><a name="getstatus"></a>を取得します。

指定`COleDateTime`されたオブジェクトの状態 (有効性) を取得します。

```
DateTimeStatus GetStatus() const throw();
```

### <a name="return-value"></a>戻り値

この`COleDateTime`値の状態を返します。 デフォルトで構築`GetStatus`されたオブジェクト`COleDateTime`を呼び出すと、有効なオブジェクトが返されます。 コンストラクターを`GetStatus``COleDateTime`null に設定して初期化されたオブジェクトを呼び`GetStatus`出すと、null が返されます。

### <a name="remarks"></a>解説

戻り値は、クラス内`DateTimeStatus`で定義される列挙型によって定義されます`COleDateTime`。

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

- `COleDateTime::error`日付/時刻値の一部を取得中にエラーが発生したことを示します。

- `COleDateTime::valid`この`COleDateTime`オブジェクトが有効であることを示します。

- `COleDateTime::invalid`この`COleDateTime`オブジェクトが無効であることを示します。つまり、その値が正しくない可能性があります。

- `COleDateTime::null`この`COleDateTime`オブジェクトが null、つまり、このオブジェクトに値が指定されていない場合を示します。 (これは、C++ の NULL とは対照的に、"値を持たない" というデータベースの意味での "null" です。

オブジェクトの`COleDateTime`ステータスは、次の場合無効です。

- 日付/時刻値に変換できなかった`VARIANT`値`COleVariant`またはから値が設定されている場合。

- 値が`time_t`、 、 または`SYSTEMTIME`、`FILETIME`から設定されている場合、有効な日付/時刻値に変換できませんでした。

- 値が無効なパラメーター値`SetDateTime`で設定されている場合。

- このオブジェクトが算術代入操作中にオーバーフローまたはアンダーフローを経験した場合、`+=`すなわち、 または`-=`.

- 無効な値がこのオブジェクトに割り当てられていた場合。

- このオブジェクトの状態が、 を使用して`SetStatus`明示的に無効に設定されている場合。

状態を無効に設定できる操作の詳細については、次のメンバー関数を参照してください。

- [Coledatetime](#coledatetime)

- [日付時間を設定します。](#setdatetime)

- [演算子 +、 -](#operator_add_-)

- [演算子 +=、-=](#operator_add_eq_-_eq)

`COleDateTime`値の境界の詳細については、「[日付と時刻: オートメーションのサポート](../../atl-mfc-shared/date-and-time-automation-support.md)」を参照してください。

### <a name="example"></a>例

[!code-cpp[NVC_ATLMFC_Utilities#10](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_12.cpp)]

## <a name="coledatetimegetyear"></a><a name="getyear"></a>コレデイトタイム::ゲットイヤー

この日付/時刻値で表される年を取得します。

```
int GetYear() const throw();
```

### <a name="return-value"></a>戻り値

この`COleDateTime`オブジェクトの値で表される年、または`COleDateTime::error`年が取得できなかった場合。

### <a name="remarks"></a>解説

有効な戻り値の範囲は 100 ~ 9999 で、これには世紀が含まれます。

この`COleDateTime`オブジェクトの値を照会するその他のメンバー関数については、次のメンバー関数を参照してください。

- [ゲットデイ](#getday)

- [Getmonth](#getmonth)

- [ゲットアワー](#gethour)

- [ゲットミニット](#getminute)

- [ゲットセカンド](#getsecond)

- [今週の週を取得します。](#getdayofweek)

- [ゲットデイオブイヤー](#getdayofyear)

`COleDateTime`値の境界の詳細については、「[日付と時刻: オートメーションのサポート](../../atl-mfc-shared/date-and-time-automation-support.md)」を参照してください。

### <a name="example"></a>例

[GetDay](#getday)の例を参照してください。

## <a name="coledatetimem_dt"></a><a name="m_dt"></a>コレデイトタイム::m_dt

この`COleDateTime`オブジェクト`DATE`の基になる構造体。

```
DATE m_dt;
```

### <a name="remarks"></a>解説

> [!CAUTION]
> この関数によって返される`DATE`ポインターがアクセスするオブジェクトの値を変更すると、この`COleDateTime`オブジェクトの値が変更されます。 この`COleDateTime`オブジェクトのステータスは変更されません。

`DATE`オブジェクトの実装の詳細については、「[日付と時刻: オートメーション サポート](../../atl-mfc-shared/date-and-time-automation-support.md)」を参照してください。

## <a name="coledatetimem_status"></a><a name="m_status"></a>コレデイトタイム::m_status

このオブジェクトの状態を`COleDateTime`格納します。

```
DateTimeStatus m_status;
```

### <a name="remarks"></a>解説

このデータ メンバの型は、クラス内で`DateTimeStatus`定義される列挙型です`COleDateTime`。 詳細については[、「COleDateTime::GetStatus 」を参照してください。](#getstatus)

> [!CAUTION]
> このデータ メンバーは、高度なプログラミングの状況に適しています。 インライン メンバー関数[GetStatus](#getstatus)と[SetStatus](#setstatus)を使用する必要があります。 この`SetStatus`データ メンバーの明示的な設定に関する詳細な注意については、「」を参照してください。

## <a name="coledatetimeoperator-"></a><a name="operator_eq"></a>を指定します。

値を`COleDateTime`コピーします。

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

これらのオーバーロードされた代入演算子は、ソースの日付/時刻値を`COleDateTime`このオブジェクトにコピーします。 オーバーロードされた各代入演算子の簡単な説明を次に示します。

- **演算子 =(** `dateSrc` **)** オペランドの値とステータスは、この`COleDateTime`オブジェクトにコピーされます。

- 演算子 *=(varSrc)* **)** **operator =(**[バリアント型 (](/windows/win32/api/oaidl/ns-oaidl-variant)または[COleVariant)](../../mfc/reference/colevariant-class.md)の日付/時刻 (VT_DATE) への変換が成功した場合、変換された値はこの`COleDateTime`オブジェクトにコピーされ、状態が有効に設定されます。 変換が成功しなかった場合、このオブジェクトの値はゼロ (1899 年 12 月 30 日、午前 0 時) に設定され、その状態は無効になります。

- **演算子 =(** `dtSrc` **)** 値`DATE`がこの`COleDateTime`オブジェクトにコピーされ、その状態が有効に設定されます。

- **演算子 =(** `timeSrc` **)** または の値が変換され、この`COleDateTime`オブジェクトにコピーされます。 `__time64_t` `time_t` 変換が成功すると、このオブジェクトのステータスは有効に設定されます。失敗した場合は無効に設定されます。

- 演算子 *=(systimeSrc)* **)** **operator =(**[SYSTEMTIME](/windows/win32/api/minwinbase/ns-minwinbase-systemtime)値は、この`COleDateTime`オブジェクトに変換されてコピーされます。 変換が成功すると、このオブジェクトのステータスは有効に設定されます。失敗した場合は無効に設定されます。

- **演算子 =(** `uDate` **)** 値`UDATE`が変換され、この`COleDateTime`オブジェクトにコピーされます。 変換が成功すると、このオブジェクトのステータスは有効に設定されます。失敗した場合は無効に設定されます。 構造体`UDATE`は「アンパック」日付を表します。 詳細については、関数[を参照してください](/windows/win32/api/oleauto/nf-oleauto-vardatefromudate)。

- **演算子 =(** `filetimeSrc` **)**[FILETIME](/windows/win32/api/minwinbase/ns-minwinbase-filetime)値は変換され、この`COleDateTime`オブジェクトにコピーされます。 変換が成功すると、このオブジェクトのステータスは有効に設定されます。それ以外の場合は無効に設定されます。 `FILETIME`世界協定時刻 (UTC) を使用するため、構造体に UTC 時刻を渡すと、結果は UTC 時刻から現地時刻に変換され、バリアント時刻として保存されます。 この動作は、Visual C++ 6.0 および Visual C++.NET 2003 SP2 と同じです。 詳細については、Windows SDK[の「ファイル時間](/windows/win32/SysInfo/file-times)」を参照してください。

詳細については、Windows SDK の[バリアント](/windows/win32/api/oaidl/ns-oaidl-variant)エントリを参照してください。

データ型の`time_t`詳細については、『*ランタイム ライブラリ リファレンス*』の[time](../../c-runtime-library/reference/time-time32-time64.md)関数を参照してください。

詳細については、Windows SDK の[システム時刻](/windows/win32/api/minwinbase/ns-minwinbase-systemtime)と[ファイルタイム](/windows/win32/api/minwinbase/ns-minwinbase-filetime)の構造体を参照してください。

`COleDateTime`値の境界の詳細については、「[日付と時刻: オートメーションのサポート](../../atl-mfc-shared/date-and-time-automation-support.md)」を参照してください。

## <a name="coledatetimeoperator---"></a><a name="operator_add_-"></a>次の操作を行います。

値を加算`ColeDateTime`および減算します。

```
COleDateTime operator+(COleDateTimeSpan dateSpan) const throw();
COleDateTime operator-(COleDateTimeSpan dateSpan) const throw();
COleDateTimeSpan operator-(const COleDateTime& date) const throw();
```

### <a name="remarks"></a>解説

`COleDateTime`オブジェクトは絶対時間を表します。 オブジェクトは相対時間[を](../../atl-mfc-shared/reference/coledatetimespan-class.md)表します。 最初の 2 つの演算子を使用すると、`COleDateTimeSpan`値の加算`COleDateTime`と減算を行えます。 3 番目の演算子を使用すると`COleDateTime`、ある値を別の`COleDateTimeSpan`値から減算して値を生成できます。

オペランドのどちらかが null の場合、結果`COleDateTime`の値の状況は NULL になります。

結果`COleDateTime`の値が許容値の範囲外である場合、その`COleDateTime`値のステータスは無効です。

どちらかのオペランドが無効で、もう一方が NULL でない場合、結果の`COleDateTime`値の状況は無効です。

オブジェクトが**-** null に設定されている場合、 および 演算子はアサートします。 **+** `COleDateTime` 例については[、「COleDateTime 関係演算子](#coledatetime_relational_operators)」を参照してください。

有効、無効、および NULL の状態値の詳細については[、m_status](#m_status)メンバー変数を参照してください。

`COleDateTime`値の境界の詳細については、「[日付と時刻: オートメーションのサポート](../../atl-mfc-shared/date-and-time-automation-support.md)」を参照してください。

### <a name="example"></a>例

[!code-cpp[NVC_ATLMFC_Utilities#12](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_13.cpp)]

## <a name="coledatetimeoperator---"></a><a name="operator_add_eq_-_eq"></a>次の値を指定します。

この`COleDateTime`オブジェクトの値`ColeDateTime`を加算および減算します。

```
COleDateTime& operator+=(COleDateTimeSpan dateSpan) throw();
COleDateTime& operator-=(COleDateTimeSpan dateSpan) throw();
```

### <a name="remarks"></a>解説

これらの演算子を使用すると、この値を`COleDateTimeSpan`加算したり、この`COleDateTime`値から値を減算することができます。 オペランドのどちらかが null の場合、結果`COleDateTime`の値の状況は NULL になります。

結果`COleDateTime`の値が許容値の範囲外である場合、この`COleDateTime`値の状態は無効に設定されます。

いずれかのオペランドが無効で、その他のオペランドが NULL でない場合、結果の`COleDateTime`値の状況は無効です。

有効、無効、および NULL の状態値の詳細については[、m_status](#m_status)メンバー変数を参照してください。

オブジェクトが**-=** null に設定されている場合、 および 演算子はアサートします。 **+=** `COleDateTime` 例については[、「COleDateTime 関係演算子](#coledatetime_relational_operators)」を参照してください。

`COleDateTime`値の境界の詳細については、「[日付と時刻: オートメーションのサポート](../../atl-mfc-shared/date-and-time-automation-support.md)」を参照してください。

## <a name="coledatetimeoperator-date"></a><a name="operator_date"></a>日付の日付の演算子

値を`ColeDateTime``DATE`に変換します。

```
operator DATE() const throw();
```

### <a name="remarks"></a>解説

この演算子は、`DATE`この`COleDateTime`オブジェクトから値がコピーされたオブジェクトを返します。 `DATE`オブジェクトの実装の詳細については、「[日付と時刻: オートメーション サポート](../../atl-mfc-shared/date-and-time-automation-support.md)」を参照してください。

`COleDateTime`オブジェクトが`DATE`null に設定されている場合、演算子はアサートします。 例については[、「COleDateTime 関係演算子](#coledatetime_relational_operators)」を参照してください。

## <a name="coledatetimeparsedatetime"></a><a name="parsedatetime"></a>コレデイトタイム::P行日時間を指定します。

文字列を解析して日付/時刻値を読み取ります。

```
bool ParseDateTime(
    LPCTSTR lpszDate,
    DWORD dwFlags = 0,
    LCID lcid = LANG_USER_DEFAULT) throw();
```

### <a name="parameters"></a>パラメーター

*日付*<br/>
解析対象の NULL で終わる文字列へのポインター。 詳細については、「解説」を参照してください。

*dwFlags*<br/>
ロケール設定と解析のフラグを示します。 次のフラグの 1 つ以上。

- LOCALE_NOUSEROVERRIDEカスタム ユーザー設定ではなく、システムの既定のロケール設定を使用します。

- VAR_TIMEVALUEONLY 解析中に日付部分を無視します。

- VAR_DATEVALUEONLY 解析中に時間の部分を無視します。

*Lcid*<br/>
変換に使用するロケール ID を示します。

### <a name="return-value"></a>戻り値

文字列が日付/時刻値に正常に変換された場合は TRUE を返し、それ以外の場合は FALSE を返します。

### <a name="remarks"></a>解説

文字列が日付/時刻値に正常に変換された場合、この`COleDateTime`オブジェクトの値はその値に設定され、状態は有効に設定されます。

> [!NOTE]
> 年の値は、100 から 9999 までの範囲で指定する必要があります。

*lpszDate*パラメーターは、さまざまな形式を取ることができます。 たとえば、次の文字列には、許容できる日付/時刻形式が含まれています。

`"25 January 1996"`

`"8:30:00"`

`"20:30:00"`

`"January 25, 1996 8:30:00"`

`"8:30:00 Jan. 25, 1996"`

`"1/25/1996 8:30:00"  // always specify the full year, even in a 'short date' format`

ロケール ID は、文字列形式が日付/時刻値への変換に使用できるかどうかにも影響します。

VAR_DATEVALUEONLYの場合、時刻の値は時間 0 または深夜に設定されます。 VAR_TIMEVALUEONLYの場合、日付値は日付 0 に設定され、つまり 1899 年 12 月 30 日になります。

文字列を日付/時刻値に変換できなかった場合、または数値オーバーフローがあった場合、この`COleDateTime`オブジェクトのステータスは無効です。

`COleDateTime`値の境界と実装の詳細については、「[日付と時刻: オートメーションのサポート](../../atl-mfc-shared/date-and-time-automation-support.md)」を参照してください。

## <a name="coledatetimesetdate"></a><a name="setdate"></a>セットデイトタイム::セットデイト

この`COleDateTime`オブジェクトの日付を設定します。

```
int SetDate(
    int nYear,
    int nMonth,
    int nDay) throw();
```

### <a name="parameters"></a>パラメーター

*年*, *nMonth*, *nDay*<br/>
この`COleDateTime`オブジェクトにコピーする日付コンポーネントを指定します。

### <a name="return-value"></a>戻り値

この`COleDateTime`オブジェクトの値が正常に設定された場合は 0。それ以外の場合は 1。 この戻り値は、列挙`DateTimeStatus`型に基づいています。 詳細については[、SetStatus](#setstatus)メンバー関数を参照してください。

### <a name="remarks"></a>解説

日付は指定した値に設定されます。 時刻は 0、午前 0 時に設定されます。

パラメーター値の境界については、次の表を参照してください。

|パラメーター|Bounds|
|---------------|------------|
|*n年*|100 - 9999|
|*nMonth*|1 - 12|
|*nDay*|0 - 31|

月の日がオーバーフローした場合は、翌月の正しい日に変換され、それに応じて月や年が増加します。 日の値が 0 の場合は、前月の最終日を示します。 動作は と同じです`SystemTimeToVariantTime`。

パラメーターで指定された日付値が無効な場合、このオブジェクトの状態は に`COleDateTime::invalid`設定されます。 [GetStatus](#getstatus)を使用して値の有効性を`DATE`確認する必要があり[、m_dt](#m_dt)の値が変更されないままであると想定しないでください。

日付値の例を次に示します。

|*n年*|*nMonth*|*nDay*|値|
|-------------|--------------|------------|-----------|
|2000|2|29|2000年2月29日|
|1776|7|4|1776年7月4日|
|1925|4|35|1925年4月35日(無効日)|
|10000|1|1|10000 年 1 月 1 日 (無効な日付)|

日付と時刻の両方を設定するには[、「COleDateTime::セットデイタイム](#setdatetime)」を参照してください。

この`COleDateTime`オブジェクトの値を照会するメンバー関数の詳細については、次のメンバー関数を参照してください。

- [ゲットデイ](#getday)

- [Getmonth](#getmonth)

- [ゲットイヤー](#getyear)

- [ゲットアワー](#gethour)

- [ゲットミニット](#getminute)

- [ゲットセカンド](#getsecond)

- [今週の週を取得します。](#getdayofweek)

- [ゲットデイオブイヤー](#getdayofyear)

`COleDateTime`値の境界の詳細については、「[日付と時刻: オートメーションのサポート](../../atl-mfc-shared/date-and-time-automation-support.md)」を参照してください。

### <a name="example"></a>例

[!code-cpp[NVC_ATLMFC_Utilities#11](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_14.cpp)]

## <a name="coledatetimesetdatetime"></a><a name="setdatetime"></a>を設定します。

この`COleDateTime`オブジェクトの日付と時刻を設定します。

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

*年*, *nMonth*, *nDay*, *nHour*, *nMin*, *nSec*<br/>
この`COleDateTime`オブジェクトにコピーする日付と時刻のコンポーネントを指定します。

### <a name="return-value"></a>戻り値

この`COleDateTime`オブジェクトの値が正常に設定された場合は 0。それ以外の場合は 1。 この戻り値は、列挙`DateTimeStatus`型に基づいています。 詳細については[、SetStatus](#setstatus)メンバー関数を参照してください。

### <a name="remarks"></a>解説

パラメーター値の境界については、次の表を参照してください。

|パラメーター|Bounds|
|---------------|------------|
|*n年*|100 - 9999|
|*nMonth*|1 - 12|
|*nDay*|0 - 31|
|*nアワー*|0 - 23|
|*nMin*|0 - 59|
|*Nsec*|0 - 59|

月の日がオーバーフローした場合は、翌月の正しい日に変換され、それに応じて月や年が増加します。 日の値が 0 の場合は、前月の最終日を示します。 動作は[、同](/windows/win32/api/oleauto/nf-oleauto-systemtimetovarianttime)じです。

パラメーターで指定された日付または時刻の値が無効な場合、このオブジェクトの状態は無効に設定され、このオブジェクトの値は変更されません。

時刻値の例を次に示します。

|*nアワー*|*nMin*|*Nsec*|値|
|-------------|------------|------------|-----------|
|1|3|3|01:03:03|
|23|45|0|23:45:00|
|25|30|0|無効|
|9|60|0|無効|

日付値の例を次に示します。

|*n年*|*nMonth*|*nDay*|値|
|-------------|--------------|------------|-----------|
|1995|4|15|1995年4月15日|
|1789|7|14|1789年7月17日|
|1925|2|30|無効|
|10000|1|1|無効|

日付のみを設定するには[、「COleDateTime::SetDate」](#setdate)を参照してください。 時刻のみを設定するには[、「COleDateTime::SetTime」](#settime)を参照してください。

この`COleDateTime`オブジェクトの値を照会するメンバー関数の詳細については、次のメンバー関数を参照してください。

- [ゲットデイ](#getday)

- [Getmonth](#getmonth)

- [ゲットイヤー](#getyear)

- [ゲットアワー](#gethour)

- [ゲットミニット](#getminute)

- [ゲットセカンド](#getsecond)

- [今週の週を取得します。](#getdayofweek)

- [ゲットデイオブイヤー](#getdayofyear)

`COleDateTime`値の境界の詳細については、「[日付と時刻: オートメーションのサポート](../../atl-mfc-shared/date-and-time-automation-support.md)」を参照してください。

### <a name="example"></a>例

[GetStatus](#getstatus)の例を参照してください。

## <a name="coledatetimesetstatus"></a><a name="setstatus"></a>を設定します。

この`COleDateTime`オブジェクトのステータスを設定します。

```cpp
void SetStatus(DateTimeStatus status) throw();
```

### <a name="parameters"></a>パラメーター

*status*<br/>
この`COleDateTime`オブジェクトの新しいステータス値。

### <a name="remarks"></a>解説

*status*パラメーターの値は、クラス`DateTimeStatus`内で定義される列挙型によって定義されます`COleDateTime`。 詳細については[、「COleDateTime::GetStatus」](#getstatus)を参照してください。

> [!CAUTION]
> この関数は、高度なプログラミングの状況に対応します。 この関数は、このオブジェクトのデータを変更しません。 ほとんどの場合、この状態を**null**または**無効**に設定するために使用されます。 代入演算子 ([演算子 =](#operator_eq)) および[SetDateTime](#setdatetime)は、ソース値に基づいてオブジェクトのステータスを設定します。

### <a name="example"></a>例

[GetStatus](#getstatus)の例を参照してください。

## <a name="coledatetimesettime"></a><a name="settime"></a>コレデイトタイム::セットタイム

この`COleDateTime`オブジェクトの時刻を設定します。

```
int SetTime(
    int nHour,
    int nMin,
    int nSec) throw();
```

### <a name="parameters"></a>パラメーター

*nHour*, *nMin*, *nSec*<br/>
この`COleDateTime`オブジェクトにコピーする時間コンポーネントを指定します。

### <a name="return-value"></a>戻り値

この`COleDateTime`オブジェクトの値が正常に設定された場合は 0。それ以外の場合は 1。 この戻り値は、列挙`DateTimeStatus`型に基づいています。 詳細については[、SetStatus](#setstatus)メンバー関数を参照してください。

### <a name="remarks"></a>解説

時刻は指定した値に設定されます。 日付は、1899 年 12 月 30 日を意味する日付 0 に設定されます。

パラメーター値の境界については、次の表を参照してください。

|パラメーター|Bounds|
|---------------|------------|
|*nアワー*|0 - 23|
|*nMin*|0 - 59|
|*Nsec*|0 - 59|

パラメーターで指定された時刻値が無効な場合、このオブジェクトの状況は無効に設定され、このオブジェクトの値は変更されません。

時刻値の例を次に示します。

|*nアワー*|*nMin*|*Nsec*|値|
|-------------|------------|------------|-----------|
|1|3|3|01:03:03|
|23|45|0|23:45:00|
|25|30|0|無効|
|9|60|0|無効|

日付と時刻の両方を設定するには[、「COleDateTime::セットデイタイム](#setdatetime)」を参照してください。

この`COleDateTime`オブジェクトの値を照会するメンバー関数の詳細については、次のメンバー関数を参照してください。

- [ゲットデイ](#getday)

- [Getmonth](#getmonth)

- [ゲットイヤー](#getyear)

- [ゲットアワー](#gethour)

- [ゲットミニット](#getminute)

- [ゲットセカンド](#getsecond)

- [今週の週を取得します。](#getdayofweek)

- [ゲットデイオブイヤー](#getdayofyear)

`COleDateTime`値の境界の詳細については、「[日付と時刻: オートメーションのサポート](../../atl-mfc-shared/date-and-time-automation-support.md)」を参照してください。

### <a name="example"></a>例

[「SetDate」](#setdate)の例を参照してください。

## <a name="see-also"></a>関連項目

[COleVariant クラス](../../mfc/reference/colevariant-class.md)<br/>
[CTimeクラス](../../atl-mfc-shared/reference/ctime-class.md)<br/>
[クラス](../../atl-mfc-shared/reference/ctimespan-class.md)<br/>
[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[ATL/MFC 共有クラス](../../atl-mfc-shared/atl-mfc-shared-classes.md)

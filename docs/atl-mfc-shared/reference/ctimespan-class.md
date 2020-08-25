---
title: CTimeSpan クラス
ms.date: 10/18/2018
f1_keywords:
- CTimeSpan
- ATLTIME/ATL::CTimeSpan
- ATLTIME/ATL::CTimeSpan::CTimeSpan
- ATLTIME/ATL::CTimeSpan::Format
- ATLTIME/ATL::CTimeSpan::GetDays
- ATLTIME/ATL::CTimeSpan::GetHours
- ATLTIME/ATL::CTimeSpan::GetMinutes
- ATLTIME/ATL::CTimeSpan::GetSeconds
- ATLTIME/ATL::CTimeSpan::GetTimeSpan
- ATLTIME/ATL::CTimeSpan::GetTotalHours
- ATLTIME/ATL::CTimeSpan::GetTotalMinutes
- ATLTIME/ATL::CTimeSpan::GetTotalSeconds
- ATLTIME/ATL::CTimeSpan::Serialize64
helpviewer_keywords:
- elapsed time, CTimeSpan object
- timespan
- time span
- CTimeSpan class
- shared classes, CTimeSpan
- time, elapsed
ms.assetid: ee1e42f6-1839-477a-8435-fb26ad475140
ms.openlocfilehash: 0c13aa0d8f6c46db3b018283ab2a408a3f9531e1
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/25/2020
ms.locfileid: "88832023"
---
# <a name="ctimespan-class"></a>CTimeSpan クラス

期間内の秒数として内部的に格納される時間。

## <a name="syntax"></a>構文

```
class CTimeSpan
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CTimeSpan::CTimeSpan](#ctimespan)|`CTimeSpan`さまざまな方法でオブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CTimeSpan:: Format](#format)|を `CTimeSpan` 書式設定された文字列に変換します。|
|[CTimeSpan::GetDays](#getdays)|このの完全な日数を表す値を返し `CTimeSpan` ます。|
|[CTimeSpan:: GetHours](#gethours)|現在の日 (-23 ~ 23) の時間数を表す値を返します。|
|[CTimeSpan:: GetMinutes](#getminutes)|現在の時間 (-59 ~ 59) の分数を表す値を返します。|
|[CTimeSpan:: GetSeconds](#getseconds)|現在の分 (-59 ~ 59) の秒数を表す値を返します。|
|[CTimeSpan:: GetTimeSpan](#gettimespan)|オブジェクトの値を返し `CTimeSpan` ます。|
|[CTimeSpan:: GetTotalHours](#gettotalhours)|このの合計時間数を表す値を返し `CTimeSpan` ます。|
|[CTimeSpan:: GetTotalMinutes](#gettotalminutes)|このの合計完了時間 (分) を表す値を返し `CTimeSpan` ます。|
|[CTimeSpan:: GetTotalSeconds](#gettotalseconds)|このの合計秒数を表す値を返し `CTimeSpan` ます。|
|[CTimeSpan::Serialize64](#serialize64)|アーカイブとの間でデータをシリアル化します。|

### <a name="operators"></a>演算子

|名前|説明|
|-|-|
|[演算子 +-](#operator_add_-)|オブジェクトを追加および減算し `CTimeSpan` ます。|
|[演算子 + =-=](#operator_add_eq_-_eq)|このとの間でオブジェクトを加算および減算し `CTimeSpan` `CTimeSpan` ます。|
|[operator = = < など。](#ctimespan_comparison_operators)|2つの相対時刻値を比較します。|

## <a name="remarks"></a>解説

`CTimeSpan` に基底クラスがありません。

`CTimeSpan` 関数は、数秒を日、時間、分、および秒のさまざまな組み合わせに変換します。

`CTimeSpan`オブジェクトは、8バイトの **__time64_t**構造体に格納されます。

コンパニオンクラス [CTime](../../atl-mfc-shared/reference/ctime-class.md)は絶対時刻を表します。

`CTime`クラスと `CTimeSpan` クラスは、派生用には設計されていません。 仮想関数がないため、との両方のオブジェクトのサイズ `CTime` `CTimeSpan` は、厳密に8バイトになります。 ほとんどのメンバー関数はインラインです。

の使用方法の詳細については、 `CTimeSpan` 「*ランタイムライブラリリファレンス*」の「[日付と時刻](../../atl-mfc-shared/date-and-time.md)」と「[時間管理](../../c-runtime-library/time-management.md)」を参照してください。

## <a name="requirements"></a>必要条件

**ヘッダー:** atltime. h

## <a name="ctimespan-comparison-operators"></a><a name="ctimespan_comparison_operators"></a> CTimeSpan 比較演算子

比較演算子。

```
bool operator==(CTimeSpan span) const throw();
bool operator!=(CTimeSpan span) const throw();
bool operator<(CTimeSpan span) const throw();
bool operator>(CTimeSpan span) const throw();
bool operator<=(CTimeSpan span) const throw();
bool operator>=(CTimeSpan span) const throw();
```

### <a name="parameters"></a>パラメーター

*スパン*<br/>
比較対象のオブジェクト。

### <a name="return-value"></a>戻り値

これらの演算子は、2つの相対時刻値を比較します。 条件が true の場合は TRUE を返します。それ以外の場合は FALSE。

### <a name="example"></a>例

[!code-cpp[NVC_ATLMFC_Utilities#169](../../atl-mfc-shared/codesnippet/cpp/ctimespan-class_1.cpp)]

## <a name="ctimespanctimespan"></a><a name="ctimespan"></a> CTimeSpan::CTimeSpan

`CTimeSpan`さまざまな方法でオブジェクトを構築します。

```
CTimeSpan() throw();
CTimeSpan(__time64_t time) throw();

CTimeSpan(
    LONG lDays,
    int nHours,
    int nMins,
    int nSecs) throw();
```

### <a name="parameters"></a>パラメーター

*timeSpanSrc*<br/>
`CTimeSpan`既に存在するオブジェクト。

*time*<br/>
時間間隔の秒数を示す **__time64_t** 時間の値。

*Ldays*、 *nhours*、 *nhours*、 *nhours*<br/>
日、時間、分、および秒。

### <a name="remarks"></a>解説

これらのすべてのコンストラクターは `CTimeSpan` 、指定された相対時間で初期化された新しいオブジェクトを作成します。 各コンストラクターについて以下に説明します。

- `CTimeSpan( );` 初期化さ `CTimeSpan` れていないオブジェクトを構築します。

- `CTimeSpan( const CTimeSpan& );` 別の `CTimeSpan` 値からオブジェクトを構築 `CTimeSpan` します。

- `CTimeSpan( __time64_t );``CTimeSpan` **__Time64_t**型からオブジェクトを構築します。

- `CTimeSpan( LONG, int, int, int );``CTimeSpan`各コンポーネントが次の範囲に制限されているコンポーネントからオブジェクトを構築します。

   |コンポーネント|Range|
   |---------------|-----------|
   |*lDays*|0 ~ 25000 (約)|
   |*nHours*|0-23|
   |*nMins*|0-59|
   |*nSecs*|0-59|

1つ以上の期間のコンポーネントが範囲外の場合は、Microsoft Foundation Class ライブラリのデバッグバージョンがアサートすることに注意してください。 を呼び出す前に、引数を検証する必要があります。

### <a name="example"></a>例

[!code-cpp[NVC_ATLMFC_Utilities#162](../../atl-mfc-shared/codesnippet/cpp/ctimespan-class_2.cpp)]

## <a name="ctimespanformat"></a><a name="format"></a> CTimeSpan:: Format

このに対応する書式設定された文字列を生成 `CTimeSpan` します。

```
CString Format(LPCSTR pFormat) const;
CString Format(LPCTSTR pszFormat) const;
CString Format(UINT nID) const;
```

### <a name="parameters"></a>パラメーター

*Pformat*、 *pszFormat*<br/>
書式設定文字列に類似した書式設定文字列 `printf` 。 書式指定コードの前にパーセント () 記号を付けると、 `%` 対応するコンポーネントが置き換えられ `CTimeSpan` ます。 書式設定文字列内のその他の文字は、返された文字列にそのままコピーされます。 の書式設定コードの値と意味を `Format` 以下に示します。

- **% D** 合計日数 `CTimeSpan`

- **% H** 現在の日の時間

- **% M** 現在の時間 (分)

- **% S** 現在の1分間の秒数

- **%%** パーセント記号

*nID*<br/>
この形式を識別する文字列の ID。

### <a name="return-value"></a>戻り値

`CString`書式設定された時刻を格納しているオブジェクト。

### <a name="remarks"></a>解説

デバッグバージョンのライブラリは、書式設定コードを確認し、コードが上のリストにない場合はアサートします。

### <a name="example"></a>例

[!code-cpp[NVC_ATLMFC_Utilities#163](../../atl-mfc-shared/codesnippet/cpp/ctimespan-class_3.cpp)]

## <a name="ctimespangetdays"></a><a name="getdays"></a> CTimeSpan::GetDays

このの完全な日数を表す値を返し `CTimeSpan` ます。

```
LONGLONG GetDays() const throw();
```

### <a name="return-value"></a>戻り値

期間内の完了した24時間の日数を返します。 この値は、期間が負の場合に負の値になることがあります。

### <a name="remarks"></a>解説

夏時間によって、が予想外の結果を返す可能性があることに注意 `GetDays` してください。 たとえば、DST が有効な場合、4月1日から5月 `GetDays` 1 日までの日数が30ではなく29として報告されます。これは、4月の1日が1時間短縮されるため、完了日としてカウントされないためです。

### <a name="example"></a>例

[!code-cpp[NVC_ATLMFC_Utilities#164](../../atl-mfc-shared/codesnippet/cpp/ctimespan-class_4.cpp)]

## <a name="ctimespangethours"></a><a name="gethours"></a> CTimeSpan:: GetHours

現在の日 (-23 ~ 23) の時間数を表す値を返します。

```
LONG GetHours() const throw();
```

### <a name="return-value"></a>戻り値

現在の日付の時間数を返します。 範囲は、-23 ~ 23 です。

### <a name="example"></a>例

[!code-cpp[NVC_ATLMFC_Utilities#165](../../atl-mfc-shared/codesnippet/cpp/ctimespan-class_5.cpp)]

## <a name="ctimespangetminutes"></a><a name="getminutes"></a> CTimeSpan:: GetMinutes

現在の時間 (-59 ~ 59) の分数を表す値を返します。

```
LONG GetMinutes() const throw();
```

### <a name="return-value"></a>戻り値

現在の時間の分数を返します。 範囲は-59 ~ 59 です。

### <a name="example"></a>例

[GetHours](#gethours)の例を参照してください。

## <a name="ctimespangetseconds"></a><a name="getseconds"></a> CTimeSpan:: GetSeconds

現在の分 (-59 ~ 59) の秒数を表す値を返します。

```
LONG GetSeconds() const throw();
```

### <a name="return-value"></a>戻り値

現在の分の秒数を返します。 範囲は-59 ~ 59 です。

### <a name="example"></a>例

[GetHours](#gethours)の例を参照してください。

## <a name="ctimespangettimespan"></a><a name="gettimespan"></a> CTimeSpan:: GetTimeSpan

オブジェクトの値を返し `CTimeSpan` ます。

```
__ time64_t GetTimeSpan() const throw();
```

### <a name="return-value"></a>戻り値

オブジェクトの現在の値を返し `CTimeSpan` ます。

## <a name="ctimespangettotalhours"></a><a name="gettotalhours"></a> CTimeSpan:: GetTotalHours

このの合計時間数を表す値を返し `CTimeSpan` ます。

```
LONGLONG GetTotalHours() const throw();
```

### <a name="return-value"></a>戻り値

このの合計時間数を返し `CTimeSpan` ます。

### <a name="example"></a>例

[!code-cpp[NVC_ATLMFC_Utilities#166](../../atl-mfc-shared/codesnippet/cpp/ctimespan-class_6.cpp)]

## <a name="ctimespangettotalminutes"></a><a name="gettotalminutes"></a> CTimeSpan:: GetTotalMinutes

このの合計完了時間 (分) を表す値を返し `CTimeSpan` ます。

```
LONGLONG GetTotalMinutes() const throw();
```

### <a name="return-value"></a>戻り値

このの合計完了時間 (分) を返し `CTimeSpan` ます。

### <a name="example"></a>例

[Gettotalhours](#gettotalhours)の例を参照してください。

## <a name="ctimespangettotalseconds"></a><a name="gettotalseconds"></a> CTimeSpan:: GetTotalSeconds

このの合計秒数を表す値を返し `CTimeSpan` ます。

```
LONGLONG GetTotalSeconds() const throw();
```

### <a name="return-value"></a>戻り値

このの合計秒数を返し `CTimeSpan` ます。

### <a name="example"></a>例

[Gettotalhours](#gettotalhours)の例を参照してください。

## <a name="ctimespanoperator---"></a><a name="operator_add_-"></a> CTimeSpan:: operator +、-

オブジェクトを追加および減算し `CTimeSpan` ます。

```
CTimeSpan operator+(CTimeSpan span) const throw();
CTimeSpan operator-(CTimeSpan span) const throw();
```

### <a name="parameters"></a>パラメーター

*スパン*<br/>
オブジェクトに追加する値 `CTimeSpan` 。

### <a name="return-value"></a>戻り値

`CTimeSpan`操作の結果を表すオブジェクト。

### <a name="remarks"></a>解説

これらの2つの演算子を使用すると、オブジェクトを相互に追加したり、相互に減算したりでき `CTimeSpan` ます。

### <a name="example"></a>例

[!code-cpp[NVC_ATLMFC_Utilities#167](../../atl-mfc-shared/codesnippet/cpp/ctimespan-class_7.cpp)]

## <a name="ctimespanoperator---"></a><a name="operator_add_eq_-_eq"></a> CTimeSpan:: operator + =、-=

このとの間でオブジェクトを加算および減算し `CTimeSpan` `CTimeSpan` ます。

```
CTimeSpan& operator+=(CTimeSpan span) throw();
CTimeSpan& operator-=(CTimeSpan span) throw();
```

### <a name="parameters"></a>パラメーター

*スパン*<br/>
オブジェクトに追加する値 `CTimeSpan` 。

### <a name="return-value"></a>戻り値

更新された `CTimeSpan` オブジェクト。

### <a name="remarks"></a>解説

これらの演算子を使用すると、 `CTimeSpan` このに対してオブジェクトの追加と削除を行うことができ `CTimeSpan` ます。

### <a name="example"></a>例

[!code-cpp[NVC_ATLMFC_Utilities#168](../../atl-mfc-shared/codesnippet/cpp/ctimespan-class_8.cpp)]

## <a name="ctimespanserialize64"></a><a name="serialize64"></a> CTimeSpan::Serialize64

> [!NOTE]
> このメソッドは、MFC プロジェクトでのみ使用できます。

メンバー変数に関連付けられたデータをアーカイブにシリアル化します。

```
CArchive& Serialize64(CArchive& ar);
```

### <a name="parameters"></a>パラメーター

*金*<br/>
`CArchive`更新するオブジェクト。

### <a name="return-value"></a>戻り値

更新された `CArchive` オブジェクト。

## <a name="see-also"></a>関連項目

[asctime、_wasctime](../../c-runtime-library/reference/asctime-wasctime.md)<br/>
[_ftime、_ftime32、_ftime64](../../c-runtime-library/reference/ftime-ftime32-ftime64.md)<br/>
[gmtime、_gmtime32、_gmtime64](../../c-runtime-library/reference/gmtime-gmtime32-gmtime64.md)<br/>
[localtime、_localtime32、_localtime64](../../c-runtime-library/reference/localtime-localtime32-localtime64.md)<br/>
[strftime、wcsftime、_strftime_l、_wcsftime_l](../../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md)<br/>
[time、_time32、_time64](../../c-runtime-library/reference/time-time32-time64.md)<br/>
[階層図](../../mfc/hierarchy-chart.md)<br/>
[ATL/MFC 共有クラス](../../atl-mfc-shared/atl-mfc-shared-classes.md)

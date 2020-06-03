---
title: クラス
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
ms.openlocfilehash: 14aa5eb52e2c631a92e40ae7053c566284e00e57
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81317502"
---
# <a name="ctimespan-class"></a>クラス

期間内の秒数として内部的に格納される時間。

## <a name="syntax"></a>構文

```
class CTimeSpan
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[次の時間を過多](#ctimespan)|さまざまな方法`CTimeSpan`でオブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[フォーマット](#format)|を`CTimeSpan`書式設定された文字列に変換します。|
|[タイムスパン::ゲットデイズ](#getdays)|この`CTimeSpan`日付の完全な日数を表す値を返します。|
|[時間スパン::ゲットアワー](#gethours)|現在の日 (-23 ~ 23) の時間数を表す値を返します。|
|[時間スパン::ゲットミニッツ](#getminutes)|現在の時間 (-59 ~ 59) の分数を表す値を返します。|
|[タイムスパン::ゲット秒](#getseconds)|現在の分 (-59 ~ 59) の秒数を表す値を返します。|
|[次の時間を過多](#gettimespan)|オブジェクトの値を`CTimeSpan`返します。|
|[時間スパン::ゲットトータルアワー](#gettotalhours)|この`CTimeSpan`時間の合計時間数を表す値を返します。|
|[時間幅::合計分](#gettotalminutes)|この`CTimeSpan`フィールドの完了時間 (分) の合計数を表す値を返します。|
|[タイムスパン::合計秒数を取得します。](#gettotalseconds)|この`CTimeSpan`値の合計秒数を表す値を返します。|
|[を使用します。](#serialize64)|アーカイブとの間でデータをシリアル化します。|

### <a name="operators"></a>オペレーター

|||
|-|-|
|[演算子 + -](#operator_add_-)|オブジェクトを加算および`CTimeSpan`減算します。|
|[演算子 += -=](#operator_add_eq_-_eq)|オブジェクトをこのに加算`CTimeSpan`したり、この`CTimeSpan`オブジェクトから引いたりします。|
|[演算子 == < など](#ctimespan_comparison_operators)|2 つの相対時間値を比較します。|

## <a name="remarks"></a>解説

`CTimeSpan`は基本クラスを持っていません。

`CTimeSpan`関数は、秒を日、時間、分、および秒のさまざまな組み合わせに変換します。

オブジェクト`CTimeSpan`は、__time64_t**構造体**(8 バイト) に格納されます。

コンパニオン クラス[CTime](../../atl-mfc-shared/reference/ctime-class.md)は、絶対時間を表します。

クラス`CTime`と`CTimeSpan`クラスは派生用に設計されていません。 仮想関数がないため、オブジェクトと`CTime``CTimeSpan`オブジェクトのサイズは正確に 8 バイトです。 ほとんどのメンバー関数はインラインです。

`CTimeSpan`の使用方法の詳細については、『 ランタイム ライブラリ リファレンス 』の「[日時](../../atl-mfc-shared/date-and-time.md)」および「[時間管理](../../c-runtime-library/time-management.md)」を*参照してください*。

## <a name="requirements"></a>必要条件

**ヘッダー:** atltime.h

## <a name="ctimespan-comparison-operators"></a><a name="ctimespan_comparison_operators"></a>比較演算子

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
比較するオブジェクト。

### <a name="return-value"></a>戻り値

これらの演算子は、2 つの相対時間値を比較します。 条件が真の場合は TRUE を返します。それ以外の場合は FALSE。

### <a name="example"></a>例

[!code-cpp[NVC_ATLMFC_Utilities#169](../../atl-mfc-shared/codesnippet/cpp/ctimespan-class_1.cpp)]

## <a name="ctimespanctimespan"></a><a name="ctimespan"></a>次の時間を過多

さまざまな方法`CTimeSpan`でオブジェクトを構築します。

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

*タイムスパンスrc*<br/>
既`CTimeSpan`に存在するオブジェクト。

*time*<br/>
**__time64_t**時間の値(期間の秒数)。

*lDays*, *nHours*, *nMins*, *nSecs*<br/>
それぞれ日、時間、分、秒。

### <a name="remarks"></a>解説

これらのコンストラクターは、指定された相対`CTimeSpan`時間で初期化された新しいオブジェクトを作成します。 各コンストラクターについて、以下に説明します。

- `CTimeSpan( );`初期化`CTimeSpan`されていないオブジェクトを構築します。

- `CTimeSpan( const CTimeSpan& );`別`CTimeSpan`の値`CTimeSpan`からオブジェクトを構築します。

- `CTimeSpan( __time64_t );`__time64_t型から`CTimeSpan`オブジェクトを構築 **__time64_t**します。

- `CTimeSpan( LONG, int, int, int );`各コンポーネントが`CTimeSpan`次の範囲に拘束されたコンポーネントからオブジェクトを構築します。

   |コンポーネント|範囲|
   |---------------|-----------|
   |*l日*|0~25,000 (約)|
   |*n時間*|0-23|
   |*nMins*|0-59|
   |*nSecs*|0-59|

1 つ以上の時間のコンポーネントが範囲外である場合、Microsoft Foundation クラス ライブラリのデバッグ バージョンがアサートされることに注意してください。 呼び出しの前に引数を検証するのは、お客様の責任です。

### <a name="example"></a>例

[!code-cpp[NVC_ATLMFC_Utilities#162](../../atl-mfc-shared/codesnippet/cpp/ctimespan-class_2.cpp)]

## <a name="ctimespanformat"></a><a name="format"></a>フォーマット

この`CTimeSpan`に対応する書式付き文字列を生成します。

```
CString Format(LPCSTR pFormat) const;
CString Format(LPCTSTR pszFormat) const;
CString Format(UINT nID) const;
```

### <a name="parameters"></a>パラメーター

*pフォーマット*, *pszフォーマット*<br/>
書式指定文字列に似た`printf`書式指定文字列。 フォーマット コードの前にパーセント記号`%`() が付いた書式コード`CTimeSpan`は、対応するコンポーネントに置き換えられます。 書式指定文字列内の他の文字は、変更されずに返された文字列にコピーされます。 フォーマットコードの値と意味`Format`を以下に示します。

- **%D**この合計日数`CTimeSpan`

- **%H**現在の日の時間

- **%M**現在の時間の分

- **%S**現在の分の秒数

- **%%** パーセント記号

*nID*<br/>
この形式を識別する文字列の ID。

### <a name="return-value"></a>戻り値

書式設定`CString`された時刻を格納するオブジェクト。

### <a name="remarks"></a>解説

ライブラリのデバッグ バージョンは、書式設定コードをチェックし、コードが上記の一覧にない場合はアサートします。

### <a name="example"></a>例

[!code-cpp[NVC_ATLMFC_Utilities#163](../../atl-mfc-shared/codesnippet/cpp/ctimespan-class_3.cpp)]

## <a name="ctimespangetdays"></a><a name="getdays"></a>タイムスパン::ゲットデイズ

この`CTimeSpan`日付の完全な日数を表す値を返します。

```
LONGLONG GetDays() const throw();
```

### <a name="return-value"></a>戻り値

期間内の完全な 24 時間の日数を返します。 期間が負の場合、この値は負の値になることがあります。

### <a name="remarks"></a>解説

夏時間は、潜在的に驚`GetDays`くべき結果を返す可能性があることに注意してください。 たとえば、DST が有効な場合、4`GetDays`月 1 日から 5 月 1 日までの日数は 30 ではなく 29 として報告されます。

### <a name="example"></a>例

[!code-cpp[NVC_ATLMFC_Utilities#164](../../atl-mfc-shared/codesnippet/cpp/ctimespan-class_4.cpp)]

## <a name="ctimespangethours"></a><a name="gethours"></a>時間スパン::ゲットアワー

現在の日 (-23 ~ 23) の時間数を表す値を返します。

```
LONG GetHours() const throw();
```

### <a name="return-value"></a>戻り値

現在の日の時間数を返します。 範囲は -23 から 23 です。

### <a name="example"></a>例

[!code-cpp[NVC_ATLMFC_Utilities#165](../../atl-mfc-shared/codesnippet/cpp/ctimespan-class_5.cpp)]

## <a name="ctimespangetminutes"></a><a name="getminutes"></a>時間スパン::ゲットミニッツ

現在の時間 (-59 ~ 59) の分数を表す値を返します。

```
LONG GetMinutes() const throw();
```

### <a name="return-value"></a>戻り値

現在の時間の分数を返します。 範囲は -59 から 59 です。

### <a name="example"></a>例

[GetHours](#gethours)の例を参照してください。

## <a name="ctimespangetseconds"></a><a name="getseconds"></a>タイムスパン::ゲット秒

現在の分 (-59 ~ 59) の秒数を表す値を返します。

```
LONG GetSeconds() const throw();
```

### <a name="return-value"></a>戻り値

現在の分の秒数を返します。 範囲は -59 から 59 です。

### <a name="example"></a>例

[GetHours](#gethours)の例を参照してください。

## <a name="ctimespangettimespan"></a><a name="gettimespan"></a>次の時間を過多

オブジェクトの値を`CTimeSpan`返します。

```
__ time64_t GetTimeSpan() const throw();
```

### <a name="return-value"></a>戻り値

オブジェクトの現在の値を`CTimeSpan`返します。

## <a name="ctimespangettotalhours"></a><a name="gettotalhours"></a>時間スパン::ゲットトータルアワー

この`CTimeSpan`時間の合計時間数を表す値を返します。

```
LONGLONG GetTotalHours() const throw();
```

### <a name="return-value"></a>戻り値

この`CTimeSpan`時間の合計時間数を返します。

### <a name="example"></a>例

[!code-cpp[NVC_ATLMFC_Utilities#166](../../atl-mfc-shared/codesnippet/cpp/ctimespan-class_6.cpp)]

## <a name="ctimespangettotalminutes"></a><a name="gettotalminutes"></a>時間幅::合計分

この`CTimeSpan`フィールドの完了時間 (分) の合計数を表す値を返します。

```
LONGLONG GetTotalMinutes() const throw();
```

### <a name="return-value"></a>戻り値

この`CTimeSpan`内の完了分の合計数を返します。

### <a name="example"></a>例

[「合計時間の取得](#gettotalhours)」の例を参照してください。

## <a name="ctimespangettotalseconds"></a><a name="gettotalseconds"></a>タイムスパン::合計秒数を取得します。

この`CTimeSpan`値の合計秒数を表す値を返します。

```
LONGLONG GetTotalSeconds() const throw();
```

### <a name="return-value"></a>戻り値

この`CTimeSpan`での完了秒数の合計を返します。

### <a name="example"></a>例

[「合計時間の取得](#gettotalhours)」の例を参照してください。

## <a name="ctimespanoperator---"></a><a name="operator_add_-"></a>次の値を指定します。

オブジェクトを加算および`CTimeSpan`減算します。

```
CTimeSpan operator+(CTimeSpan span) const throw();
CTimeSpan operator-(CTimeSpan span) const throw();
```

### <a name="parameters"></a>パラメーター

*スパン*<br/>
オブジェクトに追加する`CTimeSpan`値。

### <a name="return-value"></a>戻り値

操作`CTimeSpan`の結果を表すオブジェクト。

### <a name="remarks"></a>解説

これら 2 つの演算子を使用すると`CTimeSpan`、互いにオブジェクトを追加したり、相互にオブジェクトを減算したりできます。

### <a name="example"></a>例

[!code-cpp[NVC_ATLMFC_Utilities#167](../../atl-mfc-shared/codesnippet/cpp/ctimespan-class_7.cpp)]

## <a name="ctimespanoperator---"></a><a name="operator_add_eq_-_eq"></a>次の値を指定します。

オブジェクトをこのに加算`CTimeSpan`したり、この`CTimeSpan`オブジェクトから引いたりします。

```
CTimeSpan& operator+=(CTimeSpan span) throw();
CTimeSpan& operator-=(CTimeSpan span) throw();
```

### <a name="parameters"></a>パラメーター

*スパン*<br/>
オブジェクトに追加する`CTimeSpan`値。

### <a name="return-value"></a>戻り値

更新された`CTimeSpan`オブジェクト。

### <a name="remarks"></a>解説

これらの演算子を使用すると、この オブジェクト`CTimeSpan`をこの に追加`CTimeSpan`したり、この オブジェクトからオブジェクトを減算したりできます。

### <a name="example"></a>例

[!code-cpp[NVC_ATLMFC_Utilities#168](../../atl-mfc-shared/codesnippet/cpp/ctimespan-class_8.cpp)]

## <a name="ctimespanserialize64"></a><a name="serialize64"></a>を使用します。

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

[asctime、_wasctime](../../c-runtime-library/reference/asctime-wasctime.md)<br/>
[_ftime、_ftime32、_ftime64](../../c-runtime-library/reference/ftime-ftime32-ftime64.md)<br/>
[gmtime、_gmtime32、_gmtime64](../../c-runtime-library/reference/gmtime-gmtime32-gmtime64.md)<br/>
[localtime、_localtime32、_localtime64](../../c-runtime-library/reference/localtime-localtime32-localtime64.md)<br/>
[strftime、wcsftime、_strftime_l、_wcsftime_l](../../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md)<br/>
[time、_time32、_time64](../../c-runtime-library/reference/time-time32-time64.md)<br/>
[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[ATL/MFC 共有クラス](../../atl-mfc-shared/atl-mfc-shared-classes.md)
